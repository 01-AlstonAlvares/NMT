# 🌐 English-Marathi Neural Machine Translation (NMT)

## 🧠 Project Title

**Dual Attention Seq2Seq Translation Portal**

**Developer:** Alston Alvares\
**Student ID:** st126488

------------------------------------------------------------------------

## 📚 1. Dataset Sourcing & Credits

The dataset utilized for this project is the **PMIndia (Parallel Corpora
for Indian Languages)** dataset, specifically the **English-Marathi
(en-mr)** parallel corpus.

-   **Source:** Reputable public database provided by\
    http://rtweb.it.iitb.ac.in/main/PMIndia/
-   **Credit:** We extend our gratitude to the researchers and
    organizations at the **Center for Indian Language Technology
    (CFILT)** and **IIT Bombay** for curating and making this valuable
    resource available for open-source research and development.

------------------------------------------------------------------------

## 🧹 2. Dataset Preparation & Preprocessing

The transformation of raw bilingual data into a format suitable for a
Seq2Seq model involved several rigorous steps tailored to both
**English** and **Marathi**.

### 🔤 Text Normalization

-   **English**
    -   Converted to lowercase to reduce vocabulary sparsity\
    -   Processed using the `en_core_web_sm` pipeline
-   **Marathi**
    -   Morphologically rich language requiring careful Devanagari
        handling\
    -   Removed leading/trailing whitespaces\
    -   Ensured punctuation consistency

------------------------------------------------------------------------

### ✂️ Tokenization & Word Segmentation

-   **English Tokenization**
    -   Performed using **spaCy**
    -   Rule-based tokenizer splits text based on punctuation and
        linguistic rules
-   **Marathi Word Segmentation**
    -   Space-based splitting supplemented with **custom tokenization
        logic**
    -   Ensures accurate Marathi word boundaries before numericalization

**Tools Used**

  -----------------------------------------------------------------------
  Tool                    Developed By            Purpose
  ----------------------- ----------------------- -----------------------
  **spaCy**               Explosion AI            Robust English text
                                                  processing

  **TorchText**           PyTorch Team            Vocabulary building &
                                                  numerical mapping
  -----------------------------------------------------------------------

------------------------------------------------------------------------

### 📖 Vocabulary Building

Vocabulary restricted to **3,000 -- 5,000 tokens** to ensure execution
within the **4GB VRAM** limits of the **NVIDIA RTX 3050 GPU**.

**Special tokens included:**

    <unk>  <pad>  <sos>  <eos>

------------------------------------------------------------------------

## ⚙️ 3. Training & Hardware Optimization

To prevent **OutOfMemoryError** on consumer hardware, the following
optimizations were implemented:

-   Iterative Loss Calculation\
-   Gradient Clipping (CLIP = 1)\
-   Validation Split (90/10)

------------------------------------------------------------------------

## 📈 4. Performance Summary

### 🏁 Final Model Comparison

  --------------------------------------------------------------------------
  Attention      Training Loss  Training PPL   Validation     Validation PPL
  Mechanism                                    Loss           
  -------------- -------------- -------------- -------------- --------------
  **General      3.7760         43.64          5.4912         242.54
  Attention**                                                 

  **Additive     3.6600         38.86          5.4427         231.08
  Attention**                                                 
  --------------------------------------------------------------------------


### 🗺️ Attention Maps

<img width="681" height="990" alt="image" src="https://github.com/user-attachments/assets/1361236d-1830-4213-8402-1beebfbbbebd" />


------------------------------------------------------------------------

## 🌍 5. Web Portal Instructions

1.  Run the script and navigate to http://127.0.0.1:5000
2.  Choose between General or Additive attention
3.  Enter an English sentence
4.  Click Translate

<img width="1919" height="926" alt="Screenshot 2026-02-07 134026" src="https://github.com/user-attachments/assets/452f7d3c-5147-4157-8979-65b5615913c3" />
<img width="1919" height="901" alt="Screenshot 2026-02-07 134223" src="https://github.com/user-attachments/assets/4aac8d0b-d51d-4042-9bdc-89cbacdd1eb8" />
<img width="1907" height="941" alt="Screenshot 2026-02-07 134256" src="https://github.com/user-attachments/assets/730184c0-753a-45f9-bb54-95ff6d34588b" />




