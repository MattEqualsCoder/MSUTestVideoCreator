# MSU Test Video Creator

MSU Test Video Creator is a Python-based commandline application originally created by [StructuralMike](https://github.com/StructuralMike) for creating mp4 and wav files of a series of PCM files to use for uploading to YouTube to test for potential copyright strikes. This version was adapted to use pip/pipx for dependency resolution and easier calling by the MSU Scripter.

## Installation

### Pre-requisites

- Python 3.8 or above
- ffmpeg 
    - Ubuntu/Debian: apt-get install libportaudio2
    - RHEL: dnf install portaudio
    - Arch: pacman -S portaudio

### Installation Option 1: pipx (recommended)

pipx is recommended as it installs the application into an isolated environment to avoid dependency conflicts with other Python applications, and it also creates it standalone application which can be ran directly via commandline.

First, you will want to install [pipx](https://pypa.github.io/pipx/).

```
$ pipx install msu_test_video_creator

$ msu_test_video_creator -f test.pcm -o test.mp4
```

If you need to upgrade, then you can run the following:

```
$ pipx upgrade msu_test_video_creator
```

### Installation Option 2: pip

First, make sure you have pip installed and running: https://packaging.python.org/en/latest/tutorials/installing-packages/

```
$ pip install msu_test_video_creator

$ py -m msu_test_video_creator -f test.pcm -o test.mp4
```

If you need to upgrade, then you can run the following:

```
$ pip install msu_test_video_creator --upgrade
```

## Usage

Depending on your environment and how you installed, you may be able to run it either directly or as a Python module:

```
# Run directly
$ msu_test_video_creator -f test.pcm -o test.mp4

# Run as Python module
$ py -m msu_test_video_creator -f test.pcm -o test.mp4
```

The application requires two arguments:

- -f: A comma-delimited list of all pcm files to include
- -i: The path to a YAML file with a list of all pcm files in the following format:
    ```
    Files:
     - c:/pathto/file-1.pcm
     - C:/pathto/file-2.pcm
    ```
- -o: The path to the mp4 file to generate


## Credits

- [StructuralMike](https://github.com/StructuralMike) for the original Python script this was based on.
- [Hazem Nabil (arkrow)](https://github.com/arkrow) for the idea of using Poetry for making/distributing Python applications.