#Voraussetzungen: pip install requests
```python
import sys
import requests



API_URL = "http://ip-api.com/json/{}"



def get_ip_info(ip):
    response = requests.get(API_URL.format(ip), timeout=5)
    data = response.json()
    return data



def main():
    if len(sys.argv) < 2:
        print("Usage: python IP_Info_Tool.py <ip-oder-domain>")
        sys.exit(1)

    ip = sys.argv[1]

    try:
        data = get_ip_info(ip)

        if data.get("status") != "success":
            print("IP konnte nicht aufgelöst werden")
            sys.exit(1)

        print(f"IP:                 {data.get('query')}")
        print(f"Land:               {data.get('country')}")
        print(f"Region:             {data.get('regionName')}")
        print(f"Stadt:              {data.get('city')}")
        print(f"Provider:           {data.get('isp')}")
        print(f"Org:                {data.get('org')}")
        print(f"Koordinaten:        {data.get('lat')}, {data.get('lon')}")

    except requests.exceptions.RequestException:
        print("Netzwerkfehler")
        sys.exit(1)



if __name__ == "__main__":
    main()
```
