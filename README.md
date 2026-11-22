# 🏢 MSME Website Content Studio

> Transform official Indian Government MSME Certificates (**Udyam Registration** & **GST Registration**) into 100% compliant, document-grounded website content and ready-to-paste Google Sites layouts.

---

## ✨ Features

- **📄 Smart Certificate Parsing:**
  - Extracts enterprise legal name, trade/unit names (supports multi-unit extraction), registered addresses (principal & additional places of business), GSTIN, Udyam numbers, and registration dates.
  - Advanced watermark suppression and multi-page table reconstruction using `pdfplumber`.
  - Scanned image detection with helpful user guidance.

- **🔍 Official NIC-2008 Grounding:**
  - Integrated official National Industrial Classification (NIC-2008) master database (`nic_2008_db.json`).
  - Auto-resolves 2-digit, 3-digit, 4-digit, and 5-digit NIC activities to prevent hallucinated or invented business scopes.

- **🌐 Google Sites Ready (Multiple Export Options):**
  - **1-Click HTML Embeds:** Beautiful, responsive HTML components with scoped CSS. Copy and paste directly into Google Sites using `Insert` ➔ `Embed` ➔ `Embed Code`.
  - **Clean Text Cards (No Markdown Symbols):** Plain-text output without `#`, `**`, `|---|---|`, or `>` characters for direct pasting into standard Google Sites *Text Boxes* or word processors.
  - **Raw Markdown:** Standard Markdown formatting with tabular registration profiles for GitHub, documentation sites, or static site generators.
  - **Live Visual Mockup:** Preview how the enterprise website will look in real time before publishing.

- **🛡️ Built-in Security & Privacy:**
  - File validation with PDF magic bytes check.
  - HTML & Markdown sanitization on all manual inputs to prevent XSS.
  - Safe clipboard copy via `data-copy` attributes.
  - Complete client certificate isolation (`.gitignore` protects confidential business documents).

---

## 🚀 Quick Start

### 1. Prerequisites
- Python 3.9 or higher
- Git

### 2. Clone the Repository
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### 3. Set Up Virtual Environment (Recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 4. Install Dependencies
```bash
pip install -r requirements.txt
```

### 5. Run the Application
```bash
python app_v2.py
```
Open your browser and navigate to:
```
http://127.0.0.1:5000
```

---

## 📖 How to Use

1. **Step 1: Upload Documents**
   - Choose document type: **Udyam Only**, **GST Only**, or **Both (Merged)**.
   - Upload official digital PDF certificates downloaded from official portals ([udyamregistration.gov.in](https://udyamregistration.gov.in) or [gst.gov.in](https://www.gst.gov.in)).
   - *(Optional)* Add or override contact information (phone, email, custom unit name, address).
   - Click **Generate Website Content**.

2. **Step 2: Review Extracted Details**
   - Review extracted legal name, trade name, addresses, enterprise type, and NIC classifications.
   - Any document conflicts (e.g. legal name mismatch between GST and Udyam) are automatically flagged for user review.

3. **Step 3: Export to Google Sites**
   - **Method A (Recommended - Rich Visual Layout):** 
     - Go to the **Google Sites HTML Embed** tab.
     - Click **Copy HTML Code** for any section or **Copy Full 1-Page HTML Embed**.
     - In Google Sites: `Insert` ➔ `Embed` ➔ select `Embed Code` tab ➔ Paste ➔ `Insert`.
   - **Method B (Plain Text Box):**
     - Go to the **Clean Text Cards** tab.
     - Click **Copy Clean Text** and paste directly into Google Sites text boxes. Zero markdown syntax cleanup required!

---

## 📁 Project Structure

```text
├── app_v2.py                 # Core Flask application and UI templates
├── nic_2008_db.json          # Official NIC-2008 master database lookup
├── 1760616763355-NIC_2008.xlsx # Master NIC-2008 reference spreadsheet
├── requirements.txt          # Python package dependencies
├── .gitignore                # Excludes private certificates & temp files
└── README.md                 # Project documentation
```

---

## 🔒 Privacy & Compliance Notice

- This tool does not store, log, or transmit uploaded certificates to any external third-party server. All parsing runs entirely on your local machine.
- Sample certificates placed in the `udyam/` folder are excluded by `.gitignore` to prevent confidential taxpayer information from leaking to public repositories.
- Generated Privacy Policies and Terms & Conditions are generic templates and should be reviewed by a qualified legal advisor before commercial deployment.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
