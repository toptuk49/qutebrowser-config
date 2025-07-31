# qutebrowser configuration ⚙️

## Requirements ✅

64-bit x86 system or Apple Silicon system
Python 3.9 or newer

## Browser Installation ⬇️

According to qutebrowser [documentation](https://qutebrowser.org/doc/install.html), it is recommended to install the program in a python virtual environment.

```bash
git clone https://github.com/qutebrowser/qutebrowser.git
cd qutebrowser

python3 scripts/mkvenv.py # Installs all needed Python dependencies
```

## Browser Usage ⚡

Running `scripts/mkvenv.py` does not install a system-wide qutebrowser script. You can launch qutebrowser by doing:

```bash
.venv/bin/python3 -m qutebrowser
```

You can create a simple wrapper script to start qutebrowser:

```bash
touch <desired_path>/qutebrowser # or any other name of a script
```

Script should contain:

```bash
#!/bin/bash

APP_DIR="$HOME/<desired_path>/qutebrowser"

if [[ "$1" == "--update" ]]; then
  cd "$APP_DIR"
  python3 scripts/mkvenv.py --update
  exit $?
fi

cd "$APP_DIR" || exit 1
"$APP_DIR/.venv/bin/python3" -m qutebrowser "$@"
```

After that you can make script executable:

```bash
chmod +x /desired/path/qutebrowser
```

Add desired path to script to $PATH if not specified:

```bash
# ~/.bash_profile or ~/.bashrc or ~/.zshrc
export PATH="$HOME/desired/path:$PATH"
```

And reload configuration:

```bash
source ~/.bash_profile # bash
source ~/.zshrc # zsh
```

After that you are able to use browser like this:

```bash
qutebrowser # run browser
qutebrowser --update # update browser
```

## Configuration Installation 🎯

### macOS 👨‍💻

```bash
git clone https://github.com/toptuk49/qutebrowser-config.git ~/.qutebrowser
```

### Linux 🐧

```bash
git clone https://github.com/toptuk49/qutebrowser-config.git ~/.config/qutebrowser
```

### Windows 🖥️

```bash
git clone https://github.com/toptuk49/qutebrowser-config.git %APPDATA%/qutebrowser/config/config.py
```
