**Setting Up The Environment for Execution**

### Step 1: Download Debian 12 ISO

Visit the official Debian website and download the Debian 12 ISO image. You can find it at [Debian Downloads](https://cdimage.debian.org/debian-cd/current/amd64/iso-dvd/).

### Step 2: Install VMware

If you don't have VMware installed, download and install VMware Workstation Player or VMware Workstation Pro from the [official VMware website](https://www.vmware.com/).

### Step 3: Create a New Virtual Machine

1. Open VMware and click on "Create a New Virtual Machine."

2. Choose "Installer disc image file (iso)" and browse to the location where you saved the Debian 12 ISO.

3. Complete the virtual machine creation wizard by specifying the guest operating system as "Linux" and version as "Debian 11.x or later."

### Step 4: Customize Virtual Machine Settings

1. Before starting the VM, you might want to customize its settings. Click on "Edit virtual machine settings."

2. Adjust parameters such as memory, CPU, and disk space according to your preferences and system resources.

### Step 5: Start the Virtual Machine

1. Start the virtual machine. It will boot from the Debian 12 ISO.

2. Follow the on-screen instructions to complete the Debian installation. This includes selecting language, region, keyboard layout, setting up users, and configuring the disk.

### Step 6: Complete the Installation

1. After Debian is installed, the system will prompt you to remove the installation media (ISO). Ensure you eject the ISO or unmount it from the virtual CD/DVD drive.

2. Finish the installation by following any remaining on-screen prompts.

### Step 7: Install VMware Tools

1. After the Debian VM is running, install VMware Tools for better integration between the guest and host systems.

   ```bash
   sudo apt update
   sudo apt install open-vm-tools
   ```

2. Follow the prompts to complete the installation.

### Step 8: Update and Upgrade

For security and stability, update and upgrade the Debian system:

```bash
sudo apt update
sudo apt upgrade
```

### Step 9: clone repository 
Clone a Git repository on your Debian 12 machine, you can follow these steps:

- Open a terminal on your Debian 12 machine.
  
```bash
sudo apt update
sudo apt install git
```

- Navigate to your home directory (you can use the `cd` command):

   ```bash
   cd ~
   ```

-  Clone the repository using the `git clone` command:

   ```bash
   git clone https://github.com/chiragmetaliya/FileShareEase.git
   ```

-  Enter the cloned repository directory:

   ```bash
   cd FileShareEase
   ```

Now you have successfully cloned the repository to your Debian 12 machine.


### Step 10: Run server.c, mirror.c
Certainly! I'll explain the steps you should take and the expected behavior for each command as part of the README page:

### Cloning the Repository:

1. **Clone the Repository:**
    - On the Debian 12 machine, navigate to the home directory using the terminal: `cd ~`
    - Clone the repository using the following command:
      ```bash
      git clone https://github.com/chiragmetaliya/FileShareEase.git
      ```
    - Enter the cloned repository directory: `cd FileShareEase`

### Running Server and Client:

1. **Compile and Run the Server (`server.c``mirror.c`):**
    - Compile and run your server application (`server.c``mirror.c`) that will handle file transfer operations.

2. **Compile and Run the Client (`client.c`):**
    - Open different terminals or machines.
    - In each terminal, compile and run the client application (`client.c`).

### Client Commands:

1. **`getfn filename`:**
    - If the file with the specified name exists in the directory tree rooted at ~, the server will return information such as filename, size (in bytes), date created, and file permissions.
    - The client will print the received information on its terminal.
    - If the file is not found, the client will print "File not found."

    Example:
    ```bash
    Client$ getfn sample.txt
    ```

2. **`getfz size1 size2`:**
    - The server will return a compressed file (`temp.tar.gz`) containing all files in the directory tree rooted at ~ with sizes between `size1` and `size2` (inclusive).
    - If no files match the specified size range, the server sends "No file found" to the client.

    Example:
    ```bash
    Client$ getfz 1240 12450
    ```

3. **`getft <extension list>`:**
    - The server will return a compressed file (`temp.tar.gz`) containing all files in the directory tree rooted at ~ with specified file types.
    - If no files match the specified file types, the server sends "No file found" to the client.

    Example:
    ```bash
    Client$ getft c txt
    Client$ getft jpg bmp pdf
    ```

4. **`getfdb date`:**
    - The server will return a compressed file (`temp.tar.gz`) containing all files in the directory tree rooted at ~ created on or before the specified date.

    Example:
    ```bash
    Client$ getfdb 2023-01-01
    ```

5. **`getfda date`:**
    - The server will return a compressed file (`temp.tar.gz`) containing all files in the directory tree rooted at ~ created on or after the specified date.

    Example:
    ```bash
    Client$ getfda 2023-03-31
    ```


