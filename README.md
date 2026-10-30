# StudyVault – Personal Study Notes & Document Storage

> **Your Notes. Our Priority.**

StudyVault is a multi-page personal study notes and document vault engineered for students, researchers, and lifelong learners. It provides hierarchical folder organization (Subjects, Chapters, Units), document management (PDF, Word, Slides, Spreadsheets, Images, and Text notes), in-browser document previews, trash recovery, and full JSON data backup/restore.

---

## 📁 Architecture & Multi-Page Layout

In strict accordance with the project requirements, StudyVault is built as a pure **multi-page website** where each page is an independent HTML file containing its own embedded HTML structure, CSS `<style>`, and Vanilla JavaScript `<script>`:

```text
StudyVault/
│
├── index.html             # Page 1: Dashboard with live metrics, quick folders, and recent documents
├── library.html           # Page 2: My Library with unlimited nested folders, drag-and-drop, and previewer
├── trash.html             # Page 3: Trash with restore individual/all and permanent delete confirmation
├── settings.html          # Page 4: Settings & Backup with storage quota meter and JSON export/restore
│
├── assets/
│   ├── studyvault-logo.svg    # Vector StudyVault logo
│   ├── studyvault-logo.png    # Official StudyVault logo PNG asset
│   └── logo-renderer.html     # High-resolution rendering canvas
│
└── README.md              # Project documentation and deployment guide
```

---

## 🚀 Key Features

### 1. Dashboard (`index.html`)
- **Live Vault Statistics**: Total Folders, Total Documents, Starred Notes, and Storage Quota Meter.
- **Quick Access Folders**: Color-coded cards for quick navigation directly to subject and chapter folders.
- **Recently Added Documents**: Comprehensive table with document badges, sizes, timestamps, and direct preview modals.
- **Global Live Search**: Live search input with keyboard shortcut (`Ctrl+K`) that searches across folders and documents in real time.

### 2. My Library (`library.html`)
- **Unlimited Folder Hierarchy**: Multi-level nested folder creation (`Subject` → `Chapter` → `Unit` → `Topic`).
- **Color Labeling**: 8 distinct color palettes (Indigo, Emerald, Amber, Rose, Purple, Sky, Cyan, Slate).
- **Folder Management**: Rename, Move (with cycle-prevention logic), and Delete to Trash.
- **Document Upload**:
  - Drag-and-drop file upload zone.
  - Multi-file selection support for PDF, DOC, DOCX, PPT, PPTX, XLS, XLSX, PNG, JPG, JPEG, and TXT.
- **Bulk Actions**: Select individual files or Select All to perform bulk starring, bulk moving, bulk downloading, and bulk deleting to trash.
- **Full Document Viewer**:
  - PDF preview with zoom (50% to 250%), 90-degree rotation, fullscreen, and download original.
  - High-res diagram/image preview with zoom and download.
  - Formatted text/code viewer.

### 3. Trash & Recovery (`trash.html`)
- **Safe Recovery**: View deleted folders and documents with original folder location and timestamp.
- **Individual & Bulk Restore**: One-click restore back to the original folder location.
- **Permanent Deletion**: Secure modal confirmation before permanently removing items.
- **Empty Trash**: Wipe deleted files to reclaim storage quota.

### 4. Settings & Backup (`settings.html`)
- **Storage Quota Analytics**: Live stacked visual bar and categorized cards (PDF, Word, Presentations, Spreadsheets, Images, Notes).
- **Download JSON Backup**: Full database export (`studyvault-backup-YYYY-MM-DD.json`) including folders, documents, metadata, and settings.
- **Upload & Restore JSON**: Instant verification and restoration of previous study vault backups.
- **User Profile**: Custom scholar name, academic email, institution, and customizable storage quota tiers (100 MB up to 1 GB).
- **Vault Maintenance**: Reset to sample academic vault or clear data.

---

## 🛠️ Running & Deploying the Website

Because StudyVault is built using standard HTML5, CSS3, and Vanilla JavaScript, it can be run using any web server or static host:

### Local Development
```bash
# Run with Vite dev server (on port 3000)
npm run dev
```

### Static Hosting / Deployment
Deploy the files directly to:
- **Firebase Hosting**:
  ```bash
  firebase init hosting
  firebase deploy
  ```
- **GitHub Pages**, **Netlify**, or **Vercel**: Simply upload or push the repository root. All separate HTML pages (`index.html`, `library.html`, `trash.html`, `settings.html`) and assets are served directly.
