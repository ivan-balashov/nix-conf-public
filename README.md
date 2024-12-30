# nix-conf-public

Template for nix configuration for darwin and linux together

## How to use

-   Fork it to your private(!!!) repository.

-   Install nix

    ``` bash
    #Linux
    sh <(curl -L https://nixos.org/nix/install) --daemon

    #macOS
    sh <(curl -L https://nixos.org/nix/install)
    ```

-   Add experimental features to work with flakes

    ``` bash
    mkdir -p ~/.config/nix
    echo "experimental-features = nix-command flakes" >> ~/.config/nix/nix.conf
    ```

-   Clone your repository to your machine

    ``` bash
    git clone https://github.com/your-username/your-config.git ~/.config/home-manager
    cd ~/.config/home-manager
    ```

-   First time apply config

    ``` bash
    #Linux
    nix run home-manager/master -- switch --flake .#linux-username

    #macOS
    nix run home-manager/master -- switch --flake .#darwin-username
    ```

-   Any other time after updating config

    ``` bash
    home-manager switch --flake .#your-hostname
    ```