# Desktop v1.2.3: installation and upgrades

[Back to the project overview](../README.md)

## Download

Download the installer for your platform from the [public v1.2.3 release](https://github.com/brianronock/rentitplus/releases/tag/v1.2.3). No GitHub sign-in is required.

| Platform | Release asset |
|---|---|
| macOS | [RentIt+.Desktop-1.2.3.dmg](https://github.com/brianronock/rentitplus/releases/download/v1.2.3/RentIt%2B.Desktop-1.2.3.dmg) |
| Windows | [RentIt+.Desktop-1.2.3.exe](https://github.com/brianronock/rentitplus/releases/download/v1.2.3/RentIt%2B.Desktop-1.2.3.exe) |
| Linux, amd64 | [rentitplus-desktop_1.2.3_amd64.deb](https://github.com/brianronock/rentitplus/releases/download/v1.2.3/rentitplus-desktop_1.2.3_amd64.deb) |

Open the DMG and install the application on macOS, run the EXE installer on Windows, or install the DEB with your package manager on a compatible Linux system. The release contains packaged applications; cloning this companion repository is not an installation step.

The macOS build is not Apple-notarized. macOS may require **System Settings → Privacy & Security → Open Anyway** after the initial launch attempt. Only approve a download whose origin you trust.

## First launch

The setup interface collects a server address, device name, and location. The current production API address is:

```text
https://rentitapi.brianronock.com
```

Use the API address for desktop setup, not the [web SPA address](https://rentitspa.brianronock.com). Initial setup and device registration require network access. Downloading an installer does not create a user account or grant access.

The desktop stores configuration and local working data under `.rentit-desktop` in the user's home directory. Its managed database path includes the device name. Keep the existing device name and local data when upgrading an established installation.

## Upgrading from the retired API address

Version 1.2.3 recognizes an existing external desktop configuration whose `rentit.baseUrl` is exactly `https://api.rentitplus.dev`, with or without a trailing slash, after trimming surrounding whitespace. It replaces that address with the current production API address and saves the configuration.

The migration updates the endpoint setting; it does not intentionally delete the local database. Back up local working data before an upgrade, particularly if changes have not yet synchronized.

Custom server addresses are left unchanged. JVM and environment overrides take precedence over the external configuration, so an explicitly overridden old address must be updated separately. The migration is not a general rewrite of every URL containing the old domain.

## Verify the installer

These SHA-256 values match the original v1.2.3 assets and the copies uploaded to this public release:

```text
6850e25a59668f2152bbedac4f9f7e95471c131d255845a536afc1ef0559936c  RentIt+.Desktop-1.2.3.dmg
bff739815e78f651d924398097f2cdd75977d99d6caff1e26b78a4de35436a80  RentIt+.Desktop-1.2.3.exe
3729a294751575da70af40bacfff7bd29a11c282433aeac30676e8d8771f9a43  rentitplus-desktop_1.2.3_amd64.deb
```

A matching checksum confirms file equality with these release assets; it is not code signing or a security certification.

## Demo use

Use fictional data only. Selected order and desktop rental operations are available to the auditor role, so the shared demo is not strictly read-only. Do not use it to store real customer or business information.

The production API address identifies the configured service; it is not an uptime guarantee. If setup cannot connect, check the address and network connection before making changes to local data.

## Source archives

GitHub automatically attaches ZIP and TAR source archives to releases. For this repository, those archives contain the companion documentation and diagrams. They do not contain the private application source code or replace the installers above.
