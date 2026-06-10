#Voraussetzungen: pip install requests
#Usage: python Website_Status_Checker.py <url>


```python
import sys
import requests
import time



TIMEOUT = 5



def main():
    if len(sys.argv) < 2:
        print("Usage: python Website_Status_Checker.py <url>")
        sys.exit(1)

    url = sys.argv[1]

    if not url.startswith(("http://", "https://")):
        url = "https://" + url

    start = time.time()

    try:
        response = requests.get(url, timeout=TIMEOUT)
        dauer = time.time() - start
        print(f"[ OK ] {url}  ({response.status_code}) - {dauer:.2f}s")

    except requests.exceptions.RequestException:
        print(f"[FAIL] {url} nicht erreichbar")
        sys.exit(1)



if __name__ == "__main__":
    main()
```
