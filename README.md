# **Bidai - Agri-Commerce App**

## Overview

**Bidai** is an Android-based Agri-Commerce application designed for vendors in the agriculture sector. Vendors can add their products and view their product listings through a dynamic and interactive dashboard. The app allows vendors to upload product details such as name, price, category, and image URL, all within a simple and intuitive user interface.

This README provides a detailed explanation of the app's structure, working logic, and features.

---

## **Table of Contents**
1. [App Architecture](#app-architecture)
2. [Features](#features)
3. [App Structure](#app-structure)
4. [Working Logic](#working-logic)
5. [Dependencies](#dependencies)
6. [Setup and Installation](#setup-and-installation)
7. [ScreenShots](#screenshots)

---
## **App Architecture**

The app currently follows a Model-View-Controller (MVC)-like architecture:

Model: This layer includes the data structures (Product class) and Room Database components (entities, DAO) to manage local data storage.

View: XML layout files and UI elements (e.g., GridView, TextView, Button) that display information and receive user input.

Controller (Activity): Java-based Activities act as controllers, handling both the UI logic and interactions with the model layer.

## **Features**

- **Vendor Login**: Vendors can log in to the app with a simple authentication system.
- **Dashboard**: The main screen shows the total number of products added and their details (image, name, price, category).
- **Add New Product**: Vendors can add new products with relevant details (name, price, image URL, category, status).
- **Expandable Product List**: Each product is displayed in a card, which expands to show additional details such as category and product status.
- **Image Loading**: Product images are loaded dynamically from a URL using **Glide**.
- **Local Database**: Product data is stored locally in the device using static arrays and lists.

---

## **App Structure**

### **Main Components:**

1. **Activities**:
   - `Login` : The entry point for the app. The user enters their mobile number.
   - `Dashbaord`:  It displays the welcome message and product summary.
   - `AddProductActivity`: The screen where vendors can add a new product, including name, price, category, and image.
   
3. **Fragments**:
   - `ProductList`: Displays the list of products using a `GridView` in the dashboard.

4. **Adapters**:
   - `ProductAdapter`: Binds product data to the `GridView` in the `ProductListt`.

5. **Database**:
   -I have not used any backend database, the data is stored statically in a List.

6. **Models**:
   - `Product`: A Java class that represents a product with fields like name, price, image URL, category, and status.

---

## **Working Logic**

### **1. User Authentication and Dashboard**
- On app launch, we go to the login page where the user is required to enter their mobile number and can login.
- On clicking he button, **Dashboard** is displayed, showing the vendor's **welcome message** and a summary of their products.
  
### **2. Product Management**
- **Product Addition**:
  - Vendors can add products via the **AddProductActivity**.
  - Fields like product name, price, category, and image URL are captured.
  - The data is stored in a static list.
  - Once the product is added, the **ProductListFragment** updates the UI by accessing the static list.

### **3. Displaying Products in GridView**
- The products are displayed using a **GridView**.
  - A **ProductAdapter** binds the data to the views in the grid. It retrieves product information from the static list and displays it in each grid item.
  - Each product card contains:
    - Product Image: Loaded from the URL using **Glide**.
    - Product Name, Price, Category: Displayed as text in the grid items.
    - An expandable section that shows extra product details when the user clicks the expand button.

### **4. Image Loading**
- **Glide** is used to load product images from URLs. The `Glide.with(context).load(product.getImageURL()).into(holder.img);` code fetches the image and displays it in the `ImageView` inside the product card.

---

## **Dependencies**

This app depends on the following libraries:
- **Glide** for loading images:
  - `com.github.bumptech.glide:glide:4.12.0`
  
Add the dependencies to your `build.gradle` file as shown in the previous code.

---

## **Setup and Installation**
The .apk file has been provided, you can install it on any android device.

### **To Run the App Locally:**
You can run the app locally without needing to worry about anything.

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/bidai

## **ScreenShots**
![Screenshot_20250512_121644](https://github.com/user-attachments/assets/902262f8-6bb0-4e02-8243-c72015dd12e2)
![Screenshot_20250512_121706](https://github.com/user-attachments/assets/3188aa07-453d-4b50-90b7-5b37660966dd)
![Screenshot_20250512_121736](https://github.com/user-attachments/assets/442c672f-8a2c-42a6-a0de-2ddc0c4fd1c1)
![Screenshot_20250512_121745](https://github.com/user-attachments/assets/e3efa1f7-7036-4d70-bb4c-2775cd12a463)
![Screenshot_20250512_121827](https://github.com/user-attachments/assets/f62fbbf8-498a-442d-83e7-6bebf41e799c)







