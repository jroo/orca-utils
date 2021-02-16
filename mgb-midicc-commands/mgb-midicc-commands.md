# Controlling mGB with Orca 
## MIDI CC Commands  

Reference table for sending [Orca](https://github.com/hundredrabbits/Orca) MIDI CC messages to control [mGB](https://github.com/trash80/mGB)

Be sure to set your CC offset in Orca to zero with the `cc:0` command. If you don't do this, commands will be sent to `CC64` and above. In order to send a sustain command on CC64, you'll need to set the offset back to 64 with the `cc:64` command.

Messages are case insensitive. `!01R` sends the same message as `!01r` 

Limitations:
- Orca can't send all 128 possible values for PU1, CC03 Pitch Sweep 
- There doesn't seem to be a way, to turn off both L and R channels via the `Pan` control (`CC10`)

| PU1 MIDI CH1              | PU1 MIDI CH2              | WAV MIDI CH3              | NOISE MIDI CH4     | 
| -------------             | -------------             | -------------             | -------------      |
|                           |                           |                           |                    |
| **CC01 Pulse Width**      | **CC01 Pulse Width**      | **CC01 Shape Select**     | **N/A**            |
| `!010` - 12.5%            | `!110` - 12.5%            | `!210` - triangle         |                    |
| `!019` - 25%              | `!119` - 25%              | `!212` - sine             |                    | 
| `!01i` - 50%              | `!11i` - 50%              | `!215` - saw              |                    | 
| `!01r` - 75%              | `!11r` - 75%              | `!270` - saw 2            |                    | 
|                           |                           | `!219` - square 0%        |                    |
|                           |                           | `!21b` - square 12.5%     |                    |
|                           |                           | `!21d` - square 25%       |                    |
|                           |                           | `!21g` - square 50%       |                    |
|                           |                           | `!21i` - mGB wave 0       |                    |
|                           |                           | `!21k` - mGB wave 1       |                    |
|                           |                           | `!21m` - mGB wave 2       |                    |
|                           |                           | `!21o` - mGB wave 3       |                    |
|                           |                           | `!21r` - mGB wave 4       |                    |
|                           |                           | `!21t` - mGB wave 5       |                    |
|                           |                           | `!21v` - mGB wave 6       |                    |
|                           |                           | `!21x` - mGB wave 7       |                    |
|                           |                           |                           |                    |
| **CC02 Envelope**         |**CC02 Envelope**          | **CC02 Shape Offset**     | **CC02 Envelope**  |
| `!020` - step 1           |`!120` - step 1            | `!220` - 00               | `!320` - step 1    |
| `!022` - step 2           |`!122` - step 2            | `!221` - 01               | `!322` - step 2    |
| `!025` - step 3           |`!125` - step 3            | `!222` - 02               | `!325` - step 3    |
| `!027` - step 4           |`!127` - step 4            | `!224` - 04               | `!327` - step 4    |
| `!029` - step 5           |`!129` - step 5            | `!225` - 05               | `!329` - step 5    |
| `!02b` - step 6           |`!12b` - step 6            | `!226` - 06               | `!32b` - step 6    |
| `!02d` - step 7           |`!12d` - step 7            | `!228` - 07               | `!32d` - step 7    |
| `!02g` - step 8           |`!12g` - step 8            | `!229` - 08               | `!32g` - step 8    |
| `!02i` - step 9           |`!12i` - step 9            | `!22a` - 09               | `!32i` - step 9    |
| `!02k` - step 10          |`!12k` - step 10           | `!22b` - 0A               | `!32k` - step 10   |
| `!02m` - step 11          |`!12m` - step 11           | `!22c` - OB               | `!32m` - step 11   |
| `!02o` - step 12          |`!12o` - step 12           | `!22d` - OC               | `!32o` - step 12   |
| `!02r` - step 13          |`!12r` - step 13           | `!22f` - OD               | `!32r` - step 13   |
| `!02t` - step 14          |`!12t` - step 14           | `!22g` - OE               | `!32t` - step 14   |
| `!02v` - step 15          |`!12v` - step 15           | `!22h` - OF               | `!32v` - step 15   |
| `!02x` - step 16          |`!12x` - step 16           | `!22i` - 10               | `!32x` - step 16   |
|                           |                           | `!22j` - 11               |                    | 
|                           |                           | `!22k` - 12               |                    | 
|                           |                           | `!22l` - 13               |                    | 
|                           |                           | `!22m` - 14               |                    | 
|                           |                           | `!22n` - 15               |                    | 
|                           |                           | `!22o` - 16               |                    | 
|                           |                           | `!22q` - 17               |                    | 
|                           |                           | `!22r` - 18               |                    | 
|                           |                           | `!22s` - 19               |                    | 
|                           |                           | `!22t` - 1A               |                    | 
|                           |                           | `!22u` - 1B               |                    | 
|                           |                           | `!22v` - 1C               |                    | 
|                           |                           | `!22w` - 1D               |                    | 
|                           |                           | `!22x` - 1E               |                    | 
|                           |                           | `!22y` - 1F               |                    | 
| **CC03 Pitch Sweep**      | **N/A**                   | **CC03 Pitch Sweep Speed**|**N/A**             |
| `!030` - 00               |                           | `!230` - 0                |                    | 
| `!031` - 04               |                           | `!232` - 1                |                    | 
| `!032` - 08               |                           | `!235` - 2                |                    | 
| `!033` - 0B               |                           | `!237` - 3                |                    | 
| `!034` - 0F               |                           | `!239` - 4                |                    | 
| `!035` - 13               |                           | `!23b` - 5                |                    | 
| `!036` - 16               |                           | `!23d` - 6                |                    | 
| `!037` - 1A               |                           | `!23g` - 7                |                    | 
| `!038` - 1E               |                           | `!23i` - 8                |                    | 
| `!039` - 21               |                           | `!23k` - 9                |                    | 
| `!03a` - 25               |                           | `!23m` - A                |                    | 
| `!03b` - 28               |                           | `!23o` - B                |                    | 
| `!03c` - 2C               |                           | `!23r` - C                |                    | 
| `!03d` - 30               |                           | `!23t` - D                |                    | 
| `!03e` - 33               |                           | `!23v` - E                |                    | 
| `!03f` - 37               |                           | `!23x` - F                |                    | 
| `!03g` - 3B               |                           |                           |                    | 
| `!03h` - 3E               |                           |                           |                    | 
| `!03i` - 42               |                           |                           |                    | 
| `!03j` - 45               |                           |                           |                    | 
| `!03k` - 49               |                           |                           |                    | 
| `!03l` - 4D               |                           |                           |                    | 
| `!03m` - 50               |                           |                           |                    | 
| `!03n` - 54               |                           |                           |                    | 
| `!03o` - 58               |                           |                           |                    | 
| `!03p` - 5B               |                           |                           |                    | 
| `!03q` - 5F               |                           |                           |                    | 
| `!03r` - 62               |                           |                           |                    | 
| `!03s` - 66               |                           |                           |                    | 
| `!03t` - 6A               |                           |                           |                    | 
| `!03u` - 6D               |                           |                           |                    | 
| `!03v` - 71               |                           |                           |                    | 
| `!03w` - 75               |                           |                           |                    | 
| `!03x` - 78               |                           |                           |                    | 
| `!03y` - 7C               |                           |                           |                    | 
| `!03z` - 7F               |                           |                           |                    | 
|                           |                           |                           |                    |
| **CC04 Pitch Bend Range** | **CC04 Pitch Bend Range** | **CC04 Pitch Bend Range** |**N/A**             |  
| `!040` - 00               |  `!140` - 00              |  `!240` - 00              |                    |  
| `!041` - 04               |  `!141` - 04              |  `!241` - 04              |                    |  
| `!042` - 08               |  `!142` - 08              |  `!242` - 08              |                    |  
| `!043` - 0B               |  `!143` - 0B              |  `!243` - 0B              |                    |  
| `!044` - 0F               |  `!144` - 0F              |  `!244` - 0F              |                    |  
| `!045` - 13               |  `!145` - 13              |  `!245` - 13              |                    |  
| `!046` - 16               |  `!146` - 16              |  `!246` - 16              |                    |  
| `!047` - 1A               |  `!147` - 1A              |  `!247` - 1A              |                    |  
| `!048` - 1E               |  `!148` - 1E              |  `!248` - 1E              |                    |  
| `!049` - 21               |  `!149` - 21              |  `!249` - 21              |                    |  
| `!04a` - 25               |  `!14a` - 25              |  `!24a` - 25              |                    |  
| `!04b` - 28               |  `!14b` - 28              |  `!24b` - 28              |                    |  
| `!04c` - 2C               |  `!14c` - 2C              |  `!24c` - 2C              |                    |  
| `!04d` - 30               |  `!14d` - 30              |  `!24d` - 30              |                    |  
| `!04e` - 33               |  `!14e` - 33              |  `!24e` - 33              |                    |  
| `!04f` - 37               |  `!14f` - 37              |  `!24f` - 37              |                    |  
| `!04g` - 3B               |  `!14g` - 3B              |  `!24g` - 3B              |                    |  
| `!04h` - 3E               |  `!14h` - 3E              |  `!24h` - 3E              |                    |  
| `!04i` - 42               |  `!14i` - 42              |  `!24i` - 42              |                    |
| `!04j` - 45               |  `!14j` - 45              |  `!24j` - 45              |                    |
| `!04k` - 49               |  `!14k` - 49              |  `!24k` - 49              |                    |
| `!04l` - 4D               |  `!14l` - 4D              |  `!24l` - 4D              |                    |
| `!04m` - 50               |  `!14m` - 50              |  `!24m` - 50              |                    |
| `!04n` - 54               |  `!14n` - 54              |  `!24n` - 54              |                    |
| `!04o` - 58               |  `!14o` - 58              |  `!24o` - 58              |                    |
| `!04p` - 5B               |  `!14p` - 5B              |  `!24p` - 5B              |                    |
| `!04q` - 5F               |  `!14q` - 5F              |  `!24q` - 5F              |                    |
| `!04r` - 62               |  `!14r` - 62              |  `!24r` - 62              |                    |
| `!04s` - 66               |  `!14s` - 66              |  `!24s` - 66              |                    |
| `!04t` - 6A               |  `!14t` - 6A              |  `!24t` - 6A              |                    |
| `!04u` - 6D               |  `!14u` - 6D              |  `!24u` - 6D              |                    |
| `!04v` - 71               |  `!14v` - 71              |  `!24v` - 71              |                    |
| `!04w` - 75               |  `!14w` - 75              |  `!24w` - 75              |                    |
| `!04x` - 78               |  `!14x` - 78              |  `!24x` - 78              |                    |
| `!04y` - 7C               |  `!14y` - 7C              |  `!24y` - 7C              |                    |
| `!04z` - 7F               |  `!14z` - 7F              |  `!24z` - 7F              |                    |
| **CC05 Preset**           | **CC05 Preset**           | **CC05 Preset**           | **CC05 Preset**    |
| `!050` - preset 0         | `!150` - preset 0         |  `!250` - preset 0        | `!350` - preset 0  |
| `!052` - preset 1         | `!152` - preset 1         |  `!252` - preset 1        | `!352` - preset 1  |
| `!055` - preset 2         | `!155` - preset 2         |  `!255` - preset 2        | `!355` - preset 2  |
| `!057` - preset 3         | `!157` - preset 3         |  `!257` - preset 3        | `!357` - preset 3  |
| `!059` - preset 4         | `!159` - preset 4         |  `!259` - preset 4        | `!359` - preset 4  |
| `!05b` - preset 5         | `!15b` - preset 5         |  `!25b` - preset 5        | `!35b` - preset 5  |
| `!05d` - preset 6         | `!15d` - preset 6         |  `!25d` - preset 6        | `!35d` - preset 6  |
| `!05g` - preset 7         | `!15g` - preset 7         |  `!25g` - preset 7        | `!35g` - preset 7  |
| `!05i` - preset 8         | `!15i` - preset 8         |  `!25i` - preset 8        | `!35i` - preset 8  |
| `!05k` - preset 9         | `!15k` - preset 9         |  `!25k` - preset 9        | `!35k` - preset 9  |
| `!05m` - preset A         | `!15m` - preset A         |  `!25m` - preset A        | `!35m` - preset A  |
| `!05o` - preset B         | `!15o` - preset B         |  `!25o` - preset B        | `!35o` - preset B  |
| `!05r` - preset C         | `!15r` - preset C         |  `!25r` - preset C        | `!35r` - preset C  |
| `!05t` - preset D         | `!15t` - preset D         |  `!25t` - preset D        | `!35t` - preset D  |
| `!05v` - preset E         | `!15v` - preset E         |  `!25v` - preset E        | `!35v` - preset E  |
| `!05x` - preset F         | `!15x` - preset F         |  `!25x` - preset F        | `!35x` - preset F  |
| **CC10 Pan**              | **CC10 Pan**              | **CC10 Pan**              | **CC10 Pan**       |
| `!0a0` - L                | `!1a0` - L                | `!2a0` - L                | `!3a0` - L         |
| `!0a9` - LR               | `!1a9` - LR               | `!2a9` - LR               | `!3a9` - LR        |
| `!0ar` - R                | `!1ar` - R                | `!2ar` - R                | `!3ar` - R         |
| **CC64 Sustain**          | **CC64 Sustain**          | **CC64 Sustain**          | **CC64 Sustain**   | 
| `!00i` - sustain*         | `!10i` - sustain *        | `!20i` - sustain *        | `!30i` - sustain*  |      

* **CC64** is used for the sustain pedal. You will need to shift the CC offset to 64 (`cc:64`) in Orca in order to send a sustain message. Once the offset is in place, you will send the command to channel 0.
