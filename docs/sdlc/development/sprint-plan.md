# Sprint Plan

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start sprints -->
## Sprint 1: Sprint 1

Stand up admin authentication, the document upload entry point, the public chat page shell, and the privacy notice.

Capacity: 20 points · Committed: 19

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-001 | Story | Standalone chat page for visitors | 5 | frontend-agent | — |
| US-009 | Story | Admin sign-in | 5 | backend-agent | — |
| US-010 | Story | Upload source documents | 8 | backend-agent | US-009 |
| ↳ US-010-T1 | Task | Implement document upload endpoint with format validation and S3 storage | — | backend-agent | — |
| ↳ US-010-T2 | Task | Enqueue uploaded document for background processing | — | backend-agent | — |
| ↳ US-010-T3 | Task | Build admin document upload UI | — | frontend-agent | — |
| US-015 | Story | Privacy notice for visitors | 1 | frontend-agent | — |

## Sprint 2: Sprint 2

Complete the document processing pipeline (chunking, embedding, indexing), document replace/remove, the admin dashboard, and the consent UI.

Capacity: 20 points · Committed: 18

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-011 | Story | Replace and remove source documents | 5 | backend-agent | US-010, US-012 |
| US-012 | Story | Document chunking, embedding and indexing | 8 | backend-agent | US-010 |
| ↳ US-012-T1 | Task | Implement PDF, Word and plain text parsers in the processing worker | — | backend-agent | — |
| ↳ US-012-T2 | Task | Implement chunking and OpenAI embedding pipeline | — | backend-agent | — |
| ↳ US-012-T3 | Task | Add document processing status tracking | — | backend-agent | — |
| US-013 | Story | Admin content dashboard | 3 | frontend-agent | US-010, US-012 |
| US-016 | Story | Explicit consent before capturing contact details | 2 | frontend-agent | US-001 |

## Sprint 3: Sprint 3

Deliver grounded retrieval-augmented answers with multi-turn memory, source citations, and the 'I don't know' fallback.

Capacity: 20 points · Committed: 19

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-002 | Story | Multi-turn conversation within a session | 5 | backend-agent | US-001, US-003 |
| US-003 | Story | Grounded answers via retrieval-augmented generation | 8 | backend-agent | US-012 |
| ↳ US-003-T1 | Task | Implement retrieval service querying pgvector for top-k relevant chunks | — | backend-agent | — |
| ↳ US-003-T2 | Task | Implement OpenAI-grounded answer generation in the chat endpoint | — | backend-agent | — |
| ↳ US-003-T3 | Task | Add automated tests for retrieval-augmented answer quality | — | qa-agent | — |
| US-004 | Story | Source citations shown with answers | 3 | backend-agent | US-003 |
| US-005 | Story | "I don't know" fallback with no invented answers | 3 | backend-agent | US-003 |

## Sprint 4: Sprint 4

Enable follow-up capture, staff email notification, admin review of follow-ups, and conversation history review.

Capacity: 20 points · Committed: 18

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-006 | Story | Capture visitor contact details and question on fallback | 5 | backend-agent | US-005, US-016 |
| US-007 | Story | Email notification to configured staff inbox | 3 | integration-agent | US-006 |
| US-008 | Story | Admin review and action of follow-up requests | 5 | backend-agent | US-006, US-009 |
| US-014 | Story | Review conversation history | 5 | backend-agent | US-002, US-009 |

## Sprint 5: Sprint 5

Support GDPR-level deletion of a visitor's personal data on request.

Capacity: 20 points · Committed: 5

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-017 | Story | Data deletion on request | 5 | backend-agent | US-006, US-008, US-014 |

## Unscheduled

_Nothing unscheduled._
<!-- sdlc:auto:end sprints -->
