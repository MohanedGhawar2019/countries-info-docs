# Getting Started

This guide will help you get started with the Countries Info library in your preferred programming language.

## Installation

Choose your platform and follow the installation instructions:

### JavaScript/Node.js
```bash
npm install @mohaned.ghawar/countries-info
```

### Python
```bash
pip install countries-info-mg
```

### PHP
```bash
composer require mohanedghawar/countries-info
```

### .NET
```bash
dotnet add package CountriesInfo
```

## Basic Usage

All implementations provide similar basic functionality:

- Get all countries
- Get country by name
- Get country by code
- Get countries by continent (C# only)

## Data Structure

All packages return country data in a consistent format:

```json
{
  "name": "String",       // Country name
  "code": "String",       // ISO 2-letter code
  "capital": "String",    // Capital city
  "continent": "String",  // Continent name
  "population": Number,   // Population count
  "area": Number         // Area in square kilometers
}
```

## Requirements

### JavaScript/Node.js
- Node.js 12.x or higher
- npm or yarn package manager

### Python
- Python 3.6 or higher
- pip package manager

### PHP
- PHP 7.4 or higher
- Composer package manager

### .NET
- .NET 6.0 or higher
- NuGet package manager

## Next Steps

- Check out the [API Reference](api-reference.md) for detailed documentation
- See [Examples](examples.md) for common use cases
- Review [Best Practices](best-practices.md) for optimization tips
