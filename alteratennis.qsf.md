# Programmable-Devices


# -------------------------------------------------------------------------- #
#
# Copyright (C) 1991-2015 Altera Corporation. All rights reserved.
# Your use of Altera Corporation's design tools, logic functions 
# and other software and tools, and its AMPP partner logic 
# functions, and any output files from any of the foregoing 
# (including device programming or simulation files), and any 
# associated documentation or information are expressly subject 
# to the terms and conditions of the Altera Program License 
# Subscription Agreement, the Altera Quartus II License Agreement,
# the Altera MegaCore Function License Agreement, or other 
# applicable license agreement, including, without limitation, 
# that your use is for the sole purpose of programming logic 
# devices manufactured by Altera and sold by Altera or its 
# authorized distributors.  Please refer to the applicable 
# agreement for further details.
#
# -------------------------------------------------------------------------- #
#
# Quartus II 64-Bit
# Version 15.0.0 Build 145 04/22/2015 SJ Web Edition
# Date created = 12:13:39  March 09, 2017
#
# -------------------------------------------------------------------------- #
#
# Notes:
#
# 1) The default values for assignments are stored in the file:
#		alteratennis_assignment_defaults.qdf
#    If this file doesn't exist, see file:
#		assignment_defaults.qdf
#
# 2) Altera recommends that you do not modify this file. This
#    file is updated automatically by the Quartus II software
#    and any changes you make may be lost or overwritten.
#
# -------------------------------------------------------------------------- #


set_global_assignment -name FAMILY "Cyclone V"
set_global_assignment -name DEVICE 5CSEMA5F31C6
set_global_assignment -name TOP_LEVEL_ENTITY bouncing_square
set_global_assignment -name ORIGINAL_QUARTUS_VERSION 15.0.0
set_global_assignment -name PROJECT_CREATION_TIME_DATE "12:13:39  MARCH 09, 2017"
set_global_assignment -name LAST_QUARTUS_VERSION 15.0.0
set_global_assignment -name VHDL_FILE vga_control.vhd
set_global_assignment -name VHDL_FILE make_image1.vhd
set_global_assignment -name BDF_FILE bouncing_square.bdf
set_global_assignment -name PROJECT_OUTPUT_DIRECTORY output_files
set_global_assignment -name MIN_CORE_JUNCTION_TEMP 0
set_global_assignment -name MAX_CORE_JUNCTION_TEMP 85
set_global_assignment -name DEVICE_FILTER_PACKAGE FBGA
set_global_assignment -name DEVICE_FILTER_PIN_COUNT 896
set_global_assignment -name ERROR_CHECK_FREQUENCY_DIVISOR 256
set_global_assignment -name PARTITION_NETLIST_TYPE SOURCE -section_id Top
set_global_assignment -name PARTITION_FITTER_PRESERVATION_LEVEL PLACEMENT_AND_ROUTING -section_id Top
set_global_assignment -name PARTITION_COLOR 16764057 -section_id Top
set_location_assignment PIN_J14 -to blue[7]
set_instance_assignment -name IO_STANDARD "2.5 V" -to blue[7]
set_location_assignment PIN_G15 -to blue[6]
set_instance_assignment -name IO_STANDARD "2.5 V" -to blue[6]
set_location_assignment PIN_F15 -to blue[5]
set_instance_assignment -name IO_STANDARD "2.5 V" -to blue[5]
set_location_assignment PIN_H14 -to blue[4]
set_instance_assignment -name IO_STANDARD "2.5 V" -to blue[4]
set_location_assignment PIN_F14 -to blue[3]
set_instance_assignment -name IO_STANDARD "2.5 V" -to blue[3]
set_location_assignment PIN_H13 -to blue[2]
set_instance_assignment -name IO_STANDARD "2.5 V" -to blue[2]
set_location_assignment PIN_G13 -to blue[1]
set_instance_assignment -name IO_STANDARD "2.5 V" -to blue[1]
set_location_assignment PIN_B13 -to blue[0]
set_instance_assignment -name IO_STANDARD "2.5 V" -to blue[0]
set_location_assignment PIN_E11 -to green[7]
set_instance_assignment -name IO_STANDARD "2.5 V" -to green[7]
set_location_assignment PIN_F11 -to green[6]
set_instance_assignment -name IO_STANDARD "2.5 V" -to green[6]
set_location_assignment PIN_G12 -to green[5]
set_instance_assignment -name IO_STANDARD "2.5 V" -to green[5]
set_location_assignment PIN_G11 -to green[4]
set_instance_assignment -name IO_STANDARD "2.5 V" -to green[4]
set_location_assignment PIN_G10 -to green[3]
set_instance_assignment -name IO_STANDARD "2.5 V" -to green[3]
set_location_assignment PIN_H12 -to green[2]
set_instance_assignment -name IO_STANDARD "2.5 V" -to green[2]
set_location_assignment PIN_J10 -to green[1]
set_instance_assignment -name IO_STANDARD "2.5 V" -to green[1]
set_location_assignment PIN_J9 -to green[0]
set_instance_assignment -name IO_STANDARD "2.5 V" -to green[0]
set_location_assignment PIN_F10 -to nblank
set_instance_assignment -name IO_STANDARD "2.5 V" -to nblank
set_location_assignment PIN_C10 -to nsync
set_instance_assignment -name IO_STANDARD "2.5 V" -to nsync
set_location_assignment PIN_A11 -to pixel_clk
set_instance_assignment -name IO_STANDARD "2.5 V" -to pixel_clk
set_location_assignment PIN_F13 -to red[7]
set_instance_assignment -name IO_STANDARD "2.5 V" -to red[7]
set_location_assignment PIN_E12 -to red[6]
set_instance_assignment -name IO_STANDARD "2.5 V" -to red[6]
set_location_assignment PIN_D12 -to red[5]
set_instance_assignment -name IO_STANDARD "2.5 V" -to red[5]
set_location_assignment PIN_C12 -to red[4]
set_instance_assignment -name IO_STANDARD "2.5 V" -to red[4]
set_location_assignment PIN_B12 -to red[3]
set_instance_assignment -name IO_STANDARD "2.5 V" -to red[3]
set_location_assignment PIN_E13 -to red[2]
set_instance_assignment -name IO_STANDARD "2.5 V" -to red[2]
set_location_assignment PIN_C13 -to red[1]
set_instance_assignment -name IO_STANDARD "2.5 V" -to red[1]
set_location_assignment PIN_A13 -to red[0]
set_instance_assignment -name IO_STANDARD "2.5 V" -to red[0]
set_location_assignment PIN_D11 -to vsync
set_instance_assignment -name IO_STANDARD "2.5 V" -to vsync
set_location_assignment PIN_AF14 -to clock50MHz
set_location_assignment PIN_B11 -to hsync
set_global_assignment -name STRATIX_DEVICE_IO_STANDARD "2.5 V"
set_location_assignment PIN_W15 -to button_down
set_location_assignment PIN_Y16 -to button_up
set_location_assignment PIN_AA14 -to button_down_2
set_location_assignment PIN_AA15 -to button_up_2
set_instance_assignment -name PARTITION_HIERARCHY root_partition -to | -section_id Top
