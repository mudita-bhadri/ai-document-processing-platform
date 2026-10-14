# User Stories and Acceptance Criteria

This document defines the core user stories and acceptance criteria for the MVP of the AI-Powered Document Processing Platform.

## US-01: Upload a Document

**Priority:** Must have

**User story**

As an insurance claims employee, I want to upload a supporting document from my local computer so that I can process its information using the platform.

**Acceptance criteria**

1. The employee can select a document from their local computer.
2. The platform validates the selected file before uploading it.
3. If the file exceeds the configured maximum size, the platform displays a clear error message and does not begin uploading it.
4. The employee cannot proceed with an invalid file.
5. The platform checks whether the uploaded document is readable and can be processed.
6. If the document is corrupted or cannot be opened, the platform displays a clear error message, does not start AI extraction and allows the employee to upload a replacement document.
7. When the upload succeeds, the platform confirms the upload and displays the filename.
8. If the upload fails, the platform displays an informative error message and allows the employee to try again.

**Open questions**

- Which file types should be supported?
- What should the maximum file size be?
- Should the platform validate whether a PDF is readable before or after uploading it?

## US-02: Extract Information Using AI

**Priority:** Must have

**User story**

As an insurance claims employee, I want the platform to extract relevant information from my uploaded document so that I can review the details without entering everything manually.

**Acceptance criteria**

1. The employee must confirm the uploaded document before AI extraction begins.
2. After confirmation, the platform starts extracting the relevant claim information.
3. The platform extracts the following fields where the information is available:
   - Claimant name
   - Policy number
   - Incident date
   - Claim amount
4. The platform displays the extracted values for the employee to review.
5. If a field cannot be extracted, the platform indicates that the value is missing rather than inventing a value.
6. If extraction fails or times out, the platform informs the employee and provides an option to retry.
7. The platform does not submit the claim automatically; the employee must review the extracted information before proceeding.

## US-03: Review and Correct Extracted Information

**Priority:** Must have

**User story**

As an insurance claims employee, I want to review and correct the information extracted by AI so that the claim details are accurate before I submit them for further processing.

**Acceptance criteria**

1. The platform displays the extracted claim fields and their values in an editable form.
2. The employee can correct an extracted value that is inaccurate.
3. The employee can enter a value for a field that the AI could not extract.
4. The platform clearly indicates which fields have no extracted value.
5. The employee can review and edit all four fields: claimant name, policy number, incident date, and claim amount.
6. The employee can save the reviewed information as a draft even when one or more of the four required fields are missing.
7. If saving a draft fails, the platform informs the employee and preserves their unsaved edits so they can retry.
8. The Submit button remains disabled until all four required fields — claimant name, policy number, incident date, and claim amount — have been provided.
9. When the employee enters values for all four required fields, the Submit button becomes enabled.
