# is it not posssible to write a selection logic or queries in driver program itself?
### yes it is possible and a great preferenece too
### previously we have written it seperately so we will write it in driver program now.

> [!NOTE]
>  we can pass the input or get the output from smartform using the form interface.
> 
> so we will use that to passs the internal tables into smartforms
> 
> ### for this we need to create a global structure using SE11.
> 
> and type table of is also not acceptable so we will create table types.

## create a global header structure
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/022f2313-e80c-414c-be5e-588c9f378033)
## create a type table
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/0ca05000-6417-490e-a166-57d793675440)


## define it in smartform
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/0c6ccf0a-2bee-4729-88f3-e1be19ab4bac)
 ## item table global structure
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/e0e83cd1-67c4-42a3-bfb4-7bf57e462300)
### table type
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/19cf111a-640c-4f03-a48b-3dcab7cfce29)
## define it in smartform
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/93842e48-1a1f-4485-b288-495b1fb94ecb)
## Declare 2 workareas in smartforms
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/ed41cd38-1d86-4c55-aec0-3c005d3ae687)

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/f94f908c-86d6-4e61-babc-a8a772175629)

# Now we need to integrate the smartform, our smartform&driverprogram is ready means we need to pass the header and item to new smartform we developed

### using function module call it in program
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/2c446339-1e19-4879-8087-4d4de5a71e4e)
now funciton module cant be hardcoded so change it using *_ssf_function_module_name_*



# OPTIONAL

![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/d0005e1d-c897-41f9-9323-66c98bebc083)
## now if we want to even write this in the driver program we can do it that also.
lets look at it
declare workarea and write a query like this
### _ so now how to pass it to smartforms? _
delcare in import parameter from smartform and pass and export from driver program.
### its a golden rule whatever you want to import in the smartform just declare the paramaeter in 
form interface and then export it from program.
![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/a0c1dba6-f7e7-4744-9444-97704697d72e)
remove or comment read line in smartform
delete from global variable coz its not a smartform variable now.


```
*&---------------------------------------------------------------------*
*& Report ZSF_DRIVERPROG_201
*&---------------------------------------------------------------------*
*&
*&---------------------------------------------------------------------*
REPORT zsf_driverprog_201_pk.

TYPES: BEGIN OF lty_data,
         ono   TYPE zdeono__28,
         odate TYPE zdeodate__28,
         pm    TYPE zdepm__28,
         ta    TYPE netwr,
         curr  TYPE zdecur__28,
       END OF lty_data.

TYPES: BEGIN OF lty_data1,
         ono   TYPE  zdeono__28,
         oin   TYPE  zdeoitmno__28,
         icost TYPE  zdeitmcost__28,
       END OF lty_data1.

DATA: lt_data TYPE TABLE OF lty_data,
      wa_data TYPE lty_data.
DATA: lt_data1 TYPE TABLE OF lty_data1.
      "wa_data1 TYPE lty_data1.


DATA: lv_fname TYPE rs38l_fnam.
PARAMETERS: p_ono TYPE zdeono__28.

SELECT ono
       odate
       pm
       ta
       curr  FROM zordh__28 INTO TABLE lt_data WHERE ono = p_ono.



IF lt_data IS NOT INITIAL.
  READ TABLE lt_data INTO wa_data INDEX 1.
  SELECT ono oin icost
    FROM zori_28
    INTO TABLE lt_data1
    FOR ALL ENTRIES IN lt_data
    WHERE ono = lt_data-ono.
ENDIF.



CALL FUNCTION 'SSF_FUNCTION_MODULE_NAME'
  EXPORTING
    formname                 = 'ZSMARTFORM_201__PK'
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
*   ARCHIVE_INDEX              = ARCHIVE_INDEX
*   ARCHIVE_INDEX_TAB          = ARCHIVE_INDEX_TAB
*   ARCHIVE_PARAMETERS         = ARCHIVE_PARAMETERS
*   CONTROL_PARAMETERS         = CONTROL_PARAMETERS
*   MAIL_APPL_OBJ              = MAIL_APPL_OBJ
*   MAIL_RECIPIENT             = MAIL_RECIPIENT
*   MAIL_SENDER                = MAIL_SENDER
*   OUTPUT_OPTIONS             = OUTPUT_OPTIONS
*   USER_SETTINGS              = 'X'
    lt_header                  = lt_data
    lt_item                    = lt_data1
    lwa_data                   = wa_data
* IMPORTING
*   DOCUMENT_OUTPUT_INFO       = DOCUMENT_OUTPUT_INFO
*   JOB_OUTPUT_INFO            = JOB_OUTPUT_INFO
*   JOB_OUTPUT_OPTIONS         = JOB_OUTPUT_OPTIONS
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


## but we will not get an output like this we need to work on currency field for that so this topic is contunued with different note file.refer https://github.com/bhuvabhavik/SMARTFORMS/edit/basics-smartform/Currency&QuantityField.md

