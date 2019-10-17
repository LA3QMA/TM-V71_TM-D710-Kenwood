# TM-V71 service mode

Conventions used in this document:

- `>>>` indicates data sent to the radio
- `<<<` indicates data received from the radio
- All characters are listed explicitly, so
  `0G <space> KENWOOD <cr>` means to send the bytes
  `0G KENWOOD` followed by a carriage return
  (e.g., `30 47 20 4B 45 4E 57 4F  4F 44 0D`).

## Enter service mode

```
>>> 0G <space> KENWOOD <cr>
<<< 0G <cr>
```

Entering service mode:

```
write:
30 47 20 4B 45 4E 57 4F  4F 44 0D                 0G KENWOOD.
read:
30 47 0D                                          0G.
```

## Exit service mode

We have not yet discovered a mechanism for directly exiting service mode, but you can return to normal operation by entering and exiting programming mode.

1. [Enter programming mode](PROGRAMMING_MODE.md#enter-programming-mode)
1. [Exit programming mode](PROGRAMMING_MODE.md#exit-programming-mode)
