---

# 📅 BookMySlot – Mini Calendly Clone

Welcome to **BookMySlot**, a simple scheduling platform built as part of the **WizCommerce Fullstack Hiring Challenge**. The goal of this project was to create a real-world app where users can create events and allow others to book time slots — think of it like a lightweight version of Calendly.

---

## 🌐 Live Links

* **Frontend (Vercel)**: [https://bookmyslot.vercel.app](#)
* **Backend (Render)**: [https://bookmyslot-api.onrender.com](#)

---

## 🛠 Tech Stack

### Frontend

* React (Vite)
* TailwindCSS
* date-fns-tz (for time zone support)

### Backend

* Express.js
* PostgreSQL (via Prisma ORM)
* Deployed on Render

---

## 🚀 Features

Here’s what’s implemented:

### 1. Create Event

* Users can create an event by entering a title, description, and a list of time slots (ISO format).
* Max number of bookings per slot can be defined.

### 2. Public Event Listing

* Displays all public events with basic info (title, creator, number of slots).
* Clicking an event opens its details page.

### 3. Booking Interface

* Visitors can book a slot by providing their name and email.
* A slot becomes unavailable once it's full.
* Duplicate bookings for the same user and slot are prevented.

### 4. Time Zone Handling

* All slots are stored in UTC in the database.
* On the frontend, slots are converted to the user's local time using `date-fns-tz`.

### 5. My Bookings (Optional)

* Users can view their past bookings by entering their email (if implemented).

---

## 📚 API Endpoints

| Method | Endpoint                 | Description                                  |
| ------ | ------------------------ | -------------------------------------------- |
| `POST` | `/events`                | Create a new event                           |
| `GET`  | `/events`                | Get a list of all events                     |
| `GET`  | `/events/:id`            | Get event details and available slots        |
| `POST` | `/events/:id/bookings`   | Book a time slot                             |
| `GET`  | `/users/:email/bookings` | View bookings for a specific user (optional) |

---

## 🗂 Project Structure

```
.
├── client/            # Frontend code (Vite + React)
│   ├── pages/
│   ├── components/
│   └── utils/
├── server/            # Backend code (Express + Prisma)
│   ├── routes/
│   ├── controllers/
│   ├── prisma/
│   └── app.js
```

---

## ⚙️ Getting Started Locally

### 1. Clone the repo

```bash
git clone https://github.com/YOUR_USERNAME/bookmyslot.git
cd bookmyslot
```

### 2. Setup Backend

```bash
cd server
npm install
cp .env.example .env  # Fill in DB connection details
npx prisma migrate dev
npm run dev
```

### 3. Setup Frontend

```bash
cd client
npm install
npm run dev
```

---

## 📝 Notes & Assumptions

* Booking is based on email.
* Time slots are stored in UTC and converted to local time on the frontend.
* A user can’t book the same slot more than once.
* Minimal error handling is added for simplicity but can be extended.



Thanks for reviewing this project! Feel free to reach out if you'd like to know more about the implementation or decisions made during development.

--------------------------------------------------------------------------------------------------------------------------------------------------

### Make sure to create a `.env` file with following variables -

```
DATABASE_URL=
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=

NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
```
