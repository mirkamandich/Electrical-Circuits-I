# Programmable-Devices


-- Generate the image: square ball moving up and down in the center of the screen
library ieee;
use ieee.std_logic_1164.all;
USE ieee.numeric_std.all; 

entity make_image1 is
	port(
		vsync:  in std_logic;
		pixel_row:  in integer range 0 to 480; 
		pixel_column: in integer range 0 to 640;
		pushbuttom_top, pushbuttom_bottom: in STD_LOGIC;
		red, green, blue: out std_logic_vector(7 downto 0));
end;
architecture image of make_image1 is

	SIGNAL ball_on, wall_on, paddle_on: STD_LOGIC;
	SIGNAL objects: STD_LOGIC_VECTOR(2 DOWNTO 0);
	-------------
	SIGNAL size : 			integer range 0 to 25;  
	SIGNAL ball_y_motion: integer range -20 to 10; 
	SIGNAL ball_y_pos: 	 integer range -20 to 490; 
	SIGNAL ball_x_motion: integer range -20 to 10;
	SIGNAL ball_x_pos:    integer range -10 to 650; 
	-------------
	CONSTANT bottom_of_screen: integer := 480;
	CONSTANT top_of_screen: integer := 1;
	CONSTANT left_of_screen: integer := 2; 
	CONSTANT right_of_screen: integer := 640;
	CONSTANT frame_thickness: integer := 40;
	-------------
	CONSTANT paddle_width: integer := 10;
	CONSTANT paddle_height: integer := 30;

	SIGNAL paddle_x_left, paddle_x_right: integer range 5 to 200; 
	SIGNAL paddle_y_bottom, paddle_y_top: integer range 30 to 460; 
	SIGNAL move_paddle: integer range 0 to 10;
	--------------
	TYPE my_rom is array (0 to 20) of std_logic_vector (0 to 20);
	CONSTANT round_shape: my_rom :=( "000000000111000000000",
												"000000001111100000000",
												"000000011111110000000",
												"000000111111111000000",
												"000001111111111100000",
												"000011111111111110000",
												"000111111111111111000",
												"001111111111111111100",
												"011111111111111111110",
												"111111111111111111111",
												"111111111111111111111",
												"111111111111111111111",
												"011111111111111111110",
												"001111111111111111100",
												"000111111111111111000",
												"000011111111111110000",
												"000001111111111100000",
												"000000111111111000000",
												"000000011111110000000",
												"000000001111100000000",
												"000000000111000000000" );
BEGIN 
	paddle_x_left <= frame_thickness + left_of_screen + 1; 
	paddle_x_right <= paddle_x_left + paddle_width;
	paddle_y_bottom <= paddle_y_top + paddle_height;
	
	size <= round_shape'length-1;  		
	
	objects <= ball_on&wall_on&paddle_on;
	
	setcolor:  PROCESS (objects)
		BEGIN
			CASE objects IS
				WHEN "100" =>
					red <=  (OTHERS => '1');  -- make the ball red
					green <= (OTHERS => '0'); -- turn off green when displaying ball
					blue  <= (OTHERS => '0'); -- turn off blue when displaying ball
				WHEN "010" =>
					red <=  (OTHERS => '0');  -- make the ball red
					green <= (OTHERS => '1'); -- turn off green when displaying ball
					blue  <= (OTHERS => '0'); -- turn off blue when displaying ball
				WHEN "001" =>
					red <=  (OTHERS => '0');  -- make the ball red
					green <= (OTHERS => '0'); -- turn off green when displaying ball
					blue  <= (OTHERS => '1'); -- turn off blue when displaying ball
				WHEN OTHERS =>
					red <=  (OTHERS => '1');  -- the background will be white (all colors set to 1 makes white)
					green <= (OTHERS => '1');
					blue  <= (OTHERS => '1');			
			END CASE;
		END PROCESS;
------------------------------------
paddle_motion: PROCESS --check if the pushbuttons are pressed
-- KEY[0] button_up Pin AA15 / KEY[1] button_down Pin AA14
BEGIN
WAIT UNTIL (vsync'event AND vsync = '1');		         		
		IF pushbuttom_top = '0' THEN 
			paddle_y_top <= paddle_y_top + 4;
		ELSIF 
			pushbuttom_bottom = '0' THEN
			paddle_y_top <= paddle_y_top - 4;
		END IF;					 
	END PROCESS;	

------------------------------------
	--check if pixel scanned in located within the square ball
	check_ball:  PROCESS (ball_x_pos, ball_y_pos, pixel_column, pixel_row, size)
   BEGIN	                                
		IF ((pixel_column >= ball_x_pos) AND (pixel_column <= ball_x_pos + size) AND (pixel_row >= ball_y_pos) AND (pixel_row <= ball_y_pos + size))
      THEN
			ball_on <= round_shape(pixel_row - ball_y_pos)(pixel_column - ball_x_pos);
			--ball_on <= '1';						
 		ELSE
			ball_on <= '0';
		END IF;
	END PROCESS;
--------------------------------

	check_paddle:  PROCESS (pixel_column, pixel_row)
   BEGIN	                                
		IF ((pixel_column >= paddle_x_left) and (pixel_column <= paddle_x_right) and (pixel_row >= paddle_y_top) and (pixel_row <= paddle_y_bottom))
      THEN
			paddle_on <= '1';
 		ELSE
			paddle_on <= '0';
		END IF;
	END PROCESS;
	
--------------------------------
	--check if pixel scanned in located within the square ball
	check_wall:  PROCESS (pixel_column, pixel_row)
   BEGIN	                                
		IF ( ((pixel_column >= left_of_screen) AND (pixel_column <= left_of_screen + frame_thickness)) OR 
		((pixel_column >= right_of_screen - frame_thickness) AND (pixel_column <= right_of_screen)) OR
		((pixel_row >= top_of_screen) AND (pixel_row <= top_of_screen + frame_thickness)) OR
		((pixel_row >= bottom_of_screen - frame_thickness) AND (pixel_row <= bottom_of_screen)) )
      THEN
			wall_on <= '1';
 		ELSE
			wall_on <= '0';
		END IF;
	END PROCESS;
------------------------------------	
	--update position of ball once every screen refresh cycle
	x_motion: PROCESS		
	BEGIN				
		WAIT UNTIL (vsync'event AND vsync = '1');		         		
		IF (ball_x_pos + size) >= right_of_screen - frame_thickness  THEN	  --reached right of monitor    			
			ball_x_motion <= - 3;			                 -- start moving up by 1 pixel
		ELSIF 
			ball_x_pos <= left_of_screen + frame_thickness THEN	 		     -- reached left of monitor   	     	 		
			ball_x_motion <= 2;                         -- start moving down by 1 pixel
		END IF;					
		ball_x_pos <= ball_x_pos + ball_x_motion;		--compute next position in the x-axis 
	END PROCESS;	
	
	y_motion: PROCESS			
	BEGIN				
		WAIT UNTIL (vsync'event AND vsync = '1');		         		
		IF (ball_y_pos + size) >= bottom_of_screen - frame_thickness  THEN	  --reached bottom of monitor    			
			ball_y_motion <= - 2;			                 -- start moving up by 1 pixel
		ELSIF 
			ball_y_pos <= top_of_screen + frame_thickness THEN	 		     -- reached top of monitor   	     	 		
			ball_y_motion <= 2;                         -- start moving down by 1 pixel
		END IF;					
		ball_y_pos <= ball_y_pos + ball_y_motion;		--compute next position in the y-axis 
	END PROCESS;
END;
