# Hotel Booking Cancellation Project

This project focuses on cleaning and preparing a hotel booking dataset for analysis and modeling.  
The process is divided into three main phases: **EDA, Data Cleaning, and Feature Engineering**.

---

## Phase 1: Exploratory Data Analysis (EDA) & Data Quality Report
- [x] Loaded the dataset.
- [x] Generated summary statistics.
- [x] Identified missing values.
- [x] Visualized missing values using a heatmap matrix.
- [x] Detected outliers in numerical columns using boxplots and the IQR method.
- [x] Documented main data quality issues under each section.

---

## Phase 2: Data Cleaning
- [x] **Handle Missing Values**  
  - *company & agent*: replaced with `0`.  
  - *country*: replaced with `"Unknown"`.  
  - *children*: imputed with median.  
- [x] **Remove Duplicates**: dropped exact duplicate rows.
- [x] **Handle Outliers**
  - Cap extreme and negative values for `adr`.  
  - Remove negative and 0 values for `adults`.  
  - Remove values greater than 5 in `children` and `babies`. 
- [x] **Fix Data Types**
  - Change `children` to int64.  
  - Change `reservation_status_date` to datetime64.

---

## Phase 3: Feature Engineering & Preprocessing
- [x] Create new features
  - `total_guests = adults + children + babies`  
  - `total_nights = stays_in_weekend_nights + stays_in_week_nights`  
  - `is_family = binary flag (Yes/No)`
- [x] Encode categorical variables
  - For nominal columns use one-hot encoding
  - For ordinal columns use label encoding
  - For high-cardinality columns use frequency encoding
- [x] Remove data leakage
  - Remove `country` after creating `country_freq`.
  - Remove `arrival_date_year` because it contains only few years but we want to generalize.
  - Remove `reservation_status` and `reservation_status_date` because they are directly related to the target `is_canceled`.
  - Remove `assigned_room_type` because it represent type of room assigned to the guest and the assignment is made after booking.
- [x] Split dataset into **Features/Target** then **train/test sets** (`test_size=0.2`, `random_state=42`, `stratify=y`).
- [x] Save cleaned dataset

---

## **Status**:
- Phase 1 --> ✅ Completed
- Phase 2 --> ✅ Completed
- Phase 3 --> ✅ Completed
