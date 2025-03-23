# Text Preprocessing using SaraikiNLP

## Table of Contents
1. [Installation](#1-installation)
2. [Importing Preprocessing Module](#2-importing-preprocessing-module)
3. [Preprocessing Functions](#3-preprocessing-functions)
   - [Remove Links](#remove-links)
   - [Remove Hashtags](#remove-hashtags)
   - [Remove Usernames](#remove-usernames)
   - [Remove Phone Numbers](#remove-phone-numbers)
   - [Remove Numbers](#remove-numbers)
   - [Remove Punctuation](#remove-punctuation)
   - [Remove White Space](#remove-white-space)
   - [Remove Multiple Spaces](#remove-multiple-spaces)
   - [Remove Line Breaks](#remove-line-breaks)
   - [Separate Numbers From Text](#separate-numbers-from-text)
   - [Remove Emojis and Symbols](#remove-emojis-and-symbols)
   - [Convert Text to Lowercase](#convert-text-to-lowercase)
   - [Remove English](#remove-english)
   - [Retain Clean Saraiki](#retain-clean-saraiki)
4. [Example Notebook](#4-example-notebook)

## 1. Installation
To use SaraikiNLP for text normalization, install it using:
```python
pip install SaraikiNLP
```

## 2. Importing Preprocessing Module
```python
from SaraikiNLP import preprocessing
```
## 3. Preprocessing Functions

### Remove Links
Removes various kind of links.
```python
print(preprocessing.remove_links(
    """میڈا ٹک ٹاک فالو کریسو تے یوٹوب وی وزٹ کریسو
       www.tiktok.com/@example

       https://youtu.be/@example"""
))
```

### Remove Hashtags
Removes hashtags both in Saraiki and English with underscores or any format.
```python
print(preprocessing.remove_hashtags(
    """#twitter
       #سرائیکی_صوبہ سرائیکستان دی تحریک زور پکڑی ودی ہے


       #sariki_suba_
    """
))
```

### Remove Usernames
Removes username handles of @username format.
```python
print(preprocessing.remove_usernames(
    """
     @ali تُوں چپ کر یار
    """
))
```

### Remove Phone Numbers
Removes almost all kind of phone number variants.
```python
print(preprocessing.remove_phone_numbers(
    """
     فون نمبر لِکھ ڳھن ناں0300 1234567
     شاکر کال نہ چاوے تاں ول اے ݙیکھیں 923001234567
     +92-300-123-456-7یا
     یا +92 3001234567
    """
))
```

### Remove Numbers
Removes all digits either in Saraiki, Arabic or English.
```python
print(preprocessing.remove_numbers(
    """
     ٧١٧ ٢٥٣٧٤٧ اے پاسورڈ ہے میڈا اے کم نہ کرے تاں Example@123__456 کر
    """
))
```

### Remove Punctuation
Removes all punctuation marks of all languages.
```python
print(preprocessing.remove_punctuation(
    """
    BREAKING NEWS:
    ...حکومت دا۔۔۔ اعلان
    123
    """
))
```

### Remove White Space
Removes multiple spaces **(2 or more than 2 spaces)**, **linebreaks** and **TAB**.
```python
print(preprocessing.remove_whitespace(
    """
    BREAKING NEWS:
    ...حکومت دا۔۔۔    اعلان
    123
    """
))
```

### Remove Multiple Spaces
Removes multiple spaces (2 or more than 2 spaces) **IGNORING line breaks (\n)**.
```python
print(preprocessing.remove_multiple_spaces(
    """
    BREAKING NEWS:
    ...حکومت دا۔۔۔    اعلان
    123
    """
))
```

### Remove Line Breaks
Removes **ONLY line breaks**, ignoring spaces and TAB.
```python
print(preprocessing.remove_linebreaks(
    """
    BREAKING NEWS:
    ...حکومت دا۔۔۔ اعلان
    123
    """
))
```

### Separate Numbers From Text
Gives a room for words and numbers attached without space to breath.
```python
print(preprocessing.separate_numbers_from_text(
    """
11لاکھ
اج10بندے
110810.22پوائنٹس
    """
))
```

### Remove Emojis and Symbols
Removes all kind of emojis, emoticons symbols and so on.
```python
print(preprocessing.remove_emojis_and_symbols(
    """
    🥀شاکر توں💡💡وی کملا.. ہیں 🥺🥺 💡

    """
))
```

### Convert Text to Lowercase
Lowercases English in text.
```python
print(preprocessing.to_lowercase(
    """
    BREAKING NEWS:
    حکومت دا اعلان

    """
))
```

### Remove English
Removes English, its punctuation and numbers.
```python
print(preprocessing.remove_english(
    """
    BREAKING NEWS:
    حکومت دا   اعلان

    """
))
```

### Retain Clean Saraiki

#### Normalizes the text first [(using normalization.normalize_text)](https://github.com/SaraikiNLP/SaraikiNLP/blob/main/Documentation/normalization.md#normalize-text) and then retains these:

👉 Removes all other languages including English, punctuation etc.

👉 Basic Arabic block (includes Urdu punctuation)

👉 Arabic Supplement

👉 Diacritical marks ( ِ َ ؒ ٗ ّ ْ ٌ ُ ۤ) etc

👉 Whitespace (\s+)

👉 Western digits (0-9)

👉 Arabic-Indic digits (٠-٩)

👉 Additional Saraiki characters (ݨ ݙ ڳ ڄ ٻ) etc

```python
print(preprocessing.retain_clean_saraiki(
    """
    BREAKING NEWS:
    ...حکومت دا۔۔۔ اعلان
    123
    """
))
```


## 4. Example Notebook
You can use [this example notebook](https://github.com/SaraikiNLP/SaraikiNLP/blob/main/Notebooks/preprocessing.ipynb) to see these functions in working.
