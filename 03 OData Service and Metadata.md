###

<img width="1178" height="488" alt="image" src="https://github.com/user-attachments/assets/74b159ff-04b5-433d-988f-44a877d5b64e" />

###

<img width="1094" height="655" alt="image" src="https://github.com/user-attachments/assets/fee9f812-d5cd-4851-af22-d23a818acaed" />

###

<img width="1134" height="558" alt="image" src="https://github.com/user-attachments/assets/d421eb2c-947b-4e1e-b2b6-2c9967e73d73" />

###

<img width="1154" height="533" alt="image" src="https://github.com/user-attachments/assets/dc80a6c0-9639-41b5-a81b-2e27384edf3d" />

###

<img width="1086" height="593" alt="image" src="https://github.com/user-attachments/assets/1884f5f3-262b-4ed3-be7a-6101c1df534d" />

###

Northwind ODATA Service :

https://services.odata.org/v2/northwind/northwind.svc/

## --> DATA
``` xml

This XML file does not appear to have any style information associated with it. The document tree is shown below.
<service xmlns="http://www.w3.org/2007/app" xmlns:atom="http://www.w3.org/2005/Atom" xml:base="https://services.odata.org/V2/northwind/Northwind.svc/">
<workspace>
<atom:title>Default</atom:title>
<collection href="Categories">
<atom:title>Categories</atom:title>
</collection>
<collection href="CustomerDemographics">
<atom:title>CustomerDemographics</atom:title>
</collection>
<collection href="Customers">
<atom:title>Customers</atom:title>
</collection>
<collection href="Employees">
<atom:title>Employees</atom:title>
</collection>
<collection href="Order_Details">
<atom:title>Order_Details</atom:title>
</collection>
<collection href="Orders">
<atom:title>Orders</atom:title>
</collection>
<collection href="Products">
<atom:title>Products</atom:title>
</collection>
<collection href="Regions">
<atom:title>Regions</atom:title>
</collection>
<collection href="Shippers">
<atom:title>Shippers</atom:title>
</collection>
<collection href="Suppliers">
<atom:title>Suppliers</atom:title>
</collection>
<collection href="Territories">
<atom:title>Territories</atom:title>
</collection>
<collection href="Alphabetical_list_of_products">
<atom:title>Alphabetical_list_of_products</atom:title>
</collection>
<collection href="Category_Sales_for_1997">
<atom:title>Category_Sales_for_1997</atom:title>
</collection>
<collection href="Current_Product_Lists">
<atom:title>Current_Product_Lists</atom:title>
</collection>
<collection href="Customer_and_Suppliers_by_Cities">
<atom:title>Customer_and_Suppliers_by_Cities</atom:title>
</collection>
<collection href="Invoices">
<atom:title>Invoices</atom:title>
</collection>
<collection href="Order_Details_Extendeds">
<atom:title>Order_Details_Extendeds</atom:title>
</collection>
<collection href="Order_Subtotals">
<atom:title>Order_Subtotals</atom:title>
</collection>
<collection href="Orders_Qries">
<atom:title>Orders_Qries</atom:title>
</collection>
<collection href="Product_Sales_for_1997">
<atom:title>Product_Sales_for_1997</atom:title>
</collection>
<collection href="Products_Above_Average_Prices">
<atom:title>Products_Above_Average_Prices</atom:title>
</collection>
<collection href="Products_by_Categories">
<atom:title>Products_by_Categories</atom:title>
</collection>
<collection href="Sales_by_Categories">
<atom:title>Sales_by_Categories</atom:title>
</collection>
<collection href="Sales_Totals_by_Amounts">
<atom:title>Sales_Totals_by_Amounts</atom:title>
</collection>
<collection href="Summary_of_Sales_by_Quarters">
<atom:title>Summary_of_Sales_by_Quarters</atom:title>
</collection>
<collection href="Summary_of_Sales_by_Years">
<atom:title>Summary_of_Sales_by_Years</atom:title>
</collection>
</workspace>
</service>

```

## --> Meta DATA

in the link just type /$metadata

``` https://services.odata.org/v2/northwind/northwind.svc/$metadata ```

Ex: 

