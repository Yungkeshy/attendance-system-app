# AI-Based Face Recognition Attendance System

![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-1.25%2B-red.svg)
![AWS](https://img.shields.io/badge/AWS-EC2-orange.svg)
![Database](https://img.shields.io/badge/Database-MySQL%20%26%20Redis-red.svg)

This repository contains the code for a full-stack, real-time facial recognition attendance system. The project uses a robust AI pipeline for identification and features a Streamlit web app, a dual-database backend, and is designed for cloud deployment on AWS EC2.

This project was developed as my Bachelor's Thesis and achieved an accuracy of over 95% in real-time testing.

---

> ### 🎓 **Academic Publication**
> This project was published in the *International Journal of Innovative Research in Engineering & Multidisciplinary Physical Sciences* (IJIRMPS), Volume 12, Issue 2.
> * **Title:** AI-Based Face Recognition Attendance System 
> * **DOI:** [`10.37082/ijirmps.v12.i2.230598`](https://doi.org/10.37082/ijirmps.v12.i2.230598) 
> * **ISSN:** 2349-7300 


---

## Abstract

*(As published in IJIRMPS)*

The AI Based Face Recognition Attendance System represents an innovative solution at the intersection of artificial intelligence and attendance management. Leveraging Python open-source libraries such as OpenCV and NumPy, alongside machine learning techniques, the system aims to streamline the attendance tracking process. By employing face detection algorithms and feature extraction methods, the system identifies individuals, records their attendance, and updates the database in real-time. The system architecture incorporates components like a front-end web application, real-time prediction module, registration form module, reporting module, Redis database, Streamlit framework, Insightface library, and AWS deployment. Through continuous improvement and innovation, the system enhances user experience, accuracy, and efficiency in attendance management.

**Keywords:** Artificial Intelligence (AI), Face Recognition, Attendance System, Machine Learning, OpenCV, Insightface

---
## 📸 Application Demo

(I strongly recommend adding a screenshot or GIF of your Streamlit app in action here. This is the most effective way to show a professor what you built.)

![Screenshot of the Streamlit App](app_screenshot.png)

---

## 🏛️ System Architecture

This project is a full-stack system, not just a script. The components work together as follows:

1.  **Frontend (Streamlit):** A user-friendly web interface that captures the live video stream from a webcam.
2.  **AI Pipeline (Python/OpenCV/InsightFace):**
    * **Face Detection:** Uses **Haar Cascade** or **HOG** to detect faces in the video feed.
    * **Feature Extraction:** A pre-trained **InsightFace** model (built on FaceNet with a MobileNetV2 backbone) extracts a 128-d feature vector (embedding) for each detected face.
    * **Recognition:** The extracted embedding is compared against a database of known student embeddings to find the closest match.
3.  **Databases (Dual System):**
    * **Redis:** Used as a high-speed, in-memory database for real-time data management, such as tracking which students have already been marked present in the current session.
    * **MySQL (via PHP):** The primary database for permanent, long-term storage of student records, embeddings, and attendance logs.
4.  **Deployment:** The entire Streamlit application is designed to be deployed on an **AWS EC2 instance** for scalable, web-based access.

---

## ✨ Key Features

* **Real-time:** Performs face detection and recognition on a live video stream.
* **High-Accuracy:** Achieves >95% accuracy using a robust, pre-trained InsightFace model.
* **Full-Stack:** Complete system with a web UI, AI model, and persistent database backend.
* **Scalable:** Deployed on AWS EC2, demonstrating cloud application management.
* **Efficient:** Uses Redis for real-time session management to avoid redundant database writes.

---

## 🛠️ Tech Stack

* **AI / Machine Learning:** Python, OpenCV, dlib, InsightFace, FaceNet, MobileNetV2 
* **Frontend:** Streamlit 
* **Backend & Database:** PHP, MySQL, Redis 
* **Deployment:** AWS EC2 

---

## 🚀 How to Run (High-Level Setup)

Setting up this project requires configuring all components of the system:

1.  **Clone Repository:**
    ```bash
    git clone [https://github.com/Yungkeshy/attendance-system-app.git](https://github.com/Yungkeshy/attendance-system-app.git)
    cd attendance-system-app
    ```
2.  **Install Python Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(You will need to create a `requirements.txt` file listing libraries like `streamlit`, `opencv-python`, `numpy`, `dlib`, `insightface`, `redis`)*

3.  **Set Up Backend:**
    * Configure a MySQL database with the required tables (e.g., `students`, `attendance_log`).
    * Deploy the PHP scripts (for `register`, `mark_attendance`, etc.) on a web server (like Apache or Nginx).

4.  **Start Redis Server:**
    * Install and run a local or remote Redis server.

5.  **Configure the App:**
    * Edit the Python scripts to point to your MySQL (PHP endpoint) and Redis server IP addresses and ports.

6.  **Run the Streamlit App:**
    ```bash
    streamlit run app.py
    ```

---

## 📜 How to Cite

If you find this work useful, please cite the original publication:

```bibtex
@article{oladele2024ai,
  title={AI-Based Face Recognition Attendance System},
  author={Oladele, Kamal Gbolahan, et al.},
  journal={International Journal of Innovative Research in Engineering \& Multidisciplinary Physical Sciences},
  volume={12},
  number={2},
  year={2024},
  issn={2349-7300},
  doi={10.37082/ijirmps.v12.i2.230598}
}
