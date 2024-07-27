# Network Configuration Commands

This guide provides a brief description of common network configuration commands used to manage a wireless network interface (`wlan0`).

## Commands

1. `ifconfig wlan0 down`
   - **Description**: Brings down the `wlan0` network interface. This command disables the wireless network interface, effectively turning off the wireless connection.

2. `sudo ifconfig wlan0 down`
   - **Description**: Similar to the previous command but executed with `sudo` to ensure administrative privileges. This is necessary because modifying network interfaces typically requires superuser permissions.

3. `sudo iwconfig wlan0 mode managed`
   - **Description**: Sets the `wlan0` interface to managed mode. In this mode, the wireless device connects to a network managed by an access point. This is the standard mode for connecting to Wi-Fi networks.

4. `sudo ifconfig wlan0 up`
   - **Description**: Brings up the `wlan0` network interface. This command re-enables the wireless network interface, making it ready to connect to a wireless network.

5. `service NetworkManager restart`
   - **Description**: Restarts the NetworkManager service. This command is useful for applying changes and ensuring that the network configuration is properly reset and recognized by the system.

## Usage

These commands are typically used in sequence to reset the wireless network interface and ensure it is properly configured. Below is an example of how they might be used together:

```bash
ifconfig wlan0 down
sudo ifconfig wlan0 down
sudo iwconfig wlan0 mode managed
sudo ifconfig wlan0 up
service NetworkManager restart
```
