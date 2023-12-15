# OperationBotFinal
Code for the ME35 final project- a robot that can autonomously retrieve a piece from the board game Operation.

#Computer files
The file finalClassMain.py is the main file used by the computer. It initializes and facilitates the image processing class, and uses the output to manage a state machine for the arm as well as send messages to the Pico. The state machine controls the behavior of the arm by switching between four possible options: Searching, Moving, Zeroing, and Found. Searching is when the camera is locating the position of the piece, Moving is when the arm is swinging out to the identified location, Zeroing is when the arm (hopefully holding the piece) moves to a preset position to see if the piece moves with it, and Found is the final state indicating a succesful removal of the piece. During normal operation, the robot cycles through the first three stages until the zeroing check is complete.

CameraManager.py is a class made to handle all the image processing using the openCV library. It's primary purpose is to map the contours of a specific color (light blue), identify the three biggest blobs by area, locate their centroids, and return those positions. These positions are returned to finalClassMain so the robot can decide it's next move.
