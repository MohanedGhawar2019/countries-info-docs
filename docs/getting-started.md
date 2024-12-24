# Getting Started with Countries Info

Countries Info is a comprehensive library for accessing detailed country information, including regions, cities, capitals, continents, and more. Available for JavaScript/Node.js, PHP, and C#.

## Installation

### JavaScript/Node.js
```bash
npm install @mohaned.ghawar/countries-info
```

### PHP
```bash
composer require mohanedghawar/countries-info
```

### C#
```bash
dotnet add package CountriesInfo
```

## Quick Start

### JavaScript/Node.js
```javascript
const CountriesService = require('@mohaned.ghawar/countries-info');

const service = new CountriesService();

// Get all countries
const countries = service.getAllCountries();

// Get cities in California, USA
const californiaCities = service.getCitiesByRegion('USA', 'California');

// Search for cities named "Paris"
const parisCities = service.searchCities('Paris');
```

### PHP
```php
use MohanedGhawar\CountriesInfo\CountriesInfo;

$service = new CountriesInfo();

// Get all countries
$countries = $service->getAllCountries();

// Get cities in California, USA
$californiaCities = $service->getCitiesByRegion('USA', 'California');

// Search for cities named "Paris"
$parisCities = $service->searchCities('Paris');
```

### C#
```csharp
using CountriesInfo;

var service = new CountriesService();

// Get all countries
var countries = service.GetAllCountries();

// Get cities in California, USA
var californiaCities = service.GetCitiesByRegion("USA", "California");

// Search for cities named "Paris"
var parisCities = service.SearchCities("Paris");
```

## Features

- **Countries Data**
  - Names (common and official)
  - ISO codes (2 and 3 letter)
  - Capitals
  - Continents
  - Population
  - Area

- **Regions Data**
  - States/Provinces for each country
  - Administrative divisions
  - Regional codes

- **Cities Data** (New in v1.1.0)
  - 150,000+ cities worldwide
  - City names and populations
  - Geographical coordinates (latitude/longitude)
  - Hierarchical organization (Country → Region → Cities)

- **Search Capabilities**
  - Search countries by name
  - Search cities across all countries
  - Filter by continent
  - Get cities by region

## Data Coverage

- 250+ Countries
- 4,000+ Regions/States
- 150,000+ Cities worldwide

## Next Steps

- Check out the [API Reference](api-reference.md) for detailed method documentation
- See [Examples](examples.md) for common use cases
- Read [Best Practices](best-practices.md) for optimization tips
