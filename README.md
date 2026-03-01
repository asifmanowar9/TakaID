# TakaID 🇧🇩💴

*Bangladeshi Banknote Classification using Deep Learning*

TakaID is a machine learning project focused on the **classification of Bangladeshi banknotes** using computer vision and deep learning techniques. The project utilizes transfer learning with pre-trained models and custom CNN architectures to achieve high-accuracy classification.

The dataset and methodology are inspired by the work of **Md. Naimul Islam Nuhash and Sadia Akter (2025)** and are designed to support research in **financial automation, currency recognition, and fraud prevention**.

---

## 📌 Introduction

Automated banknote classification is critical for modern financial systems such as ATMs, vending machines, and currency authentication platforms. Manual verification is time-consuming and prone to human error.

TakaID provides high-quality images of Bangladeshi currency notes captured under diverse conditions, enabling robust supervised machine learning and deep learning–based classification models.

---

## 💵 Supported Denominations

The dataset includes **9 Bangladeshi banknote denominations**:

| Denomination | Class |
|--------------|-------|
| 2 taka | 0 |
| 5 taka | 1 |
| 10 taka | 2 |
| 20 taka | 3 |
| 50 taka | 4 |
| 100 taka | 5 |
| 200 taka | 6 |
| 500 taka | 7 |
| 1000 taka | 8 |

---

## [📊 Dataset Overview](https://drive.google.com/drive/folders/13P5Soos4thSeu9Su62lHVENzrSF3kxCA)

- **Total Images:** 900+ (JPG format)  
- **Augmented Images:** 9,000+ (1,000 per class after augmentation)
- **Collection Locations:** Sonargaon, Munshigonj, Narayanganj.  
- **Capture Conditions:**  
  - Different lighting environments  
  - Multiple camera angles  
- **Devices Used:**  
  - iPhone 16 Pro Max 
  - Pixel 6a    

The dataset includes **new, old, worn, and damaged banknotes**, ensuring real-world applicability.

---

## 🤖 Models Implemented

| Model | Architecture | Accuracy | Status |
|-------|-------------|----------|--------|
| **MobileNetV2** | Transfer Learning | 99% | ✅ Completed |
| **ResNet50** | Transfer Learning | 87% | ✅ Completed |
| **VGG19** | Transfer Learning | - | ❌ Not Completed |
| **Custom CNN** | From Scratch | 95.2% | ✅ Completed |

### Model Details

#### MobileNetV2 (Best Performance)
- Pre-trained on ImageNet
- Fine-tuned for 9-class classification
- Image size: 128×128
- Batch size: 32

#### ResNet50
- Pre-trained on ImageNet
- Image size: 224×224
- Batch size: 32

#### VGG19
- Pre-trained on ImageNet  
- Image size: 224×224
- Frozen base layers with custom Dense layers

#### Custom CNN
- Built from scratch for domain-specific features
- Optimized for texture and pattern recognition
- Image size: 224×224

---

## 🧪 Data Preprocessing & Augmentation

### Preprocessing Steps
- Cropping to extract the clean banknote region  
- Contrast and brightness adjustment  
- Orientation normalization  
- Color correction  
- Pixel normalization (rescale 1./255)
- Removal of blurred, duplicated, or low-quality images  

### Data Augmentation Techniques
- Rotation (±10°)
- Width/Height shift (10%)
- Zoom (10%)
- Brightness adjustment (0.8-1.2)
- Shear transformation (5%)

### Dataset Split
- **Training:** 70%
- **Validation:** 15%
- **Test:** 15%

---

## 📁 Project Structure

