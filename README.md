# Build-Your-Own-Optical-Character-Recognition
https://codingchallenges.fyi/challenges/challenge-ocr

# Learnings Summary
## Experiment with different Blur techniques and the Canny edge detection
- Blur detection algorithms considered: box, gaussian and median
- Gaussian Blur performs the best and gives very natural boundaries later with edge detection. Possibly due to the way images are clicked as well, the center of attention pixel is sharper while blurring out pixels as we move away.

## Trying to understand Canny Algorithm by coding individual steps
### Step 1: Apply Sobel Operator in 2 directions to understand the sharp gradient presence
- Use kernel to get x & y direction magnitudes
- Take root of sum of squares to get magnitude
- Take arctan2 to get the angle

### Step 2: Non maximum suppression
- Thin out the edges by suppressing now local maxima (done by comapring with the 2 neighbours in the appropriate directions)
- Local maxima in the gradient direction are kept

### Step 3: Double Thresholding
- Classify edges to strong, weak or non-edges
- Strong Edge is set to white(255), weak to gray(1) and non-edge to black(0)

### Step 4: Edge tracking by hysteris
- Weak edges connected to strong edges are checked
- Weak edges with connection are kept
