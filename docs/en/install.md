# Installation (ISO)

Important: installing the OnPremise SRT Server ISO will **erase the entire disk** on the target machine.

**It does not run in virtual machines. Physical hardware only.**

## Steps

1) Download the ISO image (ZIP) and extract it.
2) Write the ISO to a bootable media:
   - Optical disk: use any ISO burning tool.
   - USB drive: use Rufus v3.13+ and choose **DD Image mode** when asked.
3) Boot the target PC from the USB/optical disk and install.

## Find the device IP on the LAN

Use mDNS/Bonjour to discover the device quickly on the local network.
Example tool: Bonjour Browser.

Once discovered, open the web panel in your browser.

## Default credentials

- Admin role: `admin / admin`
- User role: `user / user`

Change passwords for security and save the recovery email.

## Licensing note (important)

Before creating channels, go to the **License** tab and verify the device is connected to the licensing server and has a free 30-day license.

If not, newly created channels may run only a few minutes.

Make sure DNS is correctly configured in the **Network** tab, so the device can refresh licensing keys.
Do not keep the device disconnected from the Internet for more than several days, or it may become blocked.
