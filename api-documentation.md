### HTTP response example:

```json
    {
		"id": "00045991_131410404514665070",
		"md5": "c2d3fc4c26dbf6dde3eb04741da7a421",
		"label": "gov_payments.pdf",
		"createdDate": "2020-11-17T20:06:15.822Z",
		"data": [{
			"createdDate": "2020-11-02T00:00:00.000Z",
			"periodMonth": 10,
			"periodYear": 2020,
			"paymentNumber": 1,
			"groupNumber": 10,
			"groupName": "מעונות יום מגזר חרדי",
			"districtNumber": 4,
			"districtName": "תל אביב",
			"organizationNumber": 111,
			"organizationName": "שם של הרשת",
			"cityNumber": 8500,
			"cityName": "אשדוד",
			"dayCareNumber": 1125,
			"dayCareName": "שם של המעון",
			"records": [{
					"totalParticipation": 1624,
					"plusHourParticipationInclPayback": null,
					"tuitionParticipationInclPayback": 1624,
					"plusHourParticipationExclPayback": null,
					"tuitionParticipationExclPayback": 1624,
					"totalParent": 1071,
					"totalTuition": 2695,
					"forcedLevel": false,
					"left": false,
					"entered": false,
					"level": 3,
					"hasLevel": true,
					"childId": "999999999",
					"motherName": "שם של אמא",
					"registrationDate": "2020-09-01T00:00:00.000Z",
					"birthday": "2019-07-09T00:00:00.000Z",
					"firstName": "שם פרטי",
					"lastName": "שם משפחה",
					"isBaby": false,
					"retro": null,
					"isOverLimit": false
				},
				{
					"totalParticipation": 2238,
					"plusHourParticipationInclPayback": null,
					"tuitionParticipationInclPayback": 2238,
					"plusHourParticipationExclPayback": null,
					"tuitionParticipationExclPayback": 1119,
					"totalParent": 3152,
					"totalTuition": 2695,
					"forcedLevel": false,
					"left": false,
					"entered": false,
					"level": 5,
					"hasLevel": true,
					"childId": "999999999",
					"motherName": "שם של אמא",
					"registrationDate": "2020-09-01T00:00:00.000Z",
					"birthday": "2020-01-06T00:00:00.000Z",
					"firstName": "שם פרטי",
					"lastName": "שם משפחה",
					"isBaby": false,
					"retro": {
						"date": "2020-09-01T00:00:00.000Z",
						"months": [{
							"level": 5,
							"month": 9,
							"hasPlusHour": false,
							"plusHourLevel": null
						}]
					},
					"isOverLimit": false
				}
			]
		}]
	}
```

### Response description

##### Description of the fields of a file


| Field name | Type | Description |
| ------------- | ------------- | ------------- | 
| id | String | A unique auto-generated ID for each response |
| md5 | String | Calculated MD5 value of the file |
| label | String | Original file name |
| createdDate | Date | Date of creation of the response |
| data | Array | An array that contains the payments according to each number of symbol that appeared in the file |

##### Description of the fields of a symbol


| Field name | Type  | Description |
| ------------- | ------------- | ------------- | 
| createdDate | Date  | Production date that appears at the top of the page. Described as:  |תאריך הפקה
| periodMonth | Number  | Number of the month of report period. Appears in the page title |
| periodYear | Number  | Number of the year of report period. Appears in the page title |
| paymentNumber | Number  | Payment number. Appears in the page title. Described as:  |מספר תשלום
| groupNumber | Number  | Group number. Described as:  |קבוצה
| groupName | String  | Group name. Described as:  |קבוצה
| districtNumber | Number  |  District number. Described as:  |מחוז
| districtName | String  |  District name. Described as:  |מחוז
| organizationNumber | Number  | Organization number. Described as:  |ארגון
| organizationName | String  | Organization name. Described as:  |ארגון
| cityNumber | Number  | City number. Described as:  |יישוב
| cityName | String  | City name. Described as:  |יישוב
| dayCareNumber | Number  | Day care number. Described as:  |מעון
| dayCareName | String  | Day care name. Described as:  |מעון
| records | Array  | An array that contains the payments |

##### Description of the fields of a payment


| Field name | Type  | Description |
| ------------- | ------------- | ------------- | 
| totalParticipation | Decimal  | Total participation. Described as:  |סהכ השתתפות
| plusHourParticipationInclPayback | Decimal  | Total government includes payback for  extra hour. Described as:  |השתתפות המשרד כולל החזר - השתתפות בשעה נוספת
| tuitionParticipationInclPayback | Decimal  | Total government includes payback for  tuition Described as:  |השתתפות המשרד כולל החזר - השתתפות בשכר לימוד
| plusHourParticipationExclPayback | Decimal  | Total government excludes payback for  extra hour. Described as:  |השתתפות המשרד לא כולל החזר - השתתפות בשעה נוספת
| tuitionParticipationExclPayback | Decimal  | Total government excludes payback for  tuition Described as:  |השתתפות המשרד לא כולל החזר - השתתפות בשכר לימוד
| totalParent | Decimal  | Parents payment. Described as:  |תשלום הורים
| totalTuition | Decimal  | tuition payment. Described as:  |תשלום שכר לימוד
| forcedLevel | Bool  | Forced level. When the symbol * appears next to the level. Described as:  |דרגת כפייה
| left | Bool  | Forced level. When the symbol # appears without a level. Described as:  |עבר למעון אחר
| entered | Bool  | Forced level. When the symbol # appears next to the level. Described as:  |עבר ממעון אחר
| level | Number  | The level of the child |
| hasLevel | Bool  | A value that indicates whether a level appears for the child |
| childId | String  | The Id of the child |
| motherName | String  | The mother name |
| registrationDate | Date  | Date of entry to the day care. Described as:  |תאריך כניסה למעון
| birthday | Date  | The birthday date of the child |
| firstName | String  | The first name of the child |
| lastName | String  | The last name of the child |
| isBaby | Bool  | A value indicating whether the child is a baby. Described as:  |תעריף תינוק
| retro | Array  | An array that contains the retro months |
| isOverLimit | Bool  | A value indicating whether the child is above the quota of the daycare limit. Described as:  |ילדים מעל מכסה

##### Description of the fields of a retro


| Field name | Type  | Description |
| ------------- | ------------- | ------------- | 

| date | Date  | Retro start date. Described as:  |רטרו
| months | Array  | An array that contains the months |

##### Description of the fields of a retro month


| Field name | Type  | Description |
| ------------- | ------------- | ------------- | 
| level | Number  | The level of the child |
| month | Number  | The number of month |
| hasPlusHour | Date  | A value that indicates whether there is a level for an extra hour |
| plusHourLevel | Date  | The level for the extra hour |
