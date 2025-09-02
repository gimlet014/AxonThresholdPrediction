# CNN for Predicting Activation Thresholds of the MRG Axon Model

This repository provides a convolutional neural network (CNN) designed to predict the activation threshold of axons simulated using the **McIntyre–Richardson–Grill (MRG) model**.  

---

## 📖 Overview
The CNN takes as input a **103-dimensional feature vector** that encodes the spatial distribution of extracellular potentials along the axon, as well as several physiological and stimulation parameters. The output is the **activation threshold**, defined as the scaling factor applied to the extracellular potential profile that causes the axon to generate an action potential.

---

## 🧩 Input Features
The model input is a vector of length **103**, consisting of:

1. **Extracellular potential distribution (100 values)**  
   - Normalized potential values sampled along the axon.  
   - Unit: Volt (V).  
   - Normalization: maximum = 1, minimum = 0.  

2. **Fiber diameter (1 value)**  
   - Unit: 5.7 μm.  
   - Range: 5.7 – 16.0.  

3. **Fiber length (1 value)**  
   - Unit: decimeter (dm).  
   - Range: 0.2 – 1.0.  

4. **Pulse width of square-wave stimulation (1 value)**  
   - Unit: millisecond (ms).  
   - Range: 0.1 – 1.0.  

---

## 🎯 Output
- **Activation threshold**  
  - Unit: Volt (V).  
  - Definition: the scaling factor applied to the normalized extracellular potential distribution such that the axon just reaches the threshold to generate an action potential.  

For example, if the predicted threshold is **10**, this indicates that the axon is activated when the difference between the maximum and minimum extracellular potential reaches **10 V**.

---

## ⚙️ Dependencies
This project has been tested with the following library versions:

- `numpy` = 1.26.4
- `keras` = 3.4.1
- `matplotlib` = 3.8.0  
- `tensorflow` = 2.17.0  
- `scikit-learn` = 1.4.1.post1  


