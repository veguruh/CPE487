# Lab 5 - Siren

The objective of this lab was to program an FPGA board to interact with a Pmod I2S digital-to-analog converter and generate different wailing noises. The program consists of the tone, wail, and siren modules. The tone module is responsible for generating the instantaneous pitch of the output signal. In the original file, it iterates through a 16-bit counter range to generate a sawtooth output. The wail module determines the upper and lower limits of the tone, as well as the speed at which the tone changes. Finally, the siren module is responsible for interacting with the JA port of the FPGA to output the signal.

## Changes Made for Modifications

### Change the Upper and Lower Tone Limits
In order to change the tone module from producing a triangle wave to instead a square wave, w1 and w2 were incorporated into the code to allow for the change in lower and upper tone limits. Likewise, the btn_press variable was incorporated in siren so that every time the button is pressed, the tone would then be changed as well since the variable is passed for use from siren to wail.
### Change the Wailing Speed
Changing the wailing speed was a matter of using the slide switches as input for the siren module. Each element of the wail_speed vector was changed from the constant (8,8) to the variable values between SW0-SW7.
### Add a Second Wail Instance to Drive the right Audio Channel
In siren_1.vhd, the two wail instances w1 and w2 were defined to distinguish the left and right audio channels. The upper and lower tone limits were inverted between the two instances, which made for starkly different sound outputs between the two.
