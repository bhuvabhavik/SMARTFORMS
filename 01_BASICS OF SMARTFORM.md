[!IMPORTANT]

# SMARTFORMS
## my sap abap **smartform notes**
> [!NOTE]
> ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/658f47b2-6bf3-4b49-ae23-d63673bc4fc4)

> [!TIP]
> form attribute gives all generic information
> form interface is used when we want to give input and take some output from  the smartforms.
>![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/92dfb10c-f6ab-4b38-8045-6d0d0f95a9d7)

# DESIGN THIS LAYOUT IN SMART FORMS
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/851a6f79-375b-4698-9948-980809c96efd)
 # for every section we will create a window
 ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/7d490e67-2f39-4469-a58e-5041e87b324f)
## create 6 windows with a meaningful description. and give meaningful dimensions
## same thing we can do using the form painter too.
### write click on the window and create text.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/371d23ea-a1b8-42fc-8084-98a788dff29d)
### whenever we have fixed number of colums always create template.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/88a09f95-2bc9-499f-b80f-3b6559626eb7)
### create templates and text
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/5bf05593-563f-4584-9507-0d563cedcc34)
### give line & column as per requirement
## to give text labels go to general attribute > text editor > pass the desired text.

### define templates and structyres and also pass row and column for every templaates object
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/38a144f4-fdaa-4525-8f3e-d073dda68c4e)

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/ba1c8fdb-6a2b-4021-bb20-a73598a4ad6b)

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/100cda5d-3e39-4707-af10-6b77f2d6fb19)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/64222e80-ea49-4cff-a121-b9d9a75cf0a5)
## flow structure
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/5ad4fb8d-057a-4dc0-85c5-f71ac03d312e)


##GO TO GLOBAL DEFINATION > TYPES > and DECLARE STRUCTURES for table

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/d421edee-767b-4b9d-bd98-0be44aebb022)

## DECLARE INTERNAL TABLES AND WORKAREAS

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/12400f32-0a38-459f-b335-1ec9fe15a643)

## NOW WRITE THE LOGIC PART TO FETCH THE DATA IN INITIALISATION PART AND DECLARE INPUT OUTPUT PARAMETERS
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/13f86ee1-023a-4100-a40d-2e3bc8f76129)

```
SELECT ONO ODATE PM TA CURR
  FROM ZORDH__28
  INTO TABLE LT_DATA
  WHERE ONO = P_ONO.

  IF LT_DATA IS NOT INITIAL.
    READ TABLE LT_DATA INTO LWA_DATA INDEX 1.
    SELECT ONO OIN ICOST
      FROM ZORI_28
      INTO TABLE LT_DATA1
      FOR ALL ENTRIES IN LT_DATA
      WHERE ONO = LT_DATA-ONO.
      ENDIF.

```

## WE HAVE MOVED THE DATA OF FIRST INTERNAL TABLE INTO WORKAREA USING READ STATEMENT
## NOW WE NEED TO LOOP OVER INTERNAL TABLE 2 
this is how to do it
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/fc433f17-69e0-4ee4-86f5-84da3ae5e1be)


![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/dc721dce-5587-4ad3-b476-61de1640166d) ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/5ab9739a-c30f-419f-bd56-648fb0abc7d5)


similarly add it to all the value fields.
# now we will go to the total part
## declare the variable for total
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/8bf4db16-65f3-4672-af8c-db2899d29173)
## then

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/097f4b86-1fa2-4abb-aed2-27eccbe97835)
 then go to footer and add texts &lv_total&

 ## everything related to design part logic part is done now we will check the output next.

 ### calling the smartforms from the driver program.
 ### whenever we run a samrtforms every smartforms generates a function module.
 now customer will not go through all the steps so making a program for it is better.
  ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/66bef865-9582-4c83-8e3c-703c7b692098)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/82590357-0c3e-40b3-9b1e-e865cb7d7230)
## thiis program is working fine but when it may goto quality or production it may fail. bevause we are hardcoded the fuction module and function module are dynaic and generate at run time.

# so the sap provided the solution for that
> [!IMPORTANT]
# SSF_FUNCTION_MODULE_NAME
## sap provide this function module in which if we pass smartform it retuens the function module of the smartform.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/f2628af9-c101-4c4d-ba1b-381f26330262)
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/fd23a4f5-35a4-494c-8609-89aaac6a994d)

```
*&---------------------------------------------------------------------*
*& Report ZSF_DRIVERPROG_201
*&---------------------------------------------------------------------*
*&
*&---------------------------------------------------------------------*
REPORT zsf_driverprog_201.
DATA: lv_fname TYPE RS38L_FNAM.
PARAMETERS: p_ono TYPE zdeono__28.


CALL FUNCTION 'SSF_FUNCTION_MODULE_NAME'
  EXPORTING
    formname                 = 'ZSMARTFORM_201'
*   VARIANT                  = ' '
*   DIRECT_CALL              = ' '
 IMPORTING
   FM_NAME                  = lv_fname
 EXCEPTIONS
   NO_FORM                  = 1
   NO_FUNCTION_MODULE       = 2
   OTHERS                   = 3
          .
IF sy-subrc <> 0.
* Implement suitable error handling here
ENDIF.




CALL FUNCTION lv_fname
  EXPORTING
*   USER_SETTINGS              = 'X'
    p_ono                      = p_ono

 EXCEPTIONS
   FORMATTING_ERROR           = 1
   INTERNAL_ERROR             = 2
   SEND_ERROR                 = 3
   USER_CANCELED              = 4
   OTHERS                     = 5
          .
IF sy-subrc <> 0.
* Implement suitable error handling here
ENDIF.
```










  



































































































































> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.
