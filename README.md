# Foodies (Chef-App) 

A robust, multi-role mobile application built with **Flutter** and **Dart** designed to empower local food creators by bridging the gap between independent home chefs and customers seeking homemade meals. 

The app features tailored user interfaces and workflows depending on whether the authenticated user is a **Chef** or a **Customer**.

---

##  Key Features

###  Multi-Role Workflows
* **Chef Dashboard:** Manage restaurant profiles, perform full CRUD operations on menu dishes (add, edit, delete), and handle incoming customer orders (accept/reject).
* **Customer Interface:** Browse local kitchens, view menus, filter by categories, manage a dynamic shopping cart, place orders, and monitor statuses.

### Implemented Concepts & Architecture
* **Data Persistence:** Handled locally using an abstract `DatabaseHelper` class leveraging **SQLite** for robust relational serialization (`toMap()` and `fromMap()`).
* **State Management:** Handled dynamically via Flutter’s native state lifecycle (`setState`) to process real-time cart computations and menu modifications natively.
* **Simulated Real-Time Tracking:** Implemented an asynchronous periodic status updates timeline to simulate real-world order fulfillment lifecycles for the customer.
* **Rich UI/UX Components:** Features clean form validation, custom container stylings, `ListView.builder` for efficient memory management in infinite lists, modal bottom sheets for fluid data entry, and integrated **Lottie animations**.

---

##  Tech Stack

* **Frontend Framework:** Flutter (Dart)
* **Database Engine:** SQLite (sqflite package)
* **Media Handlers:** Image Picker (for profile & dish upload)
* **Animations:** Lottie
* **Environment:** Android Studio

---

##  System Architecture & Workflow

### Application Flow
1. **Authentication:** Determines if an account exists or routes to Role-Based Login.
2. **Chef Lifecycle:** Manage Menu -> View Order -> Update Fulfillment Status -> Customer Notification.
3. **Customer Lifecycle:** Browse Restaurants -> Build Cart -> Checkout -> Simulative Timeline Tracking.

### Core Schema Overview
The relational system maintains distinct structures tracking `User`, `Restaurant`, `Dish`, `Cart`, and `Order` objects safely bound together by relational entity keys managed by the SQLite helper class.

---

##  Future Enhancements
* [ ] Migrate local SQLite structure to **Firebase Cloud Firestore** for real-time remote syncing.
* [ ] Integrate payment gateways (Stripe/PayPal APIs).
* [ ] Implement Firebase Cloud Messaging (FCM) for native device push notifications.
* [ ] Expand platform support to iOS and Web targets.
