# API Documentation: ePark Statistics
ePARK api documentation for statistics

# Version 1.1.2

> *Last updated: 2023-11-21*
> 

The ePark Statistics API allows to fetch different types of statistics regarding parking sessions. All requests are sent to the base URL: **[https://eparkera.se/api/v1/statistics](https://eparkera.se/api/v1/statistics)**.

**Authentication**: Barer Token

**Response:** JSON

---

## **Endpoints**

### **Occupancy**

Endpoint: **`/occupancy`**

HTTP Method: **`POST`**

Get current occupancy of one or several zones, or in a specific time period.

### Request Parameters

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| zone_id | int | No | A unique ePARK internal identifier for the zone |
| public_zone_code | string | No | Public identifier for the zone |
| from | UTC Date (Y-m-dTH:i:s+00:00) | No | Date from. Iso8601String |
| to | UTC Date (Y-m-dTH:i:s+00:00) | NO | The ending time of the parking ticket. Iso8601String |

### Response

The response body contains the details of the zone

| Parameter | Type | Description |
| --- | --- | --- |
| zone_id | int | A unique ePARK internal identifier for the zone. |
| public_zone_code | string | Public identifier for the zone |
| title | string | The zone title |
| occupancy | int | The number of active parking session |

```
{
  "zone_id": 1234,
  "public_zone_code": "321",
  "title": "My zone",
  "occupancy": 32 
}
```


---
