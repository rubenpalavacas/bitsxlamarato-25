# NEST Endometrial Cancer Risk Calculator
<img width="2437" height="1054" alt="imagen" src="https://github.com/user-attachments/assets/aaeb8823-e9c1-42ae-b390-c3392a3717b8" />

## How to run it?
The best way to try out our solution is to download the .ipynb file, upload it to Google Colab or a similar platform, and upload the three files to the execution file-system (the .png images and the .csv dataset). Then, execute and everything is ready!

## Overview
A clinical decision support tool that helps health specialists predict prognosis for endometrial cancer patients in the NSMP (p53 Wild-Type, POLE Non-Mutated) molecular subgroup using a Cox Proportional Hazards model.

## Quick Start
Simple Gradio interface deployed on Google Colab for instant risk stratification. Input clinical parameters and get immediate risk assessment with survival predictions and visualizations.

## Methodology
**Cox Proportional Hazards Model** with L2 regularization (penalizer=0.1)

**Pipeline:**
1. **Filter**: NSMP cases only (p53 WT + POLE Non-Mutated)
2. **Train**: CPH model on 5 key features using lifelines
   - FIGO Stage, Histological Grade, LVSI, Myometrial Infiltration, Beta-Catenin
3. **Score**: NEST Score = Σ(Log-HR × Feature Value)
4. **Classify**: Low/Intermediate/High risk categories

**Model Performance:** C-index 0.85 | N=91 patients

## Tech Stack
- **Model**: lifelines (Cox PH)
- **UI**: Gradio
- **Viz**: Plotly
- **Platform**: Google Colab

