<img width="1575" height="819" alt="image" src="https://github.com/user-attachments/assets/b0a458b0-f68b-4660-8c30-3252446642c6" /><img width="741" height="339" alt="image" src="https://github.com/user-attachments/assets/a583972c-5981-4863-a10a-5d00176161cf" />##

<img width="1120" height="596" alt="image" src="https://github.com/user-attachments/assets/6e097407-805e-4bd2-8897-27044b21197b" />


## Code base Approach

Ex task : There is a Database table ex:  ztest_empl_mast, expose the table contents as OData URI or endpoint to external systems


### Step 1 : Create Project( SEGW )

<img width="1067" height="756" alt="image" src="https://github.com/user-attachments/assets/33b2064d-4a80-476a-ad94-c56ced9ab93b" />

Project types :

<img width="1194" height="777" alt="image" src="https://github.com/user-attachments/assets/d32e88b4-e3c2-4400-8c10-df2b30b0d4f6" />

<img width="625" height="162" alt="image" src="https://github.com/user-attachments/assets/99529e0d-fb44-46d3-883e-ce7f96c29bfb" />


Note : OData V4 is not reccommended by SAP VIA SEGW


----


<img width="741" height="339" alt="image" src="https://github.com/user-attachments/assets/bd21529b-3570-4509-a645-7e52c78c4ba1" />

## Creation of entity type:

<img width="1575" height="819" alt="image" src="https://github.com/user-attachments/assets/3c75f30d-38a9-47d0-b910-b45b670e0968" />


<img width="1454" height="438" alt="image" src="https://github.com/user-attachments/assets/3326efca-b938-4015-b808-0725388d34ba" />

manually with each fields->> Here the fields can be added manually ( like a structure under properties )


pull an exsting structure ->>


<img width="1365" height="535" alt="image" src="https://github.com/user-attachments/assets/a8b62d6a-a007-403b-9466-f9fed2e2925e" />

<img width="1460" height="601" alt="image" src="https://github.com/user-attachments/assets/b5f5ceef-93f7-4c9c-997c-d93b25b2fb76" />

`` **complex type : no key fields but in entity type we have key fields** ``

<img width="1554" height="782" alt="image" src="https://github.com/user-attachments/assets/27ee8711-1799-418c-8197-496ac4fcb035" />


## 

Creation of  Entity Set

<img width="1597" height="360" alt="image" src="https://github.com/user-attachments/assets/6393754c-04ad-4b13-8623-9e627df20de8" />

## CLICK ON GENERATE RUNTIME OBJECTS

<img width="373" height="74" alt="image" src="https://github.com/user-attachments/assets/fe4925d7-197f-4990-806f-cfe6275a81ca" />

<img width="824" height="623" alt="image" src="https://github.com/user-attachments/assets/97b73c98-10ad-4c40-9cf1-18ba6c32fc0f" />

MPC CLass: Model Provider Class: Info about all entity types, entity sets, associations and navigation properties all in code format

DPC CLass: DATA Provider Class: This Actually provide the data 

### We should only touch extension classes ex:

ZCL_ZTEST_AM_ODTA_EMPD_MPC_EXT

ZCL_ZTEST_AM_ODTA_EMPD_DPC_EXT

### dont touch :

ZCL_ZTEST_AM_ODTA_EMPD_MPC

ZCL_ZTEST_AM_ODTA_EMPD_DPC

### TECHNICAL MODEL and SERVICE Name we can give to outer world for exposure of our services:
Ex:

ZTEST_AM_ODTA_EMPD_01_MDL

Ex: 

ZTEST_AM_ODTA_EMPD_01_SRV

Creation of Runtype Artifacts

<img width="538" height="167" alt="image" src="https://github.com/user-attachments/assets/07d60b6a-572c-49de-ba27-f232dc192eda" />


## HOW TO EXPOSE THIS SERVICE TO OUTER WORLD ?

REGESTER THE SERVICE :

<img width="451" height="226" alt="image" src="https://github.com/user-attachments/assets/684fbd5a-4e4d-4162-b494-f23ae37a04df" />

cHECK SYSTEM ALIAS:

<img width="1664" height="383" alt="image" src="https://github.com/user-attachments/assets/4d7245e7-eff9-4351-beff-453d32de3914" />


<img width="1465" height="688" alt="image" src="https://github.com/user-attachments/assets/24b233d5-b578-4288-81f8-7012513b89af" />



nEXT mAINTAIN THE SERVICE :

<img width="356" height="241" alt="image" src="https://github.com/user-attachments/assets/c6dc9a97-a2cc-43ba-87e7-2e49e2731229" />

or /n/iwfnd/maint_service like below:

<img width="1872" height="929" alt="image" src="https://github.com/user-attachments/assets/79256eb0-33bc-4d40-8131-371954734fca" />

# Once SICF Service got activated, we can display this service to the outer world.

# go to maintain service tcode : SICF or

ICF Node maintenace :

<img width="890" height="275" alt="image" src="https://github.com/user-attachments/assets/badff724-38f4-49b4-8e68-5e8789cefe18" />


## To Test your service go to /n/IWFND/GW_CLIENT

OR GO TO This by the below button :

<img width="816" height="209" alt="image" src="https://github.com/user-attachments/assets/cda7cc3e-2442-4509-b3bd-367e52dd9692" />

###

<img width="1888" height="939" alt="image" src="https://github.com/user-attachments/assets/aa563680-62a1-4886-a311-eb7b3285b391" />

execute..

just execute and you can see all the details.

to view the metadata , put $metadata in end of URI.

EX: /sap/opu/odata/sap/ZTEST_AM_ODTA_EMPD_01_SRV/$metadata


<img width="1852" height="917" alt="image" src="https://github.com/user-attachments/assets/525eefde-1218-4f6a-8779-8f2c66644af5" />


































