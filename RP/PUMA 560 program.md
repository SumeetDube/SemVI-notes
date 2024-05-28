![[Pasted image 20240514150020.png]]
```
; Program to unload a part from Machine 1 and load it onto Machine 2
; Define locations
DEF P1 = XYZWPR(150, 250, 0, 0, 90, 0) ; Machine 1 location
DEF P2 = XYZWPR(150, 250, 50, 0, 90, 0) ; Machine 2 location
DEF P1_APP = XYZWPR(150, 350, 0, 0, 90, 0) ; Approach point for Machine 1
DEF P2_APP = XYZWPR(150, 350, 50, 0, 90, 0) ; Approach point for Machine 2

; Set speeds
SPEED = 30 IN/SEC ; Default speed
APPRO_SPEED = 10 IN/SEC ; Approach speed

; Main program
SIGNAL 105 ; Set input signal at port 105 to trigger the cycle

; Unload from Machine 1
APPRO P1_APP, APPRO_SPEED ; Approach Machine 1
MOVET P1, APPRO_SPEED ; Move to Machine 1
GRASP 1 ; Close gripper to pick up the part
MOVET P1_APP, APPRO_SPEED ; Move away from Machine 1

; Load onto Machine 2
APPRO P2_APP, APPRO_SPEED ; Approach Machine 2
MOVET P2, APPRO_SPEED ; Move to Machine 2
GRASP 0 ; Open gripper to release the part
MOVET P2_APP, APPRO_SPEED ; Move away from Machine 2

; Return to home position
HOME ; Move to the home position

END ; End of program
```
![[Pasted image 20240514150052.png]]
![[Pasted image 20240514224356.png]]