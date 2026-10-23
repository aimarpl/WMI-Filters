# WMI Filters for Windows Server Operating Systems

[← Back to index](../README.md)

Filters that target server releases (`ProductType="2"` or `"3"`) by Windows version or build.

All filters use the `root\CIMv2` namespace.

## Contents

- [Long-Term Servicing Channel (LTSC)](#long-term-servicing-channel-ltsc)
  - [Windows Server 2025](#windows-server-2025)
  - [Windows Server 2022](#windows-server-2022)
  - [Windows Server 2019](#windows-server-2019)
  - [Windows Server 2016](#windows-server-2016)
  - [Windows Server 2012 R2](#windows-server-2012-r2)
  - [Windows Server 2012](#windows-server-2012)
  - [Windows Server 2008 R2](#windows-server-2008-r2)
  - [Windows Server 2008](#windows-server-2008)
  - [Windows Server 2003 and Windows Server 2003 R2](#windows-server-2003-and-windows-server-2003-r2)
  - [Windows Server 2000](#windows-server-2000)
- [Annual Channel (AC)](#annual-channel-ac)
  - [Windows Server 23H2](#windows-server-23h2)
- [Semi-Annual Channel (SAC)](#semi-annual-channel-sac)
  - [Windows Server 20H2](#windows-server-20h2)
  - [Windows Server 2004](#windows-server-2004)
  - [Windows Server 1909](#windows-server-1909)
  - [Windows Server 1903](#windows-server-1903)
  - [Windows Server 1809](#windows-server-1809)
  - [Windows Server 1803](#windows-server-1803)
  - [Windows Server 1709](#windows-server-1709)

## Long-Term Servicing Channel (LTSC)

The standard Windows Server releases. All filters match both domain controllers (`ProductType="2"`) and member servers (`ProductType="3"`).

| Filter | Build / version |
| --- | --- |
| [Windows Server 2025](#windows-server-2025) | 26100 |
| [Windows Server 2022](#windows-server-2022) | 20348 |
| [Windows Server 2019](#windows-server-2019) | 17763 |
| [Windows Server 2016](#windows-server-2016) | 14393 |
| [Windows Server 2012 R2](#windows-server-2012-r2) | 6.3 |
| [Windows Server 2012](#windows-server-2012) | 6.2 |
| [Windows Server 2008 R2](#windows-server-2008-r2) | 6.1 |
| [Windows Server 2008](#windows-server-2008) | 6.0 |
| [Windows Server 2003 and Windows Server 2003 R2](#windows-server-2003-and-windows-server-2003-r2) | 5.2 |
| [Windows Server 2000](#windows-server-2000) | 5.0 |

### Windows Server 2025

Windows Server 2025.

```sql
select * from Win32_OperatingSystem where Version like "10.0.26100%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2022

Windows Server 2022.

```sql
select * from Win32_OperatingSystem where Version like "10.0.20348%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2019

Windows Server 2019.

```sql
select * from Win32_OperatingSystem where Version like "10.0.17763%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2016

Windows Server 2016.

```sql
select * from Win32_OperatingSystem where Version like "10.0.14393%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2012 R2

Windows Server 2012 R2.

```sql
select * from Win32_OperatingSystem where Version like "6.3%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2012

Windows Server 2012.

```sql
select * from Win32_OperatingSystem where Version like "6.2%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2008 R2

Windows Server 2008 R2.

```sql
select * from Win32_OperatingSystem where Version like "6.1%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2008

Windows Server 2008.

```sql
select * from Win32_OperatingSystem where Version like "6.0%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2003 and Windows Server 2003 R2

Windows Server 2003 and 2003 R2.

```sql
select * from Win32_OperatingSystem where Version like "5.2%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2000

Windows 2000 Server.

```sql
select * from Win32_OperatingSystem where Version like "5.0%" and (ProductType="2" or ProductType="3")
```

> [!NOTE]
> Windows 2000 does not evaluate WMI filters: the GPO is applied to it regardless of the filter. Use security filtering or a dedicated OU instead.

## Annual Channel (AC)

Container-focused annual releases.

| Filter | Build / version |
| --- | --- |
| [Windows Server 23H2](#windows-server-23h2) | 25398 |

### Windows Server 23H2

Windows Server version 23H2.

```sql
select * from Win32_OperatingSystem where Version like "10.0.25398%" and (ProductType="2" or ProductType="3")
```

## Semi-Annual Channel (SAC)

Retired semi-annual Server Core releases.

| Filter | Build / version |
| --- | --- |
| [Windows Server 20H2](#windows-server-20h2) | 19042 |
| [Windows Server 2004](#windows-server-2004) | 19041 |
| [Windows Server 1909](#windows-server-1909) | 18363 |
| [Windows Server 1903](#windows-server-1903) | 18362 |
| [Windows Server 1809](#windows-server-1809) | 17763 |
| [Windows Server 1803](#windows-server-1803) | 17134 |
| [Windows Server 1709](#windows-server-1709) | 16299 |

### Windows Server 20H2

Windows Server version 20H2.

```sql
select * from Win32_OperatingSystem where Version like "10.0.19042%" and (ProductType="2" or ProductType="3")
```

### Windows Server 2004

Windows Server version 2004.

```sql
select * from Win32_OperatingSystem where Version like "10.0.19041%" and (ProductType="2" or ProductType="3")
```

### Windows Server 1909

Windows Server version 1909.

```sql
select * from Win32_OperatingSystem where Version like "10.0.18363%" and (ProductType="2" or ProductType="3")
```

### Windows Server 1903

Windows Server version 1903.

```sql
select * from Win32_OperatingSystem where Version like "10.0.18362%" and (ProductType="2" or ProductType="3")
```

### Windows Server 1809

Windows Server version 1809.

```sql
select * from Win32_OperatingSystem where Version like "10.0.17763%" and (ProductType="2" or ProductType="3")
```

### Windows Server 1803

Windows Server version 1803.

```sql
select * from Win32_OperatingSystem where Version like "10.0.17134%" and (ProductType="2" or ProductType="3")
```

### Windows Server 1709

Windows Server version 1709.

```sql
select * from Win32_OperatingSystem where Version like "10.0.16299%" and (ProductType="2" or ProductType="3")
```

## See also

- [WMI Filters for Windows Client Operating Systems](Windows-Client.md)
- [WMI Filters for Roles and Architecture](Roles-and-Architecture.md)
