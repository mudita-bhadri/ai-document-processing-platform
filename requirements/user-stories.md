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
