# Vehicle-Counter
 MSIB : AI Engineer Intern Knowledge Test

# Vehicle Counting System using YOLOv8n

This project implements a vehicle counting system using custom-trained YOLOv8 object detection and tracking. It processes a video of a toll gate area, detects and tracks vehicles (buses and cars), and counts them as they pass through different gates.

## Features

- Detects and tracks buses and cars using custom-trained YOLOv8
- Counts vehicles passing through 8 different gates
- Visualizes tracking lines and gate boundaries
- Displays real-time count of vehicles for each gate
- Generates an output video with annotations and counts
- Provides a summary of vehicle counts after processing

## Requirements

- Python 3.11.9
- OpenCV==4.10.0
- Numpy==1.26.4
- Ultralytics YOLOv8n
- torch==2.2.0 torchvision==0.17.0 torchaudio==2.2.0

## Structure

- Vehicle-Counter
  - assets
    - toll gate.mp4
    - vehicle_count_output.mp4
  - Training
    - datasets
      - test
        - images
        - labels
      - train
        - images
        - labels
      - valid
        - images
        - labels
    - runs
      - detect
        - train
          - weights
            - best.pt
            - last.pt
    - data.yaml
    - train.ipynb
    - yolov8n.pt
  - main.ipynb

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/Muhamadridhoalisya/Vehicle-Counter.git
   cd Vehicle-Counter
   ```

2. Install the required packages:
   ```
   pip install ipykernel
   ```
   ```
   pip install torch==2.2.0 torchvision==0.17.0 torchaudio==2.2.0
   ```
   ```
   pip install numpy
   ```
   ```
   pip install opencv-pytho
   ```
   ```
   pip install ultralytics
   ```

## Attention

* if you have error about ultralytics setting, please check "C:\Users\muham\AppData\Roaming\Ultralytics\settings.yaml". Change 'datasets_dir: C:\Users\muham\Downloads\Compressed\msib\datasets' with your directory datasets
* Please do not upgrade 'torch' library and 'python' version, the new version have bug.

## Usage

1. Place your input video file (e.g., `toll_gate.mp4`) in the project directory.

2. Open file 'main.ipynb' in Visual Studio Code.

3. Change video and model directory to yours in this code section:
   - model = YOLO(r"Training\runs\detect\train\weights\best.pt")
   - video_path = r"assets\toll_gate.mp4"
   - output_path = r"assets\vehicle_count_output.mp4"

2. Run 'main.ipynb' with execute cell (default Ctrl+Alt_Enter)

3. The code will process the video and generate an output video named `vehicle_count_output.mp4`.

4. Press 'q' if you want to quit the video display window. If not, the code automatically stop when video duration end.

5. After processing, the script will print a summary of vehicle counts for each gate and the total counts.

## Customization

- To use a different input video, change the `video_path` variable in the script.
- To adjust the gate locations or add more gates, modify the `coordinates` dictionary in the script.
- if you want to training again, make sure that directory in file 'Training\data.yaml' is right.

## Output

The script generates:
1. An annotated video (`vehicle_count_output.mp4`) in `assets\vehicle_count_output.mp4` showing:
   - Detected vehicles with bounding boxes
   - Tracking lines for each vehicle
   - Gate boundaries
   - Real-time vehicle counts for each gate

3. A console output with:
   - Vehicle counts for each gate
   - Total counts for buses and cars

## Youtube link:
https://youtu.be/goYInexc3kw

## License

-

## Acknowledgements

- This project uses the custom-trained YOLOv8 model from Ultralytics.
- image labeling using roboflow.
- Only 2 class in custom trained model: 'BUS' and 'CAR'.
- 'model' in 'model = YOLO(r"Training\runs\detect\train\weights\best.pt")' is using trained model.
- Train your model using 'Training\train.ipynb'.
- This project build in Visual Studio Code Windows 11.

## Contact

Muhamad Ridho Al Isya - muhamad.ridho.al-2021@ftmm.unair.ac.id

Project Link: https://github.com/Muhamadridhoalisya/Vehicle-Counter.git
