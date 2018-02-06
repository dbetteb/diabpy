# Statistics function for diabpy

## Definition of important terms

### Scales of measurement for glycemia

Depending in the country Blood Glucose levels are measured in `mg/dL` or
in `mmol/L`. One major advantage of `diabpy` is that it is adimensionnalized, in the sense that it does not assume a specific scale has been used, it is however capable of switching and guessing what scales have been used and suggests to switch if results seem unrealistic.

```python
from diabpy.base import Glyc
glyc = Glyc.loader('data/GlycemiaLevels.csv')
```

will import and create an instance of `diabpy` `Glyc`, doing so, it will check for consistency, whenever glycemia levels seem unrealistic it would ask the user to confirm the scale

```python
glyc = Glyc.loader('data/GlycemiaLevelsWeird.csv')
glyc.report()
>> Scale do not appear clearly, can you confirm what scale is used ? 
Possible choices are {'mmol/L','mg/dL','mmol/dL','g/L','mg/L'} or enter a new
unit with the following format 'x/y' where x refers to g or mmol and y to liter capacity.
Format used :
```



### Blood Glucose Indexes

**Low Blood Glucose Index** and **High Blood Glucose Index** are common indices to represent the occurence of hypoglycemia and hyperglycemia events. One key feature of LBGI and HBGI is to account
for the non symmetry of glycemia measures. Typically, in `mg/DL` low glycemia range between 20 and 70 while hyperglycemia can go up from 250 to more than 550 (depending on the device).





