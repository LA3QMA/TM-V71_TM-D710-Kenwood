# TM-V71 programming mode

Conventions used in this document:

- `>>>` indicates data sent to the radio
- `<<<` indicates data received from the radio
- All characters are listed explicitly, so
  `0M <space> PROGRAM <cr>` means to send the bytes
  `0M PROGRAM` followed by a carriage return
  (e.g., `30 4D 20 50 52 4F 47 52 41 4D 0D`).

## Enter programming mode

```
>>> 0M <space> PROGRAM <cr>
<<< 0M <cr>
```

Entering programming mode:

```
write:
30 4D 20 50 52 4F 47 52  41 4D 0D                 0M PROGRAM.
read:
30 4D 0D                                          0M.
```

You will see `PROG MCP` on the display, but if your code does not interact with the radio, the display will change to `PROG ERR`. You can still successfully read and write memory, but additional bits will be set in the response code to memory commands.

## Status response

In programming mode, the radio will acknowledge commands with a one byte status code.
This code does not* indicate that the command was unsuccessful; it simply acknowledges the command and provides information about the state of the radio.

### Successful response

If everything is successful, the radio will response with `0b00000110` (aka `0x06`). 

### Error response

If the radio is in an error state (e.g. because you took too long to interact with it), the radio will response with `0b00001111` (aka 0x0f).

## Exit programming mode

```
>>> E
<<< <status> <cr> <0x00>
```

Exiting programming mode:

```
write:
45                                                E
read:
06                                                .
read:
0D                                                .
read:
00                                                .
```

## Read memory

```
>>> R <addr_byte_1> <addr_byte_2> <len>
<<< W <addr_byte_1> <addr_byte_2> <len> <data>
>>> 0x06
<<< <status>
```

Reading four bytes from address `0x0`:

```
write:
52 00 00 04                                       R...
read:
57 00 00 04                                       W...
read:
00 4B 01 FF                                       .K..
write:
06                                                .
read:
06                                                .
```

Reading 16 bytes from address `0x1710`:

```
write:
00000000: 52 17 10 10                                       R...
read:
00000000: 57 17 10 10                                       W...
read:
00000000: F0 15 AB 08 00 00 A2 17  17 00 C0 27 09 00 FF FF  ...........'....
write:
00000000: 06                                                .
read:
00000000: 06                                                .
```

## Write memory

```
>>> W <addr_byte_1> <addr_byte_2> <len> <data...>
<<< <status>
```

Writing four bytes to address 0:

```
write:
57 00 00 04                                       W...
write:
00 4B 01 FF                                       .K..
read:
06                                                .
```
