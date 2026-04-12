# 🎯 Virtual Advertising Overlay using Computer Vision

This project implements a **real-time virtual advertising system** that overlays a sponsor logo onto a sports field while maintaining correct perspective and handling occlusions.

It simulates how advertisements are digitally placed on fields during live sports broadcasts.

---

## 🚀 Features

* 🎥 **Dynamic Logo Placement**

  * Uses **Homography** to map a 2D logo onto the ground plane
  * Keeps the logo fixed even when the camera moves

* 🔄 **Camera Motion Handling**

  * Uses **Optical Flow (Lucas-Kanade)** to track ground points
  * Ensures stable placement during panning and zooming

* 👤 **Occlusion Handling**

  * Uses **YOLOv8** to detect players
  * Players correctly appear **above the logo**

* 🎨 **Realistic Blending**

  * Alpha blending with opacity control
  * Optional brightness matching for natural look

* ⚡ **End-to-End Pipeline**

  * Fully automated (no manual uploads required)
  * Works directly in **Google Colab**

---

## 🛠️ Tech Stack

* Python
* OpenCV
* NumPy
* YOLOv8 (Ultralytics)
* Matplotlib
* Google Colab

---

## 📁 Project Structure

```
├── Virtual_Advertising_Overlay_System.ipynb        # Complete pipeline (Colab notebook)
├── logo.png
├── video.mp4
├── README.md              # Project documentation
```

---

## ▶️ How to Run

1. Open the notebook in **Google Colab**
2. Run all cells sequentially
3. The notebook will:

   * Download video automatically
   * Download logo automatically
   * Process frames
   * Generate output video

---

## 📌 Methodology

### 1. Ground Plane Detection

* Manually define 4 points on the field
* Represents the area where the logo will be placed

### 2. Homography Transformation

* Compute transformation matrix using:

```math
H = mapping(logo → ground)
```

* Warps logo to match field perspective

### 3. Tracking (Optical Flow)

* Uses **Lucas-Kanade Optical Flow**
* Tracks ground points across frames
* Updates homography dynamically

### 4. Occlusion Handling

* YOLOv8 detects players
* Creates a mask
* Removes logo where players are present

### 5. Logo Blending

* Alpha blending:

```
Result = α * Logo + (1 - α) * Frame
```

---

## 📊 Output

* 🎬 Final processed video with overlay
* 🖼️ Frame samples
* 🔍 Side-by-side comparison (original vs processed)

---

## 💡 Key Highlights

* Handles **camera motion**
* Maintains **real-world alignment**
* Supports **real-time processing**
* Implements **industry-relevant CV techniques**

---

## 📷 Example Use Case

* Sports broadcasting
* Virtual advertisements
* Augmented reality overlays

---

## 🧠 Learnings

* Homography & perspective transformation
* Optical flow tracking
* Object detection with YOLO
* Real-world CV pipeline design

---

## 👤 Author

**Sunayana Yadav**
