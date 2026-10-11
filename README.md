# Smart-Attendance
# Smart Attendance System Using Face Recognition

## 📌 Project Overview

The **Smart Attendance System Using Face Recognition** is a Python-based application that automates attendance marking using a webcam and facial recognition technology. It identifies registered individuals by comparing their faces with images stored in a local database and automatically records their attendance in an Excel file.

The system uses OpenCV for face detection, DeepFace for face recognition, and Excel files for maintaining daily attendance records. It also allows users to register new individuals through the webcam.

## 🎯 Objectives

- Automate the attendance marking process using face recognition.
- Reduce manual effort in maintaining attendance records.
- Identify registered individuals using facial images.
- Store attendance records in an Excel file organized by date.
- Allow new individuals to be registered through the webcam.

## ✨ Features

- **Real-Time Face Detection:** Detects faces from the webcam feed using OpenCV and a Haar Cascade classifier.
- **Face Recognition:** Uses DeepFace to compare detected faces against registered face images.
- **Automatic Attendance Marking:** Marks recognized individuals as present.
- **Duplicate Prevention During a Session:** Prevents the same person from being marked more than once during a single program session.
- **Face Registration:** Allows users to register a new individual by pressing the `R` key and entering their name.
- **Daily Attendance Sheets:** Creates a separate Excel worksheet for each date.
- **Excel-Based Record Management:** Stores names, attendance status, and dates in `attendance_master.xls`.
- **Unknown Face Detection:** Displays an unknown-face label when a face cannot be matched to the registered database.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| OpenCV (`cv2`) | Webcam access, face detection, and video display |
| DeepFace | Facial recognition and identity matching |
| TensorFlow | Machine learning framework used by the DeepFace environment |
| Haar Cascade | Detecting faces in video frames |
| `xlwt` | Creating and writing Excel `.xls` files |
| `xlrd` | Reading existing Excel workbooks |
| `xlutils` | Copying and updating existing Excel workbooks |
| `os` | File and directory management |
| `datetime` | Retrieving the current date |

## ⚙️ System Workflow

1. **Initialize the system:** Load the required libraries and create the `known_faces` directory if it does not exist.
2. **Initialize attendance storage:** Create `attendance_master.xls` if necessary and prepare a worksheet for the current date.
3. **Access the webcam:** Capture live video using OpenCV.
4. **Detect faces:** Convert each video frame to grayscale and detect faces using the Haar Cascade classifier.
5. **Recognize individuals:** Pass each detected face to DeepFace to search for a matching image in the registered face database.
6. **Mark attendance:** If a registered individual is recognized and has not already been marked during the current session, record their name, `Present` status, and date.
7. **Register new individuals:** Press `R` to register a person by entering their name. The captured face image is saved in the corresponding folder.
8. **Save and exit:** Press `Q` to stop the webcam and save the attendance workbook.

## 📂 Project Structure

```text
Smart-Attendance-System/
│
├── known_faces/
│   ├── Person1/
│   │   └── Person1_1.jpg
│   ├── Person2/
│   │   └── Person2_1.jpg
│   └── ...
│
├── attendance_master.xls
├── smart_attendance.py
└── README.md
```

**Note:** The `known_faces` directory and Excel file are created automatically when needed. The Python filename shown above is an example; replace it with your actual script filename.

## 💻 Requirements

- Python installed on your computer.
- A working webcam.
- Internet access for installing the required packages.
- Sufficient system resources to run TensorFlow and DeepFace.
- Registered facial images for the individuals whose attendance you want to record.

## 🚀 Installation and Setup

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd Smart-Attendance-System
```

Alternatively, download the repository and open the project folder.

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install opencv-python deepface tensorflow xlwt xlrd==1.2.0 xlutils
```

The project uses `xlrd` to read legacy `.xls` files, so version compatibility matters. If you encounter installation or runtime errors, check the package compatibility with your Python version.

### 4. Run the Application

```bash
python smart_attendance.py
```

Replace `smart_attendance.py` with the name of your Python file if it differs.

### 5. Register Individuals

- Wait for the webcam feed to appear.
- Press `R` to register a person.
- Enter the person's name in the terminal.
- The captured face image is saved under `known_faces/<person_name>/`.

Registered individuals can then be recognized in subsequent runs, provided their saved images remain in the database.

## ⌨️ Keyboard Controls

| Key | Action |
|---|---|
| `R` | Register a new individual |
| `Q` | Exit the application and save attendance |

**Important:** When registering a person, the application requests their name through the terminal, so keep the terminal accessible while the webcam window is running.

## 📊 Attendance Record Format

Attendance is stored in `attendance_master.xls`, with a separate worksheet for each date.

| Name | Status | Date |
|---|---|---|
| Person1 | Present | YYYY-MM-DD |
| Person2 | Present | YYYY-MM-DD |

The actual date is generated automatically when the application runs.

## 🔍 Applications

- Classroom attendance management.
- College laboratory attendance.
- Small office attendance tracking.
- Demonstrations of computer vision and facial recognition.
- Academic projects involving Python and machine learning.

## ⚠️ Limitations

- Face recognition accuracy depends on image quality, lighting, camera position, and the selected recognition model.
- The system requires a working webcam.
- Attendance is stored locally in an Excel file rather than a centralized database.
- Duplicate prevention applies to the current execution session; restarting the application can allow the same person to be marked again on the same date.
- The current implementation does not include liveness detection, so it should not be assumed to prevent attendance spoofing using photographs or screens.
- The face registration process saves the currently selected face crop and does not include a separate identity verification step.

## 🔮 Future Enhancements

- Add liveness detection to help prevent spoofing.
- Improve recognition by collecting multiple images under different lighting conditions.
- Integrate a database such as MySQL or SQLite.
- Develop a web dashboard for viewing attendance records.
- Generate attendance reports in Excel or PDF format.
- Add authentication and role-based access for administrators.
- Improve duplicate prevention across application restarts.

## 🔐 Privacy and Security

Facial images are biometric data. Store them securely, obtain appropriate consent before collecting or processing them, restrict access to registered images and attendance records, and follow applicable privacy requirements.

## 👨‍💻 Author

**Your Name**

GitHub: [Your GitHub Profile](<your-github-profile-url>)

## 📄 License

This project is intended for educational and learning purposes. Add a license file if you plan to distribute the project publicly.
