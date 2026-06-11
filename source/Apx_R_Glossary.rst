.. _appendix-r-glossary:

Glossary
=========

_ADR
  A reserved name in ACPI name space. It refers to an address on a bus that has standard enumeration. An example would be PCI, where the enumeration method is described in the PCI Local Bus specification.

_CRS
  A reserved name in ACPI name space. It refers to the current resource setting of a device. A _CRS is required for devices that are not enumerated in a standard fashion. _CRS is how ACPI converts nonstandard devices into Plug and Play devices.

_HID
  A reserved name in ACPI name space. It represents a device’s plug and play hardware ID and is stored as a 32-bit compressed EISA ID. _HID objects are optional in ACPI. However, a _HID object must be used to describe any device that will be enumerated by the ACPI driver in the OS. This is how ACPI deals with non–Plug and Play devices.

_UID
  A reserved name in ACPI name space. It is a serial number style ID that does not change across reboots. If a system contains more than one device that reports the same _HID, each device must have a unique _UID. The _UID only needs to be unique for device that have the exact same _HID value. 

ACPI Device Path
  A Device Path that is used to describe devices whose enumeration is not described in an industry-standard fashion. These devices must be described using ACPI AML in the ACPI name space; this type of node provides linkage to the ACPI name space. 

ACPI
  Refers to the Advanced Configuration and Power Interface Specification and to the concepts and technology it discusses. The specification defines a new interface to the system board that enables the operating system to implement operating system-directed power management and system configuration. 

Alt-GR Unicode 
  Represents the character code of a key when the Alt-GR modifier key is held down. This key (A2) in some keyboard layouts is defined as the right alternate key and serves the same function as the left alternate key. However, in many other layouts it is a secondary modifier key similar to shift. For instance, key C1 is equated to the letter a and its Unicode character code in the typical U.K. keyboard is a non-shifted character code of 0x0061. When holding down the Alt-GR key in conjunction with the pressing of key C1, , the value on the same keyboard often produces an á, which is a character code 0x00E1.

Base Code (BC)
  The PXE Base Code, included as a core protocol in EFI, is comprised of a simple network stack (UDP/IP) and a few common network protocols (DHCP, Bootserver Discovery, TFTP) that are useful for remote booting machines.

BC
  See Base Code (BC)

Big Endian
  A memory architecture in which the low-order byte of a multibyte datum is at the highest address, while the high-order byte is at the lowest address. See Little Endian. 

BIOS Boot Specification Device Path
  A Device Path that is used to point to boot legacy operating systems; it is based on the BIOS Boot Specification, Version 1.01. 

BIOS Parameter Block (BPB)
  The first block (sector) of a partition. It defines the type and location of the FAT File System on a drive. 

BIOS
  Basic Input/Output System. A collection of low-level I/O service routines. 

Block I/O Protocol
  A protocol that is used during boot services to abstract mass storage devices. It allows boot services code to perform block I/O without knowing the type of a device or its controller. 

Block Size
  The fundamental allocation unit for devices that support the Block I/O Protocol. Not less than 512 bytes. This is commonly referred to as sector size on hard disk drives.

Boot Device
  The Device Handle that corresponds to the device from which the currently executing image was loaded.

Boot Manager
  The part of the firmware implementation that is responsible for implementing system boot policy. Although a particular boot manager implementation is not specified in this document, such code is generally expected to be able to enumerate and handle transfers of control to the available OS loaders as well as UEFI applications and drivers on a given system. The boot manager would typically be responsible for interacting with the system user, where applicable, to determine what to load during system startup. In cases where user interaction is not indicated, the boot manager would determine what to load and, if multiple items are to be loaded, what the sequencing of such loads would be.

Block Size 
  The fundamental allocation unit for devices that support the Block I/O Protocol. Not less than 512 bytes. This is commonly referred to as sector size on disk drives. 

Boot Services Table
  A table that contains the firmware entry points for accessing boot services functions such as Task Priority Services and Memory Allocation Services. The table is accessed through a pointer in the System Table. 

Boot Services Time
  The period of time between platform initialization and the call to ExitBootServices(). During this time, UEFI Driver and applications are loaded iteratively and the system boots from an ordered list of EFI OS loaders. 

Boot Services
  The collection of interfaces and protocols that are present in the boot environment. The services minimally provide an OS loader with access to platform capabilities required to complete OS boot. Services are also available to drivers and applications that need access to platform capability. Boot services are terminated once the operating system takes control of the platform.

BPB
  See BIOS Parameter Block (BPB). 

BTT
  Block Translation Table: A software mechanism for adding single block write atomicity to any Block Mode ranges or byte-addressable Persistent Memory ranges.

Callback 
  Target function which augments the Forms Processor’s ability to evaluate or process configuration settings. Callbacks are not available when the Forms Processor is operating in a Disconnected state.

CIM
  See Common Information Model (CIM). 

Cluster
  A collection of disk sectors. Clusters are the basic storage units for disk files. See File Allocation Table (FAT). 

COFF
  Common Object File Format, a standard file format for binary images.

