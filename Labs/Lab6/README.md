# Lab 6
 The objective of lab 6 was to program the FPGA board to run a pong game through a VGA display. The board used a 5 kΩ potentiometer to send input signals corresponding to the bat’s movement, which was programmed using the adc_if module to convert the analog input into a 12-bit digital signal to move the bat on the display. 

## Modifications

### Bat_n_ball
-	In the new file, every time the game begins the horizontal speed of the ball increases upon hitting the bat as seen when adding the ball_x_motion variable into the loop. The variable hit_count and dtop_dbl_hit were added to the mball process in order to account the number of times the ball hits the bat and to prevent a double hit of the ball on the bat, respectively. Whenever the ball hits the bat, the width of the bat(bat_w) decreases by 1 pixel and the hit_count increases by 1.
-	The variable hit_count was added to store the hit count that would be displayed on the 7-segment display.
### Pong.vhd
-	A cnt variable is implemented to generate the timing signals as the ball hits the bat every time and causes the ball to move faster.




