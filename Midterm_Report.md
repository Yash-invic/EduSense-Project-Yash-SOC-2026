# Midterm Progress Report

## Project Overview
This report covers my progress in the SOC EduSense project so far. Over the time till now, with the first 2 week's content I have focused on building a foundation in cleaning messy data and understanding the basics of PyTorch to train neural networks.

## Week 1: Data Cleaning & Preprocessing
**Goal:** Take a messy, raw dataset and clean it up so it is ready for machine learning models.

**What I did and learned:**
* **Finding Errors:** Used Pandas to explore the data and found issues like text hidden inside number columns, which messed up the data types.
* **Fixing Missing Data:** Instead of deleting rows with missing values, I filled categorical blanks with the mode and numerical blanks with the median to keep the data accurate.
* **Handling Outliers:** Used the IQR (Interquartile Range) method to cap extreme values so they don't break the model later, without losing valuable data points.
* **Prep for ML:** Standardized the text, scaled the numerical features so they are on the same level, and used VIF and PCA to check how the features relate to each other.

## Week 2: PyTorch & Neural Networks
**Goal:** Going further from basic data handling and start building actual deep learning models using PyTorch.

**What I did and learned:**
* **Tensors:** Learned how PyTorch tensors work, how they are similar to NumPy arrays, and why we move them to GPUs to speed up math operations.
* **Building a Model:** Built a simple Linear Regression model (`nn.Linear`) from scratch.
* **The Training Loop:** Wrote a complete training loop. I learned how to make a forward pass, calculate the error using a loss function, zero out the old gradients, use backpropagation to find the fixes, and step the optimizer to update the weights.
* **Learning Rates:** Experimented with different learning rates to see what happens when the model tries to learn too fast (overshooting) versus too slow.

## Current Status & Next Steps
Both Week 1 and Week 2 assignments are fully complete and uploaded. So the material and assignment required upto the midterm report as per mentors is completed. I have also started looking into the Week 3 materials, which involves processing audio files to give the AI assistant voice capabilities (it's deadline is after midterm submission).