Coherency Domain
  (1) The global set of resources that is visible to at least one processor in a platform. 
  (2) The address resources of a system as seen by a processor. It consists of both system memory and I/O space.

Common Information Model (CIM)
  An object-oriented schema defined by the DMTF. CIM is an information model that provides a common way to describe and share management information enterprise-wide. 

Console I/O Protocol
  A protocol that is used during Boot Services to handle input and output of text-based information intended for the system administrator. It has two parts, a Simple Input Protocol that is used to obtain input from the ConsoleIn device and a Simple Text Output Protocol that is used to control text-based output devices. The Console I/O Protocol is also known as the EFI Console I/O Protocol. 

ConsoleIn
  The device handle that corresponds to the device used for user input in the boot services environment. Typically the system keyboard.

ConsoleOut
  The device handle that corresponds to the device used to display messages to the user from the boot services environment. Typically a display screen.

DBCS
  Double Byte Character Set.

Desktop Management Interface (DMI)
  | A platform management information framework, built by the DMTF and designed to provide manageability for desktop and server computing platforms by providing an interface that is: 
  | (1) independent of any specific desktop operating system, network operating system, network protocol, management protocol, processor, or hardware platform; 
  | (2) easy for vendors to implement; and 
  | (3) easily mapped to higher-level protocols.

DMTF (formerly Desktop Management Task Force)
  The DMTF is a standards organization comprised of companies from all areas of the computer industry. DMTF creates open manageability standards spanning diverse emerging and traditional IT infrastructures including cloud, virtualization, network, servers and storage.

Device Handle
  A handle points to a list of one or more protocols that can respond to requests for services for a given device referred to by the handle.

Device I/O Protocol
  A protocol that is used during boot services to access memory and I/O. Also called the EFI Device I/O Protocol. 

Device Path Instance
  When an environment variable represents multiple devices, it is possible for a device path to contain multiple device paths. An example of this would be the ConsoleOut environment variable that consists of both a VGA console and a serial output console. This environment variable would describe a console output stream that would send output to both devices and therefore has a Device Path that consists of two complete device paths. Each of these paths is a device path instance.

Device Path Node
  A variable-length generic data structure that is used to build a device path. Nodes are distinguished by type, subtype, length, and path-specific data. See Device Path. 

Device Path Protocol
  A protocol that is used during boot services to provide the information needed to construct and manage Device Paths. Also called the EFI Device Path Protocol. 

Device Path
  A variable-length binary data structure that is composed of variable-length generic device path nodes and is used to define the programmatic path to a logical or physical device. There are six major types of device paths: Hardware Device Path, ACPI Device Path, Messaging Device Path, Media Device Path, BIOS Boot Specification Device Path, and End of Hardware Device Path. 

DHCP
  See Dynamic Host Configuration Protocol (DHCP). 

Disconnected 
  The state when a Forms Processor is manipulating a form set without being connected to the Target’s pre-OS environment. For example, after booting an OS, a Forms Processor cannot execute call-backs or read the configuration settings. For example, when running a Forms Browser while on a remote machine that is not connected to the Target. In these cases, the Forms Processor has limited knowledge of the Target’s current configuration settings and limited or no ability to use call-backs.

Disk I/O Protocol
  A protocol that is used during boot services to abstract Block I/O devices to allow non-block-sized I/O operations. Also called the EFI Disk I/O Protocol.

DMI
  See DBCS. 

DMTF
  See DMTF (formerly Desktop Management Task Force). 

DNS
  Domain Name System. A protocol used manipulating and translating hostname and IP address

DTLS
  Datagram Transport Layer Security. A protocol to provide communication privacy above UDP.

Dynamic Host Configuration Protocol (DHCP)
  A protocol that is used to get information from a configuration server. DHCP is defined by the DMTF (formerly Desktop Management Task Force), not EFI. 

EAP
  Extensible Authentication Protocol. An authentication framework which supports multiple authentication methods

EBC Image
  Executable EBC image following the PE32 file format.

EBC
  See EFI Byte Code (EBC). 

EFI
  Extensible Firmware Interface. An interface between the operating system (OS) and the platform firmware.

EFI Byte Code (EBC)
  The binary encoding of instructions as output by the EBC C compiler and linker. The EBC Image is executed by the interpreter.

EFI File
  A container consisting of a number of blocks that holds an image or a data file within a file system that complies with this specification.

EFI Hard Disk
  A hard disk that supports the new EFI partitioning scheme (GUID Partition). 

EFI-compliant
  Refers to a platform that complies with this specification. 

EFI-conformant
  See EFI-compliant. 

End of Hardware Device Path
  A Device Path which, depending on the subtype, is used to indicate the end of the Device Path instance or Device Path structure. 

Enhanced Mode (EM)
  The 64-bit architecture extension that makes up part of the Intel® Itanium® architecture. 

Event Services
  The set of functions used to manage events. Includes EFI_BOOT_SERVICES.CheckEvent(), EFI_BOOT_SERVICES.CreateEvent(), EFI_BOOT_SERVICES.CloseEvent(), EFI_BOOT_SERVICES.SignalEvent(), and EFI_BOOT_SERVICES.WaitForEvent(). 

