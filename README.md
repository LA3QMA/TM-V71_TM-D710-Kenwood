# TM-V71 and TM-D710(G) Kenwood - PC RIG control commands

Reverse engineered RIG control commands for the Kenwood TM-V71 and TM-D710(G).

Thanks to: LA8OKA, W6GPS, WM8S and N1LKS for helping.

Based on rev.11 02 april 2009

## Contributing

Please report any errors or new information to the [issue
tracker](https://github.com/LA3QMA/TM-V71_TM-D710-Kenwood/issues).

## Additional information

- [TM-D710/TM-V71 mailing list](https://kenwood-radios.groups.io/g/main/messages) and (https://kenwood-radios.groups.io/g/TM-D710-and-TM-V71)

## Available control commands for the display unit
(Firmware V1.03 TM-D710Gx, Firmware V2.14 TM-D710x)

These commands work with the display unit on the TM-D710 (and the TM-V71 when using the RC-D710 accessory).

- AE [Display serial number](/commands/AE.md) (This will display gibberish)
- BE [Enable/disable BCON - TMD710G](/commands/BE.md) (When APRS is enabled)
- BL [Backlight status](/commands/BL.md)
- CS [Callsign](/commands/CS.md)
- GP [Internal GPS - TM-D710G](/commands/GP.md)
- GT [Internal GPS](/commands/GT.md) Returns N if internal GPS is not on
- ID [Radio Model](/commands/ID.md)
- RT [Time](/commands/RT.md)
- SR [Reset](/commands/SR.md)
- TC [TNC control mode](/commands/TC.md)
- TN [TNC status](/commands/TN.md)
- TS [TNC control mode 2](/commands/TS.md)
- TY [Display Type](/commands/TY.md)
- 0M PROGRAM [Enters MCP programming mode](PROGRAMMING_MODE.md)

## Available control commands for the main unit
(Firmware V1.03 TM-D710Gx, Firmware V2.10 TM-D710x)

- AE [Radio serial number](/commands/AE.md)
- AS [Reverse](/commands/AS.md)
- BC [PTT and CTRL Band](/commands/BC.md)
- BT [Burst tone](/commands/BT.md)
- BY [Squelch open/closed](/commands/BY.md)
- CC [Call channel](/commands/CC.md)
- CD [Toggle between memory name and channel number](/commands/CD.md)
- DL [Dual Band Mode/Single Band Mode](/commands/DL.md)
- DM [DTMF memory](/commands/DM.md)
- DT [DTMF](/commands/DT.md)
- DW [Emulates the Microphone Down Key](/commands/DW.md)
- FO [VFO channel](/commands/FO.md)
- FV [Firmware version](/commands/FV.md)
- ID [Radio Model](/commands/ID.md)
- LK [Lock](/commands/LK.md)
- ME [Memory channel, frequency, offset etc](/commands/ME.md)
- MN [Memory name](/commands/MN.md)
- MR [Memory channel](/commands/MR.md)
- MS [Power on message](/commands/MS.md)
- MU [Menu](/commands/MU.md)
- PC [Output power](/commands/PC.md)
- PV [Programmable VFO](/commands/PV.md)
- RX [Receive](/commands/RX.md)
- SQ [Squelch status](/commands/SQ.md)
- SR [Reset](/commands/SR.md)
- SS [S-meter squelch](/commands/SS.md)
- TT [Transmit tone](/commands/TT.md)
- TX [Transmit](/commands/TX.md)
- TY [Radio Type](/commands/TY.md)
- UP [Emulates the Microphone Up Key](/commands/UP.md)
- VM [Memory/VFO](/commands/VM.md)
- 0M PROGRAM [Enters MCP programming mode](PROGRAMMING_MODE.md)
- 0G KENWOOD [Enters service mode](SERVICE_MODE.md)
