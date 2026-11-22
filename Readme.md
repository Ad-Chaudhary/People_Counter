# Real-Time People Counting System (YOLO11 + BoT-SORT + ReID)

A computer vision web application built with **Ultralytics YOLO11**, **BoT-SORT with Re-Identification (ReID)**, and **Streamlit**. It detects and tracks only the `person` class (`class 0`) to count both people currently in frame and total unique individuals across video files or a live webcam feed.

## Features
- **Person-Only Filtering:** Strictly isolates COCO `class 0` (`person`), ignoring background objects.
- **Persistent Multi-Object Tracking:** Combines BoT-SORT motion modeling (`sparseOptFlow` camera motion compensation) with ReID appearance embeddings to maintain consistent Track IDs.
- **Dual Input Modes:**
  1. **Upload Video:** Process `.mp4`, `.avi`, `.mov`, and `.mkv` files with real-time bounding box overlays.
  2. **Live Feed:** Stream directly from a local webcam (`cv2.VideoCapture`).
- **Interactive Controls:** Adjust detection confidence thresholds dynamically from the sidebar.

## Project Structure
```text
├── app.py                # Streamlit frontend and tracking pipeline
├── botsort_reid.yaml     # Custom BoT-SORT + ReID configuration
├── yolo11n.pt            # Pre-trained YOLO11n weights
├── requirements.txt      # Python dependencies
└── README.md
```

## Quick Start

1. **Clone the repository**
   ```bash
   git clone [https://github.com/](https://github.com/)<your-username>/<your-repo-name>.git
   cd <your-repo-name>
   ```

2. **Install dependencies** (Python 3.10–3.12 recommended)
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Streamlit app**
   ```bash
   streamlit run app.py
   ```