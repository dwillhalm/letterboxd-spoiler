# Letterboxd Spoiler

A Python script in a Jupyter notebook to automatically batch-edit your Letterboxd reviews and mark them as containing spoilers. 

I only realized after hundreds of reviews that the spoiler flag was not automatically raised when creating a review. I felt bad because a lot of my reviews contain spoilers but do not warn about it. I wrote this script to automate it. Note that using this is technically against the letterboxd terms of service but it is for a good cause so I hope it'll be excused that I share it here

## Features
- Opens reviews automatically in your default browser.
- Uses **Image Recognition** to detect if a spoiler tag is already present (skips if yes).
- **Failsafe:** Move cursor to top left corner to interrupt

## Prerequisites
- Python 3.10 or 3.11
- Firefox Logged into Letterboxd (Other browser might work too but I only tested it in Firefox)
- A `reviews.csv` file (from your Letterboxd export: -> settings -> data -> export your data)
- The script is for macOs. Permissions for VS Code are required such as Accesibility (On your device: -> settings -> privacy & security -> accesibility -> make sure VS Code is toggled on)

## Installation

1. Clone the repo:
   ```bash
   git clone [https://github.com/dwillhalm/letterboxd-spoiler.git](https://github.com/dwillhalm/letterboxd-spoiler.git)
   ```
2. Install the required libraries:
    ```bash
    pip3 install -r requirements.txt
    ```

## Setup & Usage

### 1. Prepare Your Data
Place your `reviews.csv` file inside the root project folder.

### 2. Open the Notebook
Launch the Jupyter notebook in VS Code

### 4. Calibrate Your Coordinates
Run the **"Calibration Cell"** inside the notebook. Using one link in the `reviews.csv` file:
1. Click on the **Edit** button.
2. Click the **Spoiler** checkbox.
3. Click the **Save** button.

### 5. Update Configuration
In the **"Configuration Cell"** of the notebook, update the variables with the numbers you gathered in the previous step:

EDIT_BTN_X, EDIT_BTN_Y
SPOILER_X, SPOILER_Y
SAVE_BTN_X, SAVE_BTN_Y

### 6. Run the Automation
Run the final cell in the notebook. Switch to your browser window and watch it work!

---

## Safety & Disclaimer

> **Important:** Keep your hands off the mouse while the script is running to avoid interfering with the automation.

* **Stopping the Script:** Move the cursor to the top left corner of the screen.
* **Rate Limits:** I tried to be conservative with waiting between clicks and changing reviews. You can shorten the sleep times but I noticed that letterboxd will block you if you go through the reviews too fast.
