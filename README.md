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

<img width="571" height="411" alt="arc" src="https://github.com/user-attachments/assets/4d35f9de-9046-43f0-81a9-8ec3cdc69097" />

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

<img width="1919" height="567" alt="image" src="https://github.com/user-attachments/assets/8030721f-1a06-4a3e-9eb2-67828a9eea89" />

---

### 5. 🔗 Linking GitHub Repo

1. Once deployed, go to **Resource → Deployment Center**.

<img width="829" height="360" alt="image" src="https://github.com/user-attachments/assets/d15dba8d-b42b-406b-8387-d26a57155f30" />

<img width="1800" height="735" alt="image" src="https://github.com/user-attachments/assets/72409ca8-9ad0-4497-a5d0-e26c196b15ec" />

2. Select:

   * **Source Control** → GitHub
     
     <img width="795" height="314" alt="image" src="https://github.com/user-attachments/assets/b983359a-6cf2-4e6b-a09b-be7c8edc23da" />

   * **Build Provider** → App Service build service
   * **Configure** → Choose your **Organization, Repository, Branch**
     
     <img width="792" height="638" alt="image" src="https://github.com/user-attachments/assets/99dda552-c2e3-46ff-bb4f-f3b67169519b" />

3. Click **Save** → Deployment starts automatically.

<img width="464" height="190" alt="image" src="https://github.com/user-attachments/assets/1086635e-2351-44b0-888c-db70fad81db7" />

*Check deployment logs on GitHub*
<img width="1880" height="451" alt="image" src="https://github.com/user-attachments/assets/9b30010a-a413-4f54-9d60-4ba65adb31e1" />

*Check deployment logs on Azure*
<img width="1288" height="530" alt="image" src="https://github.com/user-attachments/assets/3d967969-79ae-4576-998c-972883a153f7" />

<img width="761" height="550" alt="image" src="https://github.com/user-attachments/assets/efad602c-b930-4754-b368-a8a59e7c387d" />

*If deployment fails - Click on Sync*
<img width="920" height="345" alt="image" src="https://github.com/user-attachments/assets/9ab0b526-9088-4784-bfdf-a2a1a392a80d" />

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

<img width="353" height="465" alt="image" src="https://github.com/user-attachments/assets/207a7fc8-36e4-432d-851f-774dee79ceb0" />

---

## 🧪 Testing the App

* Homepage → Input form for AQI prediction.
* Result page → Displays predicted AQI value.

---

## 🚀 Future Enhancements

* Use live weather data APIs for real-time AQI prediction.
* Add interactive charts for predictions.
* Enable CI/CD pipeline for automatic deployment.
