# Tamara Clothing – Website

A modern boutique website for **Tamara Clothing**, located on Outering Road, Fedha, Nairobi.

Built with **Next.js 15**, **Tailwind CSS**, **Supabase**, and deployed on **Vercel**.

---

## 🚀 Quick Start

### 1. Install dependencies
```bash
npm install
```

### 2. Set up environment variables
Copy the example file and fill in your values:
```bash
cp .env.local.example .env.local
```

Edit `.env.local`:
```env
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key-here
NEXT_PUBLIC_WHATSAPP_NUMBER=254700000000
NEXT_PUBLIC_BUSINESS_ADDRESS=Outering Road, Fedha, Nairobi
NEXT_PUBLIC_INSTAGRAM_HANDLE=tamaraclothing
```

### 3. Set up Supabase
1. Go to [supabase.com](https://supabase.com) and create a new project
2. In the SQL Editor, paste and run the contents of `supabase-schema.sql`
3. Copy your Project URL and anon key into `.env.local`

### 4. Run the dev server
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

---

## 📦 Deploying to Vercel

1. Push your project to a GitHub repo
2. Go to [vercel.com](https://vercel.com) and import the repo
3. Add your environment variables in the Vercel dashboard
4. Deploy — it's live! 🎉

---

## 🗂 Project Structure

```
tamara-clothing/
├── app/
│   ├── components/
│   │   ├── Navbar.tsx         # Navigation bar
│   │   ├── Footer.tsx         # Footer
│   │   └── ProductCard.tsx    # Reusable product card
│   ├── products/
│   │   ├── page.tsx           # Shop page (server)
│   │   └── ProductsClient.tsx # Category filtering (client)
│   ├── lookbook/
│   │   └── page.tsx           # Lookbook/feed page
│   ├── contact/
│   │   └── page.tsx           # Find Us page
│   ├── globals.css            # Global styles
│   ├── layout.tsx             # Root layout
│   └── page.tsx               # Homepage
├── lib/
│   └── supabase.ts            # Supabase client + types
├── supabase-schema.sql        # Database setup script
├── .env.local.example         # Environment variables template
└── tailwind.config.js         # Tailwind configuration
```

---

## 🛍 Adding Products

### Via Supabase Dashboard
1. Go to your Supabase project → **Table Editor**
2. Open the `products` table
3. Click **Insert Row**
4. Fill in: `name`, `description`, `price`, `category`, `image_url`, `is_available`, `is_featured`

### Uploading Product Images
1. In Supabase → **Storage** → `product-images` bucket
2. Upload your image
3. Click the image → **Get Public URL**
4. Paste that URL into the `image_url` field of your product

### Adding Lookbook Posts
Same as products — use the `posts` table in Supabase Table Editor.

---

## 🎨 Customisation

### Update your WhatsApp number
In `.env.local`, set:
```
NEXT_PUBLIC_WHATSAPP_NUMBER=254XXXXXXXXX
```
(Include country code, no `+` sign)

### Update Instagram handle
In `Footer.tsx` and `lookbook/page.tsx`, replace `tamaraclothing` with your actual handle.

### Update opening hours
In `app/contact/page.tsx`, find the hours array and update as needed.

### Colors
In `tailwind.config.js` and `globals.css`, the main brand colors are:
- Rose gold: `#c4735c`
- Cream: `#fdfaf6`
- Charcoal: `#2a2420`

---

## 📱 Pages

| Page | Route | Description |
|------|-------|-------------|
| Home | `/` | Hero, featured products, lookbook teaser, WhatsApp CTA |
| Shop | `/products` | All products with category filter |
| Lookbook | `/lookbook` | Editorial grid of posts & style content |
| Find Us | `/contact` | Location, hours, map, WhatsApp |

---

## 💡 Future Features to Add

- [ ] Admin panel (password-protected) for uploading products without touching Supabase
- [ ] M-Pesa payment integration (via Daraja API)
- [ ] Size guide page
- [ ] Product search
- [ ] WhatsApp order form that auto-fills product details

---

Made with ♥ in Nairobi for Tamara Clothing
