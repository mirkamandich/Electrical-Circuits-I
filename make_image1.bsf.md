# Programmable-Devices


/*
WARNING: Do NOT edit the input and output ports in this file in a text
editor if you plan to continue editing the block that represents it in
the Block Editor! File corruption is VERY likely to occur.
*/
/*
Copyright (C) 1991-2015 Altera Corporation. All rights reserved.
Your use of Altera Corporation's design tools, logic functions 
and other software and tools, and its AMPP partner logic 
functions, and any output files from any of the foregoing 
(including device programming or simulation files), and any 
associated documentation or information are expressly subject 
to the terms and conditions of the Altera Program License 
Subscription Agreement, the Altera Quartus II License Agreement,
the Altera MegaCore Function License Agreement, or other 
applicable license agreement, including, without limitation, 
that your use is for the sole purpose of programming logic 
devices manufactured by Altera and sold by Altera or its 
authorized distributors.  Please refer to the applicable 
agreement for further details.
*/
(header "symbol" (version "1.1"))
(symbol
	(rect 16 16 248 192)
	(text "make_image1" (rect 5 0 60 12)(font "Arial" ))
	(text "inst" (rect 8 160 20 172)(font "Arial" ))
	(port
		(pt 0 32)
		(input)
		(text "vsync" (rect 0 0 25 12)(font "Arial" ))
		(text "vsync" (rect 21 27 46 39)(font "Arial" ))
		(line (pt 0 32)(pt 16 32)(line_width 1))
	)
	(port
		(pt 0 48)
		(input)
		(text "pixel_row[8..0]" (rect 0 0 56 12)(font "Arial" ))
		(text "pixel_row[8..0]" (rect 21 43 77 55)(font "Arial" ))
		(line (pt 0 48)(pt 16 48)(line_width 3))
	)
	(port
		(pt 0 64)
		(input)
		(text "pixel_column[9..0]" (rect 0 0 70 12)(font "Arial" ))
		(text "pixel_column[9..0]" (rect 21 59 91 71)(font "Arial" ))
		(line (pt 0 64)(pt 16 64)(line_width 3))
	)
	(port
		(pt 0 80)
		(input)
		(text "pushbuttom_top" (rect 0 0 63 12)(font "Arial" ))
		(text "pushbuttom_top" (rect 21 75 84 87)(font "Arial" ))
		(line (pt 0 80)(pt 16 80)(line_width 1))
	)
	(port
		(pt 0 96)
		(input)
		(text "pushbuttom_bottom" (rect 0 0 79 12)(font "Arial" ))
		(text "pushbuttom_bottom" (rect 21 91 100 103)(font "Arial" ))
		(line (pt 0 96)(pt 16 96)(line_width 1))
	)
	(port
		(pt 0 112)
		(input)
		(text "pushbuttom_top_2" (rect 0 0 74 12)(font "Arial" ))
		(text "pushbuttom_top_2" (rect 21 107 95 119)(font "Arial" ))
		(line (pt 0 112)(pt 16 112)(line_width 1))
	)
	(port
		(pt 0 128)
		(input)
		(text "pushbuttom_bottom_2" (rect 0 0 89 12)(font "Arial" ))
		(text "pushbuttom_bottom_2" (rect 21 123 110 135)(font "Arial" ))
		(line (pt 0 128)(pt 16 128)(line_width 1))
	)
	(port
		(pt 232 32)
		(output)
		(text "red[7..0]" (rect 0 0 33 12)(font "Arial" ))
		(text "red[7..0]" (rect 178 27 211 39)(font "Arial" ))
		(line (pt 232 32)(pt 216 32)(line_width 3))
	)
	(port
		(pt 232 48)
		(output)
		(text "green[7..0]" (rect 0 0 42 12)(font "Arial" ))
		(text "green[7..0]" (rect 169 43 211 55)(font "Arial" ))
		(line (pt 232 48)(pt 216 48)(line_width 3))
	)
	(port
		(pt 232 64)
		(output)
		(text "blue[7..0]" (rect 0 0 35 12)(font "Arial" ))
		(text "blue[7..0]" (rect 176 59 211 71)(font "Arial" ))
		(line (pt 232 64)(pt 216 64)(line_width 3))
	)
	(drawing
		(rectangle (rect 16 16 216 160)(line_width 1))
	)
)
