# Group-1-Assignment-DIP
This Assignment are made by :
1. MUHAMMAD AMSYAR AIDIT BIN MOHD NAZRUL (082422)
2. NUR JANNAH HANIYYA BINTI IBRAHIM (0823329)

This Assignment are made to highlighting object of particular interest
- we made 4 difference image for this technique
- Python coding are submitted in file:
  1. Cat 1 image 
  2. Cat 2 image
  3. Butterfly image
  4. Rabbit image

# Team Contribution
1. MUHAMMAD ASMYAR AIDIT :Lead Developer (NumPy/SciPy Logic), Code Optimization, README Documentation
Responsible for the technical implementation of the project. I developed the Python scripts that handle image matrix manipulation without relying on OpenCV. My primary focus was translating the color theory (RGB channels) into NumPy boolean logic and implementing the scipy.ndimage functions to clean up the masks."
   
2. NUR JANNAH HANIYYA : Image Data Collection, Testing & Parameter Tuning, Presentation Slides
Responsible for the experimental side of the project. Gathered the dataset of challenging images (camouflage/multi-color objects) and performed iterative testing. Adjusted the sensitivity of the color filters and the size of the morphological kernels to ensure the code worked across different test cases, also led the creation of the final presentation."

Final Presentation : https://www.canva.com/design/DAG9bAGZRs0/q5pGs3IbD7HXpehKNOVQRQ/edit?utm_content=DAG9bAGZRs0&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton

#Discussion & Analysis
We chose to solve these specific segmentation cases using **low-level matrix manipulation** (NumPy) rather than high-level libraries like OpenCV or AI-based tools. 
* **Educational Value:** This approach forced us to understand *how* digital images work at the pixel level (RGB channels as 3D matrices).
* **The "Camouflage" Problem:** Standard color filters often fail when the foreground and background share colors (e.g., the white cat vs. white flowers). We selected these images specifically to demonstrate how **Morphological Operations** (Opening/Dilation) can filter objects by *size* and *structure* when color information is insufficient.

Case 1: The Camouflage Challenge (Cat1 & butterfly) 
**Challenge:** Segmenting a white/orange cat from a background containing white daisies (color overlap). And also the butterfly and the folwer is really hard to seperate the colour because of each of them has red high colour.
<p float="left">
  <img src="Butterfly image" width="45%" /> 
</p>

  Case 2: Multi-Color Object (Rabbit)
**Challenge:** Segmenting a multi-colored object (White/Pink) while ignoring similar colored noise (pink flowers on the ground).
<p float="left">
  <img src="path/to/rabbit_segmented.png" width="45%" /> 
</p>

Case 3: Color Logic (Butterfly)
**Challenge:** Distinguishing an Orange butterfly from a Deep Red flower using channel ratios.
<p float="left">
  <img src="path/to/butterfly_segmented.png" width="45%" /> 
</p>

### What the Results Tell Us
1.  **Color is not enough:** Our results show that relying on a single color channel (like "Red > 100") is rarely sufficient for real-world images. We had to implement **Channel Ratios** (e.g., `Green > Red * 0.4` for the butterfly) to achieve accurate selection.
2.  **Morphology is powerful:** The cleanliness of our final images—specifically the removal of scattered flowers in the Rabbit and Cat images, proves that spatial filtering (eroding small noise) is just as critical as color detection.
3.  **Limitations:** The algorithm is highly sensitive to lighting and specific color values. Unlike Machine Learning models which generalize, our hard-coded thresholds (e.g., `kernel_size=15`) must be tuned for each specific image context.











