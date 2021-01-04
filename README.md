# Pi Setup

This is how I set up a Raspberry Pi.

### 1. Load the operating system on the SD card

I'm using the Raspberry Pi Imager on a Mac and load Raspberry Pi OS (32-Bit)

### 2. Manually make the initial configuration

Connect the Pi to a monitor, plug keyboard and mouse and power it on. Configure the basic settings:

- country
- language
- timezone
- password
- wifi network

Restart the Pi and update the Pi configuration via `sudo raspi-config` or Preferences > Raspberry Pi Configuration:

- Set hostname
- Boot to CLI
- Enable SSH interface

Restart again

### 3. Network and SSH configuration

You might want to make a DHCP reservation.

Try to SSH onto the Pi. If it doesn't accept the password then set it directly via the console:

        sudo passwd pi

Create SSH keys

        ssh-keygen -t rsa

Copy your public key to `.ssh/authorized_keys`.

### 4. Login and update packages

        ssh pi
        sudo apt update
        sudp apt upgrade

You might want to reboot

### 5. Run ansible playbook

Assuming you have ansible installed on your development box:

        ansible-playbook playbook.yml
