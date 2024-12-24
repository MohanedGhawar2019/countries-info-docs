# Examples and Use Cases

This document provides common examples and use cases for the Countries Info library across different programming languages.

## Common Use Cases

### 1. List All Countries

Get a list of all countries and their basic information.

### 2. Find Country Details

Look up specific country information using name or code.

### 3. Continental Analysis

Group or filter countries by continent.

### 4. Population Statistics

Calculate population statistics and demographics.

### 5. Geographic Analysis

Analyze country sizes and distributions.

## Implementation Examples

### Basic Queries

#### Getting Basic Country Information
Find basic information about a specific country.

#### Filtering Countries
Filter countries based on various criteria.

#### Statistical Analysis
Perform basic statistical analysis on country data.

### Advanced Use Cases

#### Regional Analysis
Group and analyze countries by region or continent.

#### Data Export
Export country data in various formats.

#### Custom Sorting
Sort countries by various criteria.

## Integration Examples

### Web Applications
- Country selector components
- Geographic visualizations
- Data dashboards

### Data Analysis
- Population studies
- Geographic analysis
- Economic comparisons

### Mobile Applications
- Country information apps
- Travel applications
- Educational tools

## Best Practices

1. Data Caching
   - Cache results for repeated queries
   - Store frequently accessed data

2. Error Handling
   - Always check for null/none returns
   - Implement proper error handling

3. Performance Optimization
   - Use appropriate search methods
   - Implement efficient filtering

4. User Experience
   - Implement case-insensitive search
   - Provide flexible search options

## Common Patterns

### Search Patterns
- Exact match search
- Partial match search
- Case-insensitive search

### Filter Patterns
- Continental filtering
- Population range filtering
- Area range filtering

### Sort Patterns
- Alphabetical sorting
- Population sorting
- Area sorting

## Tips and Tricks

1. Search Optimization
   - Use codes for exact matches
   - Use names for user-friendly searches

2. Data Processing
   - Batch processing techniques
   - Efficient data transformation

3. Integration
   - API integration patterns
   - Database integration

4. Performance
   - Caching strategies
   - Memory optimization

## Code Examples

### Basic Country Information

#### JavaScript/Node.js
```javascript
const CountriesService = require('@mohaned.ghawar/countries-info');

const service = new CountriesService();

// Get basic country info
const usa = service.getCountryByCode('USA');
console.log(`Country: ${usa.name.common}`);
console.log(`Capital: ${usa.capital}`);
console.log(`Population: ${usa.population.toLocaleString()}`);

// Get European countries
const europeanCountries = service.getCountriesByContinent('Europe');
console.log(`Number of European countries: ${europeanCountries.length}`);
```

#### PHP
```php
use MohanedGhawar\CountriesInfo\CountriesInfo;

$service = new CountriesInfo();

// Get basic country info
$usa = $service->getCountryByCode('USA');
echo "Country: {$usa['name']['common']}\n";
echo "Capital: {$usa['capital']}\n";
echo "Population: " . number_format($usa['population']) . "\n";

// Get European countries
$europeanCountries = $service->getCountriesByContinent('Europe');
echo "Number of European countries: " . count($europeanCountries) . "\n";
```

#### C#
```csharp
using CountriesInfo;

var service = new CountriesService();

// Get basic country info
var usa = service.GetCountryByCode("USA");
Console.WriteLine($"Country: {usa.Name.Common}");
Console.WriteLine($"Capital: {usa.Capital}");
Console.WriteLine($"Population: {usa.Population:N0}");

// Get European countries
var europeanCountries = service.GetCountriesByContinent("Europe");
Console.WriteLine($"Number of European countries: {europeanCountries.Count()}");
```

## Working with Cities (New in v1.1.0)

### Find Cities by Region
```javascript
// JavaScript
const californiaCities = service.getCitiesByRegion('USA', 'California');
console.log(`Cities in California: ${californiaCities.length}`);
californiaCities.slice(0, 5).forEach(city => {
    console.log(`${city.name}: Population ${city.population.toLocaleString()}`);
});
```

