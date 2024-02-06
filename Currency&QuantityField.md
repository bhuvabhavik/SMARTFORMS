# Currency and Quantity field
we have the below error in our smartform lets understand and reslove it
Message:
Reference field LWA_DATA1-ICOST unknown in form.


## the problem is icost is amount so it always require currency.

# if you are passing a amount and quantity to a smartform from a program and you dont have a reference field in the same table/structure sap will give a error so to solve that error.
-->

## we will use CURRENCY?QUANTITY tab in the smartform to resolve this error.

we have 2 solutions for this.
but in our scenario first solution will not work but most of the time it works.
so lets look at it

## first solution is take the reference field in the same structure.
## pass the extra column in structure and do the needful.
## but in this case of ours we dont have currency column in the item table so this solution unfortunately doesnt work for us so we will go for second alternative.

>[!NOTE]
>
>```
> interviewer most fav question? in what scenario we maek use of currency/quantity field.
> ....
> ....
> ...
> ..
>```
## SOLUTION @2

1. GO TO SMARTFORMS > GLOBAL DECLARATION
2. GO TO CURRENCY/QTY
3. SPECIFY THE REFERENCE FIELD THERE
4. ![image](https://github.com/bhuvabhavik/SMARTFORMS/assets/49744703/1186858e-c002-414c-b6b0-3708658d01ed)
