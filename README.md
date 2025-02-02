# **SafeGamingApi**

SafeGamingApi is a collection of Flask-based APIs designed to enhance the safety, security, and transparency of gaming environments. The suite includes tools for monitoring game file integrity, detecting threats in voice chat, sending timely reminders to players, monitoring system resources, filtering swear words, detecting gambling elements in games, encrypting sensitive data, and preventing fraud.

---

## **Features**

### 1. **Game File Integrity Monitoring**
   - **File**: `Game_transparency.py`
   - **Description**: Monitors the integrity of critical game files and checks if they exist.
   - **Endpoint**: `/status` (GET)
   - **Customization**: Set `GAME_FILES_DIR` and `critical_files` to match your game's directory and critical files.

---

### 2. **Voice Threat Detection**
   - **File**: `Voice_Threat_Detection.py`
   - **Description**: Preprocesses and balances a dataset of labeled sentences, uses a Sentence Transformer model to encode sentences, and calculates cosine similarity for threat detection. Supports real-time voice input for threat detection.
   - **Features**:
     - Dataset loading and cleaning
     - Dataset balancing
     - Bulk and real-time threat detection
     - Evaluation metrics (accuracy, precision, recall)
     - Misclassified examples export

---

### 3. **Timely Reminders**
   - **File**: `TimelyReminder.py`
   - **Description**: Sends periodic reminders to players to take breaks. Tracks playtime and supports custom reminders.
   - **Endpoints**:
     - `/start_game_timer` (POST): Starts a timer for a user.
     - `/get_reminders` (GET): Retrieves reminders for a user.
   - **Customization**: Set `reminder_interval_minutes` and `max_reminders`.

---

### 4. **Real-Time System Resource Monitoring**
   - **File**: `RealtimeDataTaken.py`
   - **Description**: Monitors system resource usage in real-time, including camera, microphone, photos access, CPU, and memory usage.
   - **Endpoint**: `/status` (GET)
   - **Features**: Cross-platform support, continuous monitoring via threading.

---

### 5. **Swear Words Filtering**
   - **File**: `HarshwordsEncryption.py`
   - **Description**: Filters swear words from input text and replaces them with '***'.
   - **Endpoint**: `/filter_swear_words` (POST)
   - **Requirements**: A CSV file (`harshwords.txt`) containing swear words.

---

### 6. **Gambling Game Detection**
   - **File**: `Gambling_game_Detection.py`
   - **Description**: Detects if a game involves gambling based on metadata. Checks for betting/wagering, randomness, and rewards.
   - **Endpoint**: `/detect_gambling_game` (POST)
   - **Features**: Handles invalid or missing metadata.

---

### 7. **Data Encryption**
   - **File**: `DataEncryption.py`
   - **Description**: Encrypts and decrypts data using the `cryptography.fernet` library. Supports JSON, text, and files.
   - **Endpoints**:
     - `/encrypt` (POST): Encrypts data or files.
     - `/decrypt` (POST): Decrypts data or files.
   - **Features**: Base64 encoding of encrypted data, automatic key generation.

---

## **8. Fraud Detection**
* **File**: `fraud_detection.py`
* **Description**: Verifies receivers via facial recognition using ID and selfie photos. Approves receivers for receiving gifts if verification is successful. Includes a random hand emoji condition for added security.
* **Endpoints**:
  * `/verify` (POST): Verifies a receiver by comparing their ID photo with a selfie.
  * `/send_gift` (POST): Allows a sender to send a gift to an approved receiver.
* **Features**:
  * Facial recognition for receiver verification.
  * Random hand emoji condition for verification.
  * Prevents unauthorized gift sending to unverified receivers.

---

This version uses `#` for the main heading and `*` for bullet points, making it clean and easy to read in Markdown. Let me know if you need further tweaks!

---

## **Installation**

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/SafeGamingApi.git
   cd SafeGamingApi
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the desired API script:
   ```bash
   python Game_transparency.py
   ```

---

## **Usage**

Each API script can be run independently. Refer to the individual script documentation for specific usage instructions and endpoint details.

---

## **Requirements**

- Python 3.7+
- Flask
- pandas
- sentence-transformers
- scikit-learn
- speechrecognition
- psutil
- opencv-python
- pyaudio
- cryptography
- face_recognition
- cmake
- dlib

---

## **File Descriptions**

| **File**                     | **Description**                                                                 |
|-------------------------------|---------------------------------------------------------------------------------|
| `Game_transparency.py`        | Monitors game file integrity and checks if critical files exist.                |
| `Voice_Threat_Detection.py`   | Detects threats in voice chat using sentence embeddings and cosine similarity.  |
| `TimelyReminder.py`           | Sends periodic reminders to players to take breaks.                             |
| `RealtimeDataTaken.py`        | Monitors system resource usage in real-time.                                    |
| `HarshwordsEncryption.py`     | Filters swear words from input text.                                            |
| `Gambling_game_Detection.py`  | Detects gambling elements in games based on metadata.                           |
| `DataEncryption.py`           | Encrypts and decrypts data using the Fernet algorithm.                          |
| `fraud_detection.py`          | Verifies users via facial recognition and prevents unauthorized gift sending.   |
| `README.md`                   | Documentation for the SafeGamingApi project.                                    |
| `hate_speech.tsv`             | Dataset for hate speech detection (used in `Voice_Threat_Detection.py`).        |
| `mainxlsx.xlsx`               | Dataset for threat detection (used in `Voice_Threat_Detection.py`).             |

---
