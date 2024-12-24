# Countries Info Documentation

Welcome to the Countries Info documentation! This comprehensive library provides detailed information about countries, regions, and cities worldwide, available in multiple programming languages.

## Latest Release: v1.1.0 🎉

We're excited to announce our latest release with comprehensive cities data! Now you can:
- Access information for 150,000+ cities worldwide
- Search cities by name across all countries
- Get cities by region or country
- Access geographical coordinates and population data

## Quick Links

- [Getting Started](docs/getting-started.md)
- [API Reference](docs/api-reference.md)
- [Code Examples](docs/examples.md)
- [Best Practices](docs/best-practices.md)
- [Changelog](CHANGELOG.md)

## Available Packages

### JavaScript/Node.js
```bash
npm install @mohaned.ghawar/countries-info
```
[![npm version](https://img.shields.io/npm/v/@mohaned.ghawar/countries-info.svg)](https://www.npmjs.com/package/@mohaned.ghawar/countries-info)

### PHP
```bash
composer require mohanedghawar/countries-info
```
[![Packagist Version](https://img.shields.io/packagist/v/mohanedghawar/countries-info.svg)](https://packagist.org/packages/mohanedghawar/countries-info)

### C#
```bash
dotnet add package CountriesInfo
```
[![NuGet version](https://img.shields.io/nuget/v/CountriesInfo.svg)](https://www.nuget.org/packages/CountriesInfo)

## Features

- **Comprehensive Data Coverage**
  - 250+ Countries
  - 4,000+ Regions/States
  - 150,000+ Cities worldwide

- **Rich Information**
  - Country details (names, codes, capitals)
  - Administrative regions
  - City data with coordinates
  - Population statistics

- **Advanced Search**
  - Search by name
  - Filter by continent
  - City search across countries
  - Region-based filtering

- **Developer-Friendly**
  - Consistent API across languages
  - Comprehensive documentation
  - Type definitions included
  - Regular updates

## Quick Example

```javascript
// JavaScript
const service = new CountriesService();

// Get all cities in California
const cities = service.getCitiesByRegion('USA', 'California');
console.log(`Found ${cities.length} cities in California`);

// Search for cities named "Paris"
const parisCities = service.searchCities('Paris');
parisCities.forEach(city => {
    console.log(`${city.name} (${city.countryCode}): ${city.regionName}`);
});
```

## Data Coverage

Our comprehensive database includes:
- Countries: Names, ISO codes, capitals, population, area
- Regions: States, provinces, territories
- Cities: Names, coordinates, population data
- Continents: Grouping and classification

## Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

- Report issues on [GitHub](https://github.com/MohanedGhawar2019/countries-info/issues)
- Join our [Discord community](https://discord.gg/countries-info)
- Follow updates on [Twitter](https://twitter.com/CountriesInfo)
