# NixOS: The Declarative and Reproducible Linux Distribution

NixOS is a unique Linux distribution built around the Nix package manager, offering a declarative and reproducible approach to system configuration. Unlike traditional distributions, NixOS ensures system stability and rollback capabilities by treating configuration as code.

## Why NixOS?

NixOS stands out for several reasons:

- **Declarative Configuration**: System configurations are managed via a single `configuration.nix` file.
- **Atomic Upgrades & Rollbacks**: Upgrades are transactional, and you can easily revert to previous system states.
- **Isolation & Reproducibility**: Packages and configurations are isolated, avoiding dependency conflicts.
- **Immutable System Configuration**: Ensures a stable and predictable environment.
- **Powerful Package Manager**: Nix enables user-level package management without root permissions.

## Installing NixOS

### Downloading the ISO
You can download the latest NixOS ISO from the [official website](https://nixos.org/download.html).

### Installation Steps

1. Boot into the NixOS live environment.
2. Set up disk partitions (e.g., using `fdisk` or `parted`).
3. Format and mount the partitions.
4. Generate the initial configuration.
5. Install the system.

Example commands:

```sh
# Create and format partitions
parted /dev/sdX -- mklabel gpt
parted /dev/sdX -- mkpart primary 1MiB 100%
mkfs.ext4 /dev/sdX1

# Mount the root partition
mount /dev/sdX1 /mnt

# Generate configuration
nixos-generate-config --root /mnt

# Edit configuration if needed
nano /mnt/etc/nixos/configuration.nix

# Install NixOS
nixos-install
reboot
```

## Configuring NixOS

### Editing `configuration.nix`
The main system configuration is defined in `/etc/nixos/configuration.nix`. Example minimal configuration:

```nix
{ config, pkgs, ... }:
{
  imports = [];

  # Set system hostname
  networking.hostName = "nixos";

  # Enable networking
  networking.networkmanager.enable = true;

  # Set locale and time zone
  time.timeZone = "UTC";
  i18n.defaultLocale = "en_US.UTF-8";

  # Define users
  users.users.yourname = {
    isNormalUser = true;
    extraGroups = [ "wheel" ];
    shell = pkgs.bash;
  };

  # Enable sudo
  security.sudo.enable = true;

  # Enable OpenSSH
  services.openssh.enable = true;

  # Enable Nix Flakes
  nix.settings.experimental-features = [ "nix-command" "flakes" ];

  # Install packages
  environment.systemPackages = with pkgs; [
    neovim git curl wget
  ];

  # Enable graphical environment (optional)
  services.xserver.enable = true;
  services.xserver.displayManager.gdm.enable = true;
  services.xserver.desktopManager.gnome.enable = true;

  # Apply configuration
  system.stateVersion = "23.11";
}
```

### Applying Changes
After modifying `configuration.nix`, apply the changes with:

```sh
sudo nixos-rebuild switch
```

## Package Management with Nix

### Installing Packages

```sh
nix-env -iA nixpkgs.firefox
```

### Removing Packages

```sh
nix-env -e firefox
```

### Searching for Packages

```sh
nix-env -qaP | grep package-name
```

## Nix Flakes: The Future of Nix

Flakes simplify dependency management and improve reproducibility.

### Enabling Flakes

Add the following to `configuration.nix`:

```nix
nix.settings.experimental-features = [ "nix-command" "flakes" ];
```

### Creating a Flake

```sh
mkdir my-flake && cd my-flake
nix flake init -t nixpkgs#hello
nix run .
```

## Conclusion

NixOS is an excellent choice for users who value reproducibility, flexibility, and stability. Whether you are a developer, a system administrator, or a power user, its declarative approach ensures a consistent and efficient workflow.

