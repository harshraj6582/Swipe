
# Billify

> Automated Data Extraction and Invoice Management System

Billify is a powerful React application that automates the extraction, processing, and management of invoice data from various file formats (Excel, PDF, and images). The application organizes extracted data into three main sections: Invoices, Products, and Customers, with real-time synchronization using Redux for consistent updates across tabs.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Data Extraction](#data-extraction)
- [Test Cases](#test-cases)
- [Data Validation & Error Handling](#data-validation--error-handling)
- [Technologies Used](#technologies-used)
- [License](#license)

## Features

### File Upload & Data Extraction
- Accepts multiple file formats:
  - Excel files containing transaction details
  - PDF files with invoice information
  - Image files of scanned invoices
- Intelligent extraction to identify and organize data correctly
- Automatic categorization into appropriate sections

### Main Application Tabs
1. **Invoices Tab**
   - Displays comprehensive invoice data with columns:
     - Serial Number
     - Customer Name
     - Product Name
     - Quantity
     - Tax
     - Total Amount
     - Date
     - Additional metadata

2. **Products Tab**
   - Shows detailed product information:
     - Name
     - Quantity
     - Unit Price
     - Tax
     - Price with Tax
     - Discount (optional)

3. **Customers Tab**
   - Contains customer information:
     - Customer Name
     - Phone Number
     - Total Purchase Amount
     - Additional customer metadata

### Centralized State Management
- Redux implementation for consistent state management
- Real-time updates across all tabs
- Synchronized data modifications (changes in one tab reflect across the application)

### Validation & Error Handling
- Data validation for completeness and accuracy
- Clear feedback for unsupported file formats
- Extraction error notifications
- User-friendly prompts for missing fields

## Installation

```bash
# Install dependencies
npm run dev 

# Start the development server
npm start
```

## Usage

1. **Upload Files**:
   - Click on the upload button in the interface
   - Select files (Excel, PDF, or image formats)
   - The extraction engine will process the files automatically

2. **Review and Manage Data**:
   - Navigate between tabs to view and edit extracted information
   - Any changes made in one tab will automatically update across all tabs

3. **Handle Missing Information**:
   - The application will highlight any missing required fields
   - Complete the missing information as prompted

## Data Extraction

Billify uses a generic extraction solution that:

1. **Identifies Document Type**: Automatically determines if the uploaded file is an Excel sheet, PDF, or image
2. **Processes Content Accordingly**:
   - For Excel: Parses structured data from cells
   - For PDFs: Uses OCR and pattern recognition to extract invoice data
   - For Images: Employs computer vision techniques to identify invoice fields
3. **Organizes Information**: Categorizes extracted data into invoices, products, and customers
4. **Validates Extraction**: Ensures data completeness and accuracy

## Test Cases

The application has been tested with various file types and combinations:

### Case 1: Invoice PDFs
- Successfully extracts invoice details from standard PDF invoices
- Handles various PDF layouts and formats

### Case 2: Invoice PDF + Images
- Processes mixed format uploads
- Correlates data between different file formats

### Case 3 & 4: Excel Files
- Extracts structured data from Excel spreadsheets
- Handles different Excel formats and layouts

### Case 5: All Types of Files
- Processes batch uploads of mixed file types
- Consolidates information from multiple sources

## Data Validation & Error Handling

- **Completeness Check**: Verifies all required fields are present
- **Format Validation**: Ensures data follows expected formats (dates, numbers, etc.)
- **Visual Indicators**: Highlights missing or potentially incorrect information
- **User Guidance**: Provides contextual help for resolving data issues

## Technologies Used

- **Frontend**: React.js
- **State Management**: Redux
- **File Processing**:
  - PDF.js for PDF processing
  - ExcelJS for Excel file handling
  - Tesseract.js for OCR functionality
- **UI Components**: Material-UI / Tailwind CSS

## License

This project is licensed under the MIT License - see the LICENSE file for details.
