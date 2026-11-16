# SAMVAAD
**Bridging Communication Through Technology**

Starter repository for an Indian Sign Language recognition research system.

## Included now
- React + Vite + Tailwind frontend foundation
- FastAPI backend with a real health endpoint
- Safe dataset inventory script (does not assume `.dat` format)
- Initial tests and phase documentation

## Important
The 8 GB dataset was not attached, so dataset contents, labels, class counts, signer counts and format remain **unverified**. No model, predictions or accuracy values are fabricated.

## Run (Windows PowerShell)

Backend:
```powershell
cd backend
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
uvicorn app.main:app --reload
```
API docs: http://127.0.0.1:8000/docs

Frontend (new terminal):
```powershell
cd frontend
npm install
npm run dev
```
Open http://localhost:5173

Dataset inspection (from repository root):
1. Copy dataset into `ml/data/raw/` (keep original untouched).
2. Run:
```powershell
py scripts/inspect_dataset.py --root ml/data/raw --output reports/dataset_inspection.json
```
The inspector inventories file paths, sizes, extensions and common file signatures. It does not execute or deserialize unknown `.dat` files. It cannot infer labels/classes until the actual format/schema is understood.

Python 3.11 and Node.js 20+ are recommended. See `docs/PHASE_PLAN.md` for the staged roadmap.
