**Clone Repo**

```bash
git clone https://github.com/JohnLeFeng/Deep-Live-Cam.git
cd Deep-Live-Cam
git checkout yep
```

**Install Dependencies**

We highly recommend using a `venv` to avoid issues.

```bash
python -m venv ____envs
____envs\Scripts\activate
pip install -r requirements.txt
```

**OpenVINO™ Execution Provider (Intel)**

1. Download OpenVINO 2025.3 from [link](https://storage.openvinotoolkit.org/repositories/openvino/packages/2025.3/windows/openvino_toolkit_windows_2025.3.0.19807.44526285f24_x86_64.zip) and unzip.

2. Copy all dlls under `<ROOT_DIR>\openvino_toolkit_windows_2025.3.0.19807.44526285f24_x86_64\runtime\bin\intel64\Release` to `____envs\Lib\site-packages\onnxruntime\capi`

3. Usage:

```bash
python run.py --execution-provider openvino
```