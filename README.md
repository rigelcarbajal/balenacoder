# Coder on BalenaOS (Fixed Version)

This is a **corrected** `docker-compose.yml` to deploy [Coder](https://coder.com/docs/install/docker) on **BalenaOS devices** (like Raspberry Pi) seamlessly.  
The **original Coder docker-compose** file is **not compatible with BalenaOS** due to unsupported `depends_on: condition: service_healthy` and unsuitable default networking assumptions.  
This version fixes those issues and is ideal for development or lightweight production environments on BalenaCloud.

## Why this version?
- Compatible with `balena push`.
- Works with Balena Supervisor's limited support for `depends_on`.
- Avoids `.local` DNS issues by using static IPs.
- Optimized for devices running BalenaOS 6.x+.

## How to deploy

1. Clone or copy this `docker-compose.yml` into your project directory.
2. Ensure your Balena device is in **Local Mode** or ready for remote deployment.
3. Push to your device or fleet:

    ```bash
    # Push locally
    balena push <DEVICE_IP>

    # Or push to fleet (if targeting via BalenaCloud)
    balena push <FLEET_NAME>
    ```

4. Access your Coder instance at:

    ```
    http://<YOUR_DEVICE_IP>:7080
    ```

    Example:

    ```
    http://YOUR_IP:7080
    ```

---

> Official Coder documentation: [https://coder.com/docs/install/docker](https://coder.com/docs/install/docker)
