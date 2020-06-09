# dod-excess-property-transfers

### About this data
Each quarter the U.S. Department of Defense releases data on military property transfers to police agencies throughout the United States.

Agencies can request surplus data from the Defense Logistic Agency's Law Enforcement Support Office. Agencies can request items as small as bandages and as large as mine-resistant vehicles or aircraft. The items are released at no cost to law enforcement agencies. 

Investigative Reporters & Editors is making this data available as a public service to journalists covering police agencies throughout the United States. The data is freely available from the [Department of Defense](https://www.dla.mil/DispositionServices/Offers/Reutilization/LawEnforcement/PublicInformation/) but the nature of the Excel file can make it difficult to easily navigate.

The only work IRE has done is to combine these records into a single CSV file. There are other tables available at the web link above, including information about ammunition transfers as well as cancelled orders. If you find problems with this data, you will need to contact the Defense Logistic Agency for clarification.

### Some specific notes about the data
The [original file](https://www.dla.mil/Portals/104/Documents/DispositionServices/LESO/DISP_AllStatesAndTerritories_03312020.xlsx) is an Excel workbook with 53 sheets. According to the agency's website, the data was initially posted in 2017. However, there are records dating back to the 1990s.

The readxl package from R was used to import the data and combine all of the records from 53 sheets into one file. There are 141,068 records in total.

#### Included fields

Field | Information
------------ | -------------
state | Two-letter postal abbreviation for the U.S. state or territory.
station_name_lea | The name of the agency receiving the item.
nsn | The 'National Stock Number' of the item. [Additional information](https://www.dla.mil/Portals/104/Documents/SmallBusiness/NSN Info.pdf)
item_name | The name of the item distributed to an agency.
quantity | The count of the item distributed. See the field `ui` for additional context.
ui | The unit of the count.
acquisition_value | Amount the military paid for the property when it was first acquired. [Source](https://www.dla.mil/DispositionServices/Offers/Reutilization/LawEnforcement/ProgramFAQs.aspx)
demil_code |Indicates the required level of destruction needed to release the item to an agency. [Additional information] (https://www.dla.mil/HQ/LogisticsOperations/Services/FIC/DEMILCoding/DEMILCodes/)
demil_ic | Demil Integrity Code. Values in the data include 0,1,3,4,5,6,7
ship_date | The date the item was shipped to an agency.
station_type | All values are "state"
