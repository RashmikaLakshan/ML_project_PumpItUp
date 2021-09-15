# ML_project_PumpItUp

## Preprocessing
### 1. Handling missing values

* Handling missing values in data set by adding 'Unknown' or 'mean value of the column' or most frequent value
    ex- 
    1. NaNs of installer, and funder columns, fill with 'Unknown'
    2. NaNs of public_meeting, and permit columns, fill with most frequent boolean value
    3. NaNs of latitude, longitude, population, and construction_year columns, fill with mean value

* drop rows from training dataset where status_group column is NaN



### 2. Feature Engineering
#### Creating New Features
* created new features with following column names. decade, year_recorder, month_recorder, yearly_week_recorder, weekday_recorder, and age

#### Feature Selection
* create Heat-map to identify correlation between numerical columns (considered mutual information for feature selection)

* Object type features which had considerable Nan values, are dropped
    ex- 
    1. scheme_management had 3000 NaN values
    2. amount_tsh had 70% of zeros
    3. num_private had 98% of zeros

* some features were dropped due to similarities of between features or features with lot of small values compared to the other features or importance with the problem or decompose features into sub features.
    
    ex- 
    1. Since payment and payment_type have same details, payment_type had been dropped due to less impact compared to the payment feature
    2. Since waterpoint_type and waterpoint_type_group have same details, waterpoint_type_group had been dropped due to less impact compared to the waterpoint_type feature
    3. Since quantity and quantity_group have same details, quantity_group had been dropped due to less impact compared to the quantity feature
    4. Since quantity and quantity_group have same details, quantity_group had been dropped due to less impact compared to the quantity feature
    5. Since source_type, source and source_class have same data representations, source_class and source_type had been dropped due to less impact compared to the source feature
    6. Since water_quality and quality_group have same details, quality_group had been dropped due to less impact compared to the water_quality feature
    7. Since management_group and management_group have same details, management_group had been dropped due to less impact compared to the management feature
    8. Since extraction_type, extraction_type_class and extraction_type_group have same data representations, extraction_type_class and extraction_type_group had been dropped due to less impact compared to the extraction_type feature
    9. subvillage had been dropped because of it has 19287 different values. also region and region_code provide similar geographical information
    10. wpt_name, and scheme_name had been dropped due to bunch of unique string values.
    11. date_recorded had been dropped due to decompose that feature into 5 sub features namely year_recorder, month_recorder, yearly_week_recorder, weekday_recorder, and age
    12. recorded_by had been dropped because of all the values are same



### 3. Encoding

* Use **Label Encoding** for categorical features.

* One-Hot encoding raised up the complexity of preprocessing due to creating bunch of columns related to catagories of columns. In addition to that, using One-Hot encoding, reached low validation accuracy than label encoding. 



### 4. Normalization