```
TakaID/
├── Code/
│   ├── BanglaTaka_Asif(new)ResNet50.ipynb    # ResNet50 implementation
│   ├── Asif/
│   │   ├── BanglaTaka_(Asif)MobileNetV2.ipynb # MobileNetV2 implementation
│   │   ├── custom CNN Model.ipynb             # Custom CNN architecture
│   │   └── evaluation_and_prediction_of_MobileNetV2.ipynb
│   ├── Augmentation/
│   │   └── Augmentation.ipynb                 # Data augmentation pipeline
│   ├── Siam/
│   │   └── BanglaTaka_Siam.ipynb              # VGG19 implementation
│   └── Talha/
│       └── BanglaTaka_Talha.ipynb             # Dataset splitting
├── Dataset/
│   ├── 2/, 5/, 10/, 20/, 50/, 100/, 200/, 500/, 1000/
│   └── Link.txt
├── Documentation/
│   └── TakaID_Paper_.pdf
├── Python Libraries/                           # Reference notebooks
│   ├── Matplotlib/
│   ├── NumPy/
│   ├── Pandas/
│   └── SciPy/
├── Test/
├── resnet50.ipynb
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
```python
tensorflow >= 2.x
numpy
pandas
matplotlib
seaborn
scikit-learn
opencv-python
```

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/asifmanowar9/TakaID.git
   ```

2. **Download the dataset**
   - Access the [Google Drive Dataset](https://drive.google.com/drive/folders/13P5Soos4thSeu9Su62lHVENzrSF3kxCA)

3. **Run the notebooks**
   - Open in Google Colab or Jupyter Notebook
   - Mount Google Drive for dataset access
   - Execute cells sequentially

---

## 🧠 Technical Implementation

### Training Configuration
```python
IMG_HEIGHT = 224
IMG_WIDTH = 224
BATCH_SIZE = 32
EPOCHS = 100
LEARNING_RATE = 0.001
```

### Callbacks Used
- ModelCheckpoint
- EarlyStopping
- ReduceLROnPlateau
- TensorBoard

---

## ⭐ Key Contributions

- First large-scale, publicly usable dataset for Bangladeshi banknotes  
- Multiple model implementations with comparative analysis
- High-quality, background-free images  
- Multiple capture devices for diversity  
- Comprehensive augmentation pipeline
- Suitable for:
  - Currency classification  
  - Financial automation  
  - Counterfeit detection research  
  - Computer vision benchmarking  

---

## 🧩 Applications

- Automated banknote recognition systems  
- ATM and cash-handling automation  
- Fraud and counterfeit detection research  
- Deep learning–based currency classification  
- FinTech and AI research in developing economies  

---

## ⚠️ Limitations & Future Work

### Current Limitations
- Mostly controlled environment images  
- Unequal representation across denominations (mitigated by augmentation)
- No counterfeit banknotes included  
- Limited to Bangladeshi currency only  

### Future Work
- Inclusion of forged and counterfeit samples  
- UV and infrared imaging  
- Cross-country currency classification  
- Real-time mobile application development
- Model optimization for edge deployment

---

## 👨‍🎓 Team

| Name | Student ID | Contribution |
|------|------------|--------------|
| **Asif Manowar** | 23100016 | Dataset Splitting, Data Pipeline | ResNet50, MobileNetV2, Custom CNN | 
| **Md. Talha Mahmud** | 23100069 | MobileNetV2 |
| **Md. Siam Hossain** | 23100084 | VGG19 Implementation(Not completed) |

**Course:** Machine Learning Lab   

---

## 📚 References

1. Md. Naimul Islam Nuhash, Sadia Akter (2025). *BanglaTaka: A Dataset for Classification of Bangladeshi Banknotes*. ScienceDirect.
2. NSTU-BDTAKA: An Open Dataset for Bangladeshi Paper Currency Detection (2024)
3. CNN-Based Bangladeshi Currency Detection with Mobile App Integration
4. Efficient Currency Recognition Systems Using Deep Learning

---

## 📜 License

This project is intended for **academic and research purposes only**.

---

<p align="center">
  <b>TakaID</b> - Classifying Bangladeshi Banknotes with Deep Learning 🇧🇩
</p>