Event
  An EFI data structure that describes an “event”—for example, the expiration of a timer. 

Event Services
  The set of functions used to manage events.Includes EFI_BOOT_SERVICES.CheckEvent(), EFI_BOOT_SERVICES.CreateEvent(), EFI_BOOT_SERVICES.CloseEvent(), EFI_BOOT_SERVICES.SignalEvent(), and EFI_BOOT_SERVICES.WaitForEvent(). 

FAT File System
  The file system on which the EFI File system is based. See File Allocation Table (FAT) and GUID Partition Table (GPT). 

FAT
  See File Allocation Table (FAT). 

File Allocation Table (FAT)
  A table that is used to identify the clusters that make up a disk file. File allocation tables come in three flavors: FAT12, which uses 12 bits for cluster numbers; FAT16, which uses 16 bits; and FAT32, which allots 32 bits but only uses 28 (the other 4 bits are reserved for future use). 

File Handle Protocol
  A component of the File System Protocol. It provides access to a file or directory. Also called the EFI File Handle Protocol. 

File System Protocol 
  A protocol that is used during boot services to obtain file-based access to a device. It has two parts, a Simple File System Protocol that provides a minimal interface for file-type access to a device, and a File Handle Protocol that provides access to a file or directory. 

Firmware
  Any software that is included in read-only memory (ROM). 

Font
  A graphical representation corresponding to a character set, in this case Unicode. For more information and examples, see https://en.wikipedia.org/wiki/Font. 

Font glyph
  The individual elements of a font corresponding to single characters are called font glyphs or simply glyphs. The first character in each of the above three lines is a glyph for the letter "A" in three different fonts. 

Form 
  Logical grouping of questions with a unique identifier.

Form Set 
  An HII database package describing a group of forms, including one parent form and zero or more child forms.

Forms Browser 
  A Forms Processor capable of displaying the user-interface information a display and interacting with a user.

Forms Processor 
  An application capable of reading and processing the forms data within a forms set.

Globally Unique Identifier (GUID)
  A 128-bit value used to differentiate services and structures in the boot services environment. The format of a GUID is defined in Appendix A. See Protocol.

Glyph
  The individual elements of a font corresponding to single characters. May also be called font keyboard layout glyphs. Also see font glyph above.

GPT
  See GUID Partition Table (GPT).

GPT disk layout: 
  The data layout on a disk consisting of a protective MBR in LBA 0, a GPT Header in LBA 1, and additional GPT structures and partitions in the remaining LBAs. See chapter 5.

GPTHeader
  The header in a GUID Partition Table (GPT). Among other things, it contains the number of GPT Partition Entries and the first and last LBAs that can be used for the entries. 

GPT Partition Entry 
  A data structure that characterizes a Partition in the GPT disk layout. Among other things, it specifies the starting and ending LBA of the partition. 

GUID Partition Table (GPT)
  A data structure that describes one or more partitions. It consists of a GPTHeader and, typically, at least one GPTPartition Entry. There are two GUID partition tables: the Primary Partition Table (located in LBA 1 of the disk) and a Backup Partition Table (located in the last LBA of the disk). The Backup Partition Table is a copy of the Primary Partition Table. 

GPTPartition Entry
  A data structure that characterizes a GUID Partition. Among other things, it specifies the starting and ending LBA of the partition.  

GUID Partition
  A contiguous group of sectors on an EFI Hard Disk. 

Handle
  See Device Handle.

Hardware Device Path
  A Device Path that defines how a hardware device is attached to the resource domain of a system (the resource domain is simply the shared memory, memory mapped I/O, and I/O space of the system). 

HII
  Human Interface Infrastructure.

HII Database 
  The centralized repository for HII-related information, organized as package lists.

HTML 
  Hypertext Markup Language. A particular implementation of SGML focused on hypertext applications. HTML is a fairly simple language that enables the description of pages (generally Internet pages) that include links to other pages and other data types (such as graphics). When applied to a larger world, HTML has many shortcomings, including localization (q.v.) and formatting issues. The HTML form concept is of particular interest to this application.

HTTP 
  Hypertext transfer protocol. HTTP functions as request-response protocol in the client-server computing rule.

IA-32
  See Intel® Architecture-32 (IA-32). 

IFR
  Internal Form Representation. Used to represent forms in EFI so that it can be interpreted as is or expanded easily into XHTML.

Image Handle
  A handle for a loaded image; image handles support the loaded image protocol. 

Image Handoff State
  The information handed off to a loaded image as it begins execution; it consists of the image’s handle and a pointer to the image’s system table. 

Image Header
  The initial set of bytes in a loaded image. They define the image’s encoding. 

Image Services
  The set of functions used to manage EFI images. Includes EFI_BOOT_SERVICES.LoadImage(), EFI_BOOT_SERVICES.StartImage(), EFI_BOOT_SERVICES.UnloadImage(), EFI_BOOT_SERVICES.Exit(), EFI_BOOT_SERVICES.ExitBootServices(), and EFI_IMAGE_ENTRY_POINT. 

