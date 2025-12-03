Here’s your **copy-paste ready README** for `ytmagic` with **all current features included**:

````markdown
# 🎬 ytmagic

`ytmagic` is a simple command-line tool that lets anyone download videos or extract audio from **YouTube, Instagram, Facebook, TikTok, X, and more** using [yt-dlp](https://github.com/yt-dlp/yt-dlp) — no technical knowledge needed.

It works on **Linux**, **macOS**, and **Windows**.

---

## 🧠 What Can It Do?

- ✅ Download full video with best quality
- 🎧 Download **audio only** and convert it to MP3
- 📥 Choose specific video quality like 360p, 720p, 1080p
- 📂 Save to a custom folder or default to `~/Downloads`
- 🔁 **Resume interrupted downloads**
- 📊 **Show all available formats** for one or more links

---

## 🔧 Installation

Make sure you have **Python 3.7+**, `ffmpeg`, and `pip/pipx` installed.

Install `ytmagic` globally using `pipx`:

```bash
pipx install ytmagic
```
````

Or for local testing (developer mode):

```bash
git clone https://github.com/owais-shafi/Yt_Magic.git
cd ytmagic
pipx install --force --editable .
```

✅ Now you can use the `ytmagic` (or `yt`) command from anywhere in your terminal.

---

## 🎯 How to Use

Basic command format:

```bash
ytmagic [options] URL1 [URL2 ... URLn]
```

### 🔤 Examples

```bash
ytmagic https://youtu.be/example1
# ▶️ Downloads best video+audio to ~/Downloads

ytmagic https://youtu.be/example2 -q 720
# ⬇️ Downloads 720p video

ytmagic https://youtu.be/example3 -a
# 🎵 Downloads and converts audio to MP3

ytmagic -a -p ~/Music https://youtu.be/example4
# 🎧 Downloads MP3 and saves it in ~/Music

ytmagic https://youtu.be/example5 https://youtu.be/example6
# ⬇️ Downloads multiple videos in order

ytmagic -f https://youtu.be/example7 https://youtu.be/example8
# 📊 Shows available qualities/formats for multiple videos

ytmagic --resume https://youtu.be/example9
# 🔁 Resumes interrupted download
```

---

## ⚙️ Command-Line Options

| Option              | Description                                                             |
| ------------------- | ----------------------------------------------------------------------- |
| `urls` (positional) | One or more video URLs (YouTube, Instagram, Facebook, TikTok, etc.)     |
| `-q`, `--quality`   | Video quality: `360`, `480`, `720`, `1080`, or `best` (default: `best`) |
| `-p`, `--path`      | Folder to save downloaded file (default: `~/Downloads`)                 |
| `-a`, `--audio`     | Download audio only and convert to MP3 (requires FFmpeg)                |
| `-f`, `--formats`   | Show available formats for all given URLs                               |
| `--resume`          | Resume interrupted downloads                                            |
| `-v`, `--version`   | Show ytmagic version                                                    |

---

## 📦 Dependencies

To use the `-a` (audio-only MP3) option, `ffmpeg` must be installed on your system.

### ✅ Install `ffmpeg`

- **Linux (Debian/Ubuntu):**

  ```bash
  sudo apt install ffmpeg
  ```

- **Linux (Arch):**

  ```bash
  sudo pacman -S ffmpeg
  ```

- **macOS (with Homebrew):**

  ```bash
  brew install ffmpeg
  ```

- **Windows (with Chocolatey):**

  ```bash
  choco install ffmpeg
  ```

- Or [download manually](https://www.gyan.dev/ffmpeg/builds/) and add it to your system PATH.

---

## 📂 Default Output Folder

If no path is given using `-p`, ytmagic saves all downloads to:

```bash
~/Downloads
```

---

## 💡 Tips

- Combine options for multiple features:

```bash
ytmagic -a -q best -p ~/Music https://youtu.be/example1 https://youtu.be/example2
```

- This downloads multiple best-quality audio files, converts them to MP3, and saves them to `~/Music`.

- Use `-f` before downloading if you want to check available formats:

```bash
ytmagic -f https://youtu.be/example1 https://youtu.be/example2
```

- Use `--resume` to continue interrupted downloads:

```bash
ytmagic --resume https://youtu.be/example1
```

---

## 📱 Run on Android (via Termux)

Yes — `ytmagic` works on Android too using [Termux](https://f-droid.org/packages/com.termux/)!

### ✅ Steps to Set It Up

1. Install Termux from Play store.
2. Open Termux and run:

```bash
pkg update && pkg upgrade
pkg install python ffmpeg termux-api
pip install pipx
pipx ensurepath
source ~/.bashrc  # Or restart Termux
```

3.Install ytmagic:

```bash
pipx install ytmagic
```

4.Grant storage access to Termux:

```bash
termux-setup-storage
```

5.Save downloads to phone storage:

```bash
ytmagic -p /sdcard/Download/ <URL>
```

6.Make media files appear in apps:

```bash
termux-media-scan /sdcard/Download/
```

7.(Optional) Add handy shortcuts in `~/.bashrc`:

```bash
alias sc='termux-media-scan /sdcard/Music/'
alias yt='ytmagic -p /sdcard/Download/'
source ~/.bashrc
```

Run `sc` after every download so media files appear in music/video apps.

---

## 👨‍🔧 Built With

- [Python](https://www.python.org/)
- [yt-dlp](https://github.com/yt-dlp/yt-dlp)
- [ffmpeg](https://ffmpeg.org/)

---

## 📜 License

MIT License — free for personal or commercial use.
