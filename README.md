
🧠 Description of the Models
----------------------------

### 1\. **Multiple Linear Regression (MLR)**

**Type:** Classical Machine Learning Model\
**Purpose:** Predicts a continuous numerical value (in this case, `waste_generated`) using multiple input features.

**How it works:**

-   MLR establishes a linear relationship between independent variables (features like category, quantity purchased, quantity consumed, and days until expiry) and the target (`waste_generated`).

-   It finds the best-fitting line (or hyperplane) that minimizes the difference between predicted and actual values.

**Formula:**

ini

CopyEdit

`waste_generated = b0 + b1*x1 + b2*x2 + ... + bn*xn`

Where:

-   `x1, x2, ..., xn` are input features

-   `b0` is the intercept

-   `b1...bn` are coefficients learned from data

**Strengths:**

-   Fast, interpretable, good for small-to-medium datasets

-   Works well when relationships are approximately linear

* * * * *

### 2\. **Neural Network (NN)**

**Type:** Deep Learning Model\
**Purpose:** Also predicts `waste_generated` using the same features but with more flexibility to learn non-linear patterns.

**How it works:**

-   A neural network consists of layers of interconnected "neurons" or nodes.

-   Each neuron takes weighted inputs, applies an activation function, and passes the output forward.

-   The model learns patterns through backpropagation by minimizing a loss function (e.g., MSE).

**Structure (example):**

-   Input Layer: Takes the features

-   Hidden Layers: Learn complex patterns

-   Output Layer: Gives the predicted value for waste generated

**Strengths:**

-   Capable of learning non-linear and complex relationships

-   Performs well with larger datasets or patterns hard to model linearly

* * * * *

⚙️ Working Process (for both models)
------------------------------------

1.  **Input Features:**

    -   `category` (encoded)

    -   `quantity_purchased`

    -   `quantity_consumed`

    -   `days_until_expiry`

2.  **Preprocessing:**

    -   Convert categorical data (like category) into numerical format (e.g., one-hot encoding)

    -   Scale/normalize numerical inputs if needed

3.  **Prediction:**

    -   Feed the processed inputs into each model

    -   The model returns a predicted value for `waste_generated`

4.  **Output:**

    -   You get two predictions:

        -   One from MLR

        -   One from Neural Network

5.  **Use Case:**

    -   These predictions can help in food inventory management, allowing teams to proactively reduce waste by understanding consumption patterns.

*******

🌐 Description of Django Integration for ML Models
--------------------------------------------------

### 🔍 What is Django Integration?

Django integration in this context refers to **embedding your trained machine learning models** (like the Neural Network and MLR) into a Django web application so they can be accessed and used via a web interface or an API.

* * * * *

⚙️ How It Works (Conceptually)
------------------------------

1.  ### 📦 **Model Loading**

    -   Your pre-trained models (saved using `.pkl` or `.h5`) are loaded into the Django server when the application starts.

    -   This enables the app to make predictions without retraining the models every time.

2.  ### 🌐 **Prediction API or View**

    -   Django provides a route (URL) where users or systems can send input data (like category, quantity purchased, etc.).

    -   This can be done through a web form or a REST API using HTTP POST requests.

3.  ### 🧹 **Preprocessing Inside Django**

    -   Before making predictions, Django preprocesses the incoming data to match the format the models expect:

        -   Encode categorical data

        -   Normalize or scale numerical inputs (if necessary)

4.  ### 🧠 **Model Prediction**

    -   The cleaned input data is passed to both the MLR and Neural Network models.

    -   Each model returns a predicted value for `waste_generated`.

5.  ### 📤 **Sending the Response**

    -   Django sends back the predictions (e.g., in JSON format).

    -   This can be displayed on a web page or consumed by another system (e.g., a mobile app, frontend dashboard).

* * * * *

💡 Why Use Django for This?
---------------------------

-   ✅ **Web Interface:** Allows easy user interaction with your models via browser.

-   ✅ **API Ready:** You can turn your model into a web service (API).

-   ✅ **Secure and Scalable:** Django includes built-in tools for user authentication, security, and scaling.

-   ✅ **Database Integration:** Easily log predictions, track usage, or save historical inputs.

-   ✅ **Extensibility:** Add forms, dashboards, and even admin panels to monitor usage or manage inputs.
