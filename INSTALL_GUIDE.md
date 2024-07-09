# Demucs Installation Instructions

Tested on Ubuntu 2-core machine with 40GB of RAM.

```bash
# Step 1: Ensure a Clean Environment
# Remove any partially installed Anaconda directories
rm -rf ~/anaconda3

# Redownload the Anaconda installer
wget https://repo.anaconda.com/archive/Anaconda3-2023.03-Linux-x86_64.sh

# Step 2: Verify the Integrity of the Installer
# Verify the SHA-256 checksum
sha256sum Anaconda3-2023.03-Linux-x86_64.sh
# Compare the output with the SHA-256 hash provided on the Anaconda distribution page

# Step 3: Run the Installer Again
# Run the installer script with bash
bash Anaconda3-2023.03-Linux-x86_64.sh

# Follow the prompts:
# - Press Enter to continue
# - Scroll through the license agreement and type `yes` to accept
# - Press Enter to confirm the installation location

# Step 4: Initialize Anaconda
# Initialize Anaconda
source ~/.bashrc

# Step 5: Create and Activate a Conda Environment
# Create a Conda environment
conda create -n demucs python=3.9

# Activate the environment
conda activate demucs

# Step 6: Install Demucs and Dependencies
# Install Demucs via pip
pip install demucs==4.0.0

# Install additional dependencies for sound processing
sudo apt-get install soundstretch

# Step 7: Verify Installation and Run Demucs
# Verify the installation
demucs --help
# You should see the help message for Demucs, indicating that it’s installed correctly

# Separate tracks using Demucs
# For example, if you have an audio file named `my_song.mp3` in your current directory, you can run:
demucs --mp3 my_song.mp3
