# 🎬 ytmagic

`ytmagic` is a simple command-line tool that lets anyone download videos or extract audio from **YouTube, Instagram, Facebook, TikTok, X, and more** using [yt-dlp](https://github.com/yt-dlp/yt-dlp) — no technical knowledge needed.

It works on **Linux**, **macOS**, and **Windows**.

## 🧠 What Can It Do?

- ✅ Download full video with best quality
- 🎧 Download **audio only** and convert it to MP3
- 📥 Choose specific video quality like 360p, 720p, 1080p, best
- 📂 Save to a custom folder or default to `~/Downloads`
- 🔁 Resume interrupted downloads
- 📊 Show all available qualities/formats for one or more links

## 🔧 Installation

Make sure you have **Python 3.7+**, `ffmpeg`, and `pip/pipx` installed.

Install `ytmagic` globally using `pip/pipx`:

```bash
pip install ytmagic

```

Or for local testing (developer mode):

```bash
git clone https://github.com/owais-shafi/YTMAGIC.git
cd ytmagic
pipx install --force --editable .

```

✅ Now you can use the `ytmagic` (or `yt`) command from anywhere in your terminal.

## 🎯 How to Use

Basic command format:

```bash
yt [options] [URL1... URLn]
```

### 🔤 Examples

1 Show the version of ytmagic:

```bash
   yt -v
```

2 Download a video in best quality (auto save to Downloads folder):

```bash
   yt https://youtu.be/VIDEO_URL
```

3 Download multiple videos in best quality to Downloads folder:

```bash
   yt URL1 URL2 URL3
```

4 Convert to MP3(Audio only) and Download to Music folder:

```bash
   yt -a -p ~/Music URL1 URL2 URL3
```

5 Download videos in different Qualities to a user-specified folder/Path:

```bash
   yt -q 720 -p ~/Videos URL1 URL2 URL3

   yt -q 360 -p ~/Videos URL1 URL2 URL3

   yt -q best -p ~/Videos URL1 URL2 URL3
```

6 Show available Qualities/formats for multiple videos:

```bash
   yt -f URL1 URL2 URL3
```

7 Resume interrupted downloads:

```bash
   yt -r URL1 URL2 URL3

   yt --resume URL1 URL2 URL3
```

---

## ⚙️ Command-Line Options

| Option              | Description                                                             |
| ------------------- | ----------------------------------------------------------------------- |
| `urls` (positional) | One or more video URLs (YouTube, Instagram, Facebook, TikTok, etc.)     |
| `-q`, `--quality`   | Video quality: `360`, `480`, `720`, `1080`, or `best` (default: `best`) |
| `-p`, `--path`      | Path to save downloaded file (default: `~/Downloads`)                   |
| `-a`, `--audio`     | Download audio only and convert to MP3 (requires FFmpeg)                |
| `-f`, `--formats`   | Show available qualities/formats for all given URLs                     |
| `-r`, `--resume`    | Resume interrupted downloads                                            |
| `-v`, `--version`   | Show ytmagic version                                                    |

---

## 📦 Dependencies

To use the `-a` (audio-only MP3) option, `ffmpeg` must be installed on your system.

### ✅ Install `ffmpeg`

- **Linux (Debian/Ubuntu or any other distro using their own package manager):**

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
yt -a -p ~/Music URL1 URL2
```

- This downloads multiple best-quality audio files, converts them to MP3, and saves them to `~/Music`.

```bash
yt -q 720 -p ~/Videos URL1 URL2
```

- This downloads multiple 720p-quality videos, and saves them to `~/Videos`.

- Use `-f` before downloading if you want to check available formats/qualities:

```bash
yt -f URL1 URL2
```

- Use `--resume` to continue interrupted downloads:

```bash
yt -r URL1 URL2 URL3
```

---

## 👨‍🔧 Built With

- [Python](https://www.python.org/)
- [yt-dlp](https://github.com/yt-dlp/yt-dlp)
- [ffmpeg](https://ffmpeg.org/)

---

## 📜 License

MIT License — free for personal or commercial use.
