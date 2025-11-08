# How to Install Ubuntu (Linux OS) on Windows using WSL

This guide will walk you through the process of installing the Windows Subsystem for Linux (WSL) and the Ubuntu distribution on your Windows machine.

## Prerequisites

Before you begin, you will need to have the following:

*   **Windows 10 or 11:** You need to be running Windows 10 version 2004 or higher (Build 19041 and higher) or Windows 11.
*   **CPU Virtualization:** You must have CPU virtualization enabled on your computer. This is usually enabled by default, but if you encounter any issues, you may need to enable it in your computer's BIOS settings.

## Installation Steps

### Step 1: Enable WSL and Virtual Machine Platform

1.  Open **PowerShell** as **Administrator**. You can do this by searching for "PowerShell" in the Start menu, right-clicking on it, and selecting "Run as administrator".
2.  Run the following commands one by one to enable WSL and the Virtual Machine Platform:

    ```powershell
    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
    ```

    ```powershell
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    ```

3.  **Restart your computer** to complete the installation of these features.

### Step 2: Install Ubuntu

1.  After restarting, open **PowerShell** as **Administrator** again.
2.  Run the following command to install WSL and Ubuntu:

    ```powershell
    wsl --install
    ```

### Step 3: Set Up Your Ubuntu Distribution

1.  Once the installation is complete, you can launch Ubuntu by searching for "Ubuntu" in the Start menu.
2.  The first time you launch Ubuntu, it will take a moment to set up. After that, you will be prompted to create a new username and password. This is a local user account for your Ubuntu environment, and it does not need to be the same as your Windows password.

### Step 4: Update and Install Packages

1.  Once your Ubuntu environment is set up, it's a good practice to update its packages. In the Ubuntu terminal, run the following command:

    ```bash
    sudo apt update && sudo apt upgrade -y
    ```

2.  You will need to enter the password you created in the previous step.
3.  It is also recommended to install some essential packages for development. You can do this by running the following command:

    ```bash
    sudo apt install -y curl build-essential git wget
    ```

## How to Launch Ubuntu

You can launch your Ubuntu distribution at any time by one of the following methods:

*   **From the Start Menu:** Open your Start menu, type "Ubuntu", and click on the Ubuntu application.
*   **From PowerShell or Command Prompt:** Open a new PowerShell or Command Prompt window and type `wsl` or `ubuntu`.

Congratulations! You now have a full Ubuntu terminal environment running directly on your Windows machine.
