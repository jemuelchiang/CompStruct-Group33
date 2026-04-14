# SUTD 50.002 Group 33 1D Project
## GRIDLOCK: Your goldfish memory won't cut it here

GridLock is a 3 by 3 grid memory game using Finite State Machine and Arithmetic Logic Unit, in Alchitry V2. <br><br>
In this single-player sequence memory game, players are given a 3x3 grid of buttons that challenges their pattern recognition and memory. Upon pressing any button, a single button lights up to start the sequence. After the player successfully mimics the sequence, the player gains 1 point and the system repeats the original sequence and appends a new input at the end. The winning condition is to successfully reach a score of 20 by memorizing 20 inputs. There is no room for error; one wrong press will end the game, and the player will have to start all over. <br><br>

*Add necessary components in Alchitry

### User Manual
- To "press" a button, flip io_led up. Flipping it up sends a high signal, flipping it back down does not do anything.
<br><br>
1. In IDLE (state debug 001), press any button to start
2. Sequence will be shown (state debug 010)
3. Mimic and input the shown sequence (state debug 011)
4. Every round, a random button input will be added at the end of the previous sequence
5. As the game progresses, the speed of which the sequence is being shown at will increase
6. Try to reach the max score of 20!
7. At Win or Lose, press any button to go back to IDLE

![Sim_User_Manual](https://github.com/user-attachments/assets/a2936057-2625-4e9a-9f88-68a0c3667a12)

### FSM Diagram
<img width="12444" height="6418" alt="FSM Diagram" src="https://github.com/user-attachments/assets/6cda02b9-e766-4b48-b4cc-4f29573a880e" />
https://lucid.app/lucidchart/6949639b-89a7-4360-8f60-d7a3c162ff72/edit?viewport_loc=-5447%2C-272%2C10669%2C4719%2C0_0&invitationId=inv_321be0d9-805e-40a1-a082-ed67cc1c8b59

### Datapath Diagram
<img width="2775" height="3731" alt="Datapath Diagram" src="https://github.com/user-attachments/assets/c4b99a36-1dd7-42b6-8e63-7d49ff33ed79" />
https://lucid.app/lucidchart/3e24ad66-47ec-4b0c-89d6-8986a44a39d0/edit?viewport_loc=-2721%2C-2223%2C5163%2C2600%2C0_0&invitationId=inv_608f2f5e-2be1-4f18-bdda-cf32c86dc1c6