Image
  (1) An executable file stored in a file system that complies with this specification. Images may be drivers, applications or OS loaders. Also called an EFI Image. 
  (2) Executable binary file containing EBC and data. Output by the EBC linker.

IME
  Input Method Editor. A program or subprogram that is used to map keystrokes to logographic characters. For example, IMEs are used (possibly with user intervention) to map the Kana (Hirigana or Katakana) characters on Japanese keyboards to Kanji.

Intel® Architecture-32 (IA-32)
  The 32-bit and 16-bit architecture described in the Intel Architecture Software Developer’s Manual. IA-32 is the architecture of the Intel® P6 family of processors, which includes the Intel® Pentium® Pro, Pentium II, Pentium III, and Pentium 4 processors. 

Intel® Itanium® Architecture
  The Intel architecture that has 64-bit instruction capabilities, new performance-enhancing features, and support for the IA-32 instruction set. This architecture is described in the Itanium™ Architecture Software Developer’s Manual. 

internationalization
  In this context, is the process of making a system usable across languages and cultures by using universally understood symbols. Internationalization is difficult due to the differences in cultures and the difficulty of creating obvious symbols; for example, why does a red octagon mean "Stop"?

Interpreter
  The software implementation that decodes EBC binary instructions and executes them on a VM. Also called EBC interpreter.

Keyboard layout
  The physical representation of a user’s keyboard. The usage of this is in conjunction to a structure that equates the physical key(s) and the associated action it represents. For instance, key C1 is equated to the letter a and its Unicode value in the typical U.K. keyboard is a non-shifted value of 0x0061.

LAN On Motherboard (LOM)
  This is a network device that is built onto the motherboard (or baseboard) of the machine.

LBA: 
  See Logical Block Address (LBA).

Legacy Platform
  A platform which, in the interests of providing backward-compatibility, retains obsolete technology. 

LFN
  See Long File Names (LFN). 

Little Endian
  A memory architecture in which the low-order byte of a multibyte datum is at the lowest address, while the high-order byte is at the highest address. See Big Endian. 

Load File Protocol
  A protocol that is used during boot services to find and load other modules of code. 

Loaded Image Protocol
  A protocol that is used during boot services to obtain information about a loaded image. Also called the EFI Loaded Image Protocol. 

Loaded Image
  A file containing executable code. When started, a loaded image is given its image handle and can use it to obtain relevant image data. 

Localization
  The process of focusing a system in so that it works using the symbols of a language/culture. To a major extent the following design is influenced by the requirements of localization.

Logical Block Address (LBA): 
  The address of a logical block on a disk. The first LBA on a disk is LBA 0.

Logographic
  A character set that uses characters to represent words or parts of words rather than syllables or sounds. Kanji is logographic but Kana characters are not.

LOM
  See LAN On Motherboard (LOM).

Long File Names (LFN)
  Refers to an extension to the FAT File System that allows file names to be longer than the original standard (eight characters plus a three-character extension). 

Machine Check Abort (MCA)
  The system management and error correction facilities built into the Intel Itanium processors. 

Master Boot Record (MBR)
  The data structure that resides on the LBA 0 of a hard disk and defines the partitions on the disk. 

MBR
  See Master Boot Record (MBR). 

MBR boot code:
  x86 code in the first LBA of a disk. 

MBR disk layout: 
  The data layout on a disk consisting of an MBR in LBA 0 and partitions described by the MBR in the remaining LBAs. See chapter 5 and Appendix NEW.

MBR Partition Record 
  A data structure that characterizes a Partition in the MBR disk layout.

MCA
  See Machine Check Abort (MCA). 

Media Device Path
  A Device Path that is used to describe the portion of a medium that is being abstracted by a boot service. For example, a Media Device Path could define which partition on a hard drive was being used. 

Memory Allocation Services
  The set of functions used to allocate and free memory, and to retrieve the memory map. Includes EFI_BOOT_SERVICES.AllocatePages(), EFI_BOOT_SERVICES.FreePages(), EFI_BOOT_SERVICES.AllocatePool(), EFI_BOOT_SERVICES.FreePool(), and EFI_BOOT_SERVICES.GetMemoryMap(). 

Memory Map
  A collection of structures that defines the layout and allocation of system memory during the boot process. Drivers and applications that run during the boot process prior to OS control may require memory. The boot services implementation is required to ensure that an appropriate representation of available and allocated memory is communicated to the OS as part of the hand-off of control.

Memory Type
  One of the memory types defined by UEFI for use by the firmware and UEFI applications. Among others, there are types for boot services code, boot services data, Runtime Services code, and runtime services data. Some of the types are used for one purpose before EFI_BOOT_SERVICES.ExitBootServices() is called and another purpose after. 

Messaging Device Path
  A Device Path that is used to describe the connection of devices outside the Coherency Domain of the system. This type of node can describe physical messaging information (e.g., a SCSI ID) or abstract information (e.g., networking protocol IP addresses). 

