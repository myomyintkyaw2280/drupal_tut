# DDEV Setup for Drupal

## Install DDEV
Follow these instructions to set up DDEV for working with Drupal, referencing the official DDEV documentation.

### Check Requirements
Ensure your system meets the [DDEV system requirements](https://ddev.readthedocs.io/en/stable/users/install/ddev-installation/).

### Install Docker
1. Go to the [Docker installation guide](https://docs.docker.com/get-docker/).
2. Select your environment and follow the instructions.
3. If installing DDEV on Docker Engine on WSL2 on Windows, the DDEV installation script will handle Docker installation.

### Install DDEV
1. Go to the [DDEV installation guide](https://ddev.readthedocs.io/en/stable/users/install/ddev-installation/).
2. Select your environment and follow the instructions.

## Install Drupal
Drupal can be installed using Composer or by cloning the Drupal core repository. Cloning is useful for contributing to Drupal core.

### Option 1: Using Composer
1. Go to the [Drupal CMS Quickstart guide](https://ddev.readthedocs.io/en/stable/users/quickstart/#drupal) and follow the instructions.
2. Once installed, the latest official release of Drupal will open in your default browser.
3. Drush, the command line shell for working with Drupal, is also installed.

### Option 2: Using Git Clone
#### Clone Drupal Core Repository
```sh
git clone https://git.drupalcode.org/project/drupal.git
cd drupal
```

#### Create the DDEV Project
```sh
ddev config --project-type drupal
```

#### Start the Project
```sh
ddev start
```

#### Install External Dependencies
```sh
ddev composer install
```

#### Install Drush (Command Line Tool for Drupal)
```sh
ddev composer require drush/drush
```

#### Install Drupal Using Drush
```sh
ddev drush site:install -y
```

#### Launch Drupal Site
```sh
ddev launch
```

#### Automatically Log Into Admin Account
```sh
ddev launch $(ddev drush uli)
```

### Congratulations!
You now have the latest development snapshot of Drupal (e.g., 11.x-dev) installed and open in your default browser. You can now test Drupal patches and merge requests.
