# Auto dataset

## Summary

- **File name**                 : C:/Program Files/Stata17/ado/base/a/auto.dta 
- **File size**                 : 15 KB
- **Description**               : 1978 automobile data                         
- **Source**                    : [Stata Corp](https://www.stata.com/manuals/dsysuse.pdf) *note that there is a link to more documentation. this could be a folder with questionnaires and field notes, or the data provider's original documentation*
- **Unit of observation**       : Automobile make and model                    
- **Key**                       : `make`                                       
- **Number of observations**    : 74 
- **Related code**              : created by `code/import/import-auto.do`, used by `code/analysis/summary-stats.do`                                          
- **Data collection frequency** :                                              
- **Data collection period**    : 1978                                         
- **Geographic coverage**       : United States
- **Languages**                 : English                                                                    
- **Weights**                   :   
- **Description of methods for data collection or generation**:
  - [Data provider's original documentation](https://www.stata.com/manuals/dsysuse.pdf)
  - Field manual
  - Survey instrument
  - Questionnaire form
  - Field notes
  - Quality assurance protocols
  - Sampling design and procedure                                          

## Variable dictionary

*If the dataset has too many variables, include only the main ones below*

| Name           | Description            | Type        | Unit              | Categories                |
|----------------|------------------------|-------------|-------------------|---------------------------|
| `make`         | Make and model         | Text        |                   |                           |
| `price`        | Price                  | Continuous  | US Dollars        |                           |
| `mpg`          | Mileage (mpg)          | Continuous  | Miles per gallon  |                           |
| `rep78`        | Repair record 1978     | Continuous  |                   |                           |
| `headroom`     | Headroom (in.)         | Continuous  | Inches            |                           |
| `trunk`        | Trunk space (cu. ft.)  | Continuous  | Cubic feet        |                           |
| `weight`       | Weight (lbs.)          | Continuous  | Pounds            |                           |
| `length`       | Length (in.)           | Continuous  | Inches            |                           |
| `turn`         | Turn circle (ft.)      | Continuous  | Feet              |                           |
| `displacement` | Displacement (cu. in.) | Continuous  | Cubic inches      |                           |
| `gear_ratio`   | Gear ratio             | Continuous  |                   |                           |
| `foreign`      | Car origin             | Binary      |                   | 0 Domestic <br> 1 Foreign |
