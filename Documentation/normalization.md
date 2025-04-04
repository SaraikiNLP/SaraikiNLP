# Text Normalization using SaraikiNLP

## Table of Contents
1. [Installation](#1-installation)
2. [Importing Normalization Module](#2-importing-normalization-module)
3. [Normalization Functions](#3-normalization-functions)
   - [Character Normalization](#character-normalization)
   - [Number Normalization](#number-normalization)
   - [Punctuation Normalization](#punctuation-normalization)
   - [Diacritics Removal](#diacritics-removal)
   - [Spacing Correction](#spacing-correction)
   - [Normalize Text](#normalize-text)
4. [Example Notebook](#4-example-notebook)

## 1. Installation
To use SaraikiNLP for text normalization, install it using:
```python
pip install SaraikiNLP
```

## 2. Importing Normalization Module
```python
from SaraikiNLP import normalization
```
## 3. Normalization Functions

### Character Normalization
This function normalizes characters in the given text.
```python

example_text = """
ڈیزل دی فی لیٹر قیمت 251 روپے 29 پیسے تھی ڳئی۔
"""

print(normalization.normalize_characters(example_text))
```

### Number Normalization
Converts numbers between native and standard format.

- `convert_native=True` (default): Converts Saraiki and Arabic numbers to Western (1,2,3,...).
- `convert_native=False`: Converts Western and Arabic numbers to Saraiki (١,٢,٣,...)

```python
print(normalization.normalize_numbers(example_text))  # Default case
print(normalization.normalize_numbers(example_text, convert_native=False))
```

### Punctuation Normalization
Standardizes punctuation marks.

- `convert_native=True`: Converts native punctuation to Western equivalents.
- `convert_native=False` (default): Preserves native punctuation except for minor removals.

```python
print(normalization.normalize_punctuation('،گھر۔۔۔؟ بار ٹھیک ہِن سارے'))  # Default case
print(normalization.normalize_punctuation('،گھر۔۔۔؟ بار ٹھیک ہِن سارے', convert_native=True))
```

### Diacritics Removal
Removes diacritics from text.
```python
print(normalization.remove_diacritics('استغفار دا وِرد کر تُوں'))
```

### Spacing Correction
Ensures proper spacing after punctuation.
```python
print(normalization.insert_space_after_punctuation(
    """
     2  سرائیکی۔۔،وسیب
    """
))
```

### Normalize Text
Normalizes text by applying **normalize_characters**, then **normalize_numbers** and **normalize_punctuation**

- `remove_diacritic=True`: Call **remove_diacritics** at end of function.
- `remove_diacritic=False` (default): Doesn't remove diacritics.


```python
print(normalization.normalize_text(
   """
   ڈیزل دی فی لیٹر قیمت 251 روپے 29 پیسے تھی ڳئی۔
   """
, remove_diacritic = True))
```

## 4. Example Notebook
You can use [this example notebook](https://colab.research.google.com/github/SaraikiNLP/SaraikiNLP/blob/main/Notebooks/normalization.ipynb) to see these functions alive!
