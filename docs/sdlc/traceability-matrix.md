# Traceability Matrix

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start legend -->
Built from recorded links, not written by a model: requirement key → plan item (`source_stable_key`) → development ticket (`stable_key`) → the ticket's test steps → the last live deployment that started after the work finished. **AC tests** counts the story's acceptance criteria that have a test case, and those whose test cases all passed in the latest finished E2E run.
<!-- sdlc:auto:end legend -->

<!-- sdlc:auto:start matrix -->
| Requirement | Epic | Title | Plan items | Sprint | Design | Code | Commits | Ticket | Tests | AC tests | Deployed |
|---|---|---|---|---|---|---|---|---|---|---|---|
| US-001 | EPIC-001 | Standalone chat page for visitors | US-001 | 1 | POST /api/chat, POST /api/conversations, conversations, frontend | — | — | not started | not run | 0/3 tested · 0/3 passing | — |
| US-002 | EPIC-001 | Multi-turn conversation within a session | US-002 | 3 | POST /api/chat, backend_api, conversations, database, messages | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-003 | EPIC-001 | Grounded answers via retrieval-augmented generation | US-003, US-003-T1, US-003-T2, US-003-T3 | 3 | POST /api/chat, backend_api, database, document_chunks, messages, openai | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-004 | EPIC-001 | Source citations shown with answers | US-004 | 3 | POST /api/chat, backend_api, database, message_citations | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-005 | EPIC-001 | "I don't know" fallback with no invented answers | US-005 | 3 | POST /api/chat, backend_api, messages | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-006 | EPIC-002 | Capture visitor contact details and question on fallback | US-006 | 4 | POST /api/followups, backend_api, database, followup_requests, frontend | — | — | not started | not run | 0/3 tested · 0/3 passing | — |
| US-007 | EPIC-002 | Email notification to configured staff inbox | US-007 | 4 | POST /api/followups, backend_api, email, followup_requests | — | — | not started | not run | 0/3 tested · 0/3 passing | — |
| US-008 | EPIC-002 | Admin review and action of follow-up requests | US-008 | 4 | GET /api/admin/followups, PATCH /api/admin/followups/{id}, backend_api, database, followup_requests, frontend | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-009 | EPIC-003 | Admin sign-in | US-009 | 1 | POST /api/admin/login, admin_users, backend_api, database, frontend | — | — | not started | not run | 0/3 tested · 0/3 passing | — |
| US-010 | EPIC-003 | Upload source documents | US-010, US-010-T1, US-010-T2, US-010-T3 | 1 | POST /api/admin/documents, backend_api, documents, frontend, object_store, queue | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-011 | EPIC-003 | Replace and remove source documents | US-011 | 2 | DELETE /api/admin/documents/{id}, PUT /api/admin/documents/{id}, backend_api, database, document_chunks, documents, object_store | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-012 | EPIC-003 | Document chunking, embedding and indexing | US-012, US-012-T1, US-012-T2, US-012-T3 | 2 | backend_api, database, document_chunks, documents, openai, worker | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-013 | EPIC-004 | Admin content dashboard | US-013 | 2 | GET /api/admin/documents, backend_api, documents, frontend | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-014 | EPIC-004 | Review conversation history | US-014 | 4 | GET /api/admin/conversations, GET /api/admin/conversations/{id}, backend_api, conversations, database, frontend, messages | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-015 | EPIC-005 | Privacy notice for visitors | US-015 | 1 | GET /api/privacy-notice, backend_api, frontend | — | — | not started | not run | 0/1 tested · 0/1 passing | — |
| US-016 | EPIC-005 | Explicit consent before capturing contact details | US-016 | 2 | POST /api/followups, backend_api, followup_requests, frontend | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
| US-017 | EPIC-005 | Data deletion on request | US-017 | 5 | POST /api/admin/data-deletion, backend_api, conversations, database, followup_requests, message_citations, messages | — | — | not started | not run | 0/2 tested · 0/2 passing | — |
<!-- sdlc:auto:end matrix -->
