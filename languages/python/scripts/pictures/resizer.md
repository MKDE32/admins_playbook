#Dependencies: pip install pillow


```python
from PIL import Image
import os



new_width = 1366

output_folder = "resized"
os.makedirs(output_folder, exist_ok=True)

for filename in os.listdir("."):
    if filename.lower().endswith((".jpg", ".jpeg", ".png")):
        img = Image.open(filename)

        width_percent = new_width / float(img.size[0])
        new_height = int(float(img.size[1]) * width_percent)

        resized_img = img.resize((new_width, new_height), Image.Resampling.LANCZOS)

        output_path = os.path.join(output_folder, filename)
        resized_img.save(output_path)

        print(f"{filename} > {new_width}x{new_height}")

print("Alle Bilder wurden skaliert")
```
