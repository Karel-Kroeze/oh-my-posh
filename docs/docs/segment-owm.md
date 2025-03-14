---
id: owm
title: Open Weather Map
sidebar_label: Open Weather Map 
---

## What

Shows the current weather of a given location.

:::caution

You **must** request an API key at the [Open Weather Map](https://openweathermap.org/price) website.
The free tier for *Current weather and forecasts collection* is sufficient.

:::

## Sample Configuration

```json
{
  "type": "owm",
  "style": "powerline",
  "powerline_symbol": "\uE0B0",
  "foreground": "#ffffff",
  "background": "#FF0000",
  "properties": {
    "apikey": "<YOUR_API_KEY>",
    "location": "AMSTERDAM,NL",
    "units": "metric",
    "enable_hyperlink" : false,
    "format": "%s (%g%s)",
    "http_timeout": 20
  }
}
```

## Properties

- apikey: `string` - Your apikey from [Open Weather Map](https://openweathermap.org)
- location: `string` - The requested location.
                        Formatted as <City,STATE,COUNTRY_CODE>. City name, state code and country code divided by comma.
                        Please, refer to ISO 3166 for the state codes or country codes - defaults to `DE BILT,NL`
- units: `string` - Units of measurement.
                    Available values are standard (kelvin), metric (celsius), and imperial (fahrenheit) - defaults to `standard`
- enable_hyperlink: `bool` - Displays an hyperlink to get openweathermap data
- format: `string` - The format string used to generate text. Defaults to `%s (%g%s)`, receiving the current weather icon,
temperature, and temperature unit as arguments. See [the Go `fmt` docs](https://pkg.go.dev/fmt) for details.
- http_timeout: `int` - The default timeout for http request is 20ms.
