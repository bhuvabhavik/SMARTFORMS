# OUTPUT AS PDF

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/3ebdf95b-9655-4855-8ef9-0a5ee7c1c598)

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/7c48d3cd-fc39-4aa5-8fb5-96f4dc7d291c)
### We have to pass GETOTF to true if we want the output in text format

### in the joboutput info we have the internal table OTF Data
### there we will get the output
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/48bac293-b163-45d5-9a6f-eed3eb2f7706)

### once we will get the text format we can convert it to pdf format
## so lets work on our first step
### so we will pass getotf to X
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/f4042dc6-106f-41f1-99ff-f03d4401c3b1)
### and it will return the output in job_output_info so we will simply declare the variable there.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/50ed5205-4c5c-4978-99d3-cb8b7a9d509b)
#### we need to declare it also
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/84393e5e-1df9-4ab0-bfb0-508d765165bc)

## so now our next step is to convert the ( OTF )output text format to pdf format
 ### we will use this function module for that.
 

 ##STEPS

 ```
- WE WILL CALL THE FUNCTION MODULE THROUGH PATTERN
- WE WILL PASSS THE FORMAT AS PDF
- WE WILL PASS THE OTF IN TABLES LS_JOB_OUTPUT_INFO-OTFDATA
- THEN WE WILL DECLARE AND PASS THE INTENRAL TABLE TO LINES
---- MEANS FN MODULE WILL TAHLE THE OTF CONVERTS IT TO PDF AND PASS THE OUTPUT AS PDF IN LINES.
```
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/21f44c6f-3d08-41bb-b48a-d85df4e56240)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/c2cf9337-affa-4725-8c35-767f1989bd61)


## SO NOW LETS SAY WE WANT TO DOWNLAOD THE PDF

```
- WE WILL CALL THE FUNCITON MODULE GUI_DOWNLOAD
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/1d564ead-fe37-49d6-8adb-aee2fb5ff295)
- we will pass the file type BIN
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/d8ad605e-0ab6-4cca-bf40-8fa4b36d7f6e)
- NOW WE WILL PASS THE INTERNAL TABLE FROM WHERE WE WNAT TO DOWNLOAD THE PDF
- 
```




# OUTPUT TYPES IN SMARTFORM

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/a3fab53e-a319-4bf3-a73b-97f50c054f00)

