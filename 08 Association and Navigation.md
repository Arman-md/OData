
# ASSOCIATION

## Association is the relationship between two or more entity types

## BASED ON ROLE and Multplicity

## NavigationpPROPERTY : Based on this we can navigate to other entity types...!

ex: 

-> for order detail entity type, we have 2 navigation properties:|


<img width="1521" height="293" alt="image" src="https://github.com/user-attachments/assets/a2145b2e-388a-485c-8d26-3c1f1b43bd7d" />

https://pragmatiqa.com/xodata/

<img width="720" height="615" alt="image" src="https://github.com/user-attachments/assets/d7807de5-3916-4bfc-b50c-8f15219a03a6" />

# Demo sales order

## step 1 : create a sales order project in SEGW

## step 2 : create entity types( VBAK and VBAP ) with only required fields only

<img width="1076" height="414" alt="image" src="https://github.com/user-attachments/assets/34f9f2e7-126e-45e0-a970-a2aee8b33d39" />

<img width="1830" height="504" alt="image" src="https://github.com/user-attachments/assets/a181e300-d104-4845-a334-14382bf56a27" />


## step 3: Generate runtime artiacts:

<img width="2015" height="697" alt="image" src="https://github.com/user-attachments/assets/8c8f809c-7fe4-4b0f-8aaa-c919aec623a3" />

## step 3: regester your service( either like below ) or via /n/iwfnd/maint_service

<img width="371" height="190" alt="image" src="https://github.com/user-attachments/assets/d16357b3-e25d-4474-8a1c-e84367f4e0af" />

## step 4: maintain using 'maintain'

<img width="371" height="190" alt="image" src="https://github.com/user-attachments/assets/0ed87788-9320-478b-9786-507b3d757e33" />


## step 5: go to gateway client via /n/iwfnd/gw_client or below screenshot :

<img width="856" height="202" alt="image" src="https://github.com/user-attachments/assets/b14259bc-25d2-4873-b98a-eaa931625f98" />

## step 6 : created the project :

<img width="1790" height="691" alt="image" src="https://github.com/user-attachments/assets/c9b24596-a989-483d-81e8-c8de9a251870" />

### metadata uri : /sap/opu/odata/sap/ZTEST_AM_ODTA_SALES_ORDER_01_SRV/$metadata

<img width="1800" height="901" alt="image" src="https://github.com/user-attachments/assets/c52cf701-81b4-4e5d-8437-1e20ba5a7714" />


## ASSOCIATION : TO establish relationship between 2 entity types SalesOrderHeader and SalesOrderItem

<img width="348" height="181" alt="image" src="https://github.com/user-attachments/assets/e69c56b0-5e31-4715-8083-0cbe4ac47f80" />

<img width="1483" height="531" alt="image" src="https://github.com/user-attachments/assets/aac7fb9a-1bd9-43bb-8e3e-01a3c251f771" />

<img width="856" height="216" alt="image" src="https://github.com/user-attachments/assets/30c0717f-3c3b-4318-bafc-a5fa30acf8b1" />

<img width="854" height="542" alt="image" src="https://github.com/user-attachments/assets/b149f43e-7eff-40de-8979-312fdbb616f8" />

<img width="1799" height="868" alt="image" src="https://github.com/user-attachments/assets/68afb167-6233-40fb-8a30-37bd179d34e8" />

### after we regenerate runtime artifacts, navigationproperty and associatiosn got added in the XML Payload :

<img width="1793" height="906" alt="image" src="https://github.com/user-attachments/assets/163d95e1-13fe-4f7a-8109-5bb7c173cea3" />

# CRUD

## Get sales order header data :

<img width="1791" height="890" alt="image" src="https://github.com/user-attachments/assets/95dd47bc-377f-40a2-bb68-a98dfb3493bd" />

implement the method : SALESORDERHEADER_GET_ENTITYSET

<img width="893" height="523" alt="image" src="https://github.com/user-attachments/assets/81556027-e8c6-4f8f-bd1b-9c358ddf4b53" />


RESULT :

<img width="1794" height="871" alt="image" src="https://github.com/user-attachments/assets/a6b081f7-9c4e-486c-bbfb-cf9063ff4ee1" />


### TO ACCESS SALES ORDER ITEMS OF A Particular Sales Order, we can use navigationproperty name :

" when we know the sales order
 ``` URI : /sap/opu/odata/sap/ZTEST_AM_ODTA_SALES_ORDER_01_SRV/SalesOrderHeaderSet('48155268')/Items ```

 OR

" when we dont know the sales order, 
 ``` /sap/opu/odata/sap/ZTEST_AM_ODTA_SALES_ORDER_01_SRV/SalesOrderItemSet ```

 in both the case, the same method :  'SALESORDERITEMSE_GET_ENTITYSET'  will be triggered...

 -> we can also display error message if Sales order is invalid / Invalid URI

 However, we get error Method 'SALESORDERITEMSE_GET_ENTITYSET' not implemented in data provider class

 <img width="1899" height="676" alt="image" src="https://github.com/user-attachments/assets/b84dd732-c1f9-4663-bbf3-89b5c02b5003" />

Implementation :

``` abap
  METHOD salesorderitemse_get_entityset.
    DATA lv_vbeln TYPE vbak-vbeln.

    lv_vbeln = VALUE #( it_key_tab[ name = 'SalesOrder' ]-value OPTIONAL ).
    lv_vbeln = |{ lv_vbeln ALPHA = IN }|.
    IF lv_vbeln IS NOT INITIAL.
      SELECT vbeln, posnr, matnr, kwmeng
        INTO CORRESPONDING FIELDS OF TABLE @et_entityset
        FROM vbap
        WHERE vbeln = @lv_vbeln.
      IF sy-subrc = 0.

      ENDIF.

    ENDIF.

  ENDMETHOD.

```


<img width="1087" height="747" alt="image" src="https://github.com/user-attachments/assets/a9a27a35-18a7-44b0-adcd-0758eb038660" />




 













 
