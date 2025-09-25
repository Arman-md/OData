
## When we try to read employeeset ( entity set ) via URI we get the below error cuz its not implemented

<img width="1828" height="893" alt="image" src="https://github.com/user-attachments/assets/be632998-d10e-46e6-b8d5-3d52c3759d02" />

##

Model Provider Class :

<img width="1051" height="434" alt="image" src="https://github.com/user-attachments/assets/4e79d31e-e78a-41b1-964e-27440774ae31" />


### how to solve ? we should implement employeeset_get_entityset method in DPC Extension class:

<img width="975" height="524" alt="image" src="https://github.com/user-attachments/assets/7caca79c-c3be-4d19-b64f-de61aa2b4f44" />


<img width="1088" height="677" alt="image" src="https://github.com/user-attachments/assets/fa890f59-56a5-496e-8d65-09bcd9d96f60" />


### now try : /sap/opu/odata/sap/ZTEST_AM_ODTA_EMPD_01_SRV/employeeSet url again


<img width="1441" height="967" alt="image" src="https://github.com/user-attachments/assets/d337b4af-116b-4559-8dcf-178d7f680da7" />


we get the xml data( metadata)

### we can also pass the key field in URI meaning reading a single record/ selected record -> entity type( like a work area)

ex: URI : /sap/opu/odata/sap/ZTEST_AM_ODTA_EMPD_01_SRV/employeeSet(Mandt='001',EmpId='E000000002')

WE GET ERROR EMPLOYEESET_GET_ENTITY Method is not implemented.

we can implement like :

<img width="1470" height="918" alt="image" src="https://github.com/user-attachments/assets/f2f11c1f-abb6-4cf8-9cc6-6234b18e734c" />

<img width="920" height="449" alt="image" src="https://github.com/user-attachments/assets/12a4dd35-413b-4ec0-8711-8951e53303d2" />


result we get 
.
.
.
<img width="1797" height="852" alt="image" src="https://github.com/user-attachments/assets/b7fcdf4e-8b54-44c9-ad7f-02a6886e8612" />


# to view in JSON

# URI : /sap/opu/odata/sap/ZTEST_AM_ODTA_EMPD_01_SRV/employeeSet(Mandt='001',EmpId='E000000002')?$format=json

# ?$format=json

<img width="1792" height="780" alt="image" src="https://github.com/user-attachments/assets/8da64f1f-0777-400e-8a6e-4de1f3724723" />

# To raise rxception in entity / entity sets we can use code like below:

![Uploading image.png…]()











