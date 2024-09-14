This script extracts specific text fields (like "Fakturnanr", "Bilagsdato", "Forfaldsdato", and "Reference")
from an invoice image using Tesseract OCR and OpenCV. 
The extracted data can be useful for automating tasks like invoice processing.

1) Requirements:
Python Libraries:
PyPDF2
pytesseract
pillow
opencv-python

2) Steps to Run:
Install Necessary Libraries:
!pip install PyPDF2
!pip install pytesseract
!pip install pillow pytesseract
Set Up Google Colab Drive: To access your image from Google Drive, mount the drive:


3) Install Tesseract OCR: Install Tesseract for Optical Character Recognition:
!apt-get install -y tesseract-ocr

4) Load the Invoice Image:
image_path = '/content/drive/MyDrive/123_invoice.PNG'

5) Convert Image to Grayscale:
OCR works better with grayscale images, so the script converts the image to grayscale using OpenCV:
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
Define Regions of Interest (ROI):
Specify the coordinates for different fields on the invoice (like Fakturnanr, Bilagsdato, etc.) using (x, y, w, h) format.

6) Extract Text from ROIs:
The function extract_text_from_roi() 
takes the ROI from the image and extracts the text using Tesseract.

7) Display Extracted Text:
The extracted text for each field (invoice number, dates, reference) will be printed out.

9) Visualize ROIs:
You can also visualize the regions on the image where the text was extracted by drawing green rectangles on the image.

10) Output:
Fakturnanr: INVO175257.
Bilagsdato: 17 juli 2024
Forfaldsdato: 16 august 2024
Reference: 137828
