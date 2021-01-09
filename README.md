# DNS over TLS and/or DNS over HTTPS Configuration for iOS

## Description

Device configuration profiles for using public dns resolvers (e.g. dns.digitale-gesellschaft.ch or cloudflare-dns.com) by using DNS over TLS and/or DNS over HTTPS on iOS devices. Profile(s) are not protected and can be uninstalled any time. In case a device is passcode protected, the passcode has to be entered in order to correctly install/uninstall the profile.

Settings according to apple device management documentation: https://developer.apple.com/documentation/devicemanagement/dnssettings

## Installation

- open the mobileconfig files via Safari or download it on the device
- click on the file to install it and switch to/open the system settings 
- either on top click to install the profile or goto: general -> profiles (at the bottom)
- follow the instructions as shown

## Usage

- select the desired DNS settings in the VPN & Network settings: System Settings -> General -> VPN & Network
- supplementary note: "automatic" stand for the interface settings (dhcp, fixed ip,...)

Changelog
---------

### v0.2 - 2021-01-09

- quad9 provider added (quad9.net)

### v0.1 - 2020-11-13

- initial version of config files (cloudflare.com & digitale-gesellschaft.ch)
