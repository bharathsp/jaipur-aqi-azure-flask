# 🌍 Jaipur Air Quality Index (AQI) Prediction with Azure Deployment

This project demonstrates how to **train and deploy a Machine Learning model** to predict the **Air Quality Index (AQI) of Jaipur** based on weather parameters.
The trained model is deployed on **Azure Web App** so it can be accessed from anywhere 🌐.

---

## 🎯 Goal

* Train a **RandomForestRegressor** model on Jaipur weather data.
* Predict AQI using:

  * 🌬️ Max Wind Speed
  * 🌬️ Avg Wind Speed
  * 🌡️ Max Temperature
  * 🌡️ Min Temperature
  * 🌡️ Avg Temperature
* Build a **Flask Web App** with an interactive UI.
* Deploy the app on **Azure Cloud** for public access.

---

## 🛠️ Tools & Technologies

* **Machine Learning:** RandomForestRegressor 🌳
* **Framework:** Flask 🐍
* **Frontend:** HTML, CSS 🎨
* **Cloud Platform:** Microsoft Azure ☁️
* **Serialization:** Pickle 📦

---

## 📂 Project Structure

```
├── app.py                       # Flask app (API + routes)
├── randomForestRegressor.pkl    # Serialized ML model
├── requirements.txt             # Dependencies
├── templates/                   # HTML templates
│   ├── home.html                # Input page
│   ├── result.html              # Result page
├── static/                      # Static files
│   ├── css/
│       └── style.css            # Styling for web pages
└── README.md                    # Project documentation
```

---

## ⚙️ Steps to Implement

### 1. 📊 Train the Model

* Train a **RandomForestRegressor** on Jaipur AQI dataset.
* Serialize the trained model:

  ```python
  import pickle
  pickle.dump(model, open("randomForestRegressor.pkl", "wb"))
  ```

---

### 2. 🖥️ Build Flask App

* `app.py`:

  * Load the pickle model.
  * Create **API endpoints**:

    * `/` → Home page (form input).
    * `/predict` → Returns prediction based on user input.
   
<img width="1170" height="698" alt="image" src="https://github.com/user-attachments/assets/766d1fea-2bc6-4895-a4bb-37decfaa19ae" />
 
* Frontend:

  * HTML templates stored in `templates/`.
  * Styling in `static/css/style.css`.

---

### 3. 📦 Requirements

Dependencies are listed in `requirements.txt`. Example:

```
numpy>=1.9.2
scipy>=0.15.1
matplotlib>=1.4.3
pandas>=0.19
```

---

### 4. ☁️ Deploying on Azure

1. Go to 👉 [portal.azure.com](https://portal.azure.com)
2. **Create Resource** → Select **Web App**.
   
  <img width="296" height="128" alt="image" src="https://github.com/user-attachments/assets/a04f5ec4-aac0-4523-b956-fc02f453495e" />
<br><br>
<img width="644" height="385" alt="image" src="https://github.com/user-attachments/assets/49cbd6a5-b777-4b43-a459-83ece6dcc0d2" />
<br><br>
<img width="446" height="210" alt="image" src="https://github.com/user-attachments/assets/83ec4ae8-f16e-47c3-8943-5a354597e725" />

3. Configure details:

   * **Subscription & Resource Group** → Create new resource group.
   * **Instance Name** → `JaipurAQI`
   * **Runtime Stack** → `Python 3.7`
   * **Region** → Central US
   * **App Service Plan** → Free (F1)

     <img width="368" height="355" alt="image" src="https://github.com/user-attachments/assets/08190274-ff3b-451f-b53d-dc0ca2a4f378" />

4. Click **Review + Create** ✅

<img width="368" height="459" alt="image" src="https://github.com/user-attachments/assets/04003c51-0707-4627-8f9a-11da349621ce" />

---

### 5. 🔗 Linking GitHub Repo

1. Once deployed, go to **Resource → Deployment Center**.

 <img width="428" height="110" alt="image" src="https://github.com/user-attachments/assets/d9a5dc47-ce7b-4018-a40a-bd65bc603f7c" />

2. Select:

   * **Source Control** → GitHub
   * **Build Provider** → App Service build service
   * **Configure** → Choose your **Organization, Repository, Branch**
3. Click **Finish** → Deployment starts automatically.

---

### 6. 📜 Deployment Logs

* Azure installs dependencies from `requirements.txt`.
* Logs show the build & deployment process.
* After success → Check **Overview Tab** for **App URL**.

---

### 7. 🌍 Access Your Web App

* Open your **Azure App URL** (e.g., `https://jaipuraqi.azurewebsites.net/`).
* Enter:

  * Max Wind Speed
  * Avg Wind Speed
  * Max Temperature
  * Min Temperature
  * Avg Temperature
* Click **Predict** → Get AQI prediction 🎉.

---

## 🧪 Testing the App

* Homepage → Input form for AQI prediction.
* Result page → Displays predicted AQI value.

---

## 🚀 Future Enhancements

* Use live weather data APIs for real-time AQI prediction.
* Add interactive charts for predictions.
* Enable CI/CD pipeline for automatic deployment.

---

### 💡 Quick Start

1. Clone repo → `git clone <repo_url>`
2. Install requirements → `pip install -r requirements.txt`
3. Run locally →

   ```bash
   python app.py
   ```

   Access at → [http://127.0.0.1:5000](http://127.0.0.1:5000)
4. Deploy on Azure (follow steps above).

🌬️🌡️ Jaipur AQI Prediction made simple with **ML + Flask + Azure Cloud** ☁️
