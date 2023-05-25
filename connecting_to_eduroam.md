
# Connect Raspberry Pi to Eduroam

This guide explains how to connect a Raspberry Pi to the Eduroam network. 

## Steps

1. **Open the terminal on the Raspberry Pi or connect to it using SSH.**

2. **Edit the `wpa_supplicant.conf` file which stores network configuration information.**
    ```bash
    sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
    ```

3. **Add the following configuration to the end of the file:**
    ```bash
    network={
        ssid="eduroam"
        proto=RSN
        key_mgmt=WPA-EAP
        pairwise=CCMP
        auth_alg=OPEN
        eap=PEAP
        identity="your-username@your-university-domain"
        password="your-password"
        phase1="peaplabel=0"
        phase2="auth=MSCHAPV2"
    }
    ```
    Replace `your-username@your-university-domain` with your Eduroam username and `your-password` with your Eduroam password.

4. **Save and close the file.** Press `Ctrl+X`, then `Y` to confirm, and finally `Enter` to exit.

5. **Reconfigure `wpa_supplicant` with the new configuration file.**
    ```bash
    sudo wpa_cli -i wlan0 reconfigure
    ```

6. **Check your connection.**
    ```bash
    ifconfig wlan0
    ```
    If you're connected to the network, you should see an `inet addr` field with an IP address. This would mean that your Raspberry Pi is successfully connected to the Eduroam network.

## Notes

Different institutions might have different configurations for Eduroam. If these instructions do not work, contact your institution's IT department for specific advice.
```