Miscellaneous Service
  Various functions that are needed to support the EFI environment. Includes EFI_BOOT_SERVICES.InstallConfigurationTable(), ResetSystem(), EFI_BOOT_SERVICES.Stall(), EFI_BOOT_SERVICES.SetWatchdogTimer(), EFI_BOOT_SERVICES.GetNextMonotonicCount(), and GetNextHighMonotonicCount(). 

MTFTP
  See Multicast Trivial File Transfer Protocol (MTFTP). 

Multicast Trivial File Transfer Protocol (MTFTP)
  A protocol used to download a Network Boot Program to many clients simultaneously from a TFTP server. 

Name Space or Namespace
  A namespace defines a contiguously-addressed range of Non-Volatile Memory conceptually similar to a SCSI Logical Unit (LUN) or a NVM Express namespace. In general, a collection of device paths; in an EFI Device Path. 

Native Code
  Low level instructions that are native to the host processor. As such, the processor executes them directly with no overhead of interpretation. Contrast this with EBC, which must be interpreted by native code to operate on a VM.

NBP
  See Network Bootstrap Program (NBP) or Network Boot Program.

Network Boot Program
  A remote boot image downloaded by a PXE client using the Trivial File Transport Protocol (TFTP) or the Multicast Trivial File Transfer Protocol (MTFTP). See Network Bootstrap Program (NBP).

Network Bootstrap Program (NBP)
  This is the first program that is downloaded into a machine that has selected a PXE capable device for remote boot services. A typical NBP examines the machine it is running on to try to determine if the machine is capable of running the next layer (OS or application). If the machine is not capable of running the next layer, control is returned to the EFI boot manager and the next boot device is selected. If the machine is capable, the next layer is downloaded and control can then be passed to the downloaded program. Though most NBPs are OS loaders, NBPs can be written to be standalone applications such as diagnostics, backup/restore, remote management agents, browsers, etc.

Network Interface Card (NIC)
  Technically, this is a network device that is inserted into a bus on the motherboard or in an expansion board. For the purposes of this document, the term NIC will be used in a generic sense, meaning any device that enables a network connection - including LOMs and network devices on external buses (USB, 1394, etc.).

NIC
  See Network Interface Card (NIC).

Non-spacing key
  Typically an accent key that does not advance the cursor and is used to create special characters similar to ÄäÊê. This function is provided only on certain keyboard layouts.

NV
  Nonvolatile.

Package
  HII information with a unique type, such as strings, fonts, images or forms.

Package List 
  Group of packages identified by a GUID. 

Page Memory
  A set of contiguous pages. Page memory is allocated by EFI_BOOT_SERVICES.AllocatePages() and returned by EFI_BOOT_SERVICES.FreePages(). 

Partition Discovery
  The process of scanning a block device to determine whether it contains a Partition. 

Partition
  A contiguous set of LBAs on a disk, described by the MBR and/or GPT disk layouts. 

PC-AT
  Refers to a PC platform that uses the AT form factor for their motherboards. 

PCI Bus Driver
  Software that creates a handle for every PCI Controller on a PCI Host Bus Controller and installs both the PCI I/O Protocol and the Device Path Protocol onto that handle. It may optionally perform PCI Enumeration if resources have not already been allocated to all the PCI Controllers on a PCI Host Bus Controller. It also loads and starts any UEFI drivers found in any PCI Option ROMs discovered during PCI Enumeration. If a driver is found in a PCI Option ROM, the PCI Bus Driver will also attach the Bus Specific Driver Override Protocol to the handle for the PCI Controller that is associated with the PCI Option ROM that the driver was loaded from. 

PCI Bus
  A collection of up to 32 physical PCI Devices that share the same physical PCI bus. All devices on a PCI Bus share the same PCI Configuration Space.

PCI Configuration Space
  The configuration channel defined by PCI to configure PCI Devices into the resource domain of the system. Each PCI device must produce a standard set of registers in the form of a PCI Configuration Header, and can optionally produce device specific registers. The registers are addressed via Type 0 or Type 1 PCI Configuration Cycles as described by the PCI Specification. The PCI Configuration Space can be shared across multiple PCI Buses. On most PC-AT architecture systems and typical Intel® chipsets, the PCI Configuration Space is accessed via I/O ports 0xCF8 and 0xCFC. Many other implementations are possible.

PCI Controller
  A hardware components that is discovered by a PCI Bus Driver, and is managed by a PCI Device Driver. PCI Functions and PCI Controller are used equivalently in this document.

PCI Device Driver
  Software that manages one or more PCI Controllers of a specific type. A driver will use the PCI I/O Protocol to produce a device I/O abstraction in the form of another protocol (i.e., Block I/O, Simple Network, Simple Input, Simple Text Output, Serial I/O, Load File).

PCI Devices
  A collection of up to 8 PCI Functions that share the same PCI Configuration Space. A PCI Device is physically connected to a PCI Buses.

PCI Enumeration
  The process of assigning resources to all the PCI Controllers on a given PCI Host Bus Controller. This includes PCI Bus Number assignments, PCI Interrupt assignments, PCI I/O resource allocation, the PCI Memory resource allocation, the PCI Prefetchable Memory resource allocation, and miscellaneous PCI DMA settings.

