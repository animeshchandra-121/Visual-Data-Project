# VDA Project: Visual Squat Analysis with YOLO & ML

## 1️⃣ Project Title & Description

**VDA Project** is an automated system for analyzing squat exercise videos using YOLO-based pose detection and machine learning. It provides actionable feedback on form, performance, and consistency, making it a valuable tool for athletes, coaches, and researchers.

## 2️⃣ Features
- **Rep Counting**: Automatically detects and counts squat repetitions.
- **Angle Tracking**: Tracks knee and joint angles throughout the exercise.
- **Form Scoring**: Scores form based on symmetry, consistency, range, and stability.
- **Anomaly Detection**: Flags unusual reps using ML.
- **Trend Analysis**: Tracks changes in form over time.
- **Performance Prediction**: Classifies speed and consistency of reps.
- **Visual Analytics**: Generates plots and dashboards.
- **Detailed Reports**: Produces text summaries and recommendations.

## 3️⃣ System Architecture
```mermaid
graph TD
    A[User Videos] --> B[YOLO Pose Detection]
    B --> C[Keypoint Extraction]
    C --> D[Angle & Rep Analysis]
    D --> E[Analytics Data (JSON)]
    E --> F[ML Analytics & Scoring]
    F --> G[Visualizations & Reports]
```

## 4️⃣ Installation Guide
- Clone the repo and navigate to the project directory.
- Install dependencies:
  ```bash
  pip install -r requirements.txt
  ```
- (Optional) Set up a virtual environment for isolation.

## 5️⃣ Model Setup
- This project uses the YOLO pose model from Ultralytics.
- The model is automatically downloaded on first use via the `ultralytics` package.
- For manual setup or offline use, follow Ultralytics' documentation: https://docs.ultralytics.com/

## 6️⃣ Usage Instructions
**Step 1:** Process your squat videos with Version 1:
```bash
python vda_version_1.py --videos path/to/video1.mp4 path/to/video2.mp4
```
- This generates `squat_analytics_data.json`.

**Step 2:** Run ML analytics with Version 2:
```bash
python vda_version_2.py
```
- This creates `squat_analytics_ml.png` and `squat_analysis_ml_report.txt`.

## 7️⃣ Requirements
- **Hardware:**
  - CPU (GPU recommended for faster video processing)
  - 8GB+ RAM
- **Software:**
  - Python 3.8+
  - OS: Windows, Linux, or macOS

## 8️⃣ Dataset Explanation
- User-provided squat videos are processed frame-by-frame.
- Keypoints and angles are extracted to form the analytics dataset (`squat_analytics_data.json`).
- No external dataset required; your videos are the data source.

## 9️⃣ Analytics Outputs
- **Metrics:**
  - Total reps, duration, average rep time, angle statistics
  - Form quality scores (overall, symmetry, consistency, range, stability)
  - Rep anomalies and performance profile
- **Visualizations:**
  - Angle trends, rep timing, form metrics, symmetry plots
- **Reports:**
  - Detailed text report with ML-based recommendations

## 🔟 Sample Results Summary
- Example ML Report:
  - Overall Form Score: 82/100
  - Symmetry: 90/100 (Excellent)
  - Consistency: 78/100 (Good)
  - Range: 65/100 (Moderate)
  - Stability: 85/100 (Smooth)
  - Performance: "Good Speed, Good Consistency"
  - Detected 1 anomalous rep (rep 7)
  - Recommendation: "Improve range of motion for deeper squats."

---

For more details, see the code in `vda_version_1.py` and `vda_version_2.py`.

You can install them using pip:

```bash
pip install numpy matplotlib scikit-learn opencv-python ultralytics
```

### Execution

1.  **Generate Analytics Data**: Run `vda_version_1.py` to process your squat videos and create the `squat_analytics_data.json` file.
2.  **Run the Analysis**: Execute `vda_version_2.py` to perform the analysis on the generated JSON data:

    ```bash
    python vda_version_2.py
    ```

### Output Files

After running the analysis, the following files will be generated:

- `squat_analytics_ml.png`: A visual dashboard containing all the analytical plots.
- `squat_analysis_ml_report.txt`: A detailed report with metrics, scores, and personalized recommendations.

## Project Structure

- `vda_version_1.py`: The script responsible for processing video files and extracting raw analytics data.
- `vda_version_2.py`: The main script for running the machine learning analysis and generating reports.
- `squat_analytics_data.json`: The JSON file containing the data extracted from the videos.
- `README.md`: This file.
