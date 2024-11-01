---
Created: 2024-02-05T23:05
---
There are five basic types of numeric conversions.

- Converting an integral type to any other integral type (excluding [[Integral Promotions]])
- Converting a floating point type to any other floating point type (excluding [[Floating Point Promotion]])
- Converting a floating point type to any integral type
- Converting an integral type to any floating point type
- Converting an integral type or a floating point type to a bool

Unlike [[Numeric Promotions]], not all numeric conversions are value-preserving. For example, converting a floating point type to an integral type may result in some value loss.

Reinterpretive conversions are potentially unsafe numeric conversions where the result may be outside the range of the source type. Signed/unsigned conversions fall into this category.

Lossy conversions are potentially unsafe numeric conversions where some data may be lost during the conversion.

Conversion from `double` to `float` can also result in data loss.