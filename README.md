Number Plate Recognition Using OpenCV and EasyOCR
This project demonstrates how to use OpenCV for detecting number plates in an image and EasyOCR for optical character recognition (OCR) to extract the text from the number plates.

Requirements
To run this project, you need to install the following Python libraries:

opencv-python – For image processing and object detection.

easyocr – For optical character recognition (OCR).

google.colab.patches – For displaying images in Google Colab (if you are using Colab).

You can install the required libraries using pip:

pip install opencv-python easyocr
Files
np1.webp – The input image (replace this with your own image of a vehicle with a number plate).

haarcascade_russian_plate_number.xml – Haar cascade XML file for detecting Russian number plates (you can download it from OpenCV's GitHub repository or other online sources).

Code Explanation
Image Loading and Preprocessing:

The image is loaded using OpenCV’s cv2.imread().

The image is converted to grayscale using cv2.cvtColor() to improve the performance of the plate detection algorithm.

Plate Detection:

A Haar Cascade classifier is used to detect the number plate(s) in the image. The cascade file haarcascade_russian_plate_number.xml is specifically designed for detecting Russian-style number plates but may work with other formats as well.

detectMultiScale() is used to find all the number plates in the image.

OCR for Text Extraction:

EasyOCR is initialized with the English language setting.

For each detected number plate, the portion of the image containing the plate is passed to EasyOCR’s readtext() function, which extracts the text (i.e., the number plate number).

Displaying the Result:

Detected plates are highlighted with a rectangle, and the recognized text (number plate) is displayed above the rectangle using cv2.putText().

The result image is displayed using cv2_imshow() (suitable for Google Colab).

How to Run
Clone the repository or download the script and necessary files.

Ensure that you have the required dependencies installed.

Replace the image path (np1.webp) with the path to your own image.

Download the Haar cascade file haarcascade_russian_plate_number.xml from an online source and place it in the same directory as the script.

Run the Python script.

Example:

python plate_detection.py
Output
The output will display the input image with rectangles drawn around the detected number plates and the extracted text (number plate information) displayed on the image.

Notes
The Haar Cascade model used here is designed for detecting Russian number plates, but it might work with other number plate styles as well. For better accuracy, consider training a more specific model for your use case.

If you are using Google Colab, ensure you use cv2_imshow() for displaying images instead of cv2.imshow().

License
This project is licensed under the MIT License - see the LICENSE file for details.
