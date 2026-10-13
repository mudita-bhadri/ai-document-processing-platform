# User Workflow
This document describes how an insurance claims employee uploads a document, reviews AI-extracted information, and submits the claim for further processing.


## Main Workflow

1. The user opens the platform and clicks **Upload**.
2. The user selects a document from their local storage.
3. The platform uploads the document and displays its filename and upload status.
4. The user reviews the uploaded document and confirms that they want to proceed with extraction. They can replace the document if necessary.
5. The platform uses AI to extract the relevant information.
6. The platform displays the extracted details for review.
7. The user reviews the details, corrects incorrect values, and adds missing information.
8. The user saves the reviewed details.
9. The user submits the claim for further processing within the platform.

## Workflow Diagram
 ```mermaid
    flowchart TD
    A[User opens platform]
    A--> B[User clicks Upload]
    B --> C[User selects a document]
    C --> D[Platform uploads document]
    D --> E{Upload successful?}
    E -- Yes --> F[Display filename and status]
    E -- No --> G[Show error and allow retry]
    G --> D
    F --> H{Confirm document?}
    H -- No --> C
    H -- Yes --> I[Start AI extraction]
    I --> J{Extraction successful?}
    J -- Yes --> K[Display extracted details]
    J -- No --> L[Show extraction error]
    L --> I
    K --> M[User reviews and edits details]
    M --> N[User saves details]
    N --> O{Save successful?}
    O -- No --> P[Show error and preserve edits]
    P --> N
    O -- Yes --> Q[Submit claim for processing]
    Q --> R([Complete])
