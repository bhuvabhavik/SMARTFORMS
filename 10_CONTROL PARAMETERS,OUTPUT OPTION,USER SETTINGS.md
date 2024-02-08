### uncomment and declare your own control and output parameters
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/68d5ba7b-2be8-4212-9fef-f8fd956beb8e)


![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/e1116754-c196-4ae2-9cea-7bc703b7d080)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/e38742b9-3642-4f94-89af-5afcff4cdec5)

## still not working? lets find it out WHY?

#### check setting > user profile > user data
## is there any output device there??
may be not 
but still its not taking our output device but its taking from there you know why????????
because
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/8119889a-6d1f-4484-8863-e3c6361b4948)
### because user setting is set to X as true, we are passing our device but still sap is considering sap user settings and in the user settings no device is there
## so the solution is to pass it to false.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/9b056a99-2945-468d-b80a-662213bd822b)
### so we need to override the sap user settings and pass it to false.
