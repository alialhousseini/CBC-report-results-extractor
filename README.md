# CBC-report-results-extractor

## Idea
This project is for extracting important features from a CBC result.

## How to use it
Just run the cells using jupyter lab or notebook

### Description of Code

##### Cell 1
Importing of needed library and locate the directory of pytesseract
##### Cell 2
1. Defining a function called process_image that takes an image as parameter. This function performs image denoising using Non-local Means Denoising algorithm [Check algorithm here](http://www.ipol.im/pub/algo/bcm_non_local_means_denoising/) with several computational optimizations.It converts image to CIELAB colorspace and then separately denoise L and AB components with given h parameters (h=10).
2. Defining a function called extract_text to extracting the text and calling the label function for a final res of labels. This function uses .image_to_string from pytesseract library to returns the result of a Tesseract OCR run on the image to string.
And then the returned result will be in a list called 'lst' and we split the every term in the list by '\n' (NEW LINE).
3. Now we read the desired image with OpenCV ( cv2.imread(myimage.jpg) ) and then plotting it with matplotlib.pyplot. Also we don't need to forget printing the text extracted from this picture. We print it by defining a variable full_text which takes the extracted text of an existing image by using the function defiened above extract_text.
4. Now we can see our uploaded picture and the extracted text, with an accuracy of 

## Requirements
- OpenCV
- Numpy
- Matplotlib
- Pytesseract
- PIL
- Tesseract OCR [Download from here](https://digi.bib.uni-mannheim.de/tesseract/tesseract-ocr-w32-setup-v5.0.0-alpha.20200328.exe)

### Note
- Extract your OCR file to C:/Program Files/Tesseract-OCR/tesseract.exe
- If you want to use another picture you should edit "extract_rep"
