# Kaggle - Santander Product Recommendation
Recommend Bank products to customers of a bank based on their past transactions.

## Overview
### Introduction:
Santander Bank, situated in Spain, offers a lending hand to their customers through personalized product recommendations. They offer several banking products to their customers. Here the bank wants us to create a system that recommends bank products to their existing customers. With a more effective recommendation system in place, Santander can better meet the individual needs of all customers and ensure their satisfaction no matter where they are in life.


### Business Problem:
Under the bank’s current system, a small number of Santander’s customers receive many recommendations while many others rarely see any resulting in an uneven customer experience. Santander is challenging Kagglers to predict which products their existing customers will use in the next month based on their past behavior and that of similar customers.

We are provided with 1.5 years of customer’s behavior data from Santander bank to predict what new products customers will purchase. The data starts at 2015-01-28 and has monthly records of products a customer has, such as "credit card", "savings account", etc. We will predict what additional products a customer will get in the last month, 2016-06-28, in addition to what they already have at 2016-05-28. These products are the columns named: ind_(xyz)_ult1, which are the columns #25 - #48 in the training data. We will predict what a customer will buy in addition to what they already had at 2016-05-28.
The test and train sets are split by time.


### ML formulation of the business problem:
It is a Recommender System problem and based on given past customer-product interaction we need to recommend bank products to existing customers.
All Submissions are evaluated according to the Mean Average Precision@7 (MAP@7) i.e model is evaluated based on the top 7 recommendations.

### Business constraints:
1.	No strict latency concerns
2.	Interpretability is partially important.
3.	Wrong recommendations can be costly.
4.	Few users can cause cold start problem.

### Data set column analysis:
*  Column 1 is the date.
* 	Columns 2 to 24 are Customer demographic data.
*	Columns 25 to 48 are bank products.

| Column Name | Description |
| ------------- | ------------- |
| fecha_dato  | The table is partitioned for this column  |
| ncodpers  | Customer code  |
| ind_empleado  | Employee index: A active, B ex employed, F filial, N not employee, P pasive  |
| pais_residencia  | Customer's Country residence  |
| sexo  | Customer's sex  |
| age  | Age  |
|fecha_alta | The date in which the customer became as the first holder of a contract in the bank|
|ind_nuevo |	New customer Index. 1 if the customer registered in the last 6 months.|
||antiguedad, |	Customer seniority (in months)|
|indrel |	1 (First/Primary), 99 (Primary customer during the month but not at the end of the month)|
|ult_fec_cli_1t |	Last date as primary customer (if he isn't at the end of the month)|
|indrel_1mes |	Customer type at the beginning of the month ,1 (First/Primary customer), 2 (co-owner ),P (Potential),3 (former primary), 4(former co-owner)|
|tiprel_1mes |	Customer relation type at the beginning of the month, A (active), I (inactive), P (former customer),R (Potential)|
|indresi |	Residence index (S (Yes) or N (No) if the residence country is the same than the bank country)|
|indext |	Foreigner index (S (Yes) or N (No) if the customer's birth country is different than the bank country)|
|conyuemp |	Spouse index. 1 if the customer is spouse of an employee|
|canal_entrada |	channel used by the customer to join|
|indfall |	Deceased index. N/S|
|tipodom |	Addres type. 1, primary address|
|cod_prov |	Province code (customer's address)|
|nomprov |	Province name|
|ind_actividad_cliente |	Activity index (1, active customer; 0, inactive customer)|
|renta |	Gross income of the household|
|segmento |	segmentation: 01 - VIP, 02 - Individuals 03 - college graduated|
|ind_ahor_fin_ult1 |	Saving Account|
|ind_aval_fin_ult1 |	Guarantees|
|ind_cco_fin_ult1 |	Current Accounts|
|ind_cder_fin_ult1 |	Derivada Account|
|ind_cno_fin_ult1 |	Payroll Account|
|ind_ctju_fin_ult1 |	Junior Account|
|ind_ctma_fin_ult1 |	Más particular Account|
|ind_ctop_fin_ult1 |	particular Account|
|ind_ctpp_fin_ult1 |	particular Plus Account|
|ind_deco_fin_ult1 |	Short-term deposits|
|ind_deme_fin_ult1 |	Medium-term deposits|
|ind_dela_fin_ult1 |	Long-term deposits|
|ind_ecue_fin_ult1 |	e-account|
|ind_fond_fin_ult1 |	Funds|
|ind_hip_fin_ult1 |	Mortgage|
|ind_plan_fin_ult1 |	Pensions|
|ind_pres_fin_ult1 |	Loans|
|ind_reca_fin_ult1 |	Taxes|
|ind_tjcr_fin_ult1 |	Credit Card|
|ind_valo_fin_ult1 |	Securities|
|ind_viv_fin_ult1 |	Home Account|
|ind_nomina_ult1 |	Payroll|
|ind_nom_pens_ult1 |	Pensions|
|ind_recibo_ult1 |	Direct Debit|

