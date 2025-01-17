# hackathone 2025 day2
# 1. Project Overview
Project Name:
HKM Mart.
Objective:
To facilitate  our customers  by creating an online store to sell products with an easy checkout process, tracking shipments, and handling payments securely.
Target Audience:
My eCommerce platform is for youngsters including casual ware, party ware and professional outfits to enhance customers’ charming personality. We also deal in kitchen and dinning to boost customers standard and  priorities.


# 2. Technologies Used
Frontend:
Next.js: React-based framework for building the frontend. It helps with Server-Side Rendering (SSR), Static Site Generation (SSG), and API routes.
oFeatures:
Component-based UI
Fast rendering
Dynamic routes for product pages and categories
Backend:
Sanity CMS: Headless Content Management System to handle content, product data, user data, and categories.
oFeatures:
Real-time content updates
Customizable schemas for product, user, order, etc.
API access to fetch product data
Third-party APIs:
Shipment & Tracking: Integrating third-party APIs like ShipEngine for shipment tracking and management.
oFeatures:
Real-time shipment status
Estimated delivery times
Shipping label generation
Payment Gateway:
Stripe : Payment solutions for processing payments securely.
oFeatures:
Credit/debit card processing
One-click payments
Multi-currency support
Other Technologies:
CSS-in-JS: Styled-components or Tailwind CSS for styling
Node.js: For handling API routes on the backend
MongoDB or PostgreSQL: For storing user, order, and product data (if applicable).



# 3. Architecture and Workflow
High-Level Architecture:

Frontend: Next.js (React)

oPages for Product Listing, Cart, Checkout, Order Confirmation
oClient-side interaction with APIs for products, cart management, and payment processing
oProduct, user, and order data fetched from Sanity CMS

Backend: Sanity CMS

oProvides product information (title, price, description, image, etc.)
oStores order data (user info, order details, shipping address, etc.)
oCustom schemas for product and order management

Third-party Integration:

oTracking: API calls to external services for tracking shipments.
oPayment Gateway: API integration with Stripe/PayPal for handling transactions securely.
Data Flow:
Product Data: Fetched from Sanity’s API, displayed in product pages.
Cart Management: Managed on the frontend (using React state, localStorage, or a backend API).
Order Creation: Upon checkout, the order data is sent to the backend (Sanity), and payment is processed via a payment API (Stripe/PayPal).
Shipping: Once the order is confirmed, shipment details are fetched from a third-party API, and shipment tracking information is updated for the customer.

# 4. Features and Functionalities
User Interface:
Product Pages: Display products with options like images, prices, descriptions, and availability.
Cart: Ability for users to add/remove products, view the cart, and proceed to checkout.
Checkout: Collect user information, handle shipping details, and integrate the payment gateway.
Order Confirmation: After successful payment, show a confirmation page with order details.
Admin Interface (optional):
Product Management: Admin can add/edit/remove products via the Sanity CMS.
Order Management: Admin can view customer orders and their statuses.
Shipment Tracking: Admin can track the shipment status of customer orders.
Payment Integration:
Stripe/PayPal: Integrate a payment gateway to securely handle transactions.
oFeatures:
Secure checkout with SSL encryption
Support for various payment methods (credit/debit cards, PayPal, etc.)
Shipment Tracking:
Integrate with third-party APIs like ShipEngine or AfterShip for tracking shipment.
oFeatures:
Automatically update tracking information in the order history
Display shipment status (in transit, delivered, etc.)

# 5. Database Schema
User Schema:
user_id: String
name: String
email: String
shipping_address: Object (address, city, zip code)
orders: Array of order IDs
Product Schema (Sanity):
product_id: String
name: String
description: Text
price: Number
category: String
image_url: String
stock_quantity: Number
Order Schema (Sanity):
order_id: String
user_id: String (reference to User)
products: Array of product IDs and quantities
total_price: Number
payment_status: String (paid, pending, etc.)
shipping_status: String (shipped, delivered, etc.)

# 6. API Integration
Sanity API:
GET Products: Fetch products from Sanity CMS.
POST Order: Create a new order in Sanity when the user checks out.
Payment Gateway (Stripe/PayPal):

Stripe:

oPOST /create-checkout-session: Create a session for payment.
oHandle checkout.session.completed webhook to update the order status.

Third-Party Shipment API:

oShipEngine/AfterShip API:
GET /track: Track shipment status using the tracking number.
POST /shipment: Create a new shipment entry after order confirmation.

# 7. Technical Skills Required

Frontend:

oReact.js, Next.js (Server-Side Rendering, Static Site Generation)
oCSS frameworks (Tailwind CSS, Styled Components, or Material UI)

Backend:

oSanity CMS (Schema design, API calls)
oNode.js (for API routes and server-side logic)

Payment Gateway:

oStripe/PayPal integration (handling payment processing)

APIs:

oThird-party API integration for shipment tracking (e.g., ShipEngine, AfterShip)
oAPI integration for product and order data management

Version Control:

oGit (for version control, collaboration, and project management)

Hosting/Deployment:

oVercel/Netlify for Next.js deployment
oSanity Studio deployment

# 8. Challenges & Solutions
Possible Challenges:
Handling concurrent user sessions, especially during high traffic periods.
Ensuring secure payment processing and protecting customer data.
Integrating third-party APIs (shipment tracking and payments) without issues.
Solutions:
Use server-side rendering (SSR) with Next.js to optimize performance.
Use Stripe's webhook to securely process payments and update the database.
Integrate third-party APIs with proper error handling and retry logic.

# 9. Conclusion
HKM Mart will facilitate customers by providing an online store with easy checkout and payment process. To ensure easness of customers we use Next.Js for frontend to optimize performance.Sanity for backend to fetch products to display on product page for customers.ShipEngine for shipment to monitor the shipment status. These technologies providee user-experience  easy and tracking of shipment and secured payment modes.
In future to enhance the performance of website we will work with innovative technologies to facilitate customers more effeciently.
