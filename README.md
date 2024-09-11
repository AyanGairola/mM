
# Game Sense

This project aims to process and analyze tennis matches by detecting players and the ball. The primary goal is to extract meaningful insights and generate statistics based on player movements and ball tracking.


## Run Locally

This project requires python 3.10


Clone the project

```bash
  git clone https://link-to-project
```

Create a new Environment

using Anaconda

```bash
conda create gameSense
```

```bash
conda activate gameSense
```

OR

using Venv

```bash
python -m venv myenv
```

```bash
source myenv/bin/activate
```

Install Dependencies
```bash
pip install -r requirements.txt
```

Go to the project directory

```bash
  cd tennis
```

Go to Models directory

```bash
  cd models
```
Download the pretrained Models from the drive link
https://drive.google.com/drive/folders/1bs47xAaW56BFVQJx6tOJ45rTH0mq4evB?usp=sharing

Add the keypoints_model.pth to the models directory

Go to player_and_ball_detection directory

```bash
  cd player_and_ball_detection directory
```

Add the player and ball detection / best.pt from the drive link to the player_and_ball_detection directory

Go back a few directories

```bash
  cd ../..
```

You should be now in Tennis direcotry 

Open the file in your favourite code eidtor

```bash
  code .
```

Open main.py

On line no. 109 add your Gemini Api Key 

```python
api_key = "YOUR_GEMINI_API_KEY"  
```

If you don't have one no issues just leave the code as it is it will fallback to non generative commentary

```python
api_key = ""  
```

Processing the video will take a lot of time because of all the api calling to gemini and the processing so it's better to grab a bite at this point. 

We have provided the pickle file for the input video provided that will decrease the time by a lot. If not using the earlier provided input file. Open main.py 

On line 86 toggle the read_from_stub value to false and the stub_path to none. 

```python
detections = unified_tracker.detect_frames(video_frames, read_from_stub=False, stub_path=None)
```

Run main.py file with the input video's pathname as argument

```bash
python3 main.py input_vods/input_video1.mp4 
```

Output Video can be found out in output_vods direcotry


## Project Overview: Development of an ML-powered system for real-time analysis of tennis matches.

### Player and Ball Tracking 
Implement real-time object detection and tracking algorithms for player and ball localization using computer vision, custom pretrained yolo models and roboflow datasets. 

 ### Court Detection and Event Analysis
 Used pretraied ResNet50 model for court detection , applied homography transformations for court boundary refinement and applied event detection techniques to detects in game events like ball hit and type of shots. 

### Commentary Generation
Integrate event-based dynamic generative ( Google Gemini) commentary engine that generates contextual insights based on in-game events.

### Mini Court Generation
Developed a Mini court based on actual court for better visualisations and calculations. 

### Player Stats
Generated player stats based on movement and ball shots. 
