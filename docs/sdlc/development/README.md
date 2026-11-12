# Development

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start narrative -->
### PLAN-001 · approved · source: plan:PLAN

Development plan version 1 for TEST555 is approved, organized into 5 sprints of 20-point capacity each covering the full chatbot build from admin auth through GDPR deletion.

Plan status: approved, version 1. Five sprints: Sprint 1 (admin auth, upload entry point, chat page shell, privacy notice), Sprint 2 (document processing pipeline, replace/remove, admin dashboard, consent UI), Sprint 3 (grounded RAG answers, multi-turn memory, citations, fallback), Sprint 4 (follow-up capture, staff notification, admin review, conversation history), Sprint 5 (GDPR-level deletion). Each sprint capacity=20 points.

**Related:** US-001, US-002, US-003, US-004, US-005, US-006, US-007, US-008, US-009, US-010, US-011, US-012, US-013, US-014, US-015, US-016, US-017

### SPRINT-1 · approved · source: plan:SPRINT-1

Sprint 1 goal: stand up admin authentication, the document upload entry point, the public chat page shell, and the privacy notice.

Capacity=20 points. Goal as stated: 'Stand up admin authentication, the document upload entry point, the public chat page shell, and the privacy notice.' Maps to admin sign-in (US-009), upload source documents (US-010), standalone chat page (US-001), and privacy notice (US-015).

**Related:** US-009, US-010, US-001, US-015

### SPRINT-2 · approved · source: plan:SPRINT-2

Sprint 2 goal: complete the document processing pipeline (chunking, embedding, indexing), document replace/remove, the admin dashboard, and the consent UI.

Capacity=20 points. Goal as stated: 'Complete the document processing pipeline (chunking, embedding, indexing), document replace/remove, the admin dashboard, and the consent UI.' Maps to document chunking/embedding/indexing (US-012), replace and remove documents (US-011), admin content dashboard (US-013), and explicit consent UI (US-016).

**Related:** US-012, US-011, US-013, US-016

### SPRINT-3 · approved · source: plan:SPRINT-3

Sprint 3 goal: deliver grounded retrieval-augmented answers with multi-turn memory, source citations, and the 'I don't know' fallback.

Capacity=20 points. Goal as stated: 'Deliver grounded retrieval-augmented answers with multi-turn memory, source citations, and the "I don't know" fallback.' Maps to grounded RAG answers (US-003), multi-turn conversation (US-002), source citations (US-004), and no-invented-answer fallback (US-005).

**Related:** US-003, US-002, US-004, US-005

### SPRINT-4 · approved · source: plan:SPRINT-4

Sprint 4 goal: enable follow-up capture, staff email notification, admin review of follow-ups, and conversation history review.

Capacity=20 points. Goal as stated: 'Enable follow-up capture, staff email notification, admin review of follow-ups, and conversation history review.' Maps to capture contact details on fallback (US-006), staff email notification (US-007), admin review/action of follow-ups (US-008), and conversation history review (US-014).

**Related:** US-006, US-007, US-008, US-014

### SPRINT-5 · approved · source: plan:SPRINT-5

Sprint 5 goal: support GDPR-level deletion of a visitor's personal data on request.

Capacity=20 points. Goal as stated: 'Support GDPR-level deletion of a visitor's personal data on request.' Maps to data deletion on request (US-017).

**Related:** US-017

### EPIC-001 · approved · source: plan:EPIC-001

Epic covering document-grounded conversational answering: the public chat experience, retrieval-augmented generation, citations, and fallback behavior.