PCI Functions
  A controller that provides some type of I/O services. It consumes some combination of PCI I/O, PCI Memory, and PCI Prefetchable Memory regions, and up to 256 bytes of the PCI Configuration Space. The PCI Function is the basic unit of configuration for PCI.

PCI Host Bus Controller
  A chipset component that produces PCI I/O, PCI Memory, and PCI Prefetchable Memory regions in a single Coherency Domain. A PCI Host Bus Controller is composed of one or more PCI Root Bridges.

PCI I/O Protocol
  A software interface that provides access to PCI Memory, PCI I/O, and PCI Configuration spaces for a PCI Controller. It also provides an abstraction for PCI Bus Master DMA.

PCI Option ROM
  A ROM device that is accessed through a PCI Controller, and is described in the PCI Controller’s Configuration Header. It may contain one or more PCI Device Drivers that are used to manage the PCI Controller.

PCI Root Bridge I/O Protocol
  A software abstraction that provides access to the PCI I/O, PCI Memory, and PCI Prefetchable Memory regions in a single Coherency Domain.

PCI Root Bridge
  A chipset component(s) that produces a physical PCI Local Bus.

PCI Segment
  A collection of up to 256 PCI Buses that share the same PCI Configuration Space. PCI Segment is defined in the ACPI Specification as the _SEG object. The SAL_PCI_CONFIG_READ and SAL_PCI_CONFIG_WRITE procedures defined in chapter 9 of the SAL Specification define how to access the PCI Configuration Space in a system that supports multiple PCI Segments. If a system only supports a single PCI Segment the PCI Segment number is defined to be zero. The existence of PCI Segments enables the construction of systems with greater than 256 PCI buses.

Pool Memory
  A set of contiguous bytes. A pool begins on, but need not end on, an “8-byte” boundary. Pool memory is allocated in pages—that is, firmware allocates enough contiguous pages to contain the number of bytes specified in the allocation request. Hence, a pool can be contained within a single page or extend across multiple pages. Pool memory is allocated by EFI_BOOT_SERVICES.AllocatePool() and returned by EFI_BOOT_SERVICES.FreePool(). 

Preboot Execution Environment (PXE)
  | A means by which agents can be loaded remotely onto systems to perform management tasks in the absence of a running OS. To enable the interoperability of clients and downloaded bootstrap programs, the client preboot code must provide a set of services for use by a downloaded bootstrap. It also must ensure certain aspects of the client state at the point in time when the bootstrap begins executing.
  | The complete PXE specification covers three areas; the client, the network and the server.
  | 
  | **Client**
  | - Makes network devices into bootable devices. 
  | - Provides APIs for PXE protocol modules in EFI and for universal drivers in the OS.
  | 
  | **Network**
  | - Uses existing technology: DHCP, TFTP, etc. 
  | - Adds “vendor-specific” tags to DHCP to define PXE-specific operation within DHCP. 
  | - Adds multicast TFTP for high bandwidth remote boot applications. 
  | - Defines Bootserver discovery based on DHCP packet format. 
  | 
  | **Server**
  | - Bootserver: Responds to Bootserver discovery requests and serves up remote boot images.
  | - proxyDHCP: Used to ease the transition of PXE clients and servers into existing network infrastructure. proxyDHCP provides the additional DHCP information that is needed by PXE clients and Bootservers without making changes to existing DHCP servers.
  | - Plug-In Modules: Example proxyDHCP and Bootservers provided in the PXE SDK (software development kit) have the ability to take plug-in modules (PIMs). These PIMs are used to change/enhance the capabilities of the proxyDHCP and Bootservers.

Protocol Handler Services
  The set of functions used to manipulate handles, protocols, and protocol interfaces. Includes EFI_BOOT_SERVICES.InstallProtocolInterface(), EFI_BOOT_SERVICES.UninstallProtocolInterface(), EFI_BOOT_SERVICES.ReinstallProtocolInterface(), EFI_BOOT_SERVICES.HandleProtocol(), EFI_BOOT_SERVICES.RegisterProtocolNotify(), EFI_BOOT_SERVICES.LocateHandle(), and EFI_BOOT_SERVICES.LocateDevicePath(). 

Protocol Handler
  A function that responds to a call to a HandleProtocol request for a given handle. A protocol handler returns a protocol interface structure. 

Protocol Interface Structure
  The set of data definitions and functions used to access a particular type of device. For example, BLOCK_IO is a protocol that encompasses interfaces to read and write blocks from mass storage devices. See Protocol. 

Protocol Revision Number
  The revision number associated with a protocol. See Protocol.

Protocol
  The information that defines how to access a certain type of device during boot services. A protocol consists of a Globally Unique Identifier (GUID), a protocol revision number, and a protocol interface structure. The interface structure contains data definitions and a set of functions for accessing the device. A device can have multiple protocols. Each protocol is accessible through the device’s handle. 

PXE Base Code Protocol
  A protocol that is used to control PXE-compatible devices. It may be used by the firmware’s boot manager to support booting from remote locations.  Also called the EFI PXE Base Code Protocol. 

