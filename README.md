# WMI Filters for Group Policy

Ready-to-use WMI filters for targeting Group Policy Objects by Windows version, build,
product type, domain role and architecture. 58 filters, each one copy-paste ready.

## Contents

| Topic | What you will find |
| --- | --- |
| [Windows client](filters/Windows-Client.md) | Windows 11 and 10 by feature update, Windows 8.1, 8, 7, Vista, XP, 2000 |
| [Windows Server](filters/Windows-Server.md) | LTSC releases 2000-2025, Annual Channel 23H2, Semi-Annual Channel 1709-20H2 |
| [Roles and architecture](filters/Roles-and-Architecture.md) | Workstations, domain controllers, member servers, PDC emulator, 64-bit / 32-bit |

## Quick reference

### ProductType (`Win32_OperatingSystem`)

| Value | Meaning |
| --- | --- |
| `1` | Workstation |
| `2` | Domain controller |
| `3` | Server (not a domain controller) |

### DomainRole (`Win32_ComputerSystem`)

| Value | Meaning |
| --- | --- |
| `0` | Standalone workstation |
| `1` | Member workstation |
| `2` | Standalone server |
| `3` | Member server |
| `4` | Backup domain controller |
| `5` | Primary domain controller (PDC emulator) |

### Shared build numbers

Some client and server releases share a build, so the filters also check `ProductType`:

| Build | Client | Server |
| --- | --- | --- |
| 26100 | Windows 11 24H2 | Windows Server 2025 |
| 19042 | Windows 10 20H2 | Windows Server 20H2 |
| 19041 | Windows 10 2004 | Windows Server 2004 |
| 18363 | Windows 10 1909 | Windows Server 1909 |
| 18362 | Windows 10 1903 | Windows Server 1903 |
| 17763 | Windows 10 1809 | Windows Server 2019 / 1809 |
| 17134 | Windows 10 1803 | Windows Server 1803 |
| 16299 | Windows 10 1709 | Windows Server 1709 |
| 14393 | Windows 10 1607 | Windows Server 2016 |

## Usage

### Create a filter in GPMC

1. Open **Group Policy Management** and go to **Forest > Domains > _your domain_ > WMI Filters**.
2. Right-click **WMI Filters** > **New**, enter a name (for example the heading of the filter) and a description.
3. Click **Add**, keep the namespace `root\CIMv2`, paste the query and click **OK**, then **Save**.
4. Select the GPO and pick the filter under **WMI Filtering** on its **Scope** tab.

A GPO can be linked to only one WMI filter, but one filter can be used by many GPOs.

### Test a query before you use it

Run the query on a target machine. Any result means the filter evaluates to **true**
(the GPO applies); no output means **false**.

```powershell
Get-CimInstance -Namespace root/CIMv2 -Query 'select * from Win32_OperatingSystem where Version like "10.0.2%" and ProductType="1"'
```

To check which build a machine reports:

```powershell
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, BuildNumber, ProductType
```

### Tips

- `%` in a `like` clause matches any number of characters, so `"10.0.2%"` matches every build that starts with 2.
- Filters are evaluated by each target computer during Group Policy processing. Keep them simple:
  a slow query delays every policy refresh.
- Windows 2000 ignores WMI filters, so a GPO with a filter still applies to it.
- Confirm results with `gpresult /h report.html` or the **Group Policy Results** wizard in GPMC.
