# Smartforms
# Text in SmartForms (_video no 25 in smartforms_)

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/7ce8e05e-4d3f-401c-80e2-16a5930b124f)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/a3c577f2-5f4b-4e46-b2bb-33b86d1a1147)

## Create a text module
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/da898a7e-6788-4e8e-8e2e-909bab862a0b)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/6cadec04-99fe-413b-a894-6d6913d3ed97)
pass the text module name
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/4ecd4079-a758-47b5-b622-9e57f49b08cc)

# NOW INCLUDE TEXT
## create include text from so10 tcode
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/8dee5fe5-df0e-49d1-9ce9-c3c36be383e0)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/77cb620f-f796-4ef6-8bc6-a7234eb5c29b)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/561f269a-19ef-4e73-b21d-cf0d21a66712)
### open include text and goto> header you will get all the parameters from there

# _lets look at how to use include text in a program_

1. import the funciton module *_read_text_*.

   ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/fa754001-52cc-4d09-9451-50fde16d1e43)
2.![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/c583924f-ad68-41f8-b664-366760e64ce9)
if get confused open include text and goto> header you will get all the parameters from there
3. create variable for receiving output (internal table and workarea in our case as tline is table type)
   ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/0d99efae-6afb-40b8-b947-0caf46e58f0e)

5. on receiving error pass the system variable *_sy-langu_*.
   _because sap store the language and 1 char but displays it in two so when we pass the 2 character then its better to pass sy-langu_
   
6. now loop on the internal table (which we have created in step 3 )
7. ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/e1900f6f-eb5b-4c84-a2bf-d395c1b4793d)




   # _DYNAMIC TEXT_

   ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/e42383d8-b5e8-4bf6-9504-f8ce99b456ae)
   ### we know whenever we want to give some input or take some output from/to the smartform always alwez we use the form interface.
___
--> we will define the internal table for dynamic text
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/a44d1f5e-4555-4bd5-b0c0-bc6e7ed7d7af)

   
###  suppose we will cerate a dynamic text in seperate window os we will create a new window.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/bb7abe9a-bbd2-4dfd-8262-9d9d5d9669bd)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/86caab61-86c3-4990-805c-b43fd184bbfc)
### we will createa  new dynamic text element
### provide the field and language
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/5db25ff3-c4fc-43b0-a692-28cbece7ead3)
### now when we execut smartfoem we wil have 2 input parameter
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/3adf44f1-f873-4bcd-8a9a-277abe2eba6c)


## but this is not we want because customer will not run the smartform, the data should be come from the program.
## so lets look at it

### so lets create a parameter in driver prigram

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/6db48c8d-eaf7-4b12-bc04-0e95de9f5b7c)

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/bccc1249-bb74-4760-a3aa-be440e7852c6)
#### what customer pass here we have to display it in our smartform. 
### we will create internal table and workarea for the ddynamic table
## _now whatever the text user pass we will pass it to internal table_

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/bd5a888e-45d2-49ff-a42f-09777899ee51)

## now most important thing to understand is we are passing the daa to dynamic text internal table and then now we will pass the internal table to the smartform.
### lets continue with that
#### call the function mdule again so we get the updated parameter we created or dynamic text.




