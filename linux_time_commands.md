Here are the **`timedatectl`** and **`systemctl`** commands used in the problems above, with examples and their explanations:

### **`timedatectl` Commands**

`timedatectl` is used to control and display time, date, and timezone settings in a Linux system.

1. **Set the system timezone**:
   This command sets the system's timezone.
   ```bash
   timedatectl set-timezone Asia/Kolkata
   ```

   - **Explanation**: This sets the system timezone to **Asia/Kolkata** (Indian Standard Time - IST).

2. **View current time settings**:
   This command shows the current time settings, including the local time, UTC time, system clock synchronization, and timezone information.
   ```bash
   timedatectl
   ```

   - **Example output**:
   ```
   Local time: Mon 2024-11-25 22:57:29 IST
   Universal time: Mon 2024-11-25 17:27:29 UTC
   Time zone: Asia/Kolkata (IST, +0530)
   System clock synchronized: no
   NTP service: active
   RTC in local TZ: no
   ```

3. **Set the system date and time**:
   You can manually set the date and time using `timedatectl`.
   ```bash
   timedatectl set-time '2024-11-25 15:00:00'
   ```

   - **Explanation**: This sets the system date and time to **November 25, 2024, 3:00 PM**.

4. **Enable or disable NTP (Network Time Protocol)**:
   This command enables or disables automatic synchronization of the system clock using NTP.
   
   - **Enable NTP**:
   ```bash
   timedatectl set-ntp true
   ```
   
   - **Disable NTP**:
   ```bash
   timedatectl set-ntp false
   ```

---

### **`systemctl` Commands**

`systemctl` is used to control and manage system services and the system's state.

1. **Restart Network Service** (in the context of networking issues):
   ```bash
   sudo systemctl restart network
   ```

   - **Explanation**: This command attempts to restart the network service. However, in newer systems using **NetworkManager**, you might need to use a different service name like `NetworkManager`.

2. **Check the status of Network Service**:
   This command can be used to check the status of the `network` service.
   ```bash
   systemctl status network
   ```

   - **Explanation**: Shows the current status of the network service (whether it’s active, inactive, or failed).

3. **Start NetworkManager** (if `network.service` does not exist):
   On many modern systems, `NetworkManager` is used instead of `network.service` to manage network configurations.
   ```bash
   sudo systemctl start NetworkManager
   ```

   - **Explanation**: Starts the **NetworkManager** service, which controls network connections.

4. **Enable NetworkManager to start on boot**:
   If you want **NetworkManager** to automatically start when the system boots, you can use:
   ```bash
   sudo systemctl enable NetworkManager
   ```

   - **Explanation**: This ensures that **NetworkManager** will start automatically at boot time.

5. **Check the status of NetworkManager**:
   This command checks whether the **NetworkManager** service is active.
   ```bash
   systemctl status NetworkManager
   ```

   - **Explanation**: Displays the status of the **NetworkManager** service, indicating whether it is running or inactive.

6. **Stop NetworkManager service**:
   If you need to stop **NetworkManager**, you can use:
   ```bash
   sudo systemctl stop NetworkManager
   ```

   - **Explanation**: Stops the **NetworkManager** service.

7. **Reboot the system**:
   If you need to reboot the system (in case changes to system settings require a restart), you can use:
   ```bash
   sudo systemctl reboot
   ```

   - **Explanation**: Reboots the system.

---

### **Examples of the commands used in the problems above:**

- **Set the time zone to `Asia/Kolkata`**:
   ```bash
   timedatectl set-timezone Asia/Kolkata
   ```

- **Check the current time settings** after setting the timezone:
   ```bash
   timedatectl
   ```

- **Enable NTP synchronization (to sync system time with online time servers)**:
   ```bash
   timedatectl set-ntp true
   ```

- **Restart the `network` service** (to apply network changes):
   ```bash
   sudo systemctl restart network
   ```

- **Check the status of `NetworkManager`** (if `network.service` is not available):
   ```bash
   systemctl status NetworkManager
   ```

By using these commands in conjunction with each other, you can manage both the system time and networking on a Linux-based system.
