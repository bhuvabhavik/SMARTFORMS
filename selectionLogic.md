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



