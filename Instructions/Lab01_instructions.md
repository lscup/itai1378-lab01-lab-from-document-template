# Lab 1: Interactive Image Processing Application

In this lab, you will create an interactive image processing application using OpenCV, Matplotlib, and ipywidgets.

### Objectives
- Understand how to use OpenCV for image processing in Python.
- Learn to use ipywidgets for creating interactive applications.
- Familiarize with Matplotlib for displaying images and histograms.

### Prerequisites
- Basic knowledge of Python programming.
- Familiarity with image processing concepts.

---

## 2. Algorithm/Concept Background

The key concepts in this lab involve image processing using OpenCV and creating an interactive interface with ipywidgets. OpenCV is a powerful library for image processing, allowing operations like conversion between color spaces, resizing, and applying transformations like rotation. Ipywidgets provide a way to create interactive controls in Jupyter Notebooks, allowing dynamic updates of outputs.

Here's how a basic image display operation works:

```
# Load an image using OpenCV
image_bgr = cv2.imread('path_to_image.jpg')
# Convert BGR to RGB
image_rgb = cv2.cvtColor(image_bgr, cv2.COLOR_BGR2RGB)
# Display using Matplotlib
plt.imshow(image_rgb)
plt.show()
```

| Property         | Description                                  |
|------------------|----------------------------------------------|
| OpenCV           | Library for computer vision and image processing |
| ipywidgets       | Library to create interactive widgets in Jupyter |
| cv2.imread()     | Function to read an image from a file        |
| cv2.cvtColor()   | Function to convert images between color spaces |
| plt.imshow()     | Function to display an image using Matplotlib |

---

## 3. Your Coding Environment

### Workspace Layout

| Area                | What It Does                                |
|---------------------|---------------------------------------------|
| Code Editor (left)  | Edit your files using the tabbed editor     |
| Terminal (right)    | See output when you click the **Run** button|
| AI Tutor (chat panel)| Ask your AI Tutor for help — it knows this lab and can guide you step by step |

### Workflow

1. Edit your code in the editor tabs
2. Click **Run** to execute and see output in the terminal
3. When ready, click **Commit** to save your work to GitHub and trigger the autograder
4. A ✅ (green check) or ❌ (red X) will appear showing whether tests passed

Tip: Commit early and often to track your progress!

---

## 4. Project Structure

Here's the file structure for this assignment:

```
notebook.ipynb - YOUR WORK
```

---

## 5. Step-by-Step Implementation

### Step 1: Import Libraries

Start by importing the necessary libraries:

```python
# Import necessary libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
import ipywidgets as widgets
from IPython.display import display
import os
```

This code imports OpenCV for image processing, NumPy for numerical operations, Matplotlib for plotting, ipywidgets for creating interactive widgets, and OS for file operations.

### Step 2: Setup Output Directory

Create a directory for saving processed images:

```python
# Define the path for the outputs directory
output_path = './outputs/'
# Use os.makedirs to create the directory if it doesn't exist
os.makedirs(output_path, exist_ok=True)
```

This ensures that there's a specific folder where all processed images will be saved.

### Step 3: Initialize Global Variables

Initialize variables to store image data:

```python
# Global variables
original_bgr = None
original_rgb = None
processed_rgb = None
```

These variables will be used to store the original and processed images.

### Step 4: Create Output Widgets

Create widgets to display images and messages:

```python
# Create output widgets
msg_out = widgets.Output()
img_out = widgets.Output()
hist_out = widgets.Output()
```

These widgets will be used to display messages, images, and histograms.

### Step 5: Define Controls

Define the interactive controls:

```python
# Create a button to browse images
browse_btn = widgets.Button(description='Browse Image')
# Create a button to convert images to grayscale
...
```

Complete the controls as per the starter code. These controls will allow users to interact with the application.

### Step 6: Implement Helper Functions

Define functions to display images and histograms:

```python
def show_images(original_rgb, processed_rgb):
    with img_out:
        img_out.clear_output(wait=True)
        fig, ax = plt.subplots(1, 2, figsize=(10, 5))
        ax[0].imshow(original_rgb)
        ax[0].set_title('Original Image')
        ax[0].axis('off')
        ax[1].imshow(processed_rgb)
        ax[1].set_title('Processed Image')
        ax[1].axis('off')
        plt.show()
...
```

### Step 7: Implement Callback Functions

Implement callback functions for the controls:

```python
def on_browse_image_click(b):
    # TODO: Implement on_browse_image_click
    pass
...
```

Fill in the TODOs to complete the functionality of each control.

### Step 8: Connect Callbacks

Link the controls to their callback functions:

```python
# Connect the buttons to their callbacks
browse_btn.on_click(on_browse_image_click)
...
```

### Step 9: Layout the Interface

Arrange the widgets for a user-friendly interface:

```python
# Display the layout
controls = widgets.VBox([browse_btn, grayscale_btn, brightness_slider, resize_dropdown, rotation_dropdown, hist_btn, save_btn])
right_side = widgets.VBox([img_out, hist_out])
ui = widgets.HBox([controls, right_side])
display(msg_out, ui)
with msg_out:
    print('Please click Browse Image to start.')
```

After these steps, your interactive application should be ready to use!

---

## 6. Testing Your Code

### Run Your Code

Click **Run** to execute and check the output. Ensure that the interface appears and you can browse and display images.

### Submit for Grading

Click **Commit**, enter a message, and look for ✅ or ❌ to see if your code passes the tests.

Expected output after browsing an image:

```
Loaded image: filename.png
```

---

## 7. Autograding

| Test                        | Points | What It Checks                                      |
|-----------------------------|--------|----------------------------------------------------|
| Notebook Execution Test     | 100    | Ensure the notebook runs without errors             |

---

## 8. Lab Report

Click the README.md tab and fill in your lab report. Use the template below:

```
# Lab Report

## Student Information
- Name:
- Date:

## Key Concepts
- Describe the key concepts you learned in this lab

## Tracing/Analysis
- Include any relevant analysis or tracing of the algorithm

## Performance
- Discuss the performance implications of your image processing implementations

## Reflection
1. What challenges did you face during this lab?
2. How did you overcome these challenges?
3. What would you do differently next time?
```

---

## 9. Submission Checklist

- [ ] All functions implemented
- [ ] Click Run — output matches expected
- [ ] Click Commit — autograder shows green check
- [ ] Lab report completed in README.md
- [ ] Final commit with completed lab report

---

Ensure you follow each step carefully and verify your implementation against the solution provided.