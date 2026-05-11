# Apna Market Frontend

Static HTML frontend for Apna Market e-commerce platform.

## Quick Start

### Local Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# The site will be available at http://localhost:3000
```

### Build

```bash
npm run build
```

## Deployment to Vercel

### Step 1: Push to GitHub

```bash
# Initialize git (if not already done)
git init
git add .
git commit -m "Initial frontend setup"

# Create a new repository on GitHub called 'apna-market-frontend'
# Then push:
git remote add origin https://github.com/YOUR_USERNAME/apna-market-frontend.git
git branch -M main
git push -u origin main
```

### Step 2: Deploy to Vercel

1. Go to [vercel.com](https://vercel.com)
2. Click "New Project"
3. Import your GitHub repository `apna-market-frontend`
4. Click "Deploy"

That's it! Your frontend will be deployed automatically.

### Step 3: Configure Backend URL (If Needed)

The frontend is configured to connect to the backend at:
```
http://13.62.153.215:5000/api
```

If you change the backend URL or port, update it in `app.js`:
```javascript
const API_URL = 'http://YOUR_BACKEND_URL:5000/api';
```

## Project Structure

```
├── app.js              # API configuration and common functions
├── styles.css          # Global styles
├── index.html          # Home page
├── login.html          # Login page
├── profile.html        # User profile
├── products.html       # Products listing
├── product.html        # Product details
├── cart.html           # Shopping cart
├── checkout.html       # Checkout page
├── orders.html         # Order history
├── order-confirmation.html  # Order confirmation
├── sell.html           # Seller dashboard
├── seller.html         # Seller profile
├── admin.html          # Admin panel
├── live.html           # Live sessions
├── cart.js             # Cart logic
├── vercel.json         # Vercel configuration
└── package.json        # Project metadata
```

## Features

- User authentication (login/register)
- Product browsing and search
- Shopping cart management
- Order placement
- Seller dashboard
- Admin panel
- Live shopping sessions
- User profile management

## Backend API

The frontend communicates with a Node.js/Express backend running on EC2.

**Backend Repository:** `social_ecom`
**Backend API Base URL:** `http://13.62.153.215:5000/api`

### Available Endpoints

- **Auth**
  - `POST /api/auth/register` - User registration
  - `POST /api/auth/login` - User login
  - `GET /api/auth/me` - Get current user
  - `PUT /api/auth/profile` - Update profile

- **Products**
  - `GET /api/products` - Get all products
  - `GET /api/products/:id` - Get product details
  - `POST /api/products` - Create product (sellers)

- **Orders**
  - `GET /api/orders` - Get user orders
  - `POST /api/orders` - Create order

- **Posts** (Social features)
  - `GET /api/posts` - Get posts feed
  - `POST /api/posts` - Create post

- **Live** (Live shopping)
  - `GET /api/live` - Get live sessions
  - `POST /api/live` - Start live session

## Environment Variables

The frontend uses the `API_URL` constant in `app.js` to connect to the backend. This is configured for the EC2 backend by default.

To change the API endpoint:
1. Edit `app.js`
2. Change the `API_URL` constant
3. Commit and push to GitHub
4. Vercel will auto-deploy

## Troubleshooting

### Users can't login/register

- Verify the backend is running on EC2
- Check that `API_URL` in `app.js` matches your backend address
- Ensure the EC2 instance allows HTTP traffic on port 5000
- Check browser console for CORS errors

### Pages not loading

- Make sure all HTML files are in the root directory
- Check `vercel.json` configuration
- Review Vercel deployment logs

## Support

For issues, check the backend repository or contact the development team.
