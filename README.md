# Python Workplace Script Demo

1. Create directory for your scripts if you don't have one already

```bash
mkdir scripts
```

2. Add scripts to path

```bash
code ~/.zshrc or code ~/.bashrc
```

3. Paste this in and save

```bash
export PATH="$PATH:$HOME/scripts"
```

4. Apply changes

```bash
source ~/.zshrc or source ~/.bashrc
```

5. Create new script (I just simply call mine py)

```bash
code scripts/<name-of-script-command>
```

6. Paste in the command and save the file

```bash
#!/bin/bash

# Check if the file name is provided
if [ -z "$1" ]; then
  echo "Usage: $0 <directory_name>"
  exit 1
fi

FILE_NAME=$1

# Navigate to the home directory and then to the 'python' directory
cd && cd python

# Create the new directory
mkdir "$FILE_NAME"

# Navigate to the newly created directory
cd "$FILE_NAME"

# Create the .gitignore file with 'venv' in it
echo "venv" > .gitignore

# Set up the virtual environment with Python 3.11
virtualenv venv --python=python3.11

# Create the notebook.ipynb file with the activation command in the first cell
cat <<EOT > notebook.ipynb
{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Select kernel in top right",
    "# Activate the virtual environment and init git with commands below",
    "# source venv/bin/activate",
    "# git init"
   ]
  }
 ],
 "metadata": {},
 "nbformat": 4,
 "nbformat_minor": 2
}
EOT

# Open the new directory in VS Code
code .
```

7. Make the script executable with the following command

```bash
chmod +x scripts/<name-of-script-command>
```

8. Easily create a new python workspace!

```bash
py dank-workspace
```

My links:

- YouTube 👉 https://youtube.com/@coleblender
- X 👉 https://twitter.com/ColeBlender
- IG 👉 https://www.instagram.com/yazzibelani

Video 👉 https://www.youtube.com/watch?v=iSnO5yY3JQg
