# Niom's Restaurant - Food Order Chatbot

A Dialogflow-powered food ordering chatbot for **Niom's Restaurant**, Sylhet, Bangladesh.
Built with FastAPI (Python) backend and a clean bluish-white frontend.

---

## Directory Structure

```
nioms_restaurant/
├── backend/          → Python FastAPI webhook server
│   ├── main.py       → Main app with intent handlers
│   ├── db_helper.py  → MySQL database operations
│   ├── generic_helper.py → Utility functions
│   └── requirements.txt
├── db/
│   └── nioms_restaurant.sql  → MySQL database dump (import this first!)
├── dialogflow_assets/
│   └── training_phrases.txt  → Intent training data for Dialogflow
└── frontend/
    ├── home.html     → Restaurant website
    ├── styles.css    → Bluish-white theme
    ├── banner.jpg    → Hero banner image
    ├── menu1.jpg
    ├── menu2.jpg
    └── menu3.jpg
```

---

## Setup Instructions

### 1. Import the Database
- Open **MySQL Workbench**
- Run the file: `db/nioms_restaurant.sql`
- This creates the `nioms_restaurant` database with all food items and tables.

### 2. Configure DB Credentials
- Open `backend/db_helper.py`
- Update `host`, `user`, `password` if different from defaults (`root`/`root`).

### 3. Install Python Dependencies
```bash
pip install -r backend/requirements.txt
```

### 4. Start the FastAPI Server
```bash
cd backend
uvicorn main:app --reload
```

### 5. Expose with ngrok (for Dialogflow webhook)
```bash
ngrok http 8000
```
- Copy the `https://...ngrok.io` URL
- Paste it into **Dialogflow → Fulfillment → Webhook URL**

> **Note:** ngrok sessions expire. Restart if you see "session expired".

### 6. Connect Dialogflow Agent
- Replace `YOUR_AGENT_ID_HERE` in `frontend/home.html` with your Dialogflow agent's embedded demo URL.

---

## Menu (Prices in BDT)

| Item            | Price  |
|-----------------|--------|
| Chicken Biryani | ৳150  |
| Murug Polaw     | ৳120  |
| Beef Biryani    | ৳220  |
| Mutton Biryani  | ৳200  |
| Kacchi          | ৳299  |
| Afgani Polaw    | ৳350  |
| Rice            | ৳20   |
| Beef            | ৳150  |
| Mutton Curry    | ৳160  |
| Ilish Fish      | ৳200  |
| Chingri Curry   | ৳160  |

---

## Contact
📧 niomraiyan@gmail.com
📍 Sylhet, Bangladesh
