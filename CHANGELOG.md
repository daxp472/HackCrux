# 📋 Changelog

All notable changes to **NyayaSankalan** will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### Changed
- Root README updated for Gemini-first AI flow and ai-poc port `8001`
- Client README replaced from Vite template with project-specific guide
- Security policy clarified with implemented vs planned controls
- System flow corrected: FIR registration actor is `POLICE`

### Planned
- Mobile app (React Native) for Police Officers
- Real-time notifications via WebSockets
- Multi-language support (Hindi, Marathi, Tamil)
- Court hearing scheduling & calendar integration
- Digital signature integration for final documents

---

## [1.0.0] — 2026-03-15

### 🎉 Initial Hackathon Release

This is the first complete release of NyayaSankalan, developed for the HackCrux hackathon.

### Added

#### Core Case Management
- FIR registration with document upload to Cloudinary
- 16-state case lifecycle mirroring real CrPC workflow
- Auto case creation on FIR registration
- Complete audit trail for every state transition
- Role-based state transition enforcement

#### Investigation Module
- Investigation event logging (Search, Seizure, Statement, Transfer)
- Evidence upload with categorisation (Photo, Report, Forensic, Statement)
- Witness management with contact and statement tracking
- Accused management with status tracking (Arrested, On Bail, Absconding)
- Investigation pause/resume workflow
- Bail application tracking (Police, Anticipatory, Court bail)

#### Document Generation
- Charge sheet creation and generation
- Closure report preparation
- Evidence list & witness list documents
- Remand application support
- Document versioning (Draft → Final → Locked)
- PDF generation via PDFKit
- Mandatory document checklist validation before court submission

#### Court Workflow
- Case submission to court by SHO
- Court clerk review with Accept / Return for Defects flow
- Defect notes and resubmission workflow
- Court actions: Cognizance, Charges Framed, Hearing, Judgment, Sentence, Acquittal, Conviction
- Case disposal and archiving
- Case reopen requests with judicial approval

#### AI Engine (Python FastAPI Microservice)
- OCR extraction from scanned FIR documents (pytesseract + pdfplumber)
- Named Entity Recognition using spaCy (names, dates, IPC sections, phone numbers)
- Automatic PII redaction from documents
- LLM-based charge sheet draft generation (FLAN-T5 via HuggingFace)
- Semantic document embeddings (sentence-transformers)
- FAISS-based similar case retrieval

#### Authentication & Security
- JWT-based authentication with configurable expiry
- bcrypt password hashing
- Helmet.js security headers
- express-validator input sanitisation
- Role-based access control (POLICE, SHO, COURT_CLERK, JUDGE)
- Complete audit logging with IP, user, action, timestamp

#### Frontend (React + Vite)
- Role-based dashboards for all 4 user types
- Case timeline visualisation
- Document management UI
- Evidence gallery
- AI document processing interface
- Analytics with Recharts
- PDF export from frontend (jsPDF)

#### Backend Infrastructure
- Node.js + Express REST API
- TypeScript throughout
- Prisma ORM with PostgreSQL
- Cloudinary CDN integration
- Winston logging
- Jest test suite

### Documentation
- Data Flow Diagrams (Level 0 & Level 1)
- Complete System Flow documentation
- Security policy (SECURITY.md)
- AI Features README
- Setup guides

---

*For older entries, check the [git log](https://github.com/daxp472/HackCrux/commits/main).*

[Unreleased]: https://github.com/daxp472/HackCrux/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/daxp472/HackCrux/releases/tag/v1.0.0
