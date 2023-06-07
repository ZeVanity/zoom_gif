# zoom_gif

copy and paste into your terminal app. 

import os 
import shutil

user = os.getenv("USER")
path = f"/Users/{user}/Library/Application Support/zoom.us/"
data_dir = os.path.join(path, "data")

if __name__ == "__main__":
    try: 
        for folder in os.listdir(data_dir):
            folder_path = os.path.join(data_dir, folder)
            if os.path.isdir(folder_path):
                shutil.move(folder_path, os.path.join(path, ".Trash"))
        print('done')
    except FileNotFoundError:
        print("Zoom data directory not found.")
