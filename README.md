import cv2
import pytesseract

# Initialize video capture from camera module
cap = cv2.VideoCapture(0)

# Set up Tesseract OCR
pytesseract.pytesseract.tesseract_cmd = r'<path_to_tesseract_executable>'

while True:
    # Capture frame-by-frame
    ret, frame = cap.read()

    # Display the captured frame
    cv2.imshow('Frame', frame)

    # Perform license plate detection and recognition
    # Implement your license plate detection and OCR code here

    # Press 'q' to exit
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

# Release video capture
cap.release()
cv2.destroyAllWindows()
