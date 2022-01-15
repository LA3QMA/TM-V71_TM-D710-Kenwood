# Memory Map

| Address         | Description                                                 |
|-----------------|-------------------------------------------------------------|
| 0x10            | Crossband repeat mode (1=on, 0=off)                         |
| 0x11            | Wireless remote mode  (1=on, 0=off)                         |
| 0x12            | Remote id (wireless remote access code)                     |
| 0x16            | Current PM channel (0-5)                                    |
| 0x17            | Key lock (0=disabled, 1=enabled)                            |
| 0x21            | PC port speed (0=9600, 1=19200, 2=38400, 3=57600)           |
| 0x30 - 0xCF     | DTMF Memory Codes (16 bytes * 10)                           |
| 0xD0 - 0xFF     | DTMF Memory Names (8 bytes * 10)                            |
| 0x120 - 0x16F   | EchoLink Memory Names (8 bytes * 10)                        |
| 0x190 - 0x1DF   | EchoLink Memory Codes (8 bytes * 10)                        |
| 0x170           | Repeater ID (12 characters)                                 |
| 0x200 - 0xC00   | [Programmable memory](#programmable-memory) (512 bytes * 6) |
| 0xE00           | Channel flags (2 bytes * 1000)                              |
| 0x1700 - 0x557F | [Channel memory](#vfo-settings) (16 bytes * 1000)           |
| 0x5800 - 0x773F | Channel names (8 bytes * 1000)                              |
| 0x77E0 - 0x782D | WX channel names                                            |
| 0x7D00 - 0x7d9f | Group names (16 bytes * 8 groups)                           |
| 0x7DA0          | Program memory names (16 bytes * 5 PMs)                     |

## VFO Settings

| Byte  | Description                             | Format notes
|-------|-----------------------------------------|----------------|
| 0-3   | RX Frequency                            | Freq * 1000000 |
| 4     | [RX Step size](tables/step_size.md)     |                |
| 5     | [Modulation](tables/mode.md)            |                |
| 6     | Bitfield                                |                |
|       | 7                                       | ???            |
|       | 4-6 tone/ctcss/dcs                      | 0b000 = none   |
|       |                                         | 0b100 = tone   |
|       |                                         | 0b010 = ctcss  |
|       |                                         | 0b001 = dcs    |
|       | 3 - reverse                             |                |
|       | 2 - split                               |                |
|       | 0-1 shift direction                     | 0x00 = simplex |
|       |                                         | 0x01 = up      |
|       |                                         | 0x10 = down    |
| 7     | [Tone frequency](tables/tone_ctcss.md)  |                |
| 8     | [CTCSS frequency](tables/tone_ctcss.md) |                |
| 9     | [DCS frequency](tables/dcs.md)          |                |
| 10-13 | tx offset                               | Freq * 1000000 |
|       | or tx frequency                         |                |
| 14    | [TX Step size](tables/step_size.md)     |                |

## Channel flags

Additional channel flags are stored in a pair of bytes starting at `0x0E00`.
If the channel is "deleted", both bytes are set to `0xff 0xff`.

The first byte indicates the band:

| Value | Band |
|-------|------|
| 05    | VHF  |
| 08    | UHF  |

Experimentation has shown that setting the high bit of the Band byte
will disable the channel, so it can be used as a disable.

The second byte is a bitfield:

| Bit | Description |
|-----|-------------|
| 0   | lockout     |
| 1   |             |
| 2   |             |
| 3   |             |
| 4   |             |
| 5   |             |
| 6   |             |
| 7   |             |

## Programmable memory

There are six programmable memory regions -- one used when PM is off, and then one for each of 5 PM channels. Each PM region is 512 bytes long.


| Offset | Description                                                            |
|--------|------------------------------------------------------------------------|
| 0x01   | Band A memory/vfo mode (0=vfo, 1=memory)                               |
| 0x02   | Band A selected frequency band (0=118MHz, 1=VHF, 2=220MHz, 3=340MHz, 4=UHF |
| 0x07   | Band A TX power (0=High, 1=Medium, 2=Low)                              |
| 0x09   | Band A S Meter Squelch (0=off, 1=on)                                   |
| 0x0D   | Band B memory/vfo mode  (0=vfo, 1=memory)                              |
| 0x0E   | Band B selected frequency band (0x05=VFH, 0x08=UHF)                    |
| 0x13   | Band B TX power  (0=High, 1=Medium, 2=Low)                             |
| 0x15   | Band B S Meter Squelch (0=off, 1=on)                                   |
| 0x2E   | Currently selected menu item                                           |
| 0x32   | PTT band (0=Band A, 1=Band B)                                          |
| 0x33   | Control band  (0=Band A, 1=Band B)                                     |
| 0x40   | Band A per-frequency-band [VFO settings](#vfo-settings) (16 bytes * 5) |
| 0x90   | Band B per-frequency-band [VFO settings](#vfo-settings) (16 bytes * 5) |
| 0xE0   | Power on message (12 bytes)                                            |
| 0xF0   | Group links (10 bytes)                                                 |
| 0x150  | Beep (0=off, 1=on)                                                     |
| 0x151  | Beep volume (0-6)                                                      |
| 0x175  | Data band (0=Band A, 1=Band B)                                         |
| 0x176  | Data speed (0=1200, 1=9600)                                            |
| 0x180  | Band mask A (0=mask, 1=use)                                            |
| 0x185  | Band mask B (0=mask, 1=use)                                            |

