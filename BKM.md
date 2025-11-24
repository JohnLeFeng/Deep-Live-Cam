**Set up Your Platform**

-   Python (3.11 recommended, 3.12 works)
-   pip
-   git
-   ffmpeg - Ref: [link](https://vocus.cc/article/64701a2cfd897800014daed0)
-   [Visual Studio 2022 Runtimes (Windows)](https://visualstudio.microsoft.com/visual-cpp-build-tools/)

**Clone the Repository**

```bash
git clone https://github.com/JohnLeFeng/Deep-Live-Cam.git
cd Deep-Live-Cam
git checkout yep
```

**Download the Models**

* Please place these files in the "**models**" folder.

    * [GFPGANv1.4](https://huggingface.co/hacksider/deep-live-cam/resolve/main/GFPGANv1.4.pth)
    * [inswapper\_128.onnx](https://huggingface.co/ezioruan/inswapper_128.onnx/blob/main/inswapper_128.onnx)

* Place below folder in the "C:\Users\<user-name>\.insightface\models\" folder.

    * [buffalo_m](https://intel-my.sharepoint.com/:f:/p/john_feng/ErFcBGHgIaVCtihCoGCXaz8B9GMJBCY1iGH7OO3w9pE4RA?e=lzIEUU)

**Install Dependencies**

We highly recommend using a `venv` to avoid issues.

```bash
python -m venv ____envs
____envs\Scripts\activate
pip install -r requirements.txt
```

**Update insightface package**

Open `____envs\Lib\site-packages\insightface\app\face_analysis.py` and update it to [face_analysis.py](https://github.com/JohnLeFeng/insightface/blob/yep/python-package/insightface/app/face_analysis.py).


**OpenVINO™ Execution Provider (Intel)**

1. Download OpenVINO 2025.3 from [link](https://storage.openvinotoolkit.org/repositories/openvino/packages/2025.3/windows/openvino_toolkit_windows_2025.3.0.19807.44526285f24_x86_64.zip) and unzip.

2. Copy all dlls under `<ROOT_DIR>\openvino_toolkit_windows_2025.3.0.19807.44526285f24_x86_64\runtime\bin\intel64\Release` to `____envs\Lib\site-packages\onnxruntime\capi`

3. Usage:

    ```bash
    python run.py --execution-provider openvino
    ```