``` xml

<edmx:Edmx xmlns:edmx="http://schemas.microsoft.com/ado/2007/06/edmx" Version="1.0">
<edmx:DataServices xmlns:m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata" m:DataServiceVersion="1.0" m:MaxDataServiceVersion="2.0">
<Schema xmlns="http://schemas.microsoft.com/ado/2009/11/edm" Namespace="NorthwindModel">
<EntityType Name="Category">
<Key>
<PropertyRef Name="CategoryID"/>
</Key>
<Property xmlns:p6="http://schemas.microsoft.com/ado/2009/02/edm/annotation" Name="CategoryID" Type="Edm.Int32" Nullable="false" p6:StoreGeneratedPattern="Identity"/>
<Property Name="CategoryName" Type="Edm.String" Nullable="false" MaxLength="15" FixedLength="false" Unicode="true"/>
<Property Name="Description" Type="Edm.String" MaxLength="Max" FixedLength="false" Unicode="true"/>
<Property Name="Picture" Type="Edm.Binary" MaxLength="Max" FixedLength="false"/>
<NavigationProperty Name="Products" Relationship="NorthwindModel.FK_Products_Categories" ToRole="Products" FromRole="Categories"/>
</EntityType>
<EntityType Name="CustomerDemographic">
<Key>
<PropertyRef Name="CustomerTypeID"/>
</Key>
<Property Name="CustomerTypeID" Type="Edm.String" Nullable="false" MaxLength="10" FixedLength="true" Unicode="true"/>
<Property Name="CustomerDesc" Type="Edm.String" MaxLength="Max" FixedLength="false" Unicode="true"/>
<NavigationProperty Name="Customers" Relationship="NorthwindModel.CustomerCustomerDemo" ToRole="Customers" FromRole="CustomerDemographics"/>
</EntityType>
<EntityType Name="Customer">
<Key>
<PropertyRef Name="CustomerID"/>

```

``` In OData : Entity type means like a structure and entity set means like a table ```

<EntityType will have several property and values 
also <EntityType will have <NavigationProperty

ex: 

``` xml
<EntityType Name="Order_Detail">
<Key>
<PropertyRef Name="OrderID"/>
<PropertyRef Name="ProductID"/>
</Key>
<Property Name="OrderID" Type="Edm.Int32" Nullable="false"/>
<Property Name="ProductID" Type="Edm.Int32" Nullable="false"/>
<Property Name="UnitPrice" Type="Edm.Decimal" Nullable="false" Precision="19" Scale="4"/>
<Property Name="Quantity" Type="Edm.Int16" Nullable="false"/>
<Property Name="Discount" Type="Edm.Single" Nullable="false"/>
<NavigationProperty Name="Order" Relationship="NorthwindModel.FK_Order_Details_Orders" ToRole="Orders" FromRole="Order_Details"/>
<NavigationProperty Name="Product" Relationship="NorthwindModel.FK_Order_Details_Products" ToRole="Products" FromRole="Order_Details"/>
</EntityType>

```

each navigation property will be linked to associations

navigationtype : will tell whats the relationship between source and target entities ( between 2 entity sets ) via associations

``` xml
<AssociationSet Name="FK_Order_Details_Orders" Association="NorthwindModel.FK_Order_Details_Orders">
<End Role="Order_Details" EntitySet="Order_Details"/>
<End Role="Orders" EntitySet="Orders"/>
</AssociationSet>

```

association will tell whats the relationship between source and target entities ( between 2 entitiy sets)


### --> ENTITY CONTAINER

``` XML
<EntityContainer Name="NorthwindEntities" m:IsDefaultEntityContainer="true">
<EntitySet Name="Categories" EntityType="NorthwindModel.Category"/>
<EntitySet Name="CustomerDemographics" EntityType="NorthwindModel.CustomerDemographic"/>
<EntitySet Name="Customers" EntityType="NorthwindModel.Customer"/>
<EntitySet Name="Employees" EntityType="NorthwindModel.Employee"/>
<EntitySet Name="Order_Details" EntityType="NorthwindModel.Order_Detail"/>
```

####-> Multiplicity

Ex:
``` xml
<Association Name="FK_Orders_Customers">
<End Type="NorthwindModel.Customer" Role="Customers" Multiplicity="0..1"/>
<End Type="NorthwindModel.Order" Role="Orders" Multiplicity="*"/>
```

meaning

**for 1 order, 0..1 customers is possible**

**for 1 customer * number of orders is possible **


To get actual data, we can use entity set name

also we can retrieve data in json format using 

https://services.odata.org/v2/northwind/northwind.svc/Products?$format=json

ex:

``` json
{
  "d": {
    "results": [
      {
        "__metadata": {
          "id": "https://services.odata.org/V2/northwind/Northwind.svc/Products(1)",
          "uri": "https://services.odata.org/V2/northwind/Northwind.svc/Products(1)",
          "type": "NorthwindModel.Product"
        },
        "Category": {
          "__deferred": {
            "uri": "https://services.odata.org/V2/northwind/Northwind.svc/Products(1)/Category"
          }
        },
        "Order_Details": {
          "__deferred": {
            "uri": "https://services.odata.org/V2/northwind/Northwind.svc/Products(1)/Order_Details"
          }
        },
        "Supplier": {
          "__deferred": {
            "uri": "https://services.odata.org/V2/northwind/Northwind.svc/Products(1)/Supplier"
          }
        },
        "ProductID": 1,
        "ProductName": "Chai",
        "SupplierID": 1,
        "CategoryID": 1,
        "QuantityPerUnit": "10 boxes x 20 bags",
        "UnitPrice": "18.0000",
        "UnitsInStock": 39,
        "UnitsOnOrder": 0,
        "ReorderLevel": 10,
        "Discontinued": false
      },

```
