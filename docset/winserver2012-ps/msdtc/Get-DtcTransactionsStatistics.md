---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: B864A4C6-F248-4685-BEE9-3DC293E01D92
manager: dansimp
---

# Get-DtcTransactionsStatistics

## SYNOPSIS
Gets a summary of transactions.

## SYNTAX

```
Get-DtcTransactionsStatistics [-CimSession <CimSession[]>] [-DtcName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DtcTransactionsStatistics** cmdlet gets a summary of transactions being handled by the Distributed Transaction Coordinator (DTC) instance specified by the **DtcName** parameter.

## EXAMPLES

### Example 1: Get DTC transactions statistics
```
PS C:\>Get-DtcTransactionsStatistics -DtcName "Local"
Open               : 1
Committed          : 0
Aborted            : 0
ForcedAbort        : 0
InDoubt            : 0
Heuristic          : 0
SinglePhaseInDoubt : 0
OpenMax            : 1
CommittedMax       : 0
AbortedMax         : 0
InDoubtMax         : 0
HeuristicMax       : 0
```

This command gets the summary of transactions handled by the Local DTC instance.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DtcName
Specifies a DTC instance.
The cmdlet gets the summary of transactions for this DTC instance.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet displays the summary of transactions handled by the local DTC instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

