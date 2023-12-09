# Weather-Forecast-API-Documentation
# INTRODUCTION

### Welcome to the Weather Forecast API documentation. This API provides access to current weather conditions and forecasts for locations worldwide.

Base URL: `https://api.weatherforecast.com`

# Authentication

### To access the Weather Forecast API, you'll need an API key. You can obtain your API key by signing up on our website `www.weatherforecast.com` and generating an API key from your account dashboard.

### Include your API key in the request header:

```
Authorization: Bearer YOUR_API_KEY
```

# Endpoints
## Get Current Weather

Retrieve current weather conditions for a specific location.
- Endpoint: `/current`
- Method: `GET`
- Parameters:
  - location: City name or coordinates (latitude, longitude)

- Example Request:
  ```
  GET /current?location=New+York HTTP/1.1
  Host: api.weatherforecast.com
  Authorization: Bearer YOUR_API_KEY
  ```
- Example Response:
  ``` json
  {
   "location": "New York",
   "temperature": 15,
   "description": "Cloudy",
   "humidity": 75,
   "wind_speed": 10,
   "wind_direction": "NE"
  }
  ```
## Get Weather Forecast

Retrieve a 7-day weather forecast for a specific location.
- Endpoint: `/forecast`
- Method: `GET`
- Parameters:
  - location: City name or coordinates (latitude, longitude)

- Example Request:
  ```
  GET /forecast?location=London HTTP/1.1
  Host: api.weatherforecast.com
  Authorization: Bearer YOUR_API_KEY
  ```
- Example Response:
  ``` json
  {
  "location": "London",
  "forecast": [
    {
      "date": "2023-12-10",
      "temperature_max": 12,
      "temperature_min": 5,
      "description": "Rainy"
    },
    {
      "date": "2023-12-11",
      "temperature_max": 10,
      "temperature_min": 4,
      "description": "Cloudy"
    },
    // ... (forecast for the next 7 days)
  ]
  }
  ```
# Rate Limits
- The API has a rate limit of 1000 requests per day per API key.
# Errors
The API uses standard HTTP status codes to indicate the success or failure of a request. Error responses include a JSON body with additional information about the error.

- Example error response:
``` json
{
  "error": {
    "code": 404,
    "message": "Location not found"
  }
}

```
# Conclusion
### Thank you for using the Weather Forecast API. For more detailed information on request parameters and response formats, please refer to our comprehensive API documentation available at `developer.weatherforecast.com`.
