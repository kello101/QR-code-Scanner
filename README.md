# QR-code-Scanner
A real-time QR code scanner using Python, OpenCV, and Pyzbar. It captures webcam frames, decodes QR codes in parallel threads, and displays the live feed with scan status. Utilizes threading, queues, and locks for smooth performance. Detected QR data is printed instantly, making it ideal for fast, responsive scanning.
Introduction:
This project is a python application that is designed to capture frames through webcam, and decodes the QR codes from these frames, and displays the decoded QR code in real-time.  

Code structure:
1.	Imports: The code imports necessary libraries including cv2, time, Thread, Lock, and Queue for multi-threading, as well as the decode function from pyzbar.pyzbar.
2.	Class Definition: The QRScanner class encapsulates the functionality of the QR code scanner. It initializes the webcam, sets camera parameters, and manages multi-threading for frame capturing and QR code processing.
3.	Frame Capture: The capture_frames method continuously captures frames from the camera and adds them to a queue for processing.
4.	QR Code Detection: The process_qr_codes method processes the frames in the queue, detects QR codes using the decode function, and calls the process_detected_qr_code method for further processing.
5.	QR Code Processing: The process detected_qr_code method extracts and prints the type and data of each detected QR code. Placeholder logic is provided for integrating with external services.
6.	User Interface: The display_ui method displays the video feed with detected QR codes and a scanning status overlay.
7.	Main Execution: The start_scanning method initializes and starts the scanning process by launching the frame capturing and processing threads, as well as displaying the user interface.
Design:
1.	Modular Design: The application is divided into several methods encapsulating specific functionalities such as frame capture, QR code processing, and UI display. This modular design enhances code readability, maintainability, and extensibility.
2.	Thread Safety: To prevent race conditions, a threading lock (qr_data_lock) is employed when accessing the shared queue (qr_data_queue) between threads. This ensures data consistency and avoids potential conflicts during queue operations.
3.	User Interface: The UI is simple but effective, displaying the webcam feed along with the detected QR codes and a status message indicating the scanning status. User interaction is minimal, with the option to quit the application by pressing the 'q' key.
 

 ![Picture1](https://github.com/user-attachments/assets/caf3ddbc-2607-47de-9c40-2127528a0d7a)
![Picture2](https://github.com/user-attachments/assets/bbfb6195-6123-4a12-85bb-0b43ff73baf8)

•	If the QR code wasn’t detected it keeps sending No frame available. After it detects the QR code it decodes it into a website.

Conclusion: 
The QR Code scanner demonstrates effective of visual computing and image processing techniques to capture, decode, and display QR codes in just a few seconds. Its modular design, multithreading implementation, and simple user interface make it a versatile tool for various applications requiring QR code scanning. However, there is room for improvement in error handling, performance optimization, GUI enhancement, and integration with external services.
