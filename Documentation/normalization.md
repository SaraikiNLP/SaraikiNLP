# Text Normalization using SaraikiNLP

## Table of Contents
1. [Installation](#installation)
2. [Importing Normalization Module](#importing-normalization-module)
3. [Normalization Functions](#normalization-functions)
   - [Character Normalization](#character-normalization)
   - [Number Normalization](#number-normalization)
   - [Punctuation Normalization](#punctuation-normalization)
   - [Diacritics Removal](#diacritics-removal)
   - [Spacing Correction](#spacing-correction)
4. [Example Notebook](#example-notebook)

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

- `convert_native=True` (default): Converts standard numbers (e.g., 123) to native script.
- `convert_native=False`: Converts native script numbers back to standard format.

```python
print(normalization.normalize_numbers(example_text))  # Default case
print(normalization.normalize_numbers(example_text, convert_native=False))
```

### Punctuation Normalization
Standardizes punctuation marks.

- `convert_native=True`: Converts standard punctuation to native equivalents.
- `convert_native=False` (default): Converts native punctuation to standard format.

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

## 4. Example Notebook
You can use [this example notebook](https://github.com/SaraikiNLP/SaraikiNLP/blob/main/Notebooks/normalization.ipynb) to see these functions in working.
