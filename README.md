Zentra — Modern E-Commerce Platform
A full-featured e-commerce web application built with React 19 and React Router v7, offering a clean shopping experience across electronics, clothing, and home & interior product categories.

Table of Contents

Overview
Features
Tech Stack
Project Structure
Getting Started
Available Scripts
Pages & Routes
Product Categories
State Management
Deployment


Overview
Zentra is a responsive e-commerce storefront that simulates a real-world marketplace. It includes a multi-step checkout flow, product browsing with filters, a shopping cart, and user authentication pages — all powered by static data and React state (no backend required to run).

Features

🏠 Home Page — Hero banner, category grid, deals tabs, featured products by category, supplier region flags, and service highlights
🛍️ Product Listing — Grid/list view toggle, sidebar filters (brand, price, condition, rating), and search query support via URL params
🔍 Product Detail — Full product info, color/size selector, quantity control, add-to-cart
🛒 Shopping Cart — Quantity adjustment, item removal, order summary with coupon field
💳 Multi-Step Checkout — Three-step flow: Shipping → Payment → Confirmation with form validation
🔐 Authentication — Login and Signup pages with form UI
🌐 Language Switcher — Header language/currency selector with country flags (UI only)
📱 Responsive Design — Mobile-friendly layout with hamburger navigation and adaptive grids
🧭 Mega Menu Navigation — Categorised dropdown with icons covering 6 top-level category groups


Tech Stack
TechnologyVersionPurposeReact^19.2.4UI frameworkReact Router DOM^7.13.1Client-side routingLucide React^0.577.0Icon libraryReact Scripts5.0.1Build tooling (Create React App)CSS Modules (plain)—Per-component styling

Project Structure
zentra/
└── ecommerce/
    ├── public/
    │   ├── index.html
    │   ├── favicon.ico
    │   ├── manifest.json
    │   └── assets/
    │       ├── Image/
    │       │   ├── backgrounds/     # Hero & banner images
    │       │   ├── interior/        # Home & interior product images
    │       │   └── tech/            # Electronics product images
    │       ├── Layout/
    │       │   ├── Brand/           # Logo assets
    │       │   ├── alibaba/         # Clothing & additional product images
    │       │   └── Misc/            # Miscellaneous UI assets
    │       └── Layout1/
    │           └── Image/flags/     # Country flag images for language switcher
    └── src/
        ├── App.js                   # Root component — routes, cart & user state
        ├── index.js                 # React entry point
        ├── styles/
        │   └── global.css           # Global base styles
        ├── components/
        │   ├── Header.jsx / .css    # Top navigation, search, cart icon, language switcher
        │   ├── Footer.jsx / .css    # Site footer
        │   └── ProductCard.jsx / .css  # Reusable product card (grid view)
        ├── data/
        │   ├── products.js          # Static product data (tech, cloth, interior, cart)
        │   └── categories.js        # Nav structure with mega menu definitions
        └── pages/
            ├── HomePage.jsx / .css          # Landing page
            ├── ProductListPage.jsx / .css   # Browse & filter products
            ├── ProductDetailPage.jsx / .css # Single product view
            ├── CartPage.jsx / .css          # Shopping cart
            ├── auth/
            │   ├── LoginPage.jsx            # Login form
            │   ├── SignupPage.jsx           # Registration form
            │   └── Auth.css                 # Shared auth styles
            └── checkout/
                ├── CheckoutPage.jsx         # Multi-step checkout
                └── CheckoutPage.css

Getting Started
Prerequisites

Node.js v16 or higher — Download here
npm v8 or higher (bundled with Node.js)

Installation
1. Clone or extract the project
bash# If cloning from a repo
git clone <your-repo-url>

# Or extract the zip and navigate into the folder
cd zentra/ecommerce
2. Install dependencies
bashnpm install
3. Start the development server
bashnpm start
4. Open in your browser
http://localhost:3000
The app hot-reloads automatically whenever you save a file.

Available Scripts
CommandDescriptionnpm startRuns the app in development mode at http://localhost:3000npm run buildBuilds the app for production into the build/ foldernpm testLaunches the test runner in interactive watch modenpm run ejectEjects from Create React App (irreversible — use with caution)

Pages & Routes
RouteComponentDescription/HomePageMain landing page with hero, categories, and featured products/productsProductListPageFull product listing with filters and view toggle/product/:idProductDetailPageIndividual product detail page/cartCartPageShopping cart with quantity controls and order summary/checkoutCheckoutPageThree-step checkout: Shipping → Payment → Confirmation/loginLoginPageUser login form/signupSignupPageUser registration form

Product Categories
The app ships with 24 static products across three categories:
CategoryProductsPrice RangeElectronicsiPhones, MacBooks, Apple Watch, Sony Camera, AirPods, Samsung Galaxy$249 – $2,498ClothingMen's & Women's casual wear, hoodies, coats, shirts$18.99 – $89.99Home & InteriorSofas, chairs, lamps, rugs, shelves, art canvas$45 – $549
Product data lives in src/data/products.js and can be extended freely.

State Management
State is managed entirely with React's built-in useState at the App.js level and passed down as props — no external state library is required.
StateLocationDescriptioncartItemsApp.jsArray of items in the cart (id, name, qty, color, size, price)userApp.jsLogged-in user object (null when logged out)searchQueryHeader.jsxCurrent search input valueselectedLangHeader.jsxActive language/currency selection
Cart persistence across page refreshes is not implemented by default — add localStorage to App.js to enable it.

Deployment
After running npm run build, deploy the generated build/ folder to any static hosting provider:
ProviderMethodNetlifyDrag & drop the build/ folder at app.netlify.comVercelRun npx vercel in the project rootGitHub PagesUse the gh-pages package: npm install gh-pages then configure homepage in package.jsonFirebase HostingRun firebase deploy after firebase init
