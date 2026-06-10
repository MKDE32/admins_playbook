```python
import secrets
import string

length = int(input("Passwortlänge: "))
include_upper = input("Großbuchstaben verwenden? (j/n)").lower() =="j"
include_lower = input("Kleinbuchstaben verwenden? (j/n)").lower() =="j"
include_digits = input("Zahlen verwenden? (j/n)").lower() =="j"
include_special = input("Sonderzeichen verwenden? (j/n)").lower() =="j"

characters = ""
if include_upper:
    characters += string.ascii_uppercase
if include_lower:
    characters += string.ascii_lowercase
if include_digits:
    characters += string.digits
if include_special:
    characters += string.punctuation

if not characters:
    print("Du musst mindestens eine Zeichenart auswählen!")
else:
    password = "".join(secrets.choice(characters) for _ in range(length))
    print("Generiertes Passwort: ", password)
```
