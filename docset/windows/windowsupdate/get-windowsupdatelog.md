---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: WindowsUpdateLog-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WindowsUpdateLog
ms.assetid: E6F01AE3-43FD-40D0-B843-7F3780B1C2F2
---

# Get-WindowsUpdateLog

## SYNOPSIS
Merges Windows Update .etl files into a single log file.

## SYNTAX

```
Get-WindowsUpdateLog [[-ETLPath] <String[]>] [[-LogPath] <String>] [[-SymbolServer] <String>]
 [-ProcessingType <String>] [-ForceFlush] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WindowsUpdateLog** cmdlet merges and converts Windows Update .etl files into a single readable WindowsUpdate.log file.
Windows Update Agent uses Event Tracing for Windows (ETW) to generate diagnostic logs.
Windows Update no longer directly produces a WindowsUpdate.log file.
Instead, it produces .etl files that are not immediately readable as written.

This cmdlet requires access to a Microsoft symbol server.

## EXAMPLES

### Example 1: Merge and convert Windows Update trace files
```
PS C:\> Get-WindowsUpdateLog
Converting C:\Windows\logs\WindowsUpdate into C:\Users\Admin\Desktop\WindowsUpdate.log 




    Directory: C:\Users\admin\AppData\Local\Temp\WindowsUpdateLog


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        5/30/2015  10:02 PM                SymCache

Input
----------------
File(s): 
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.112451.395.1.etl
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.112502.723.1.etl
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.112524.191.1.etl
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.121921.075.1.etl
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.122031.684.1.etl
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.122432.434.1.etl
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.122432.434.2.etl
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.122432.434.3.etl
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.122432.434.4.etl
     C:\Windows\logs\WindowsUpdate\WindowsUpdate.20150529.122432.434.5.etl

0.00%8.33%16.67%25.00%33.33%41.67%50.00%58.33%66.67%75.00%83.33%91.67%100.00%

Output
----------------
DumpFile:           C:\Users\admin\AppData\Local\Temp\WindowsUpdateLog\wuetl.CSV.tmp.0

The command completed successfully. 

WindowsUpdate.log written to C:\Users\admin\Desktop\WindowsUpdate.log
```

This command merges and converts Windows Update trace files (.etl files) into a single readable WindowsUpdate.log file.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ETLPath
Specifies an array of paths of Windows Update .etl files to convert into WindowsUpdate.log.
The default value for this parameter is the Windows Update trace file directory for the current device.
The acceptable values for this parameter are:

- The full path of a directory that contains one or more .etl files.
- The full path of a single .etl file.
- A comma-separated list of full paths of .etl files.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ForceFlush
Indicates that this cmdlet forces the Windows Update Agent on the current device to flush all of its traces to .etl files.
This process stops the Update Orchestrator and Windows Update services.
Running this cmdlet with this parameter requires administrative credentials.
You can start Windows PowerShell with administrative credentials by using the Run as administrator command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPath
Specifies the full path to which **Get-WindowsUpdateLog** writes WindowsUpdate.log.
The default value is WindowsUpdate.log in the Desktop folder of the current user.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessingType
Specifies the file type that **Get-WindowsUpdateLog** uses for temporary files that are created during intermediate processing.
The acceptable values for this parameter are:

- CSV (comma-separated values)
- XML

By default, the value is CSV.
The temporary files are in $env:TEMP\WindowsUpdateLog.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: CSV, XML

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SymbolServer
Specifies the URL of Microsoft Symbol Server.
By default, this value is the Microsoft public symbol server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Update Cmdlets](./windowsupdate.md)
