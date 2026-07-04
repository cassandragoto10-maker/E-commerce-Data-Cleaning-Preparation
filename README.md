# DecodeLabs Internship Project 1: Data Cleaning & Preparation

## Project Overview
This project represents the foundational phase of the DecodeLabs Data Analytics internship program. The objective was to transform a raw, messy e-commerce dataset into a "Gold Standard" dataset suitable for analysis and modeling.

## Dataset Description
The raw dataset contains 1,001 e-commerce orders with 14 columns:
- **OrderID**: Unique order identifier
- **Date**: Order date and time
- **CustomerID**: Customer identifier
- **Product**: Product name
- **Quantity**: Number of items ordered
- **UnitPrice**: Price per unit
- **ShippingAddress**: Delivery address
- **PaymentMethod**: Payment method used
- **OrderStatus**: Current order status
- **TrackingNumber**: Shipping tracking number
- **ItemsInCart**: Items added to cart at checkout
- **CouponCode**: Applied coupon code (if any)
- **ReferralSource**: Customer acquisition source
- **TotalPrice**: Total order value

## Data Cleaning Strategy

### 1. Duplicate Removal
- Identified and removed duplicate records using `OrderID` as the unique identifier
- **Result**: 0 duplicate records remain (100% uniqueness verified)

### 2. Handling Missing Values
- `CouponCode` column: Blank entries replaced with "No Code" (indicating no coupon was used)
- **Result**: No missing values in critical columns (`OrderID`, `CustomerID`, `Product`)

### 3. Date Format Standardization
- Converted all dates to ISO 8601 format (YYYY-MM-DD)
- Removed unnecessary timestamps
- **Result**: 100% of dates now follow consistent format

### 4. Text Normalization
- Applied Proper Case formatting to all text columns
- Removed leading and trailing whitespace
- **Columns affected**: `Product`, `PaymentMethod`, `OrderStatus`, `ReferralSource`, `ShippingAddress`, `CustomerID`
- **Result**: Consistent capitalization and no extraneous spaces

### 5. Payment Method Standardization
- Changed `Online` to `Online Card` for consistency with other payment methods
- **Result**: Uniform payment method taxonomy

### 6. Numeric Precision
- Rounded all monetary values to 2 decimal places
- **Columns affected**: `UnitPrice`, `TotalPrice`, `Quantity`
- **Result**: Consistent financial precision throughout dataset

## Methodology
The cleaning process was implemented using Python's Pandas library in a Google Colab environment. This approach ensures:

- **Reproducibility**: The entire workflow can be replicated exactly
- **Scalability**: The same code can handle datasets of any size
- **Documentation**: All changes are tracked in a comprehensive change log
- **Auditability**: Every modification is recorded with a Change ID, description, and impact assessment

## Files in This Repository

| File Name | Description |
|-----------|-------------|
| `Project1_Data_Cleaned.xlsx` | Final cleaned dataset with embedded Change_Log sheet |
| `Project1_Data_Cleaned.csv` | Cleaned dataset in CSV format for easy viewing |
| `Dataset for Data Analytics.xlsx` | Original raw dataset (preserved for reference) |
| `decode_labs_project1_cleaning.py` | Python script containing all cleaning logic |
| `Project1_Change_Log.pdf` | PDF version of the change log |
| `requirements.txt` | Python dependencies for reproducing the environment |
| `README.md` | This documentation file |

## Change Log Summary
The following changes were applied to the dataset:

| Change ID | Description | Impact | Status |
|-----------|-------------|--------|--------|
| CR001 | Removed duplicate OrderID records | Removed 0 duplicate rows | Resolved |
| CR002 | Filled missing CouponCode values | Updated 356 rows to "No Code" | Resolved |
| CR003 | Verified no missing values in critical columns | Confirmed 0 missing values | Resolved |
| CR004 | Standardized Date column to ISO 8601 format | Removed timestamps from all rows | Resolved |
| CR005 | Applied Proper Case and trimmed whitespace | Standardized 6 text columns | Resolved |
| CR006 | Changed 'Online' to 'Online Card' | Updated payment method taxonomy | Resolved |
| CR007 | Rounded numeric columns to 2 decimal places | Fixed floating-point precision | Resolved |
| CR008 | Final verification of data integrity | Zero duplicates, correct date format | Resolved |

## How to Reproduce This Project

### Prerequisites
- Python 3.7 or higher
- Google Colab account (recommended) or local Python environment

### Installation
```bash
pip install pandas numpy openpyxl
