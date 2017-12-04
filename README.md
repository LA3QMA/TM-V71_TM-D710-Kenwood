# TM-V71 and TM-D710(G) Kenwood - PC RIG control commands
RIG control commands for the Kenwood TM-V71 and TM-D710(G)

Reverse engineered commands for the TM-V71 and TM-D710(G).

Thanks to: LA8OKA, W6GPS and WM8S for helping.

Based on rev.11 02 april 2009

__Please report any errors as this has been converted from my old documents.__

https://groups.yahoo.com/neo/groups/TM-D710_TM-V71

Available control commands for the **display unit**:

- BL	[Backlight status](/commands/BL.md) (Not TH-D710G)
- TN	[TNC status](/commands/TN.md)
- CS	[Callsign](/commands/CS.md)
- TC	[TNC controll mode](/commands/TC.md)
- TS	[TNC controll mode 2](/commands/TS.md)
- ID	[Radio Model](/commands/ID.md)
- AE	[Display serialnumber](/commands/AE.md) * Does only display giberish *
- TY	[Display Type](/commands/TY.md)
- RT	[Time](/commands/RT.md)
- GT	[Internal GPS](/commands/GT.md) Returns N if internal GPS is not on
- GP	[Internal GPS - TM-D710G](/commands/GP.md)
- BE	[Enable/disable BCON - TMD710G](/commands/BE.md) **When APRS is enabled**
- SR	[Reset](/commands/SR.md)
- PROGRAM		[0M PROGRAM : Enters MCP programming mode](/commands/0M_PROGRAM.md) (Command is: ZERO MIKE space PROGRAM)

Available control commands for the **main unit**:

- ID	[Radio Model](/commands/ID.md)
- AE	[Radio serialnumber](/commands/AE.md)
- FV	[Firmware version](/commands/FV.md)
- TY	[Radio Type](/commands/TY.md)
- DL	[Dual Band Mode/Single Band Mode](/commands/DL.md)
- MR	[Memory channel](/commands/MR.md)
- ME	[Memory channel, frequency, offset etc](/commands/ME.md)
- FO	[VFO channel](/commands/FO.md)
- BC	[PTT and CTRL Band](/commands/BC.md)
- VM	[Memory/VFO](/commands/VM.md)
- DW	[Emulates the Microphone Down Key](/commands/DW.md)
- UP	[Emulates the Microphone Up Key](/commands/UP.md)
- PC	[Output power](/commands/PC.md)
- SQ	[Squelch status](/commands/SQ.md)
- BY	[Squelch open/closed](/commands/BY.md)
- RX	[Receive](/commands/RX.md)
- TX	[Transmit](/commands/TX.md)
- BT	[Burst tone](/commands/BT.md)
- AS	[Reverse](/commands/AS.md)
- SR	[Reset](/commands/SR.md)
- CC	[Call channel](/commands/CC.md)
- LK	[Lock](/commands/LK.md)
- PV	[Programmable VFO](/commands/PV.md)
- MN	[Memory name](/commands/MN.md)
- MS	[Power on message](/commands/MS.md)
- TT	[Transmit tone](/commands/TT.md)
- CD	[Togle between memory name and channel number](/commands/CD.md)
- DM	[DTMF memory](/commands/DM.md)
- SS	[S-meter squelch](/commands/SS.md)
- DT	[DTMF](/commands/DT.md)
- MU	[Menu](/commands/MU.md)
- PROGRAM		[0M PROGRAM : Enters MCP programming mode](/commands/0M_PROGRAM.md) (Command is: ZERO MIKE space PROGRAM)
- SERVICE	[0G KENWOOD : Enters service mode](/commands/0G_KENWOOD.md) (Command is: ZERO GOLF space KENWOOD)
