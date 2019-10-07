# Memory Map

| Address         | Description                                       |
|-----------------|---------------------------------------------------|
| 0x10            | crossband repeat mode (1=on, 0=off)               |
| 0x11            | wireless remote mode  (1=on, 0=off)               |
| 0x12            | remote id (wireless remote access code)           |
| 0x17            | Key lock (0=disabled, 1=enabled)                  |
| 0x21            | PC port speed (0=9600, 1=19200, 2=38400, 3=57600) |
| 0x30 - 0x3F     | DTMF Memory Code CH0 - Menu 301                   |
| 0x40 - 0x4F     | DTMF Memory Code CH1 - Menu 301                   |
| 0x50 - 0x5F     | DTMF Memory Code CH2 - Menu 301                   |
| 0x60 - 0x6F     | DTMF Memory Code CH3 - Menu 301                   |
| 0x70 - 0x7F     | DTMF Memory Code CH4 - Menu 301                   |
| 0x80 - 0x8F     | DTMF Memory Code CH5 - Menu 301                   |
| 0x90 - 0x9F     | DTMF Memory Code CH6 - Menu 301                   |
| 0xA0 - 0xAF     | DTMF Memory Code CH7 - Menu 301                   |
| 0xB0 - 0xBF     | DTMF Memory Code CH8 - Menu 301                   |
| 0xC0 - 0xCF     | DTMF Memory Code CH9 - Menu 301                   |
| 0xD0 - 0xD7     | DTMF Memory Name CH0 - Menu 301                   |
| 0xD8 - 0xDF     | DTMF Memory Name CH1 - Menu 301                   |
| 0xE0 - 0xE7     | DTMF Memory Name CH2 - Menu 301                   |
| 0xE8 - 0xEF     | DTMF Memory Name CH3 - Menu 301                   |
| 0xF0 - 0xF7     | DTMF Memory Name CH4 - Menu 301                   |
| 0xF8 - 0xFF     | DTMF Memory Name CH5 - Menu 301                   |
| 0x100 - 0x107   | DTMF Memory Name CH6 - Menu 301                   |
| 0x108 - 0x10F   | DTMF Memory Name CH7 - Menu 301                   |
| 0x110 - 0x117   | DTMF Memory Name CH8 - Menu 301                   |
| 0x118 - 0x11F   | DTMF Memory Name CH9 - Menu 301                   |
| 0x170           | Repeater ID (12 characters)                       |
| 0x201           | Band A memory/vfo mode (0=vf0, 1=memory)          |
| 0x202           | Band A selected frequency band                    |
| 0x20D           | Band B memory/vfo mode                            |
| 0x20E           | Band B selected frequency band                    |
| 0x215           | S Meter Squelch                                   |
| 0x22E           | Currently selected menu item                      |
| 0x2e0           | Poweron message                                   |
| 0x232           | PTT band                                          |
| 0x233           | Control band                                      |
| 0x250           | Band A vfo setting (16 bytes)                     |
| 0x2C0           | Band B vfo setting (16 bytes)                     |
| 0x350           | beep                                              |
| 0x351           | beep volume                                       |
| 0xE00           | Channel flags (2 bytes * 1000)                    |
| 0x1700 - 0x557F | Channel memory (16 bytes * 1000)                  |
| 0x5800 - 0x773f | Channel names (8 bytes * 1000)                    |
| 0x77e0 - 0x782D | WX channel names                                  |
| 0x7d00 - 0x7d9f | Group names (16 bytes * 8 groups)                 |
| 0x7da0          | Program memory names (16 bytes * 5 PMs)           |

## VFO format

| Byte  | Description         | Format notes
|-------|---------------------|----------------|
| 0-3   | RX Frequency        | Freq * 1000000 |
| 4     | Step size           |                |
| 5     | Modulation          |                |
| 6     | Bitfield            |                |
|       | 7                   | ???            |
|       | 4-6 tone/ctcss/dcs  | 0b000 = none   |
|       |                     | 0b100 = tone   |
|       |                     | 0b010 = ctcss  |
|       |                     | 0b001 = dcs    |
|       | 3 - reverse         |                |
|       | 2 - split           |                |
|       | 0-1 shift direction | 0x00 = simplex |
|       |                     | 0x01 = up      |
|       |                     | 0x10 = down    |
| 7     | tone frequency      |                |
| 8     | ctcss frequency     |                |
| 9     | dcs frequency       |                |
| 10-13 | tx offset           | Freq * 1000000 |
|       | or tx frequency     |                |


## Channel entry format

| Byte  | Description         | Format notes
|-------|---------------------|----------------|
| 0-3   | RX Frequency        | Freq * 1000000 |
| 4     | Step size           |                |
| 5     | Modulation          |                |
| 6     | Bitfield            |                |
|       | 7                   | ???            |
|       | 4-6 tone/ctcss/dcs  | 0b000 = none   |
|       |                     | 0b100 = tone   |
|       |                     | 0b010 = ctcss  |
|       |                     | 0b001 = dcs    |
|       | 3 - reverse         |                |
|       | 2 - split           |                |
|       | 0-1 shift direction | 0x00 = simplex |
|       |                     | 0x01 = up      |
|       |                     | 0x10 = down    |
| 7     | tone frequency      |                |
| 8     | ctcss frequency     |                |
| 9     | dcs frequency       |                |
| 10-13 | tx offset           | Freq * 1000000 |
|       | or tx frequency     |                |
| 14    | tx step size        |                |

## Channel flags

Additional channel flags are stored in a pair of bytes starting at `0x0E00`.
If the channel is "deleted", both bytes are set to `0xff 0xff`.

The first byte indicates the band:

| Value | Band |
|-------|------|
| 05    | VHF  |
| 08    | UHF  |

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
