# Unit mapping intuition
No matter we use automation or not, we need to manually map the unit of new product classified to FV.
Actually, for LB, OZ it is easy to get the portion by function because we already have UNITS_WEIGHT in transaction files.
<img width="610" height="300" alt="image" src="https://github.com/user-attachments/assets/1743e5c9-d1d3-40b8-a2b3-02af52572a18" />

<img width="700" height="200" alt="image" src="https://github.com/user-attachments/assets/2abd5856-6012-422f-9478-b65711e99880" />
<img width="527" height="219" alt="Screenshot 2025-09-18 at 23 33 13" src="https://github.com/user-attachments/assets/9eea9b6d-676f-4b68-8b10-a64068abc52c" />






# Workflow
**Step 1(automation)- Mapping unit from the old transaction files**
In put:  
1.	transaction_mapped.xlsx (newly mapped transaction records with dummies)
2.	FV_dummy_unit_updated_Jul .xlsx (past mapped transaction records with dummies and portion)
3.	FV_products.xlsx (lists of products description of FV_dummy1=1)

Output:
FV_unit.xlsx 

 <img width="800" height="150" alt="image" src="https://github.com/user-attachments/assets/f17a29f1-dba4-4e36-97f8-5114cef5d69d" />

Column PRODUCT_DESCRIPTION show the list of lists of products description of FV_dummy1=1
Column UNIT_OF_MEASURE show the corresponding unit of measure of all products description
Column UNIT_OF_MEASURE_mapped show the corresponding unit of measure after mapping for products description (1N, EA) (newly added products this round has no data for this column)
Column FNDDS_SCHNUCKS show the corresponding mapped value for products description (1N, EA) (newly added products this round has no data for this column)

After process, I found that some products from old transaction files are mapped to multiple  values, I think we should make a consistence regarding this products.
These duplicated mapped products are saved in sheet duplicated_unit_mapping in file: 
FV_unit.xlsx 


The sheet 3 shows the new products (1N, EA)  need to be manually mapped, since there are only 48 of them, I plan to make a consistency of FV_dummy=1 case and unit_mapping from old files before move on to the manual process.

**Step 2- manually mapping unit**

Use file: FV_unit.xlsx (output of step 2), manually map the unit of new products and save in file: : FV_unit.xlsx

**Step 3(automation)- calculate portion**
Input:
1.	transaction_mapped.xlsx (newly mapped transaction records with dummies)
2.	FV_unit.xlsx (fully unit mapped fv product list)

Output: transaction_portion.xlsx (newly mapped transaction records with dummies and portion)
