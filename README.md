# SharpEssentials

[![Build Status](https://github.com/SharpNexSolutions/sharpessentials.functions/CI)](https://github.com/SharpNexSolutions/sharpessentials.functions/actions)
[![Coverage](https://github.com/SharpNexSolutions/sharpessentials.functions)](https://github.com/SharpNexSolutions/sharpessentials.functions)
[![NuGet](https://img.shields.io/nuget/v/SharpEssentials)](https://www.nuget.org/packages/SharpEssentials)
[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://go.avbc.me/i9HwDKlQ)

> **SharpEssentials** is the ultimate C# utility library for .NET developers, helping you write cleaner, more efficient code with zero dependencies.

---

## Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Getting Started](#getting-started)
- [Usage Examples](#usage-examples)
- [Why Choose SharpEssentials?](#why-choose-sharpessentials)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [Support & Community](#support--community)
- [License](#license)

---

## Features

**Core Utilities**
- Argument Validation: `ThrowIfNull`, `ThrowIfEmpty`, `ThrowIfInvalid`
- Type Helpers: Safe casting, null coalescing, enum parsing
- Exception Handling: Retry policies, exception unwrapping

**Collections & LINQ**
- `Batch`, `DistinctBy`, `ToDictionarySafe`
- `ForEachWithIndex`, `Shuffle`, `Paginate`

**Functional Programming**
- `Option<T>`, `Result<T>`, `Either<L, R>`
- Pattern matching extensions

**String Operations**
- Truncation, formatting, validation
- Levenshtein distance, phonetic matching

**DateTime Helpers**
- Business day calculations
- Timezone conversions
- Human-readable intervals ("2 hours ago")

---

## Installation

Use your preferred .NET package manager:

```bash
# NuGet Package Manager
Install-Package SharpEssentials

# .NET CLI
dotnet add package SharpEssentials

# Paket CLI
paket add SharpEssentials
```

**Compatibility:** .NET 8.0+

---

## Getting Started

```csharp
using SharpEssentials;

// Validate arguments
order.ThrowIfNull(nameof(order));

// Batch operations
var batches = Enumerable.Range(1, 1000).Batch(100);

// Functional result handling
var result = Result.Try(ParseConfigFile);
result.Match(
    success: config => Save(config),
    failure: ex => Log.Error(ex)
);
```

---

## Usage Examples

### Retry Policy with Exponential Backoff
```csharp
var data = await RetryPolicy
    .WithExponentialBackoff(3, TimeSpan.FromSeconds(1))
    .ExecuteAsync(() => FetchRemoteDataAsync());
```

### String Helpers
```csharp
var clean = " HELLO world ".TrimAll(); // "HELLO world"
var similarity = "color".SimilarityTo("colour"); // 0.91
```

---

## Why Choose SharpEssentials?

| Metric         | SharpEssentials | Alternatives |
|---------------:|:--------------:|-------------:|
| **Performance**| ⚡ Optimized    | 🐢 Slower    |
| **Dependencies**| 0              | 3+           |
| **Maintenance**| Active         | Abandoned    |
| **Documentation**| ✅ Comprehensive| Minimal     |

- Battle-tested in production
- Consistent, intuitive API
- Detailed XML docs with examples

---

## Documentation

- 📖 [Full API Reference](https://github.com/yourname/SharpEssentials/wiki)
- 🌐 [GitHub Wiki](https://github.com/yourname/SharpEssentials/wiki)
- 🎬 [Video Tutorials](https://www.youtube.com/SharpEssentials)

---

## Contributing

We welcome your contributions! Please:

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m "Add AmazingFeature"`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

```bash
git clone https://github.com/yourname/SharpEssentials.git
cd SharpEssentials
dotnet restore
dotnet build
dotnet test
```

---

## Support & Community

- 📚 [FAQ](https://github.com/yourname/SharpEssentials/wiki/FAQ)
- 🐛 [Report Issues](https://github.com/yourname/SharpEssentials/issues)
- 💬 [Join our Discord](https://discord.gg/SharpEssentials)
- 📢 Follow us on [Twitter](https://twitter.com/SharpEssentials) and [LinkedIn](https://linkedin.com/company/sharpessentials)

---

## License

Distributed under the MIT License. See `LICENSE` for details.

---

Thank you for choosing **SharpEssentials**! 🎉
Happy coding! 💻🚀
