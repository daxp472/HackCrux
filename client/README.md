# NyayaSankalan Client

Frontend application for NyayaSankalan CMS.

## Stack

- React 19
- TypeScript
- Vite
- React Router
- Tailwind CSS
- Axios
- Recharts

## Features in Client

- Role-based dashboards: `POLICE`, `SHO`, `COURT_CLERK`, `JUDGE`
- FIR creation and case drill-down
- Investigation tools: evidence, witness, accused management
- Court workflow screens and defect/resubmission flow
- Document request workflow
- Case timeline and audit views
- Notifications UI and toast alerts
- Analytics dashboard (status distribution, trends, efficiency chart)
- AI widgets and AI demo page (`/ai-demo`)

## Development

```bash
cd client
npm install
npm run dev
```

Default dev URL: `http://localhost:5173`

## Environment

Create `client/.env`:

```env
VITE_API_URL=http://localhost:5000/api
```

## Build

```bash
npm run build
npm run preview
```

## Notes

- This app expects backend API auth; login first.
- If backend runs on another host/port, update `VITE_API_URL`.
