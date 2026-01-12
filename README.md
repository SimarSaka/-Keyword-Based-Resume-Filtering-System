# Resume Filtering System (Keyword Based)

## The Problem: Manual Resume Screening

Recruiters often review hundreds of resumes manually, which is slow, tiring, and inconsistent. Important keyword combinations can easily be missed when scanning large numbers of PDF files by hand. This creates a bottleneck in the hiring process and reduces efficiency.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig10.jpeg?raw=true)


## The Solution: Automated Precision

This project provides a standalone desktop application that automatically scans resume folders, extracts text from PDFs, and filters candidates based on keyword relevance.

The system processes resumes in bulk, scores candidates objectively, and dramatically reduces manual effort.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig01.jpeg?raw=true)
 

## Resume Filtering System Overview

The Resume Filtering System is a desktop-based application that allows recruiters to quickly evaluate large numbers of resumes using keyword-based analysis.

It supports configurable filtering modes, scoring, and direct file access from the interface.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig02.jpeg?raw=true)
 

## System Architecture Overview

The application follows a modular architecture with clear separation of responsibilities:

- Data Ingestion for PDF parsing  
- Core Logic for matching, scoring, and sorting  
- User Interface for interaction and result visualization  

This structure makes the system easy to understand, maintain, and extend.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig03.jpeg?raw=true)
 

## Data Ingestion Engine

The system uses PyMuPDF (fitz) to extract text from PDF resumes.

Key steps include:
- Opening PDF files directly from disk
- Iterating through all pages
- Combining extracted text into a single searchable string
- Handling corrupted files safely without crashing

This ensures reliable text extraction across diverse resume formats.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig04.jpeg?raw=true)
 

## Intelligent Keyword Matching

The keyword matching engine uses regular expressions to ensure accuracy.

Two matching strategies are applied:
- Whole-word matching for single keywords
- Phrase matching for multi-word skills

All matches are case-insensitive to maintain consistency across resumes.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig05.jpeg?raw=true)
 

## Scoring and Filtering Logic

Each resume is evaluated using a transparent scoring formula:

Score = (Matched Keywords / Total Keywords) × 100

Filtering modes:
- Match ANY: Resume is included if at least one keyword is found
- Match ALL: Resume must contain every keyword to be included

This allows both broad screening and strict filtering.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig06.jpeg?raw=true)

 
## Prioritizing the Best Candidates

After scoring, resumes are automatically sorted to highlight the most relevant candidates first.

Sorting rules:
- Higher score first
- Alphabetical filename as a tie-breaker

Each result includes the filename, score, matched keywords, and missing keywords.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig07.jpeg?raw=true)
 
 

## UI Design Language

Although built with Tkinter, the interface is styled to appear modern and professional.

Design principles include:
- Dark theme for reduced eye strain
- Accent colors for focus and clarity
- Clear separation between inputs, results, and details

The UI emphasizes usability and readability.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig08.jpeg?raw=true)

 

## Interface Architecture

The UI layout is carefully structured within a fixed window size (980×620).

The interface is divided into:
- A header section for title and context
- A left control panel for inputs and actions
- A right results area with scrollable output and details

This layout ensures clarity even when processing large resume sets.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig09.jpeg?raw=true)

 

## Asynchronous Performance

To prevent UI freezing during heavy operations, the application uses multithreading.

Execution model:
- Main thread maintains UI responsiveness
- Worker thread processes PDF scanning and keyword matching
- UI updates occur safely after processing completes

This ensures smooth performance even for large folders.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig10.jpeg?raw=true)

 

 ## End-to-End User Flow

The application follows a clear workflow designed for ease of use:
- Input: Select resume folder and enter keywords
- Execution: Run the filter while progress is shown
- Review: Inspect results and keyword details
- Action: Open resumes directly from results using double-click

This flow moves seamlessly from input to actionable output.
 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig11.jpeg?raw=true)
 
 

## Robustness and Error Handling

The system is designed to remain stable under common edge cases.

Key safeguards include:
- Input validation to prevent invalid execution
- Graceful handling of corrupt or unreadable PDFs
- Protected OS-level file operations

Errors are handled without crashing, keeping the application reliable.

 ![image alt](https://github.com/SimarSaka/-Keyword-Based-Resume-Filtering-System/blob/main/Fig12.jpeg?raw=true)
