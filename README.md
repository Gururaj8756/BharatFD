
---

# **FAQ API - Backend Developer Intern Project**  

## **Overview**  
This project is a Django REST Framework (DRF) API for managing FAQs (Frequently Asked Questions). It includes:  

✅ A **REST API** for fetching and submitting FAQs.  
✅ **Django Admin Panel** for managing FAQs.  
✅ **Multilingual Support** (Automatic translation).  
✅ **Redis Caching** for optimized performance.  

---

## **Tech Stack**  
- **Backend:** Django, Django REST Framework  
- **Database:** PostgreSQL / SQLite  
- **Cache:** Redis  
- **Translation:** Google Translate API  

---

## **Features**  
- **Retrieve FAQs via API** (with multilingual support).  
- **Users can submit questions via API**.  
- **Admin can answer FAQs from Django Admin Panel**.  
- **Automatic translation** of questions into multiple languages (Hindi, Bengali, etc.).  
- **Redis integration** for caching translations.  

---

## **Installation**  

### **1️⃣ Clone the Repository**  
```bash
git clone https://github.com/your-repository/faq_project.git
cd faq_project
```

### **2️⃣ Create & Activate Virtual Environment**  
```bash
python3 -m venv venv  
source venv/bin/activate  # On Mac/Linux  
venv\Scripts\activate     # On Windows  
```

### **3️⃣ Install Dependencies**  
```bash
pip install -r requirements.txt
```

### **4️⃣ Apply Migrations**  
```bash
python manage.py migrate
```

### **5️⃣ Create Superuser (For Admin Access)**  
```bash
python manage.py createsuperuser
```

### **6️⃣ Run the Server**  
```bash
python manage.py runserver
```
Now, visit:  
- **Django Admin Panel**: [`http://127.0.0.1:8000/admin/`](http://127.0.0.1:8000/admin/)  
- **FAQ API**: [`http://127.0.0.1:8000/api/faqs/`](http://127.0.0.1:8000/api/faqs/)  

---

## **API Endpoints**  

| Method | Endpoint             | Description                          |
|--------|----------------------|--------------------------------------|
| `GET`  | `/api/faqs/`         | Retrieve all answered FAQs          |
| `GET`  | `/api/faqs/?lang=hi` | Retrieve FAQs in Hindi              |
| `POST` | `/api/faqs/`         | Submit a new question               |

---

## **Using the API**  

### **📌 Submit a Question (POST Request)**  
- **Endpoint:** `http://127.0.0.1:8000/api/faqs/`  
- **Headers:** `Content-Type: application/json`  
- **Body (JSON format):**  
```json
{
  "question": "What is Django?"
}
```
- **Response:**  
```json
{
  "message": "Your question has been submitted"
}
```

### **📌 Fetch Answered FAQs (GET Request)**  
```bash
curl http://127.0.0.1:8000/api/faqs/
```
- **Response (if questions are answered):**  
```json
[
  {
    "question": "What is Django?",
    "answer": "Django is a web framework."
  }
]
```

### **📌 Fetch FAQs in Hindi (`lang=hi` parameter)**  
```bash
curl http://127.0.0.1:8000/api/faqs/?lang=hi
```

---

## **Redis Setup**  
Ensure Redis is running before starting the project.  

- **Install Redis:**  
  ```bash
  sudo apt install redis-server  # Linux  
  brew install redis             # macOS  
  ```
- **Start Redis:**  
  ```bash
  redis-server
  ```

---

## **Admin Panel Usage**  
1. Open **Django Admin Panel**: [`http://127.0.0.1:8000/admin/`](http://127.0.0.1:8000/admin/)  
2. Log in with your **superuser** credentials.  
3. Navigate to **FAQs** and find submitted questions.  
4. Add an answer and **save**.  
5. The API will now return this answered question.  

---

## **This project demonstrates:**  
✅ **API Development** with Django & DRF  
✅ **Multilingual FAQs** with Google Translate  
✅ **Efficient Caching** using Redis  
✅ **Admin Panel** for managing FAQs  

---
