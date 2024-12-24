# Changelog

All notable changes to the Countries Info packages will be documented in this file.

## [1.1.0] - 2024-12-24

### Added
- Cities functionality across all platforms (JavaScript, PHP, C#)
  - Added `getCitiesByRegion` method to get cities in a specific region
  - Added `getAllCitiesInCountry` method to get all cities in a country
  - Added `getCityCount` method to get total number of cities in a country
  - Added `searchCities` method to search cities across all countries
- City data structure with:
  - City names
  - Population data
  - Geographical coordinates (latitude/longitude)
  - Country and region context
- Comprehensive city data coverage:
  - 150,000+ cities worldwide
  - Population data for major cities
  - Coordinates for geographical queries

### Changed
- Updated documentation with city-related examples and API reference
- Improved error handling for city-related queries
- Enhanced type definitions for TypeScript users
- Optimized data loading for better performance

### Fixed
- Case sensitivity issues in country code lookups
- Region name matching in various locales
- Memory usage optimizations for large datasets

## [1.0.0] - 2024-12-22

### Added
- Initial release of all packages:
  - JavaScript (@mohaned.ghawar/countries-info)
  - Python (countries-info-mg)
  - PHP (mohanedghawar/countries-info)
  - .NET (CountriesInfo)

### Features
- Comprehensive country data including:
  - Country names
  - ISO codes
  - Capital cities
  - Continents
  - Population data
  - Area information
- Case-insensitive search
- Null safety
- Type safety (where applicable)
- Bundled JSON data
- MIT License

### Documentation
- API reference
- Usage examples
- Best practices guide
- Getting started guide

## Future Plans

### Upcoming Features
- Additional search criteria
- Population statistics helpers
- Geographic calculations
- Regular data updates
- Additional country information

### Documentation Improvements
- Interactive examples
- Video tutorials
- More code samples
- Performance optimization guides

### Technical Enhancements
- Performance optimizations
- Additional type safety
- Extended test coverage
- CI/CD improvements
