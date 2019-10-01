__Set/Read the memory channel__


Set the memory channel:

	ME p1, p2, p3, p4, p5, p6, p7, p8, p9, p10, p11, p12, p13, p14, p15, p16

Read the memory channel:

	ME xxx

Clear the memory channel:

  ME xxx,
	
Returns: memory channel number (3 digit)

|p|function|
|---|---|
|1|Memory channel number 3 digit
|2|RX frequency in Hz 10 digit. C clears the channel
|3|[RX step size](/tables/step_size.md)
|4|[Shift direction](/tables/shift.md)
|5|[Reverse](/tables/status.md)
|6|[Tone status](/tables/status.md)
|7|[CTCSS status](/tables/status.md)
|8|[DCS status](/tables/status.md)
|9|[Tone frequency](/tables/tone_ctcss.md)
|10|[CTCSS frequency](/tables/tone_ctcss.md)
|11|[DCS frequency](/tables/DCS.md)
|12|Offset frequency in Hz 8 digit
|13|[Mode](/tables/mode.md)
|14|TX frequency in Hz 10 digit.
|15|[TX step size](/tables/step_size.md)
|16|[Lock out](/tables/status.md)

# 800-1300MHz not possible to set
