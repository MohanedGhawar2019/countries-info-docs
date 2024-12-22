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

## Language-Specific APIs

### JavaScript/Node.js

#### Functions
- `getAllCountries()`
- `getCountryByName(name: string)`
- `getCountryByCode(code: string)`

#### Return Types
- Array of country objects
- Single country object or null

### Python

#### Functions
- `get_all_countries()`
- `get_country_by_name(name: str)`
- `get_country_by_code(code: str)`

#### Return Types
- List of dictionaries
- Single dictionary or None

### PHP

#### Methods
- `getAllCountries()`
- `getCountryByName(string $name)`
- `getCountryByCode(string $code)`

#### Return Types
- Array of associative arrays
- Single associative array or null

### .NET (C#)

#### Methods
- `GetAllCountries()`
- `GetCountryByCode(string code)`
- `GetCountriesByContinent(string continent)`

#### Return Types
- `IEnumerable<Country>`
- `Country?`

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
