# SENDING PDF AS EMAIL 📧📨

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/8ba75ac5-60e1-42eb-821f-f692d2bbd0c2)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/f6b8de60-ddae-4eab-afe5-3b1d7b39dbdd)



![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/dfad0a49-68f2-4f0b-bb74-31d74ced82a1)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/373f19df-0d22-442d-a1e1-cb312010095a)


# Step 1️⃣:
## Get the bin file of the smartform.📁

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/8545249c-41ba-4b01-bacb-ba973d16c5d7)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/53bc73e0-c888-4f36-aa8b-579a207e251f)


# Step 2️⃣:
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/49ac41f6-b3aa-40c6-b9cf-a875db079921)
### SAP alreeady provided function module to convert XString to Binary
### This function module will convert from xsring to binary.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/6748f618-ef34-4c35-9b09-58dc2a24b117)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/e6c76b83-8c12-4a4a-bada-7d623386ab94)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/a6f18a1b-9521-4898-a380-3be5b24397d9)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/f5e5c9e2-482e-48f6-8604-c97bb7586c95)
### use solix_tab as a type reason we will discuss further

# Step 3️⃣:
### now we will comeon to classes.
#### whenever we want to create send request we use ### CL_BCS class
### now we wil go to se24. se24 is the tcodefor the global classes.


- Goto patern > goto abap object pattern
- Give the name of class and method
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/00966703-f23b-4c61-bf6f-f576b5abcb94)
- Create_persistant is used to create a send request.
- Declare an object of type cl_bcs
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/ba97351e-e946-4362-b3a1-058b37e5eb00)
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/5bc8b4ec-2a4f-4fc6-87b4-2251ecc85c53)





# Step 4️⃣:
## Create the sap user/external user

#### - firstly we need to create the receipient and then we can pass it so lets create the receipient first.
#### - we have 2 classes to create the recepiemt
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/6cfa5dc6-0478-4d37-b756-3caead24ebab)

## # LEtsss say we are doing for SAP USER
- Go to se24 and pass the class
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/da2a2339-c152-4d17-84f5-4daca8581609)
- we will use the create method to get the sap user.
- goto pattern > abap object pattern > pass class and method
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/a987bdcf-81f6-448b-95fb-f362b7730541)
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/9c961d7e-b009-44f5-909f-090f0d26f667)
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/ddfa68f2-8514-4265-a7fd-0ba66dade78d)
- WE have created the user now we need to create the recepient. we will use add_recepient method
- ####### NOTE:: add_recepient is an instance method so we need to call with object.
- so we will go to pattern abap object pattern and pass the clss instance and method
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/331d4e92-8ac6-462c-b8c9-f21f3afc685f)
- we can simply pass the object of our recepient
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/3c667dc0-90fe-464f-b318-dc357b8a7234)
- 



# NOW WE WLL SEEE HOW CAN WE CREATE THE EXTERNAL USER
### we can use the ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/4b5b37bf-f769-481c-aaf7-0718a1b0f9f0) method to create the external class.



➡ we will goto pattern > abap object pattern & pass class&method
➡ ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/16a47d04-8618-4866-9594-52c338716a3f)
➡ ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/1d2c1a3d-24e2-4cdc-bb06-bb43b13aaf8a)
➡ ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/ec30b214-1d8f-4514-9d26-8d1889063076)
➡ we created the user now we need to add user as recepient
➡ ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/862d55d4-997d-4e02-9533-9b508ce0ef12)
➡
➡
➡

# NEXT STEP 6️⃣ - CREATE THE DOCUMENT

- WE WILL GOTO SE24 TCODE(GLOBAL CLASSES)
- WE WILL GOTO ##CL_DOCUMENT_BCS
- WE WILL USE CREATE_DOCUMENT STATIC METHOD
- ##LETS MOVE TOWARDS DOCUMENTATION CREATION
- WE WILL PASS THECLASS AND METHOD
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/f3c4bb0e-17c6-412e-9e88-5b0c52584210)
- 
- WE WILL DECLARE INTERNAL TABLE AND WA FOR I_TEXT(MAIL BODY)
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/364d43d4-94ed-42ec-b464-1889b732876f)
- ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/be8dc159-1722-4383-82b5-68fa71ab1745)

### NOW WE NEED TO INSERT THE DATA TO LT_TEXT INTERNAL TABLE
#### SO FIESTLY WE WILL PASS THE DATA TO WORKAREA AND THEN APPEND IT TO INTENRAL TABLE
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/f8ae5110-87c6-42e8-9567-c42acb8bed58)
 (DEAR SIR)
FILL THE CONTENT AS REQUIED IN LINES
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/511600ad-08b9-43b2-8a59-e04458389613)
#### we will pass the doc classificaion as RAW
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/b90de1a2-80f6-4964-95a5-0fc8f53b5760)

acept output from result
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/9bda2113-5403-4129-abcc-58e390feb641)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/683ba8b8-2d69-4d82-a270-f129a6ecc90a)


# STEP 7️⃣: ADD THE ATTACHMENT.

WE WILL PASS CLASS METHOD AND INSTANCE.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/07427725-9801-40ac-ab1b-3ca1dcfce999)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/5c5314a7-228c-4057-85e4-7dfac876e644)

>[NOTE]
>WITH THE HELP OF #CL_BCS CLASS WE CREATED THE SEND PROCESS AND WE ADDED THE RECEPIENT.
>WITH THE HELP OF SECOND CLASS #CL_DOCUMENT_BCS WE SIMPLY CREAEED THE DOCUMENT AND ADDED THE ATTACHENT.
>JUST THINK WE HAVE USED TWO SEPERATE CLASSES BUT IS THERE ANY LINK BETWEEN THEM? ##NO
>
>

## SO IN THE NEXT STEP WE WILL LEARN THAT

# STEP 7️⃣: SET THE DOCUMENT.

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/7f1ae1ca-395b-40cd-9af7-f32829abf8c6)


![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/ef1f7fd2-5e18-4a90-9d5c-7e953689eac1)
### _WE WILL PASSTHE OBJECT OF DOCUMENT CLASS. WE NEED TO LINK BOTH OF THEM
____
## NOW WE NEED TO WORK ON THE SEND 📩 BUTTON
## 🚨 BEFORE SEND WE NEED TO WORK ON ACTIVATE/DEACTIVATE IMMEDIATE SENDING
###CURRENTLY WE WILL GO FOR IMMEDIATE SNEDING ONLY
CALL METHOD THROUGH OBJECT AS ITS A INSTANCE 
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/7b555e5d-1204-466a-8249-9c2166e2c379)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/60debcb7-bf32-44d1-8b75-e176b74ed160)

# NEXT STEP: SEND 
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/72e48a1e-4d1d-4274-bd3a-d6a2a5b85d4d)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/6f4c33c5-23ed-4901-b37a-684f5ecac573)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/846c9796-04cb-4f7f-9230-7e8afd635c04)

## NOW AT THE LAST WE NEED TO COMMIT OUR WORK
### COMMIT IS ONLY REQUIRED IF YOU ARE SENDING THE MAIL OUTSIDE SAP ,WITHIN SAP ITS NOT REQUIRED AT ALL.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/8127f764-31e3-4b28-9c69-e37382848c73)






































































