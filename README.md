# C# Coding Assignment: Time Mirror Transformation

## Problem Overview
Implement a `WhatIsTheTime` method that returns the analog clock time in its mirror position. This challenge tests your ability to manipulate time representations, handle various input formats, and implement robust input validation.

## Requirements and Specifications

### Basic Functionality
The method should transform a given time to its mirror position on an analog clock. 

**Examples:**
| Input | Expected result |
| ----------- | ----------- |
| 05:25 | 06:35 |
| 01:50 | 10:10 |
| 11:58 | 12:02 |
| 12:01 | 11:59 |

**Notes:**
- Hours should be between 1 and 12 (inclusive)
- Special time conversions:
  - ```0:20``` becomes ```12:20```
  - ```13:20``` becomes ```01:20```

### Detailed Requirements

#### 1a: Input Validation
Handle invalid input values by returning an error message.

**Validation Examples:**
| Input | Output |
| ----------- | ----------- |
| ```05:89``` | ```Invalid input!``` |

#### 1b: Flexible Number Input
Support alternative number representations.

**Examples:**
| Input | Output |
| ----------- | ----------- |     
| ```03:25``` | ```08:35``` |
| ```0$:25``` | ```08:35``` |

#### 2: Word Number Support
Extend method to accept word-based number inputs.

**Word Input Examples:**
| Input | Output |
| ----------- | ----------- |     
| ```1:20``` | ```11:40``` |
| ```one twenty``` | ```11:40``` |

#### 3: Special English Time Phrases
Add support for idiomatic time expressions.

**Phrase Examples:**
- ```half past eight``` equals ```08:30```
- ```quarter to eight``` equals ```07:45```

#### 4: Multiple Input Handling
Process multiple time inputs separated by ```;;```.

**Multiple Input Examples:**
| Input | Output |
| ----------- | ----------- |   
| ```05:25;;one fifty;;11:58``` | ```06:35;;10:10;;12:02``` |

#### 4a: Duplicate Time Handling
Remove duplicate times from the result set.

**Duplicate Handling Example:**
| Input | Output |
| ----------- | ----------- |   
| ```05:25;;five twentyfive``` | ```06:35``` |

## Recommended Implementation Approach

### Design Considerations
1. **Strategy Pattern**: Consider using the Strategy pattern for different input parsing strategies (numeric, word-based, special phrases).
2. **Validation Layer**: Implement a robust input validation mechanism.
3. **Immutability**: Use immutable time representation where possible.

### Suggested C# Technologies
- Use `DateTime` or a custom `TimeSpan` for time manipulation
- Leverage pattern matching and `switch` expressions
- Utilize `Enum` for time-related constants
- Consider functional programming approaches with LINQ

### Sample Project Structure
If you don't know how to start, this can inspire you. However, feel free to try something yourself!
```
TimeTransformation/
├── Core/
│   ├── TimeConverter.cs
│   ├── InputParser.cs
│   └── Validators/
├── Models/
│   └── TimeRepresentation.cs
└── Extensions/
    └── TimeExtensions.cs
```

## Best Practices
- Implement comprehensive unit tests
- Use meaningful variable and method names
- Handle edge cases gracefully
- Write clean, maintainable code
- Consider performance for large input sets

## Extra Challenge Ideas
- Add support for 24-hour time format
- Implement internationalization for time parsing
- Create a CLI or web API around the time transformation logic

## Final Words
- Embrace clean code principles
- Focus on readability and maintainability
- Be creative in your implementation
- Test thoroughly!
