# Hướng dẫn sử dụng

## Chạy trên Google Colab

<a href="https://colab.research.google.com/github/tripleseven190504/change-face/blob/main/DeepFake.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Chạy trên local

### Linux

```bash
cd ~
pip install --upgrade pip
git clone https://github.com/tripleseven190504/change-face.git
pip install fastapi kaleido python-multipart uvicorn
pip install --force-reinstall lida gcsfs google-colab huggingface-hub imageio tensorflow tensorflow-probability torchdata torchtext yfinance
pip install -r ~/change-face/requirements.txt
wget https://huggingface.co/ezioruan/inswapper_128.onnx/resolve/main/inswapper_128.onnx -O inswapper_128.onnx
mkdir ~/change-face/models
mv inswapper_128.onnx ~/change-face/models
pip uninstall onnxruntime onnxruntime-gpu -y
pip install torch torchvision torchaudio --force-reinstall --index-url https://download.pytorch.org/whl/cu118
pip install onnxruntime-gpu==1.15.1
```

```bash
cd ~/change-face
python run.py -s ~/face.jpeg -t ~/video.mp4 -o ~/new_video.mp4 --frame-processor face_swapper
```

### Windows

Download [Cuda](https://developer.download.nvidia.com/compute/cuda/11.8.0/network_installers/cuda_11.8.0_windows_network.exe)
#### Setup
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
```batch
choco install python --version=3.10.11
choco install git
choco install ffmpeg
choco install vcredist2015
choco install visualstudio2022buildtools --package-parameters "--add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended"
python -m ensurepip
```

```batch
@echo off
cd %USERPROFILE%\Desktop
git clone https://github.com/tripleseven190504/change-face.git
pip install fastapi kaleido python-multipart uvicorn
pip install --force-reinstall lida gcsfs google-colab huggingface-hub imageio tensorflow tensorflow-probability torchdata torchtext yfinance
pip install -r %USERPROFILE%\Desktop\change-face\requirements.txt
wget https://huggingface.co/ezioruan/inswapper_128.onnx/resolve/main/inswapper_128.onnx -O inswapper_128.onnx
mkdir %USERPROFILE%\Desktop\change-face\models
move inswapper_128.onnx %USERPROFILE%\Desktop\change-face\models
pip uninstall onnxruntime onnxruntime-gpu -y
pip install torch torchvision torchaudio --force-reinstall --index-url https://download.pytorch.org/whl/cu118
pip install onnxruntime-gpu==1.15.1

```
```batch
cd %USERPROFILE%\Desktop\change-face\
python run.py -s face.jpg -t video.mp4 -o new_video.mp4 --frame-processor face_swapper
```
