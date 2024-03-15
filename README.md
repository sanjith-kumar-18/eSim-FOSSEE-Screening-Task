# eSim Installation Guide

This repository provides step-by-step instructions for installing eSim (an open-source Electronic Design Automation tool) on Ubuntu-based systems using apt package manager and additional tools like Oracle VirtualBox.

**Virtual box installtion**
Refer to [Oracle VirtualBox installation guide](https://www.virtualbox.org/wiki/Linux_Downloads) for installation instructions suitable for your system.

## Prerequisites

Before proceeding with the installation, ensure that the following tools and packages are available on your system:

- `wget`
- `unzip`
- `sudo`
- `python3-venv`
- `software-properties-common`
- `kicad`
- `verilator`
- `Oracle VirtualBox`

## Installation Steps

1. Update package lists:

    ```bash
    sudo apt-get -y update
    ```

2. Install required packages:

    ```bash
    sudo apt-get -y install wget sudo unzip python3-venv
    ```

3. Download eSim package:

    ```bash
    wget https://static.fossee.in/esim/installation-files/eSim-2.4.zip
    ```

4. Unzip the downloaded package:

    ```bash
    unzip eSim-2.4.zip
    ```

5. Navigate to eSim directory:

    ```bash
    cd eSim-2.4
    ```

6. Make the installation script executable:

    ```bash
    chmod +x install-eSim.sh
    ```

7. Run the eSim installation script:

    ```bash
    ./install-eSim.sh --install
    ```

8. After adding the repository, create a Python virtual environment:

    ```bash
    sudo python3 -m venv .
    source bin/activate
    ```

9. Install `software-properties-common`:

    ```bash
    sudo apt-get -y install software-properties-common
    ```

10. Add additional repositories:

    Edit the `/etc/apt/sources.list` file and add the following line:

    ```
    deb http://cz.archive.ubuntu.com/ubuntu focal main universe
    ```

    ```bash
    echo "deb http://cz.archive.ubuntu.com/ubuntu focal main universe" | sudo tee -a /etc/apt/sources.list
    ```

11. Install `kicad`:

    ```bash
    sudo apt-get -y install --install-recommends kicad
    ```

12. Update package lists again:

    ```bash
    sudo apt-get -y update
    ```

13. Install `ghdl-llvm`:

    ```bash
    sudo apt-get install ghdl-llvm
    ```

14. Install `verilator`:

    ```bash
    wget http://kr.archive.ubuntu.com/ubuntu/pool/universe/v/verilator/verilator_4.028-1_amd64.deb
    sudo apt-get install ./verilator_4.028-1_amd64.deb
    ```

## Tools Used

- [eSim](https://esim.fossee.in/): Open-source Electronic Design Automation tool.
- [Oracle VirtualBox](https://www.virtualbox.org/): Virtualization software for running virtual machines on your system.

## Usage

Once installed, you can start using eSim by following its documentation and tutorials available on the [eSim website](https://esim.fossee.in/).

## Contributing

If you encounter any issues with the installation process or have suggestions for improvements, feel free to open an issue or submit a pull request to this repository.

## License

This installation guide is provided under the [MIT License](LICENSE).
