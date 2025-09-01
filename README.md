# Hotel Booking Cancellation Project

This project focuses on cleaning and preparing a hotel booking dataset for analysis and modeling.  
The process is divided into three main phases: **EDA, Data Cleaning, and Feature Engineering**.

---

## Phase 1: Exploratory Data Analysis (EDA) & Data Quality Report
- [x] Loaded the dataset.
- [x] Generated summary statistics (`.describe()`, `.info()`).
- [x] Identified missing values.
- [x] Visualized missing values using a heatmap matrix.
- [x] Detected outliers in numerical columns using boxplots and the IQR method.
- [x] Documented main data quality issues under each section.

---

## Phase 2: Data Cleaning
- [x] **Handle Missing Values**  
  - *company & agent*: changed to object type then replaced with `"None"`.  
  - *country*: replaced with `"Unknown"`.  
  - *children*: imputed with median.  
- [x] **Remove Duplicates**: dropped exact duplicate rows.  
- [ ] **Handle Outliers**: cap extreme values (e.g., `adr > 1000 → 1000`).  
- [ ] **Fix Data Types**: ensure date columns are correctly formatted.

---

## Phase 3: Feature Engineering & Preprocessing
- [ ] Create new features:  
  - `total_guests = adults + children + babies`  
  - `total_nights = stays_in_weekend_nights + stays_in_week_nights`  
  - `is_family` = binary flag (Yes/No)  
- [ ] Encode categorical variables:  
  - One-hot encoding for low-cardinality (e.g., meal, market_segment).  
  - Frequency/grouping for high-cardinality (e.g., country).  
- [ ] Remove data leakage: drop `reservation_status` & `reservation_status_date`.  
- [ ] Split dataset into **train/test sets** (`test_size=0.2`, `random_state=42`).  

---

## **Status**:
- Phase 1 --> ✅ Completed
- Phase 2 --> ⏳ In Progress
- Phase 3 --> ❌ Not Started
