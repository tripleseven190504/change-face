# Preview

![preview image](preview.png)

## Hướng dẫn cài đặt

### Chuẩn bị

1. Mở PowerShell với quyền quản trị bằng cách nhấn phải vào biểu tượng PowerShell và chọn "Run as Administrator".

2. Chạy lệnh sau để cài đặt Chocolatey hoặc Scoop `nếu chưa có`:
    1. Chocolatey
    ```powershell
    Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
    ```
    2. Scoop
    ```powershell
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
    ```

3. Sau khi cài đặt Chocolatey thành công, chạy lệnh sau
    ```powershell
    choco install ffmpeg -y
    ```
    hoặc
    ```powershell
    scoop install ffmpeg
    ```
4. Cài đặt [Visual C++ Build Tools](https://aka.ms/vs/17/release/vs_BuildTools.exe) và [Python](https://www.python.org/ftp/python/3.10.11/python-3.10.11-amd64.exe) kèm theo [Cuda](https://developer.nvidia.com/cuda-downloads?target_os=Windows&target_arch=x86_64), [FFMPEG](https://github.com/BtbN/FFmpeg-Builds/releases](https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Windows&target_arch=x86_64))
5. Cài InsightFace:
   ```powershell
   pip install insightface
   ```
### Chạy ứng dụng

Để chạy ứng dụng, hãy mở tệp `start.bat`

**Chú ý:** Lần đầu tiên cài đặt, bạn sẽ cần phải tải và cài đặt một số thư viện và các file phụ trợ có dung lượng khoảng `2. GB`.
