# Agricultural Dataset Collection

A comprehensive collection of agricultural datasets for machine learning competitions and research. This repository contains over 140,000 images across multiple agricultural domains including crop classification, disease detection, and pest identification.

## 📊 Dataset Overview

### Total Statistics
- **Total Images**: 140,000+ images
- **Crop Types**: 140+ different agricultural crops
- **Disease Types**: 100+ plant diseases and conditions
- **Geographic Coverage**: Global agricultural regions
- **Data Formats**: Classification, detection (YOLO), and segmentation tasks

## 📁 Dataset Structure

### 1. CDDM-images (~75,000+ images)
**Location**: `CDDM-images/images/`

Comprehensive crop disease dataset with detailed disease classifications:
- **50+ crop types**: Apple, Tomato, Potato, Rice, Wheat, Corn, Grape, Orange, Bell Pepper, Blueberry, Cherry, etc.
- **Disease conditions**: Each crop includes multiple disease states and healthy samples
- **Organization**: Folder structure by crop and disease type
- **Format**: JPG images with consistent naming

**Key Crops Include**:
- Apple (10 disease types + healthy)
- Tomato (10 disease types + healthy) 
- Potato (3 disease types + healthy)
- Rice (6 disease types + healthy)
- Wheat (7 disease types + healthy)
- Corn (4 disease types + healthy)

### 2. PlantVillage (~25,000+ images)
**Location**: `PlantVillage/`

Classic plant disease dataset focusing on major crops:
- **Primary crops**: Tomato, Potato, Bell Pepper
- **Disease focus**: Bacterial spots, blights, molds, viruses
- **Format**: Mixed formats (.JPG, .jpg, .jpeg, .png)
- **Note**: Contains duplicate nested folders (needs cleanup)

**Disease Categories**:
- Bacterial diseases
- Fungal diseases  
- Viral diseases
- Pest damage
- Healthy samples

### 3. Plants and Crops (100k images) (~26,000+ images)
**Location**: `Plants and Crops (100k images)/RGB_224x224/`

Diverse crop classification dataset:
- **140 crop types**: From common (Tomatoes, Wheat) to exotic (Açaí, Durian)
- **Pre-processed**: Standardized to 224x224 RGB format
- **Splits**: Train/validation/test sets included
- **Global coverage**: Crops from different geographical regions

**Crop Categories Include**:
- Grains (Wheat, Rice, Barley, Oats)
- Fruits (Apples, Oranges, Grapes, Bananas)
- Vegetables (Tomatoes, Potatoes, Carrots, Lettuce)
- Nuts (Almonds, Cashews, Walnuts)
- Spices (Cinnamon, Turmeric, Saffron)

### 4. CCMT Dataset (~11,000+ images)
**Location**: `Dataset for Crop Pest and Disease Detection/`

Specialized pest and disease detection dataset:
- **Focus crops**: Cashew, Cassava, Maize, Tomato
- **Augmented data**: Both raw and augmented versions available
- **Train/test splits**: Properly organized for ML training
- **Pest detection**: Includes pest damage classifications

**Disease/Pest Types**:
- Cashew: Anthracnose, Gumosis, Leaf Miner, Red Rust
- Cassava: Bacterial Blight, Brown Spot, Green Mite, Mosaic
- Maize: Fall Armyworm, Grasshopper, Leaf Beetle, Streak Virus
- Tomato: Leaf Blight, Leaf Curl, Septoria Leaf Spot, Verticillium Wilt

### 5. Detecting Diseases (~5,500 images)
**Location**: `detecting-diseases-beans-strawberry-tomato/`

YOLO-format annotated dataset:
- **Crops**: Beans, Strawberry, Tomato
- **Format**: YOLO v7 PyTorch annotations
- **Pre-processing**: Resized to 416x416
- **Annotations**: Bounding box annotations for disease detection

**Disease Categories**:
- Strawberry: Angular Leafspot, Anthracnose Fruit Rot, Gray Mold, Powdery Mildew
- Tomato: Disease, Leaf Mold, Spider Mites
- Bean: ALS, Bean Rust


## ⚠️ Current Issues

### Data Quality Issues
1. **File Format Inconsistencies**
   - Mixed case extensions (.jpg vs .JPG)
   - Multiple image formats (.jpg, .jpeg, .png)
   - Some files missing extensions

2. **Duplicate Content**
   - PlantVillage has nested duplicate folders
   - Overlapping tomato/potato samples across datasets

3. **Labeling Inconsistencies**
   - Different naming conventions (underscores vs commas vs spaces)
   - Varying disease specificity levels
   - Inconsistent taxonomy across datasets

