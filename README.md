# EFI_GA-X670-GX-AX_REV10
Hackintosh EFI for GIGABYTE X670 GAMING X AX (rev. 1.0)
------------------------------------------------------------------------------------------------
Link to the manufacturer's page: https://www.gigabyte.com/us/Motherboard/X670-GAMING-X-AX-rev-10
------------------------------------------------------------------------------------------------
This OpenCore-EFI works with macOS Ventura & macOS Sequoia (not tested with macOS Sonoma).
------------------------------------------------------------------------------------------------

AUDIO:   Realtek HD Audio (ALC897)
OpenCore (AudioDxe.efi) - mac chime output on speaker-out

macOS Ventura (Kexts/AppleALC.kext v1.7.7) - speaker-out, line-out, line-in

macOS Sequoia -not supported-
------------------------------------------------------------------------------------------------
ETHERNET:   Realtek RTL8125 2.5GbE LAN
macOS Ventura/Sequoia (Kexts/LucyRTL8125Ethernet.kext)
------------------------------------------------------------------------------------------------
WIFI:
MediaTek Wi-Fi 6E RZ616 BT5.2 (MT7922A22M) - (removed from system)

macOS Ventura/Sequoia -not supported-
------------------------------------------------------------------------------------------------

USB-MAPPING: (Kexts/UTBMap_GA-X670-GX-AX_REV10.kext)
1x Front USB Type-C with switch (USB3.0+USB2.0)
4x Front USB Type-A Ports (USB3.0+USB2.0)
1x Back USB Type-C Port with switch (only USB3.0)
8x Back USB Type-A Ports (only USB2.0)
1x Internal USB 2.0 for Bluetooth
------------------------------------------------------------------------------------------------
CPU:
AMD Ryzen 9 7950X 4.5 GHz AM5
iGPU AMD Radeon Graphics (disabled in BIOS)

*¹ CPU is set to ECO-Mode (maxed at 105W instead of 170W) (optional BIOS setting)

*² CPU Precision Boost Overdrive (PBO) is disabled (optional BIOS setting)
------------------------------------------------------------------------------------------------

RAM:
Kingston FURY Beast DDR5-5200 MHz 288-Pin 128 GB Kit (4 x 32 GB)
KF552C40BBK-64 (2x)
(Default (JEDEC) configuration for 4 modules in dual channel running @ DDR5-3600 MHz)
------------------------------------------------------------------------------------------------

PCI EXPRESS CARDS:
Sapphire TOXIC AMD Radeon RX 6950 XT Limited Edition 16 GB
PCIEX16 (Slot 1)
macOS Ventura/Sequoia (Kexts/nootrx.kext)
------------------------------------------------------------------------------------------------

GIGABYTE MAPLE RIDGE (rev. 1.0)
Intel JHL8540 Thunderbolt 4-Controller
PCIEX4 (Slot 2)
macOS Ventura/Sequoia (ACPI/SSDT-NV00_GC-MAPLE-RIDGE_REV10.aml)

(BIOS F9 is the last update that unofficial supports the Maple Ridge TB4 AIC on this mainboard.
"Enable Thunderbolt" and "disable security" in UEFI BIOS is inevitable.
Both PCIe 6-Pin power cables must be connected for working PCIe-tunneling.)
(Windows 11 needs the latest Drivers from ASUS ThunderboltEX 4, GIGABYTE Drivers are outdated.)
Link to the manufacturer's driver page: https://www.asus.com/motherboards-components/motherboards/accessories/thunderboltex-4/helpdesk_download?model2Name=ThunderboltEX-4
------------------------------------------------------------------------------------------------

Fenvi FV-T919 WIFI 802.11ac BT4.0 Wireless PCIe Adapter
Broadcom BRCM94360CD
PCIEX2 (Slot 3)
macOS Ventura (native)
macOS Sequoia (OCLP)
------------------------------------------------------------------------------------------------#

BOOTLOADER:
OpenCore v1.0.4
------------------------------------------------------------------------------------------------

HINTS:
-Generate your own "System Serial Nummer" and "System UUID" for this EFI-Files before using.
You can use OpenCoreConfigurator or similar.
It can be found in PlatformInfo/DataHub-Generic-PlatformNVRAM.

-If you want to use FileVault with OCLP-RootPatches (Fenvi T919),
enable "FileVault on Broken Seal"-Patch in Kernel/Patch.

-If you want to use supported RX 6000-Series GPU,
disable "nootrx.kext" and enable "whatevergreen.kext" in Kernel/Add.

-If you don't want to use Maple Ridge Thunderbolt 4 AIC,
disable "SSDT-DTGP.aml" and "SSDT-NV00_GC-MAPLE-RIDGE_REV10.aml" in ACPI/Add.
------------------------------------------------------------------------------------------------