PXE
  See Preboot Execution Environment (PXE). 

Question 
  IFR which describes how a single configuration setting should be presented, stored, and validated.

Read-Only Memory (ROM)
  When used with reference to the UNDI specification, ROM refers to a nonvolatile memory storage device on a NIC.

Reset
  The action which forces question values to be reset to their defaults.

ROM
  See Question.

Runtime Services Table
  A table that contains the firmware entry points for accessing runtime services functions such as Time Services and Virtual Memory Services. The table is accessed through a pointer in the System Table. 

Runtime Services
  Interfaces that provide access to underlying platform specific hardware that may be useful during OS runtime, such as timers. These services are available during the boot process but also persist after the OS loader terminates boot services.

SAL
  See System Abstraction Layer (SAL). 

scan code
  A value representing the location of a key on a keyboard. Scan codes may also encode make (key press) and break (key release) and auto-repeat information. 

Serial Protocol
  A Protocol that is used during boot services to abstract byte stream devices-that is, to communicate with character-based I/O devices.

SGML
  Standard Generalized Markup Language. A markup language for defining markup languages.

shifted Unicode
  Shifted Unicode represents the Unicode character code of a key when the shift modifier key is held down. For instance, key C1 is equated to the letter a and its Unicode character code in the typical U.K. keyboard is a non-shifted value of 0x0061. When the shift key is held down in conjunction with the pressing of key C1, however, the value on the same keyboard often produces an A, which is a the Unicode character code 0x0041.

  A Protocol that is used during boot services to abstract byte stream devices—that is, to communicate with character-based I/O devices. 

Simple File System Protocol
  A component of the File System Protocol. It provides a minimal interface for file-type access to a device. 

Simple Input Protocol
  A protocol that is used to obtain input from the ConsoleIn device. It is one of two protocols that make up the Console I/O Protocol. 

Simple Network Protocol
  A protocol that is used to provide a packet-level interface to a network adapter. Also called the EFI Simple Network Protocol. 

Simple Text Output Protocol
  A protocol that is used to control text-based output devices. It is one of two protocols that make up the Console I/O Protocol. 

SKU
  Stock keeping unit. An acronym commonly used to reference a “version” of a particular platform. An example might be “We have three different SKUs of this platform.”

SMBIOS
  See System Management BIOS (SMBIOS). 

SNIA
  Storage Network Industry Association.(www.snia.org) 

SNIA Common RAID Disk Data Format
  Storage Network Industry Association Common RAID Disk Data Format Specification, Revision 1.2, July 28, 2006. (www.snia.org) 

SSL
  Secure Sockets Layer. A security protocol that provides communications privacy over the Internet. It is predecessor to TLS.

StandardError
  The device handle that corresponds to the device used to display error messages to the user from the boot services environment.

Status Codes
  Success, error, and warning codes returned by boot services and runtime services functions. 

string
  A null-terminated array of 16-bit UCS-2 encoded Unicode characters. All strings in this specification are encoded using UCS-2 unless otherwise specified.

Submit
  The action which forces modified question values to be written back to storage.

System Abstraction Layer (SAL)
  Firmware that abstracts platform implementation differences, and provides the basic platform software interface to all higher level software. 

System Management BIOS (SMBIOS)
  A table-based interface that is required by the Wired for Management Baseline Specification. It is used to relate platform-specific management information to the OS or to an OS-based management agent. 

System Table
  Table that contains the standard input and output handles for a UEFI application, as well as pointers to the boot services and runtime services tables. It may also contain pointers to other standard tables such as the ACPI, SMBIOS, and SAL System tables. A loaded image receives a pointer to its system table when it begins execution. Also called the EFI System Table. 

Target
  The system being configured.

Task Priority Level (TPL)
  The boot services environment exposes three task priority levels: “normal,” “callback,” and “notify.” 

Task Priority Services
  The set of functions used to manipulate task priority levels. Includes EFI_BOOT_SERVICES.RaiseTPL() and EFI_BOOT_SERVICES.RestoreTPL(). 

TFTP
  See Trivial File Transport Protocol (TFTP). 

Time Format
  The format for expressing time in an EFI-compliant platform. For more information, see Appendix A. 

Time Services
  The set of functions used to manage time. Includes GetTime(), SetTime(), GetWakeupTime(), and SetWakeupTime(). 

Timer Services
  The set of functions used to manipulate timers. Contains a single function, EFI_BOOT_SERVICES.SetTimer(). 

TLS
  Transport Layer Security. A protocol to provide privacy and data integrity between two communicating applications above TCP.

TPL
  See Target.

Trivial File Transport Protocol (TFTP)
  A protocol used to download a Network Boot Program from a TFTP server. 

UEFI 
  Unified Extensible Firmware Interface. The interface between the operating system (OS) and the platform firmware defined by this specification.

UEFI Application
  Modular code that may be loaded in the boot services environment to accomplish platform specific tasks within that environment. Examples of possible applications might include diagnostics or disaster recovery tools shipped with a platform that run outside the OS environment. UEFI applications may be loaded in accordance with policy implemented by the platform firmware to accomplish a specific task. Control is then returned from the UEFI application to the platform firmware.

