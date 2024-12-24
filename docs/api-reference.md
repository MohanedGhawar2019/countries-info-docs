# API Reference

This document details the API for all language implementations of the Countries Info library.

## Common Features

All implementations share these core features:

### Get All Countries
Returns an array/list of all countries with their complete information.

### Get Country by Name
Retrieves a single country's information by its name (case-insensitive).

### Get Country by Code
Retrieves a single country's information by its ISO code (case-insensitive).

### Get Countries by Continent
Returns an array of countries in the specified continent.

### Search Countries by Name
Returns an array of countries whose names contain the search term.

### Get Country Regions
Returns an array of region names for the given country code.

### Get Cities by Region
Returns an array of cities in a specific region of a country.

### Get All Cities in Country
Returns an array of all cities in a country.

### Get City Count
Returns the total number of cities in a country.

### Search Cities
Search for cities across all countries.

## Language-Specific APIs

### JavaScript/Node.js

#### Functions
- `getAllCountries()`
- `getCountryByName(name: string)`
- `getCountryByCode(code: string)`
- `getCountriesByContinent(continent: string)`
- `searchByName(query: string)`
- `getCountryRegions(countryCode: string)`
- `getCitiesByRegion(countryCode: string, regionName: string)`
- `getAllCitiesInCountry(countryCode: string)`
- `getCityCount(countryCode: string)`
- `searchCities(name: string)`

#### Return Types
- Array of country objects
- Single country object or null
- Array of region names
- Array of cities
- Number

### Python

#### Functions
- `get_all_countries()`
- `get_country_by_name(name: str)`
- `get_country_by_code(code: str)`
- `get_countries_by_continent(continent: str)`
- `search_by_name(query: str)`
- `get_country_regions(country_code: str)`
- `get_cities_by_region(country_code: str, region_name: str)`
- `get_all_cities_in_country(country_code: str)`
- `get_city_count(country_code: str)`
- `search_cities(name: str)`

#### Return Types
- List of dictionaries
- Single dictionary or None
- List of region names
- List of cities
- Number

### PHP

#### Methods
- `getAllCountries()`
- `getCountryByName(string $name)`
- `getCountryByCode(string $code)`
- `getCountriesByContinent(string $continent)`
- `searchByName(string $query)`
- `getCountryRegions(string $countryCode)`
- `getCitiesByRegion(string $countryCode, string $regionName)`
- `getAllCitiesInCountry(string $countryCode)`
- `getCityCount(string $countryCode)`
- `searchCities(string $name)`

#### Return Types
- Array of associative arrays
- Single associative array or null
- Array of region names
- Array of cities
- Number

### .NET (C#)

#### Methods
- `GetAllCountries()`
- `GetCountryByCode(string code)`
- `GetCountriesByContinent(string continent)`
- `SearchByName(string query)`
- `GetCountryRegions(string countryCode)`
- `GetCitiesByRegion(string countryCode, string regionName)`
- `GetAllCitiesInCountry(string countryCode)`
- `GetCityCount(string countryCode)`
- `SearchCities(string name)`

#### Return Types
- `IEnumerable<Country>`
- `Country?`
- `IEnumerable<string>`
- `IEnumerable<City>`
- `int`

## Error Handling

### JavaScript
```javascript
// Returns null if country not found
const country = getCountryByName('NonExistentCountry');
if (country === null) {
    console.log('Country not found');
}
```

### Python
```python
# Returns None if country not found
country = get_country_by_name('NonExistentCountry')
if country is None:
    print('Country not found')
```

### PHP
```php
// Returns null if country not found
$country = $countriesInfo->getCountryByName('NonExistentCountry');
if ($country === null) {
    echo 'Country not found';
}
```

### C#
```csharp
// Returns null if country not found
var country = service.GetCountryByCode("XX");
if (country == null)
{
    Console.WriteLine("Country not found");
}
```

## Response Format

All APIs return data in this consistent format:

```json
{
  "name": "String",
  "code": "String",
  "capital": "String",
  "continent": "String",
  "population": Number,
  "area": Number
}
```

## Rate Limits and Performance

- No rate limits (data is bundled)
- Responses are instantaneous
- Memory usage is minimal
- No network calls required

## Best Practices

1. Cache results when making multiple queries
2. Use ISO codes for precise matching
3. Handle null/None returns appropriately
4. Use case-insensitive search functions

## Data Types

### Country Object
```typescript
interface Country {
  name: {
    common: string;
    official: string;
  };
  codes: {
    iso2: string;
    iso3: string;
  };
  capital: string;
  continent: string;
  population: number;
  area: number;
}
```

### City Object
```typescript
interface City {
  name: string;
  latitude: string;
  longitude: string;
  population: number;
  countryCode?: string;  // Included in searchCities results
  regionName?: string;   // Included in searchCities results
}
```

## Language-Specific Notes

### JavaScript/Node.js
- All methods are synchronous
- Case-insensitive search
- ES6 module and CommonJS support

### PHP
- All methods return null instead of undefined
- Case-insensitive search
- PSR-4 autoloading support

### C#
- Methods follow C# naming conventions (PascalCase)
- Strong typing with nullable reference types
- LINQ-friendly collections