```php
// PHP
$californiaCities = $service->getCitiesByRegion('USA', 'California');
echo "Cities in California: " . count($californiaCities) . "\n";
array_slice($californiaCities, 0, 5).forEach(function($city) {
    echo "{$city['name']}: Population " . number_format($city['population']) . "\n";
});
```

```csharp
// C#
var californiaCities = service.GetCitiesByRegion("USA", "California");
Console.WriteLine($"Cities in California: {californiaCities.Count()}");
foreach (var city in californiaCities.Take(5))
{
    Console.WriteLine($"{city.Name}: Population {city.Population:N0}");
}
```

### Search Cities Globally
```javascript
// JavaScript
const parisCities = service.searchCities('Paris');
parisCities.forEach(city => {
    console.log(`${city.name} (${city.countryCode}): ${city.regionName}`);
});
```

```php
// PHP
$parisCities = $service->searchCities('Paris');
foreach ($parisCities as $city) {
    echo "{$city['name']} ({$city['countryCode']}): {$city['regionName']}\n";
}
```

```csharp
// C#
var parisCities = service.SearchCities("Paris");
foreach (var city in parisCities)
{
    Console.WriteLine($"{city.Name} ({city.CountryCode}): {city.RegionName}");
}
```

### City Statistics
```javascript
// JavaScript
const countries = ['USA', 'FRA', 'GBR'];
countries.forEach(code => {
    const count = service.getCityCount(code);
    console.log(`Cities in ${code}: ${count.toLocaleString()}`);
});
```

```php
// PHP
$countries = ['USA', 'FRA', 'GBR'];
foreach ($countries as $code) {
    $count = $service->getCityCount($code);
    echo "Cities in {$code}: " . number_format($count) . "\n";
}
```

```csharp
// C#
var countries = new[] { "USA", "FRA", "GBR" };
foreach (var code in countries)
{
    var count = service.GetCityCount(code);
    Console.WriteLine($"Cities in {code}: {count:N0}");
}
```

## Advanced Examples

### Find Most Populous Cities
```javascript
// JavaScript
const allUsCities = service.getAllCitiesInCountry('USA');
const topCities = allUsCities
    .sort((a, b) => b.population - a.population)
    .slice(0, 10);

console.log('Top 10 US Cities by Population:');
topCities.forEach((city, index) => {
    console.log(`${index + 1}. ${city.name}: ${city.population.toLocaleString()}`);
});
```

### Cities Near Coordinates
```javascript
// JavaScript
function findCitiesNearCoordinates(lat, lon, maxDistance) {
    const allCities = service.getAllCitiesInCountry('USA');
    return allCities.filter(city => {
        const distance = calculateDistance(
            lat, lon,
            parseFloat(city.latitude),
            parseFloat(city.longitude)
        );
        return distance <= maxDistance;
    });
}

// Helper function to calculate distance between coordinates (in km)
function calculateDistance(lat1, lon1, lat2, lon2) {
    const R = 6371; // Earth's radius in km
    const dLat = toRad(lat2 - lat1);
    const dLon = toRad(lon2 - lon1);
    const a = Math.sin(dLat/2) * Math.sin(dLat/2) +
              Math.cos(toRad(lat1)) * Math.cos(toRad(lat2)) *
              Math.sin(dLon/2) * Math.sin(dLon/2);
    const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1-a));
    return R * c;
}

function toRad(deg) {
    return deg * (Math.PI/180);
}

// Find cities within 50km of San Francisco
const nearbySF = findCitiesNearCoordinates(37.7749, -122.4194, 50);
console.log(`Cities within 50km of San Francisco: ${nearbySF.length}`);
```

## Additional Resources

- [API Reference](api-reference.md)
- [Best Practices](best-practices.md)
- [Getting Started Guide](getting-started.md)