UEFI Boot Service Driver
  A UEFI driver that is loaded into boot services memory and stays resident until boot services terminate. 

UEFI Driver
  A module of code typically inserted into the firmware via protocol interfaces. Drivers may provide device support during the boot process or they may provide platform services. It is important not to confuse UEFI drivers with OS drivers that load to provide device support once the OS takes control of the platform.

UEFI OS Loader
  A UEFI application that is the first piece of operating system code loaded by the firmware to initiate the OS boot process. This code is loaded at a fixed address and then executed. The OS takes control of the system prior to completing the OS boot process by calling the interface that terminates all boot services.

UEFI Runtime Services Driver
  A UEFI driver that is loaded into runtime services memory and stays resident during runtime. 

Unaccepted Memory
  Some Virtual Machine platforms, such as AMD SEV-SNP, introduce the concept of memory acceptance, requiring memory to be accepted before it can be used by the guest. This protects against a class of attacks by the virtual machine platform.

UNDI
  See Universal Network Device Interface (UNDI).

Unicode Collation Protocol
  A protocol that is used during boot services to perform case-insensitive comparisons of strings. 

Unicode
  An industry standard internationalized character set used for human readable message display.

Universal Network Device Interface (UNDI)
  UNDI is an architectural interface to NICs. Traditionally NICs have had custom interfaces and custom drivers (each NIC had a driver for each OS on each platform architecture). Two variations of UNDI are defined in this specification: H/W UNDI and S/W UNDI. H/W UNDI is an architectural hardware interface to a NIC. S/W UNDI is a software implementation of the H/W UNDI.

Universal Serial Bus (USB)
  A bi-directional, isochronous, dynamically attachable serial interface for adding peripheral devices such as serial ports, parallel ports, and input devices on a single bus. 

URI
  Uniform resource identifier. URI is a string of characters used to identify a name of a resource.

USB Bus Driver
  Software that enumerates and creates a handle for each newly attached USB Controller and installs both the USB I/O Protocol and the Device Path Protocol onto that handle, starts that device driver if applicable. For each newly detached USB Controller, the device driver is stopped, the USB I/O Protocol and the Device Path Protocol are uninstalled from the device handle, and the device handle is destroyed.

USB Bus
  A collection of up to 127 physical USB Devices that share the same physical USB bus. All devices on a USB Bus share the bandwidth of the USB Bus.

USB Controller
  A hardware component that is discovered by a USB Bus Driver, and is managed by a USB Device Driver. USB Interface and USB Controller are used equivalently in this document.

USB Device Driver
  Software that manages one or more USB Controller of a specific type. A driver will use the USB I/O Protocol to produce a device I/O abstraction in the form of another protocol (i.e., Block I/O, Simple Network, Simple Input, Simple Text Output, Serial I/O, Load File).

USB Device
  A USB peripheral that is physically attached to the USB Bus.

USB Enumeration
  A periodical process to search the USB Bus to detect if there have been any USB Controller attached or detached. If an attach event is detected, then the USB Controllers device address is assigned, and a child handle is created. If a detach event is detected, then the child handle is destroyed.

USB Host Controller
  Moves data between system memory and devices on the USB Bus by processing data structures and generating the USB transactions. For USB 1.1, there are currently two types of USB Host Controllers: UHCI and OHCI.

USB Hub
  A special USB Device through which more USB devices can be attached to the USB Bus.

USB I/O Protocol
  A software interface that provides services to manage a USB Controller, and services to move data between a USB Controller and system memory. 

USB Interface
  The USB Interface is the basic unit of a physical USB Device.

USB
  See Universal Serial Bus (USB).

Variable Services
  The set of functions used to manage variables. Includes GetVariable(), SetVariable(), and GetNextVariableName(). 

Virtual Memory Services
  The set of functions used to manage virtual memory. Includes SetVirtualAddressMap() and ConvertPointer(). 

VM
  The Virtual Machine, a pseudo processor implementation consisting of registers which are manipulated by the interpreter when executing EBC instructions.

Watchdog Timer
  An alarm timer that may be set to go off. This can be used to regain control in cases where a code path in the boot services environment fails to or is unable to return control by the expected path. 

WfM
  See Wired for Management (WfM). 

Wired for Management (WfM)
  Refers to the Wired for Management Baseline Specification. The Specification defines a baseline for system manageability issues; its intent is to help lower the cost of computer ownership. 

x64
  Processors that are compatible with instruction sets and operation modes as exemplified by the AMD64 or Intel® Extended Memory 64 Technology (Intel® EM64T) architecture.

XHTML
  Extensible HTML. XHTML "will obey all of the grammar rules of XML (properly nested elements, quoted attributes, and so on), while conforming to the vocabulary of HTML (the elements and attributes that are available for use ant their relationships to one another)." [PXML, pg., 153]. Although not completely defined, XHTML is basically the intersection of XML and HTML and does support forms.

XML
  Extensible Markup Language. A subset of SGML. Addresses many of the problems with HTML but does not currently (1.0) support forms in any specified way.
