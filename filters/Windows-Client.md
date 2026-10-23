# WMI Filters for Windows Client Operating Systems

[← Back to index](../README.md)

Filters that target workstation releases (`ProductType="1"`) by Windows version or build.

All filters use the `root\CIMv2` namespace.

## Contents

- [Windows 11](#windows-11)
  - [Windows 11 (All Versions)](#windows-11-all-versions)
  - [Windows 11 (25H2)](#windows-11-25h2)
  - [Windows 11 (24H2)](#windows-11-24h2)
  - [Windows 11 (23H2)](#windows-11-23h2)
  - [Windows 11 (22H2)](#windows-11-22h2)
  - [Windows 11 (21H2)](#windows-11-21h2)
- [Windows 10](#windows-10)
  - [Windows 10 (All Versions)](#windows-10-all-versions)
  - [Windows 10 (22H2)](#windows-10-22h2)
  - [Windows 10 (21H2)](#windows-10-21h2)
  - [Windows 10 (21H1)](#windows-10-21h1)
  - [Windows 10 (20H2)](#windows-10-20h2)
  - [Windows 10 (2004)](#windows-10-2004)
  - [Windows 10 (1909)](#windows-10-1909)
  - [Windows 10 (1903)](#windows-10-1903)
  - [Windows 10 (1809)](#windows-10-1809)
  - [Windows 10 (1803)](#windows-10-1803)
  - [Windows 10 (1709)](#windows-10-1709)
  - [Windows 10 (1703)](#windows-10-1703)
  - [Windows 10 (1607)](#windows-10-1607)
  - [Windows 10 (1511)](#windows-10-1511)
  - [Windows 10 (1507)](#windows-10-1507)
- [Legacy Windows](#legacy-windows)
  - [Windows 8 and 8.1](#windows-8-and-81)
  - [Windows 8.1](#windows-81)
  - [Windows 8](#windows-8)
  - [Windows 7](#windows-7)
  - [Windows Vista](#windows-vista)
  - [Windows XP](#windows-xp)
  - [Windows 2000](#windows-2000)

## Windows 11

Windows 11 reports version `10.0` like Windows 10; the build number (22000 and later) tells them apart.

| Filter | Build / version |
| --- | --- |
| [Windows 11 (All Versions)](#windows-11-all-versions) | 10.0.2xxxx |
| [Windows 11 (25H2)](#windows-11-25h2) | 26200 |
| [Windows 11 (24H2)](#windows-11-24h2) | 26100 |
| [Windows 11 (23H2)](#windows-11-23h2) | 22631 |
| [Windows 11 (22H2)](#windows-11-22h2) | 22621 |
| [Windows 11 (21H2)](#windows-11-21h2) | 22000 |

### Windows 11 (All Versions)

Every Windows 11 release (builds 22000 and later).

```sql
select * from Win32_OperatingSystem where Version like "10.0.2%" and ProductType="1"
```

### Windows 11 (25H2)

Windows 11 version 25H2.

```sql
select * from Win32_OperatingSystem where Version like "10.0.26200%" and ProductType="1"
```

### Windows 11 (24H2)

Windows 11 version 24H2 (also LTSC 2024).

```sql
select * from Win32_OperatingSystem where Version like "10.0.26100%" and ProductType="1"
```

### Windows 11 (23H2)

Windows 11 version 23H2.

```sql
select * from Win32_OperatingSystem where Version like "10.0.22631%" and ProductType="1"
```

### Windows 11 (22H2)

Windows 11 version 22H2.

```sql
select * from Win32_OperatingSystem where Version like "10.0.22621%" and ProductType="1"
```

### Windows 11 (21H2)

Windows 11 version 21H2 (original release).

```sql
select * from Win32_OperatingSystem where Version like "10.0.22000%" and ProductType="1"
```

## Windows 10

Windows 10 builds range from 10240 to 19045.

| Filter | Build / version |
| --- | --- |
| [Windows 10 (All Versions)](#windows-10-all-versions) | 10.0.1xxxx |
| [Windows 10 (22H2)](#windows-10-22h2) | 19045 |
| [Windows 10 (21H2)](#windows-10-21h2) | 19044 |
| [Windows 10 (21H1)](#windows-10-21h1) | 19043 |
| [Windows 10 (20H2)](#windows-10-20h2) | 19042 |
| [Windows 10 (2004)](#windows-10-2004) | 19041 |
| [Windows 10 (1909)](#windows-10-1909) | 18363 |
| [Windows 10 (1903)](#windows-10-1903) | 18362 |
| [Windows 10 (1809)](#windows-10-1809) | 17763 |
| [Windows 10 (1803)](#windows-10-1803) | 17134 |
| [Windows 10 (1709)](#windows-10-1709) | 16299 |
| [Windows 10 (1703)](#windows-10-1703) | 15063 |
| [Windows 10 (1607)](#windows-10-1607) | 14393 |
| [Windows 10 (1511)](#windows-10-1511) | 10586 |
| [Windows 10 (1507)](#windows-10-1507) | 10240 |

### Windows 10 (All Versions)

Every Windows 10 release (builds 10240-19045).

```sql
select * from Win32_OperatingSystem where Version like "10.0.1%" and ProductType="1"
```

### Windows 10 (22H2)

Windows 10 version 22H2.

```sql
select * from Win32_OperatingSystem where Version like "10.0.19045%" and ProductType="1"
```

### Windows 10 (21H2)

Windows 10 version 21H2 (also LTSC 2021).

```sql
select * from Win32_OperatingSystem where Version like "10.0.19044%" and ProductType="1"
```

### Windows 10 (21H1)

Windows 10 version 21H1.

```sql
select * from Win32_OperatingSystem where Version like "10.0.19043%" and ProductType="1"
```

### Windows 10 (20H2)

Windows 10 version 20H2.

```sql
select * from Win32_OperatingSystem where Version like "10.0.19042%" and ProductType="1"
```

### Windows 10 (2004)

Windows 10 version 2004.

```sql
select * from Win32_OperatingSystem where Version like "10.0.19041%" and ProductType="1"
```

### Windows 10 (1909)

Windows 10 version 1909.

```sql
select * from Win32_OperatingSystem where Version like "10.0.18363%" and ProductType="1"
```

### Windows 10 (1903)

Windows 10 version 1903.

```sql
select * from Win32_OperatingSystem where Version like "10.0.18362%" and ProductType="1"
```

### Windows 10 (1809)

Windows 10 version 1809 (also LTSC 2019).

```sql
select * from Win32_OperatingSystem where Version like "10.0.17763%" and ProductType="1"
```

### Windows 10 (1803)

Windows 10 version 1803.

```sql
select * from Win32_OperatingSystem where Version like "10.0.17134%" and ProductType="1"
```

### Windows 10 (1709)

Windows 10 version 1709.

```sql
select * from Win32_OperatingSystem where Version like "10.0.16299%" and ProductType="1"
```

### Windows 10 (1703)

Windows 10 version 1703.

```sql
select * from Win32_OperatingSystem where Version like "10.0.15063%" and ProductType="1"
```

### Windows 10 (1607)

Windows 10 version 1607 (also LTSB 2016).

```sql
select * from Win32_OperatingSystem where Version like "10.0.14393%" and ProductType="1"
```

### Windows 10 (1511)

Windows 10 version 1511.

```sql
select * from Win32_OperatingSystem where Version like "10.0.10586%" and ProductType="1"
```

### Windows 10 (1507)

Windows 10 version 1507 (original release, also LTSB 2015).

```sql
select * from Win32_OperatingSystem where Version like "10.0.10240%" and ProductType="1"
```

## Legacy Windows

Older client releases, identified by the major and minor version.

| Filter | Build / version |
| --- | --- |
| [Windows 8 and 8.1](#windows-8-and-81) | 6.2 / 6.3 |
| [Windows 8.1](#windows-81) | 6.3 |
| [Windows 8](#windows-8) | 6.2 |
| [Windows 7](#windows-7) | 6.1 |
| [Windows Vista](#windows-vista) | 6.0 |
| [Windows XP](#windows-xp) | 5.1 / 5.2 |
| [Windows 2000](#windows-2000) | 5.0 |

### Windows 8 and 8.1

Windows 8 and Windows 8.1 together.

```sql
select * from Win32_OperatingSystem where (Version like "6.3%" and ProductType="1") or (Version like "6.2%" and ProductType="1")
```

### Windows 8.1

Windows 8.1.

```sql
select * from Win32_OperatingSystem where Version like "6.3%" and ProductType="1"
```

### Windows 8

Windows 8.

```sql
select * from Win32_OperatingSystem where Version like "6.2%" and ProductType="1"
```

### Windows 7

Windows 7.

```sql
select * from Win32_OperatingSystem where Version like "6.1%" and ProductType="1"
```

### Windows Vista

Windows Vista.

```sql
select * from Win32_OperatingSystem where Version like "6.0%" and ProductType="1"
```

### Windows XP

Windows XP (5.2 covers XP Professional x64 Edition).

```sql
select * from Win32_OperatingSystem where (Version like "5.1%" or Version like "5.2%") and ProductType="1"
```

### Windows 2000

Windows 2000 Professional.

```sql
select * from Win32_OperatingSystem where Version like "5.0%" and ProductType="1"
```

> [!NOTE]
> Windows 2000 does not evaluate WMI filters: the GPO is applied to it regardless of the filter. Use security filtering or a dedicated OU instead.

## See also

- [WMI Filters for Windows Server Operating Systems](Windows-Server.md)
- [WMI Filters for Roles and Architecture](Roles-and-Architecture.md)
