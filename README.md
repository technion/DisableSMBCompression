# DisableSMBCompression
CVE-2020-0796 Flaw Mitigation - Active Directory Administrative Templates

The little we know about the new SMB3 flaw, is that we've been provided this mitigation for SMB3 servers:

```
Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" DisableCompression -Type DWORD -Value 1 -Force
```

This repository contains ADMX templates to provide a nice interface to this setting. This allows easy mass deployment of the given mitigation, and easy rollback when desired.

# Installation
See this Microsoft guide for installing new admx files:
https://support.microsoft.com/en-au/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra

Under "Administrative Templates", find the new "SMB Compression Support" setting as below.

![ADMX Template](https://github.com/technion/DisableSMBCompression/raw/master/SMBadmx.jpg)

# References:
https://www.bleepingcomputer.com/news/security/microsoft-leaks-info-on-wormable-windows-smbv3-cve-2020-0796-flaw/
https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV200005
