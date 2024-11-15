# Convolutional_Neural_Networks

## Convolution Example with 4x5 Input Image

Let's walk through an example of performing **convolution** on a **4x5 input image** with a **2x2 filter**. This example will show how to handle both positive and negative values before applying the **ReLU activation** function.

### Input Image (4x5 matrix):

\[
\begin{bmatrix}
5 & 3 & 6 & 1 & 4 \\
2 & 7 & 9 & 5 & 8 \\
3 & 4 & 2 & 8 & 6 \\
6 & 1 & 7 & 9 & 3
\end{bmatrix}
\]

### Filter (2x2 matrix):

\[
\begin{bmatrix}
1 & -1 \\
1 & -1
\end{bmatrix}
\]

### Parameters:
- **Stride = 1** (filter moves one step at a time).
- **No Padding** (valid padding).

### Step 1: Perform Convolution

We slide the filter over the input image, performing element-wise multiplication and summing the results for each position.

1. **Top-left position:**
   \[
   \begin{bmatrix}
   5 & 3 \\
   2 & 7
   \end{bmatrix}
   \]
   \[
   (5 \times 1) + (3 \times -1) + (2 \times 1) + (7 \times -1) = 5 - 3 + 2 - 7 = -3
   \]

2. **Top-middle position:**
   \[
   \begin{bmatrix}
   3 & 6 \\
   7 & 9
   \end{bmatrix}
   \]
   \[
   (3 \times 1) + (6 \times -1) + (7 \times 1) + (9 \times -1) = 3 - 6 + 7 - 9 = -5
   \]

3. **Top-right position:**
   \[
   \begin{bmatrix}
   6 & 1 \\
   9 & 5
   \end{bmatrix}
   \]
   \[
   (6 \times 1) + (1 \times -1) + (9 \times 1) + (5 \times -1) = 6 - 1 + 9 - 5 = 9
   \]

4. **Second row, left position:**
   \[
   \begin{bmatrix}
   2 & 7 \\
   3 & 4
   \end{bmatrix}
   \]
   \[
   (2 \times 1) + (7 \times -1) + (3 \times 1) + (4 \times -1) = 2 - 7 + 3 - 4 = -6
   \]

5. **Second row, middle position:**
   \[
   \begin{bmatrix}
   7 & 9 \\
   4 & 2
   \end{bmatrix}
   \]
   \[
   (7 \times 1) + (9 \times -1) + (4 \times 1) + (2 \times -1) = 7 - 9 + 4 - 2 = 0
   \]

6. **Second row, right position:**
   \[
   \begin{bmatrix}
   9 & 5 \\
   2 & 8
   \end{bmatrix}
   \]
   \[
   (9 \times 1) + (5 \times -1) + (2 \times 1) + (8 \times -1) = 9 - 5 + 2 - 8 = -2
   \]

7. **Third row, left position:**
   \[
   \begin{bmatrix}
   3 & 4 \\
   6 & 1
   \end{bmatrix}
   \]
   \[
   (3 \times 1) + (4 \times -1) + (6 \times 1) + (1 \times -1) = 3 - 4 + 6 - 1 = 4
   \]

8. **Third row, middle position:**
   \[
   \begin{bmatrix}
   4 & 2 \\
   1 & 7
   \end{bmatrix}
   \]
   \[
   (4 \times 1) + (2 \times -1) + (1 \times 1) + (7 \times -1) = 4 - 2 + 1 - 7 = -4
   \]

9. **Third row, right position:**
   \[
   \begin{bmatrix}
   2 & 8 \\
   7 & 9
   \end{bmatrix}
   \]
   \[
   (2 \times 1) + (8 \times -1) + (7 \times 1) + (9 \times -1) = 2 - 8 + 7 - 9 = -8
   \]

### Step 2: Output Feature Map

After performing the convolution for each region, the resulting output feature map (before activation) is:

\[
\begin{bmatrix}
-3 & -5 & 9 \\
-6 & 0 & -2 \\
4 & -4 & -8
\end{bmatrix}
\]

### Step 3: Apply ReLU Activation

The **ReLU activation function** replaces negative values with 0:

\[
\text{ReLU}(x) = \max(0, x)
\]

After applying ReLU to the feature map:

\[
\begin{bmatrix}
\max(0, -3) & \max(0, -5) & \max(0, 9) \\
\max(0, -6) & \max(0, 0) & \max(0, -2) \\
\max(0, 4) & \max(0, -4) & \max(0, -8)
\end{bmatrix}
=
\begin{bmatrix}
0 & 0 & 9 \\
0 & 0 & 0 \\
4 & 0 & 0
\end{bmatrix}
\]

### Final Output After Convolution and ReLU Activation:

The final output after applying convolution and the ReLU activation function is:

\[
\begin{bmatrix}
0 & 0 & 9 \\
0 & 0 & 0 \\
4 & 0 & 0
\end{bmatrix}
\]

---

### Summary:

- **Input Image:** 4x5 matrix with positive values.
- **Filter:** 2x2 matrix with both positive and negative values.
- **Stride:** 1.
- **Padding:** None (valid padding).
- **Output Feature Map:** 3x4 matrix before activation.
- **ReLU Activation:** Negative values are replaced with 0.
