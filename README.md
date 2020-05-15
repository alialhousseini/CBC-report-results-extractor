# CBC-report-results-extractor

## Idea
This project is for extracting important features from a CBC result.

## How to use it
Just run the cells using jupyter lab or notebook

## Description of Code
#### Cell 1
Importing of needed library and locate the directory of pytesseract
#### Cell 2 and 3
1. Defining a function called process_image that takes an image as parameter. This function performs image denoising using Non-local Means Denoising algorithm [Check algorithm here](http://www.ipol.im/pub/algo/bcm_non_local_means_denoising/) with several computational optimizations.It converts image to CIELAB colorspace and then separately denoise L and AB components with given h parameters (h=10).
2. Defining a function called extract_text to extracting the text and calling the label function for a final res of labels. This function uses .image_to_string from pytesseract library to returns the result of a Tesseract OCR run on the image to string.
And then the returned result will be in a list called 'lst' and we split the every term in the list by '\n' (NEW LINE).
3. Now we read the desired image with OpenCV ( cv2.imread(myimage.jpg) ) and then plotting it with matplotlib.pyplot. Also we don't need to forget printing the text extracted from this picture. We print it by defining a variable full_text which takes the extracted text of an existing image by using the function defiened above extract_text.
4. Now we can see, our uploaded picture and the extracted text, and we have an accuracy of 89.976%
#### Cell 4
Here we have declared a function locate that takes a list and a word, and then searching the word inside this list using for loop and enumerate. Enumerate() method adds a counter to an iterable and returns it in a form of enumerate object. This enumerate object can then be used directly in for loops or be converted into a list of tuples using list() method.
So if the word is in the list, the function will return it, otherwise returning NULL.
#### Cell 5
1. Creating a dictionary and a variable called target_word assigned to the word "Summary". Because as we see in the picture, the needed information are in a section called Summary.
2. Using an algorithm and the indexing and slicing using built-in methods in python we have printed the needed values in arranged type.
#### Cell 6
Declaring a class called main_rep that takes the images and has the following methods:
1. process_image: denoising the image using opencv for better accuracy. You can check the function documentation for further details about the all the arguments provided.
2. extract_text: extracting text from an image using pytesseract and splitting it according to line breaks.
3. locate : this function is simply used to determine a part of a string inside of a list of strings and returns the index where it was found first.
**Well, this cell contains all the above line of codes but in more arranged way to use them in a more easier way.**

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
