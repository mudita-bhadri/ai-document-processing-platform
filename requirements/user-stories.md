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
6. If AI extraction fails, the platform informs the employee, retains the uploaded document and allows them to retry extraction without uploading the document again.
7. The platform does not submit the claim automatically; the employee must review the extracted information before proceeding.

**Open Questions**
- Should the employee be able to retry extraction, or should they be able to proceed directly to manual entry when extraction fails?

## US-03: Review, Correct and Submit a Claim

**Priority:** Must have

**User story**

As an insurance claims employee, I want to review and correct the information extracted by AI and submit the completed claim so that I can ensure the claim details are accurate before further processing.

**Acceptance criteria**

1. The platform displays the four extracted claim fields — claimant name, policy number, incident date, and claim amount — in an editable form.
2. The employee can correct inaccurate extracted values and enter values for fields that the AI could not extract.
3. The platform clearly indicates fields for which no value was extracted.
4. The Submit button remains disabled until all four required fields have been provided.
5. The Submit button becomes enabled when all four required fields have been provided.
6. When the employee submits a claim, the platform validates the field values against the applicable validation rules.
7. If validation fails, the platform identifies the fields that need correction and prevents submission.
8. If submission succeeds, the platform confirms the submission and assigns the claim a unique reference identifier.
9. If submission fails, the platform informs the employee and allows them to retry without requiring them to re-enter the claim details.

**Open questions**

- What validation rules should apply to each field?
- Which claim statuses should the MVP support?
- Should submitted claims be editable?
- How should the platform handle repeated submission attempts?
- Should the platform preserve unsaved edits if the employee accidentally closes the page or loses their session?
