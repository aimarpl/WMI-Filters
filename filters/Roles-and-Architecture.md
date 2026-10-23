# WMI Filters for Roles and Architecture

[← Back to index](../README.md)

Filters that target machines by product type, domain role or OS architecture.

All filters use the `root\CIMv2` namespace.

## Contents

- [Operating System Types](#operating-system-types)
  - [Desktop Operating Systems](#desktop-operating-systems)
  - [Domain Controllers](#domain-controllers)
  - [Member Servers](#member-servers)
  - [Domain Controllers and Member Servers](#domain-controllers-and-member-servers)
- [Computer System Types](#computer-system-types)
  - [Standalone Workstation](#standalone-workstation)
  - [Member Workstation](#member-workstation)
  - [Standalone Server](#standalone-server)
  - [Member Server](#member-server)
  - [Backup Domain Controller](#backup-domain-controller)
  - [Primary Domain Controller (PDC)](#primary-domain-controller-pdc)
- [64-bit and 32-bit Operating Systems](#64-bit-and-32-bit-operating-systems)
  - [64-bit operating systems](#64-bit-operating-systems)
  - [32-bit operating systems](#32-bit-operating-systems)

## Operating System Types

Based on `Win32_OperatingSystem.ProductType`, independent of the Windows version.

| Filter | Matches |
| --- | --- |
| [Desktop Operating Systems](#desktop-operating-systems) | ProductType 1 |
| [Domain Controllers](#domain-controllers) | ProductType 2 |
| [Member Servers](#member-servers) | ProductType 3 |
| [Domain Controllers and Member Servers](#domain-controllers-and-member-servers) | ProductType 2 / 3 |

### Desktop Operating Systems

All Windows workstation operating systems.

```sql
select * from Win32_OperatingSystem where ProductType="1"
```

### Domain Controllers

All Windows server operating systems that are domain controllers.

```sql
select * from Win32_OperatingSystem where ProductType="2"
```

### Member Servers

All Windows server operating systems that are not domain controllers.

```sql
select * from Win32_OperatingSystem where ProductType="3"
```

### Domain Controllers and Member Servers

All Windows server operating systems.

```sql
select * from Win32_OperatingSystem where ProductType="2" or ProductType="3"
```

## Computer System Types

Based on `Win32_ComputerSystem.DomainRole`: domain membership and domain controller role.

| Filter | Matches |
| --- | --- |
| [Standalone Workstation](#standalone-workstation) | DomainRole 0 |
| [Member Workstation](#member-workstation) | DomainRole 1 |
| [Standalone Server](#standalone-server) | DomainRole 2 |
| [Member Server](#member-server) | DomainRole 3 |
| [Backup Domain Controller](#backup-domain-controller) | DomainRole 4 |
| [Primary Domain Controller (PDC)](#primary-domain-controller-pdc) | DomainRole 5 |

### Standalone Workstation

Workstation that is not joined to a domain.

```sql
select * from Win32_ComputerSystem where DomainRole="0"
```

### Member Workstation

Domain-joined workstation.

```sql
select * from Win32_ComputerSystem where DomainRole="1"
```

### Standalone Server

Server that is not joined to a domain.

```sql
select * from Win32_ComputerSystem where DomainRole="2"
```

### Member Server

Domain-joined server that is not a domain controller.

```sql
select * from Win32_ComputerSystem where DomainRole="3"
```

### Backup Domain Controller

Domain controller that does not hold the PDC emulator role.

```sql
select * from Win32_ComputerSystem where DomainRole="4"
```

### Primary Domain Controller (PDC)

The domain controller that holds the PDC emulator FSMO role.

```sql
select * from Win32_ComputerSystem where DomainRole="5"
```

## 64-bit and 32-bit Operating Systems

Based on `Win32_Processor.AddressWidth`, which reports the operating system's architecture, not the CPU's.

| Filter | Matches |
| --- | --- |
| [64-bit operating systems](#64-bit-operating-systems) | AddressWidth 64 |
| [32-bit operating systems](#32-bit-operating-systems) | AddressWidth 32 |

### 64-bit operating systems

64-bit Windows.

```sql
select * from Win32_Processor where AddressWidth = "64"
```

### 32-bit operating systems

32-bit Windows (including 32-bit Windows on a 64-bit CPU).

```sql
select * from Win32_Processor where AddressWidth = "32"
```

## See also

- [WMI Filters for Windows Client Operating Systems](Windows-Client.md)
- [WMI Filters for Windows Server Operating Systems](Windows-Server.md)