4. **Size Variations**
   - Images in different resolutions
   - Some datasets pre-processed, others raw

## 🛠️ Recommended Dataset Management

### 1. Unified Structure
```
agricultural_dataset/
├── crop_classification/          # From "Plants and Crops (100k images)"
├── disease_detection/           # From CDDM-images, PlantVillage, CCMT
├── pest_detection/             # From CCMT and pest-focused datasets
└── annotations/                # YOLO/COCO format annotations
```

### 2. Competition-Ready Organization
```
competition_dataset/
├── train/                     # 70% of data
│   ├── crops/                # Crop classification task
│   ├── diseases/             # Disease detection task
│   └── pests/                # Pest detection task
├── validation/               # 15% of data
├── test/                     # 15% of data
└── metadata/
    ├── labels.json           # Unified label mapping
    ├── dataset_info.json     # Dataset statistics
    └── splits.json           # Train/val/test assignments
```

### 3. Data Preprocessing Pipeline

#### Standardization Steps:
1. **Format Normalization**
   - Convert all images to .jpg format
   - Normalize file extensions to lowercase
   - Resize to standard dimensions (224x224 or 256x256)

2. **Duplicate Removal**
   - Remove nested PlantVillage duplicates
   - Identify overlapping samples using image hashing
   - Handle cross-dataset duplicates

3. **Label Unification**
   - Create consistent taxonomy for crops and diseases
   - Map different naming conventions to standard terms
   - Add comprehensive metadata files

#### Quality Control:
- Validate image integrity
- Remove corrupted or extremely small images
- Ensure consistent aspect ratios
- Cross-reference disease names across datasets

### 4. Technical Implementation

#### Data Versioning:
- Use Git LFS for large files
- Implement DVC (Data Version Control) for dataset management
- Create dataset manifest files for reproducibility

#### Data Loaders:
- PyTorch/TensorFlow data loaders
- Efficient image preprocessing pipelines
- Balanced sampling strategies for imbalanced classes

#### Evaluation Framework:
- Multi-task evaluation metrics
- Cross-dataset validation protocols
- Robustness testing across different conditions

## 🎯 Competition Advantages

### Unique Strengths:
1. **Scale**: 150,000+ images across multiple agricultural domains
2. **Diversity**: Multiple crop types, diseases, and pests
3. **Task Variety**: Classification, detection, and segmentation tasks
4. **Global Coverage**: Crops from different geographical regions
5. **Multi-format**: Different annotation formats for various ML approaches

### Potential Competition Tasks:
- **Crop Classification**: Identify crop types from images
- **Disease Detection**: Detect and classify plant diseases
- **Pest Identification**: Identify pest damage and types
- **Multi-task Learning**: Combined crop and disease classification
- **Few-shot Learning**: Learning with limited samples per class

## 🚀 Immediate Action Items

### Priority Tasks:
1. **Clean up duplicates** in PlantVillage folder
2. **Standardize file naming** across all datasets
3. **Create unified label mapping** for diseases and crops
4. **Generate dataset statistics** and quality reports
5. **Set up data validation pipeline** for incoming data

### Development Tasks:
1. **Implement data preprocessing scripts**
2. **Create data loading utilities**
3. **Develop evaluation metrics**
4. **Set up version control system**
5. **Create dataset documentation**

## 📋 Usage Guidelines

### For Researchers:
- Cite original dataset sources appropriately
- Follow data usage licenses (CC BY 4.0 for some datasets)
- Maintain dataset integrity during preprocessing

### For Competitions:
- Ensure fair train/validation/test splits
- Implement proper cross-validation strategies
- Consider data augmentation for imbalanced classes

### For Production:
- Validate model performance across different datasets
- Test robustness to domain shifts
- Consider real-world deployment constraints

## 📞 Dataset Sources

- **PlantVillage**: Original PlantVillage dataset
- **CDDM**: Crop Disease Detection and Management dataset
- **CCMT**: Cashew, Cassava, Maize, Tomato dataset
- **Roboflow**: Detecting diseases dataset (CC BY 4.0)
- **Plants and Crops**: 100k images dataset

## 📄 License Information

- **Detecting Diseases**: CC BY 4.0
- **Other datasets**: Please check individual dataset licenses
- **Combined dataset**: Follow original dataset licensing requirements

## 🤝 Contributing

To contribute to this dataset collection:
1. Follow the established naming conventions
2. Maintain data quality standards
3. Update documentation for new additions
4. Ensure proper attribution for all sources

---

**Note**: This is a collection of multiple agricultural datasets. Please ensure you have proper rights to use each individual dataset according to their respective licenses.
