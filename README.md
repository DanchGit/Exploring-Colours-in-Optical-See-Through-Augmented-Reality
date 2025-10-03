# Exploring Colours in Optical See-Through Augmented Reality

## Problem
Accurate colour characterisation in Optical See-Through (OST) Augmented Reality (AR) remains a challenge.  
Unlike opaque displays, OST AR devices (e.g. Microsoft HoloLens 2) blend virtual content with real-world backgrounds, leading to unpredictability.

## Contribution
- Benchmarked multiple colour characterisation models for OST AR:
  - Linear RGB-to-XYZ matrix with LUT correction
  - Polynomial regression (CIELAB-to-RGB)
- Developed a bidirectional deep learning model (forward + inverse)
- Conducted **psychophysical experiments** (2 alternate forced choice, and just noticeable difference thresholds) to compare model predictions with human perception.
- Built custom **Unity + MRTK3 applications** for display control, experiment design, and data collection.
- Created a novel dataset of >5000 images captured through HL2 optics under varied real-world background conditions.<br/><br/>
    
      
<!--![alt text](https://github.com/DanchGit/Exploring-Colours-in-Optical-See-Through-Augmented-Reality/blob/main/Images/Traditional%20Setup.png "The setup for spectroradiometer measurements on the HoloLens 2 screen")-->
<img src="https://github.com/DanchGit/Exploring-Colours-in-Optical-See-Through-Augmented-Reality/blob/main/Images/Traditional%20Setup.png" alt="Alt Text" style="width:50%; height:auto;"><br/>*The setup for spectroradiometer measurements on the HoloLens 2 screen* <br/><br/>


<img src="https://github.com/DanchGit/Exploring-Colours-in-Optical-See-Through-Augmented-Reality/blob/main/Images/DL%20setup%20and%20dataset.png" alt="Alt Text" style="width:80%; height:auto;"><br/>*The setup for DL data collection, and sample of the collected data*<br/><br/>
<!--![alt text](https://github.com/DanchGit/Exploring-Colours-in-Optical-See-Through-Augmented-Reality/blob/main/Images/DL%20setup%20and%20dataset.png "The setup for DL data collection, and sample of the collected data") -->

## Method
<!--![Pipeline diagram – INSERT FIGURE HERE]-->
- **Spectroradiometric characterisation** with Konica Minolta CS2000 for physical ground-truth data.  
- **Data-driven modelling**: trained neural networks with combined device+background input.  
- **Psychophysics**: measured perceptual thresholds and model alignment with human judgments.  
- **Validation**: compared ∆E00 metrics vs. perceptual preference.

<img src="https://github.com/DanchGit/Exploring-Colours-in-Optical-See-Through-Augmented-Reality/blob/main/Images/DL%20network%20arch.png" alt="Alt Text" style="width:70%; height:auto;"><br/>*The Deep Learning method* <br/><br/>

## Results
<!--![Key quantitative results – e.g., table of ∆E00 values]-->

- Matrix + LUT model: lowest mean error (∆E00 ≈ 1.0).  
- Polynomial regression: overfit to training data, validation error ≈ 9.7.  
- Deep learning forward model: ∆E00 ≈ 0.08 (below JND threshold).  
- **Human observers preferred more saturated colours**, diverging from purely quantitative metrics.
- 
<img src="https://github.com/DanchGit/Exploring-Colours-in-Optical-See-Through-Augmented-Reality/blob/main/Images/JND.png" alt="Alt Text" style="width:40%; height:auto;"><br/>*Just Noticeable Differences of 5 Colour centers for 6 observers* <br/><br/>

<!--

## How to Run
```bash
git clone <repo_url>
cd project
pip install -r requirements.txt
# Example run for demo 
python demo_forward_model.py --input data/sample.png --background data/bg.png
-->
