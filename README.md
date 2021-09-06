# JSON-Inventory-Management-System-Python
It is a Inventory Management System made with **Python3** and using ***JSON*** files.

# About The Project
It is developed using Python3.The main purpose of the project is to manage inventory of shop. It supports facilities like **ADDING**, **DELETING**, **MODIFYING** and **VIEWING** the inventory items also provides user to **PURCHASE** any item and generating its **TOTAL BILL**.

## Files
  * IMS.ipynb 
  * Purchase.ipynb
  * Inventory.json
  * sales.json
  
## Attributes
  1. Product Id
  2. Product Name
  3. Product Type 
  4. Product Price
  5. Product Quantity
  6. Product Discount

## Details
| File     | Function    | Details |
| ---      | ---         | ---     |
|IMS.ipynb | Add | For ***addition*** of new products to the Inventory.|
|           |Delete | For ***deletion*** of the existing product from the Inventory.|
|          |View | To ***view*** all the items in the Inventory.  |
|           |Modify | To ***modify*** the existing items and update the inventory.|
|sales.ipynb| Purchase | To ***buy*** and print its ***total cost***.|
|           | View     | To ***view*** the updated and overall stock in inventory.|
|           | Sales Made | To view all the ***sales made*** by the user.|
|Inventory.json|  Data Set| All the basic data is ***updated*** here. |     |
|sales.json  | Data Set | All the ***sales*** related data is stored here.|

### Short Insights of CODE

#### Addition
```Python3
prodid = str(input("Enter product id:"))

        if (prodid not in record.keys()):

            name = str(input("Enter name:"))
            types = str(input("Enter the type of product:"))
            price = int(input("Enter price:"))
            quan = int(input("Enter quantity:"))
            disc = int(input("Enter the Discount:"))

            record[prodid] = {'Name': name,'type':types, 'price': price, 'quantity': quan, 'discount' : disc}

            js = json.dumps(record)

            fd = open("Inventory.json",'w')
            fd.write(js)
            fd.close()

        else: 
            print("Invalid Id number or id number already present in the inventory")
```
#### Deletion
```Python3
 delete = input("Enter the id number to delete the product details: ")

            if(delete in record.keys()):
                del record[delete]

                js = json.dumps(record)

                fd = open("Inventory.json",'w')
                fd.write(js)
                fd.close()
            else:
                print("Item not present in the inventory")
```
#### Sales Made
```Python3
fd = open("Inventory.json",'r')
        r = fd.read()
        fd.close()
        record = json.loads(r)
        print("\nID\t\tNAME\t\tTYPE\t\tPRICE\t\tQUANTITY\tDISCOUNT\n")
        for i in record:
            print(i,"      ",record[i]['Name'],"\t\t",record[i]['type'],"\t",record[i]['price'],"\t\t",record[i]['quantity'],"\t\t",record[i]['discount'])
            
```
##### Refer files to see detailed codes
***


