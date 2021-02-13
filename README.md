# DNS over TLS and/or DNS over HTTPS Configuration for iOS

## Description

Device configuration profiles for using public dns resolvers (e.g. dns.digitale-gesellschaft.ch or cloudflare-dns.com) by using DNS over TLS and/or DNS over HTTPS on iOS devices. Profile(s) are not protected and can be uninstalled any time. In case a device is passcode protected, the passcode has to be entered in order to correctly install/uninstall the profile.

Settings according to apple device management documentation: <https://developer.apple.com/documentation/devicemanagement/dnssettings>

### Conditional Encrypted DNS profiles

In order to exclude certain networks from direct encrypted DNS requests profiles can be adapted for conditional use. Such exclusions can be defined using domain names, network names (SSID) or adress (ranges). One possible use case may be the exclusion of the home network with an own dns resolver for accessing the local NAS system. In order to use such functionality the following code section has to be added to the regular configuration file in which the string "WIFI Network Name" has to be replaced with the corresponding network name which shall be excluded.

```xml
<key>OnDemandRules</key>
    <array>
        <dict>
            <key>Action</key>
            <string>Disconnect</string>
            <key>SSIDMatch</key>
            <array>
                <string>WIFI Network Name</string>
            </array>
        </dict>
        <dict>
            <key>Action</key>
            <string>Connect</string>
        </dict>
    </array>
```

In the subfolder "conditional" there are two sample files for such cases.

- diy_template as name states provides the basic structure. the "#" characters are filler-only-characters and have to be replaced accordingly
- diy_cloudflare-htttps_conditional.mobileconfig is an example config

## Installation

- open the mobileconfig files via Safari or download it on the device
- click on the file to install it and switch to/open the system settings
- either on top click to install the profile or goto: general -> profiles (at the bottom)
- follow the instructions as shown

## Usage

- select the desired DNS settings in the VPN & Network settings: System Settings -> General -> VPN & Network
- supplementary note: "automatic" stand for the interface settings (dhcp, fixed ip,...)

## Changelog

### v0.3 - 2021-01-17

- adding conditional configuration files (template & cloudflare sample)

### v0.2 - 2021-01-09

- quad9 provider added (quad9.net)

### v0.1 - 2020-11-13

- initial version of config files (cloudflare.com & digitale-gesellschaft.ch)