Unassigned role, no points at epic level. Child stories: US-001 (standalone chat page), US-002 (multi-turn conversation), US-003 (grounded RAG answers), US-004 (source citations), US-005 ('I don't know' fallback).

**Related:** US-001, US-002, US-003, US-004, US-005

### EPIC-002 · approved · source: plan:EPIC-002

Epic covering follow-up capture and staff notification when the chatbot cannot answer.

Unassigned role, no points at epic level. Child stories: US-006 (capture contact details and question on fallback), US-007 (email notification to staff inbox), US-008 (admin review and action of follow-up requests).

**Related:** US-006, US-007, US-008

### EPIC-003 · approved · source: plan:EPIC-003

Epic covering admin document management: sign-in, upload, replace/remove, and the chunking/embedding/indexing pipeline.

Unassigned role, no points at epic level. Child stories: US-009 (admin sign-in), US-010 (upload source documents), US-011 (replace and remove source documents), US-012 (document chunking, embedding and indexing).

**Related:** US-009, US-010, US-011, US-012

### EPIC-004 · approved · source: plan:EPIC-004

Epic covering the admin dashboard and conversation history review capabilities.

Unassigned role, no points at epic level. Child stories: US-013 (admin content dashboard), US-014 (review conversation history).

**Related:** US-013, US-014

### EPIC-005 · approved · source: plan:EPIC-005

Epic covering GDPR-level privacy and data protection: notice, consent, and deletion on request.

Unassigned role, no points at epic level. Child stories: US-015 (privacy notice for visitors), US-016 (explicit consent before capturing contact details), US-017 (data deletion on request).

**Related:** US-015, US-016, US-017

### US-001 · approved · source: plan:US-001

Story: standalone chat page for visitors.

Points=5, role=frontend-agent. Part of EPIC-001 (Document-Grounded Conversational Answering); planned for Sprint 1 per that sprint's goal of delivering the public chat page shell.

**Related:** EPIC-001, SPRINT-1

### US-002 · approved · source: plan:US-002

Story: multi-turn conversation within a session.

Points=5, role=backend-agent. Part of EPIC-001; planned for Sprint 3 per that sprint's goal of delivering multi-turn memory.

**Related:** EPIC-001, SPRINT-3

### US-003 · approved · source: plan:US-003

Story: grounded answers via retrieval-augmented generation.

Points=8, role=backend-agent. Part of EPIC-001; planned for Sprint 3. Broken into tasks: US-003-T1 (retrieval service querying pgvector for top-k relevant chunks), US-003-T2 (OpenAI-grounded answer generation in the chat endpoint), US-003-T3 (automated tests for RAG answer quality, role=qa-agent).

**Related:** EPIC-001, SPRINT-3, US-003-T1, US-003-T2, US-003-T3

### US-003-T1 · approved · source: plan:US-003-T1

Task: implement retrieval service querying pgvector for top-k relevant chunks.

Role=backend-agent. Child task of US-003 (grounded RAG answers).

**Related:** US-003

### US-003-T2 · approved · source: plan:US-003-T2

Task: implement OpenAI-grounded answer generation in the chat endpoint.

Role=backend-agent. Child task of US-003 (grounded RAG answers).

**Related:** US-003

### US-003-T3 · approved · source: plan:US-003-T3

Task: add automated tests for retrieval-augmented answer quality.

Role=qa-agent. Child task of US-003 (grounded RAG answers).

**Related:** US-003

### US-004 · approved · source: plan:US-004

Story: source citations shown with answers.

Points=3, role=backend-agent. Part of EPIC-001; planned for Sprint 3 per that sprint's goal of delivering source citations.

**Related:** EPIC-001, SPRINT-3

### US-005 · approved · source: plan:US-005

Story: 'I don't know' fallback with no invented answers.

Points=3, role=backend-agent. Part of EPIC-001; planned for Sprint 3 per that sprint's goal of delivering the fallback behavior.

**Related:** EPIC-001, SPRINT-3

### US-006 · approved · source: plan:US-006

Story: capture visitor contact details and question on fallback.

Points=5, role=backend-agent. Part of EPIC-002 (Follow-up Capture and Staff Notification); planned for Sprint 4.

**Related:** EPIC-002, SPRINT-4

### US-007 · approved · source: plan:US-007

Story: email notification to configured staff inbox.

Points=3, role=integration-agent. Part of EPIC-002; planned for Sprint 4.

**Related:** EPIC-002, SPRINT-4

### US-008 · approved · source: plan:US-008

Story: admin review and action of follow-up requests.

Points=5, role=backend-agent. Part of EPIC-002; planned for Sprint 4.

**Related:** EPIC-002, SPRINT-4

### US-009 · approved · source: plan:US-009

Story: admin sign-in.

Points=5, role=backend-agent. Part of EPIC-003 (Admin Document Management); planned for Sprint 1 per that sprint's goal of standing up admin authentication.

**Related:** EPIC-003, SPRINT-1

### US-010 · approved · source: plan:US-010

Story: upload source documents.

Points=8, role=backend-agent. Part of EPIC-003; planned for Sprint 1. Broken into tasks: US-010-T1 (upload endpoint with format validation and S3 storage), US-010-T2 (enqueue uploaded document for background processing), US-010-T3 (admin document upload UI, role=frontend-agent).

**Related:** EPIC-003, SPRINT-1, US-010-T1, US-010-T2, US-010-T3

### US-010-T1 · approved · source: plan:US-010-T1

Task: implement document upload endpoint with format validation and S3 storage.

Role=backend-agent. Child task of US-010 (upload source documents).

**Related:** US-010

### US-010-T2 · approved · source: plan:US-010-T2

Task: enqueue uploaded document for background processing.

Role=backend-agent. Child task of US-010 (upload source documents).

**Related:** US-010

### US-010-T3 · approved · source: plan:US-010-T3

Task: build admin document upload UI.

Role=frontend-agent. Child task of US-010 (upload source documents).

**Related:** US-010

### US-011 · approved · source: plan:US-011

Story: replace and remove source documents.

Points=5, role=backend-agent. Part of EPIC-003; planned for Sprint 2 per that sprint's goal of delivering document replace/remove.

**Related:** EPIC-003, SPRINT-2

### US-012 · approved · source: plan:US-012

Story: document chunking, embedding and indexing.

Points=8, role=backend-agent. Part of EPIC-003; planned for Sprint 2. Broken into tasks: US-012-T1 (PDF, Word and plain text parsers in the processing worker), US-012-T2 (chunking and OpenAI embedding pipeline), US-012-T3 (document processing status tracking).

**Related:** EPIC-003, SPRINT-2, US-012-T1, US-012-T2, US-012-T3

### US-012-T1 · approved · source: plan:US-012-T1

Task: implement PDF, Word and plain text parsers in the processing worker.

Role=backend-agent. Child task of US-012 (document chunking, embedding and indexing).

**Related:** US-012

### US-012-T2 · approved · source: plan:US-012-T2

Task: implement chunking and OpenAI embedding pipeline.

Role=backend-agent. Child task of US-012 (document chunking, embedding and indexing).

**Related:** US-012

### US-012-T3 · approved · source: plan:US-012-T3

Task: add document processing status tracking.

Role=backend-agent. Child task of US-012 (document chunking, embedding and indexing).

**Related:** US-012

### US-013 · approved · source: plan:US-013

Story: admin content dashboard.

Points=3, role=frontend-agent. Part of EPIC-004 (Admin Dashboard and Conversation Review); planned for Sprint 2.

**Related:** EPIC-004, SPRINT-2

### US-014 · approved · source: plan:US-014

Story: review conversation history.

Points=5, role=backend-agent. Part of EPIC-004; planned for Sprint 4.

**Related:** EPIC-004, SPRINT-4

### US-015 · approved · source: plan:US-015

Story: privacy notice for visitors.

Points=1, role=frontend-agent. Part of EPIC-005 (Privacy and Data Protection, GDPR-level); planned for Sprint 1.

**Related:** EPIC-005, SPRINT-1

### US-016 · approved · source: plan:US-016

Story: explicit consent before capturing contact details.

Points=2, role=frontend-agent. Part of EPIC-005; planned for Sprint 2 per that sprint's goal of delivering the consent UI.

**Related:** EPIC-005, SPRINT-2

### US-017 · approved · source: plan:US-017

Story: data deletion on request (GDPR-level).

Points=5, role=backend-agent. Part of EPIC-005; planned for Sprint 5, the sole focus of that sprint.

**Related:** EPIC-005, SPRINT-5
<!-- sdlc:auto:end narrative -->
