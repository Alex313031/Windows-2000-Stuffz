By default, under NT 4.0, it is not possible to automatically power off the computer after exiting Windows NT.  
This functionality requires a specialized HAL (Hardware Abstraction Layer) provided by the motherboard manufacturer.

Service Pack 6 (SP6) now includes a HAL that enables the "PowerdownAfterShutdown" feature.

The corresponding modified HAL files from SP6 are here:

Single Processor
hal.dll

Multi-Processor
halmps.dll

The `hal.dll` file must be copied to the `System32` directory. If multi-processor, rename halmps.dll to hal.dll and replace one in `System32`.

After replacing the original HAL, you must also add the `PowerdownAfterShutdown` key (Reg_SZ) with a value of "1" to the registry,
located at: `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\Winlogon`.

Please also note that this entire procedure will only work if Service Pack 6 (SP6) is installed!

The developer of the SoftEx HAL.DLL is Softex Inc: 
[http://www.softexinc.com(Web Archive)](https://web.archive.org/web/20050406032822fw_/http://www.softexinc.com/homeproductpage.asp) (Web Archive).
