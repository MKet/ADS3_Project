# ADS3_Project
```py
df_average = df
average = ["PREV_POLY_INFORCE_QTY","POLY_INFORCE_QTY", "NB_WRTN_PREM_AMT", "WRTN_PREM_AMT", "PRD_ERND_PREM_AMT"]
for index, row in df_average.iterrows():
    for col in average:
        if(row[col] == 0):
            try:
                newvalue = df_average[(df_average["STATE_ABBR"] ==row["STATE_ABBR"])and (df_average["PROD_LINE"] == row["PROD_line"])].mean()
            except(ValueError): #No average can be found since its all 0
                newvalue = 0 
            df_average.set_value(index, col, newvalue)
df_average.head(10)
```
