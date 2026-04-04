# Double Clap Workspace Trigger

A minimal Python script that listens for a double clap to automatically open applications, websites, and set up your workspace.

## Prerequisites

On macOS, you will likely need to install PortAudio before installing the Python packages:
```bash
brew install portaudio
```

## Installation

Install the required Python packages using pip:
```bash
pip install -r requirements.txt
```

## Usage

Start the listener from your terminal:
```bash
python app.py
```
Wait for the terminal to print `Listening for double claps...`. Once running, give two loud, distinct claps, and your configured tasks will execute! 

*Note: After triggering the protocol, the listening gets paused to avoid audio feedback from music/videos. To completely stop the script, press `Ctrl+C` in your terminal.*

## How to Customize Tasks

To change what happens when you double clap, open `app.py` and scroll down to the `if clap_count == 2:` block. 

You can add or remove tasks inside this block. The easiest way to trigger things on Mac is using `os.system()`. Examples:

```python
# 1. Open an application
os.system("open -a 'Spotify'")

# 2. Open a website in your browser
os.system("open -a 'Google Chrome' 'https://github.com'")

# 3. Open a specific project or file
os.system("open -a 'Visual Studio Code' '/Path/To/Your/Project'")
```
Just place your desired commands in `app.py`, save, and run it again!
