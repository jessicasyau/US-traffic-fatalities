This file documents the data element definitions and codes seen as the column headers in the FARS_accident_2019 csv. To view the original full document click [here](https://crashstats.nhtsa.dot.gov/Api/Public/ViewPublication/813254).

### STATE
- Identifies the State in which the crash occurred.
- ![state_codes](state_codes.jpg)

### STATENAME
- Identifies the name of the state in which the crash occurred.
- String

### ST_CASE	
- The unique case number assigned to each crash.
- [x]xxxxx - [one]/two characters for state code followed by four characters for case number

### VE_TOTAL
- The number of contact motor vehicles that the officer reported on the police crash report as a unit involved in the crash. This includes vehicles in transport and vehicles not in transport (i.e. parked vehicles)
- 1-999

### VE_FORMS
- Number of Vehicle Forms Submitted- ALL 
- Number of Motor Vehicles in Transport (MVIT) 
- A count of the number of motor vehicles in transport involved in the crash. Legally parked vehicles are not included.
- 1-999

### PVH_INVL
- Number of Parked/Working Vehicles
- A count of the number of parked and working vehicles involved in the crash.
- 0-999

### PEDS
- Number of Forms Submitted for Persons Not in Motor Vehicles
- The number of Person Forms (Not a Motor Vehicle Occupant) that are applicable to this case (i.e., non-occupants).
- 0-99

### PERSONS
- Number of Forms Submitted for Persons in Motor Vehicles 
- A count of the number of Person Level (Motor Vehicle Occupant) Forms that are applicable to this case (i.e., occupants).
- 0-999

### PERMVIT
- Number of Persons in Motor Vehicles in Transport (MVIT) 
- A count of the number of motorists in the crash. A motorist is a driver, passenger or unknown occupant type of a motor vehicle in transport.
- 0-999

### PERNOTMVIT
- Number of Persons Not in Motor Vehicles in Transport (MVIT) 
- A count of the number of non-motorists in the crash. A non-motorist is defined as a pedestrian, a cyclist, an occupant of a motor vehicle not in transport, a person riding a horse, an occupant of an animal drawn conveyance, person associated with non-motorist conveyance (e.g., baby carriage, skate board, wheelchair), or an other non-motorist (e.g., person outside a trafficway, person in a house). 
- 0-98

### COUNTY
- The location of the unstabilized event with regard to the County. The codes are from the General Services Administration’s (GSA) publication of worldwide Geographic Location Codes (GLC).
- ![county_description_codes](county_description_codes.jpg)

### COUNTYNAME
- xxx(xx) - The name of the county (code from the COUNTY field)

### CITY
- The location of the unstabilized event with regard to the City. The codes are from the General Services Administration’s (GSA) publication of worldwide Geographic Location Codes (GLC). 
- ![city_description_codes](city_description_codes.jpg)

### CITYNAME
- Name of the city

### DAY


DAYNAME


### MONTH
- The month in which the crash occurred.
- ![month_description_codes](month_description_codes.jpg)


MONTHNAME


YEAR


DAY_WEEK


DAY_WEEKNAME


HOUR


HOURNAME


MINUTE


MINUTENAME


NHS


NHSNAME


ROUTE


ROUTENAME


TWAY_ID	TWAY_ID2


RUR_URB	RUR_URBNAME


FUNC_SYS


FUNC_SYSNAME


RD_OWNER


RD_OWNERNAME


MILEPT


MILEPTNAME


LATITUDE


LATITUDENAME


LONGITUD	


LONGITUDNAME


SP_JUR


SP_JURNAME


HARM_EV


HARM_EVNAME


MAN_COLL


MAN_COLLNAME


RELJCT1


RELJCT1NAME


RELJCT2


RELJCT2NAME


TYP_INT


TYP_INTNAME


WRK_ZONE


WRK_ZONENAME


REL_ROAD


REL_ROADNAME


LGT_COND


LGT_CONDNAME


WEATHER1


WEATHER1NAME


WEATHER2


WEATHER2NAME


WEATHER


WEATHERNAME


SCH_BUS


SCH_BUSNAME


RAIL


RAILNAME


NOT_HOUR


NOT_HOURNAME


NOT_MIN


NOT_MINNAME


ARR_HOUR


ARR_HOURNAME


ARR_MIN


ARR_MINNAME


HOSP_HR


HOSP_HRNAME


HOSP_MN


HOSP_MNNAME


CF1


CF1NAME


CF2


CF2NAME


CF3


CF3NAME


FATALS


DRUNK_DR
