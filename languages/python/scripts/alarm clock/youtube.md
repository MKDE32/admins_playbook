# python Youtube_wakeup.py --url https://www.youtube.com/playlist?list=<your_playlist>
# Dependencies: pip install selenium webdriver-manager pycaw comtypes
# Windows, Firefox
# New Firefox Profil (Win + R firefox.exe -P)
# profiles located in C:\Users\<Username>\AppData\Roaming\Mozilla\Firefox\Profiles
# profile_name = "5tnrerhs.Wecker"    <-- ADJUST
# todo: Video stops always after about 40 seconds...


```python
import os
import time
import argparse
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.firefox.service import Service
from webdriver_manager.firefox import GeckoDriverManager
from selenium.webdriver.firefox.options import Options



# ---------------- Argumente ----------------
parser = argparse.ArgumentParser(description="YouTube-Wecker Firefox")
parser.add_argument("--url", required=True, help="YouTube Playlist- oder Video-URL")
args = parser.parse_args()

YOUTUBE_URL = args.url

# ---------------- Firefox MIT PROFIL starten ----------------
service = Service(GeckoDriverManager().install())

options = Options()
options.add_argument("-profile")

profile_base = r"C:\Users\<User>\AppData\Roaming\Mozilla\Firefox\Profiles"        # <-- HIER ANPASSEN!
profile_name = "5tnrerhs.Wecker"                                                  # <-- HIER ANPASSEN!
profile_path = os.path.join(profile_base, profile_name)

options.add_argument(profile_path)

driver = webdriver.Firefox(
    service=service,
    options=options
)

wait = WebDriverWait(driver, 20)

driver.get(YOUTUBE_URL)

# ---------------- Play klicken ----------------

try:
    first_video = wait.until(
        EC.element_to_be_clickable(
            (By.XPATH, '(//ytd-playlist-video-renderer)[1]//a[@id="thumbnail"]')
        )
    )
    first_video.click()
    print("▶ Erstes Playlist-Video gestartet")
except Exception as e:
    print("❌ Konnte erstes Playlist-Video nicht starten:", e)

# ---------------- Vollbild ----------------
time.sleep(1)
driver.find_element(By.TAG_NAME, "body").send_keys("f")
print("🖥 Vollbild aktiviert")
```
