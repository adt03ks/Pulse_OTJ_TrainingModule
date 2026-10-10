# Pulse · TMC Security Officer OJT

Independent, working browser-local module based on the October 9, 2026 Memorial Hermann TMC Security Officer OJT checklist. Includes the selected Pulse Training System logo, all 120 task rows across eight sections, all 33 source assessment questions, three fictional report examples, typed trainer/supervisor/manager attestations and a personalized PDF certificate.

## Open or integrate

Serve the contents of `dist/` as static files. For an existing GitHub Pages Pulse project, copy `dist/` into `pulse/ojt/` (or the existing module directory) and add a Pulse hub link to `pulse/ojt/index.html`. All asset references are relative. The deployed private Site is an independent preview, not an update to the existing Pulse repository.

## Completion logic

1. Enter officer name, employee ID and OJT start date.
2. Review eight lessons. Record each task as demonstrated, practiced, observed competent or N/A.
3. Competent tasks require trainer initials, employee initials and date; N/A requires supervisor initials, employee initials and date.
4. Trainer and supervisor sign off each complete section.
5. Complete three fictional narratives and record trainer and supervisor review.
6. Take the 33-question test. Default threshold is 80% (27/33); management can change it.
7. Management confirms current policy and threshold, then records employee/trainer/supervisor/manager attestations.
8. Download or print a landscape certificate with name, frozen completion timestamp in America/Chicago, assessment score, basic skills, approver names and unique local record ID.

Changes to profile, competency records, report practice, plaza references or requirements revoke the existing final attestation and certificate. Export a JSON training record before switching officers or clearing browser data.

## Current preview boundaries

LocalStorage holds one officer record per browser. There is no authentication, remote database, cross-device synchronization, tamper-resistant grading or centrally verifiable certificate registry. Typed sign-offs are not identity-verified. Certificates identify themselves as local training records. Assessment answers exist in browser code and this is not a secure examination service. Narratives must use fictional details; do not enter patient names, MRNs or PHI.

## Connect to the existing Pulse / SecureTrack backend

The existing repository, Supabase project configuration and verified role model were not available in this task. Before operational deployment:

- Replace LocalStorage persistence with authenticated, per-officer records under Pulse/Supabase row-level security. Retain the existing auth and manager assignment rules.
- Trainer observation and supervisor approvals must be written only by their verified accounts. Record actor ID, server timestamp, task/section version, N/A reason and audit history.
- Keep the answer key and scoring on the server. Randomize test presentation, preserve attempt records, and enforce the management-set threshold on the server.
- Issue the final certificate only after the server verifies all prerequisite records and the authorized security manager approves. Use a server timestamp and registry-backed ID.
- Build manager roster/progress screens from shared records; prevent an officer from granting their own approvals.
- Retain confidential records behind existing access controls. Do not send PHI through ordinary SMS/email or store secrets in client code. If using an Edge Function, enforce approved origins and verified user authorization.
- Security Management must approve the local policy content, emergency code definitions, post applicability and passing threshold. The source specifically requires current-policy confirmation before sign-off.

Source materials use Resolver for dispatch/reporting and title the fictional report examples “Report Exec.” The module directs users to the current department-approved platform instead of inventing a reconciliation.

## Files

`index.html`: module shell; `style.css`: responsive Pulse branding and print styles; `content.js`: faithful checklist data; `app.js`: progress, attestations, scoring and raster PDF certificate generation; `assets/`: Pulse logo and source checklist. No external JavaScript dependencies.

## Validation

JavaScript syntax checked. Automated state/interaction checks cover task/question counts, locked assessment, pass/fail scoring, required supervisor initials for N/A, certificate prerequisites, stable completion timestamp and revocation after edits. Browser visual QA was unavailable in the current environment; confirm desktop/mobile layout and PDF download in the target Pulse environment before staff rollout.
