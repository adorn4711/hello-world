
## Current situation

Today the credentials `AP0R326P` and `VM00685P` are owned by iERP teams, but used by the PDO Tax team to read the data
| Interface              | Account     | Reports to | Sponsor  | CDV View |
| ---------------------- | -------     | ---------- | -------- | --------- 
| I00733 Payable Details | AP0R326P    | RKARTH39   | HLOGANAT | ZDV_PTR_TDH_PAY |
| I00685 Vendor Master   | VM00685P    | DPINNAMA   | JBAJI    | ZDV_STP_TAXBS


```mermaid
flowchart LR
    I00733(iERP system I00733)--AP0R326P -->ViewI00733( View ZDV_PTR_TDH_PAY)
    ViewI00733--AP0R326P-->IICS(Informatica Tax PDO)
    I00685(iERP system I00685)--VM00685P -->ViewI00685(View ZDV_STP_TAXBS)
    ViewI00685--VM00685P -->IICS
```    

## Future situation

PDO Tax Team has own credentials for reading the view

### Write access
| Interface              | Account     | Reports to | Sponsor  | CDV View |
| ---------------------- | -------     | ---------- | -------- | --------- 
| I00733 Payable Details | AP0R326P    | RKARTH39   | HLOGANAT | ZDV_PTR_TDH_PAY |
| I00685 Vendor Master   | VM00685P    | DPINNAMA   | JBAJI    | ZDV_STP_TAXBS

### Read access solution (one account for PDO Tax Team to read data) (preferred solution)

| Interface              | Account    | Reports to | Sponsor  | CDV View |
| ---------------------- | -------    | ---------- | -------- | --------- 
| I00733 Payable Details | TX0R326P    | GWAGNER9   | GWAGNER9 | ZDV_PTR_TDH_PAY |
| I00685 Vendor Master   | TX0R326P    | GWAGNER9   | GWAGNER9 | ZDV_STP_TAXBS

Dana already requested the accounts TX0R326P, TX0R326U, TX0R326Q, TX0R326D

```mermaid
flowchart LR
    I00733(iERP system I00733)--AP0R326P -->ViewI00733( View ZDV_PTR_TDH_PAY)
    ViewI00733-- TX0R326P -->IICS(Informatica Tax PDO)
    I00685(iERP system I00685)--VM00685P -->ViewI00685(View ZDV_STP_TAXBS)
    ViewI00685-- TX0R326P -->IICS
```    

### Read access solution (several accounts for PDO Tax Team to read data) 
| Interface              | Account    | Reports to | Sponsor  | CDV View |
| ---------------------- | -------    | ---------- | -------- | --------- 
| I00733 Payable Details | TAX733P    | GWAGNER9   | GWAGNER9 | ZDV_PTR_TDH_PAY |
| I00685 Vendor Master   | TAX685P    | GWAGNER9   | GWAGNER9 | ZDV_STP_TAXBS

```mermaid
flowchart LR
    I00733(iERP system I00733)--AP0R326P -->ViewI00733( View ZDV_PTR_TDH_PAY)
    ViewI00733-- TAX733P -->IICS(Informatica Tax PDO)
    I00685(iERP system I00685)--VM00685P -->ViewI00685(View ZDV_STP_TAXBS)
    ViewI00685-- TAX685P -->IICS

```    
