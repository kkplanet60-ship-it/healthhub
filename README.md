# 🌿 HealthHub — Pakistan's Trusted Nutrition & Wellness Coach

A modern, single-page web application for a nutrition and wellness coaching business in Pakistan. Built with vanilla HTML, CSS, and JavaScript, powered by Supabase as the backend.

---

## ✨ Features

- **Hero Section** — Elegant landing with animated blob and call-to-action buttons
- **Services Section** — Displays available coaching and wellness packages
- **Products Shop** — Customers can browse and order nutrition products
- **Consultation Booking** — Users can book a session with preferred date/time
- **Contact Form** — Direct messaging to the business
- **Email Lead Capture** — Newsletter/waitlist sign-up
- **Admin Dashboard** — Password-protected panel to view bookings, orders, leads, contacts, and manage products

---

## 🛠 Tech Stack

| Layer      | Technology                          |
|------------|-------------------------------------|
| Frontend   | HTML5, CSS3, Vanilla JavaScript     |
| Fonts      | Google Fonts (Cormorant Garamond, Jost) |
| Backend    | [Supabase](https://supabase.com) (PostgreSQL + REST API) |
| Hosting    | Static hosting (e.g. GitHub Pages, Netlify, Vercel) |

---

## 🚀 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/healthhub.git
cd healthhub
```

### 2. Set Up Supabase

1. Go to [https://supabase.com](https://supabase.com) and create a free account
2. Create a new project
3. In your Supabase dashboard, go to **SQL Editor** and create the following tables:

```sql
-- Bookings table
create table bookings (
  id uuid default gen_random_uuid() primary key,
  name text,
  whatsapp text,
  email text,
  health_goal text,
  preferred_date text,
  preferred_time text,
  message text,
  created_at timestamp default now()
);

-- Orders table
create table orders (
  id uuid default gen_random_uuid() primary key,
  customer_name text,
  whatsapp text,
  email text,
  product_name text,
  price text,
  payment_method text,
  created_at timestamp default now()
);

-- Leads table
create table leads (
  id uuid default gen_random_uuid() primary key,
  email text unique,
  created_at timestamp default now()
);

-- Contacts table
create table contacts (
  id uuid default gen_random_uuid() primary key,
  name text,
  contact text,
  message text,
  created_at timestamp default now()
);

-- Products table
create table products (
  id uuid default gen_random_uuid() primary key,
  name text,
  price numeric,
  description text,
  category text,
  created_at timestamp default now()
);
```

### 3. Configure Your Supabase Keys

In `index.html`, find this section near the top and replace with your own project URL and anon key:

```javascript
const _supabase = window.supabase.createClient(
  'YOUR_SUPABASE_PROJECT_URL',
  'YOUR_SUPABASE_ANON_KEY'
);
```

You can find these in your Supabase project under **Settings → API**.

### 4. Open the Site

Since this is a static site, simply open `index.html` in your browser — or deploy it to any static host.

---

## 🔐 Admin Dashboard

The admin panel is accessible via a hidden button in the footer (or via direct trigger). It requires a password to log in. To change the admin password, search for `ADMIN_PASS` in `index.html` and update the value.

---

## 📁 Project Structure

```
healthhub/
├── index.html        # Main (and only) HTML file — contains all HTML, CSS, and JS
├── README.md         # Project documentation
├── .gitignore        # Files excluded from Git
└── LICENSE           # Project license
```

---

## 🌐 Deployment

This site works on any static hosting platform:

- **GitHub Pages** — Push to a `gh-pages` branch or enable Pages in repo settings
- **Netlify** — Drag and drop the folder, or connect your GitHub repo
- **Vercel** — Import repo and deploy instantly

---

## 📬 Contact

For questions or collaboration, reach out via the contact form on the site.

---

## 📄 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
