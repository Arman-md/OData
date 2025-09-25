# POST -> CREATE

<img width="1842" height="882" alt="image" src="https://github.com/user-attachments/assets/9978186f-3c32-4226-ab2c-a7e73b560800" />

## We try to create a new data in gatweay client and when post, we get error : 'EMPLOYEESET_CREATE_ENTITY method not implemented.

<img width="1806" height="891" alt="image" src="https://github.com/user-attachments/assets/ad30c2be-5542-4ca3-890c-eec15271dad9" />


## Step 1 : assume from the front end we get the data in JSON format ( which we need to post in SAP Database)

<img width="1842" height="882" alt="image" src="https://github.com/user-attachments/assets/f8965a61-3387-44cf-a716-d675b4095806" />


## Step 2 : we implement the relevant method : EMPLOYEE_CREATE_ENTITY method and in the implementation, we read the data coming from the 
## gateway client 

## Then write to the data base 

<img width="1062" height="550" alt="image" src="https://github.com/user-attachments/assets/934a23aa-af79-4580-815e-41a6c671bbbb" />

```
```
<img width="1786" height="838" alt="image" src="https://github.com/user-attachments/assets/c55b2e1a-9368-471b-b5f5-5479b4bf0a85" />


# PUT -> UPDATE

In our example, we are chnaging country to -> RUSSIA (Old was USA)

We get error : EMPLOYEE_UPDATE_ENTITY not implemented

<img width="1813" height="864" alt="image" src="https://github.com/user-attachments/assets/78be9b51-8eec-4077-ac66-0262f9107262" />

##Solution

### Step 1 Redefine the method EMPLOYEESET_UPDATE_ENTITY

### STEP 2 WRITE THE LOGIC TO READ THE INCOMING ENTRY FROM FRONT END. IF Exists, then 

### STEP 3 Update the edb table as per the entry and give bak the result to ER_ENTITY

<img width="1625" height="862" alt="image" src="https://github.com/user-attachments/assets/a4581453-cb36-431e-be38-e40d3bac672d" />

<img width="1335" height="756" alt="image" src="https://github.com/user-attachments/assets/35c47926-f86e-4cc6-98bf-a85100051ace" />

<img width="1573" height="229" alt="image" src="https://github.com/user-attachments/assets/386bad66-f084-4eb6-a89c-214ce6c4b6f6" />

# DELETE -> DELETE

## JUST PASS THE KEY FIELDS IN THE URI but you will get not implemented error:

<img width="1830" height="910" alt="image" src="https://github.com/user-attachments/assets/44ee4a82-7e71-47e7-a439-d6526477ab3d" />
























