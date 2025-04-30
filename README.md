# 📱 React Phone Catalog

A responsive and feature-rich React application for browsing and managing a product catalog of phones, tablets, and accessories.

---

## 📦 App Structure

The application includes the following core components:

- **`Header`**: Contains the logo, navigation menu, search bar, favorites, and shopping cart icons.
- **`Footer`**: Includes a link to the GitHub repository and a "Back to top" button.
- **`NotFoundPage`**: Displays a `Page not found` message for invalid routes, with a link to return to the homepage.
- **`Breadcrumbs`**: Shows the navigation trail with:
  - A link to the Home page;
  - A category page link (`Phones`, `Tablets`, or `Accessories`);
  - The current product name.
  - Includes smooth hover transitions for links.

---

## 🏠 Home Page (`/`)

The home page contains the following sections:

### 🔄 `PicturesSlider`

- Displays personalized promotional images.
- Automatically changes images every 5 seconds.
- Loops back to the first image after the last.
- Includes navigation dots for selecting specific images.

### 🔥 `Hot Prices` Section

- Uses the `ProductsSlider` component.
- Displays discounted products, sorted by the largest absolute discount.
- Includes `<` and `>` buttons for horizontal scrolling.

### 🛍️ Shop by Category

- Links to `/phones`, `/tablets`, and `/accessories`.

### 🆕 `Brand New` Section

- A `ProductsSlider` showing the newest products based on the `year` field.

---

## 📄 Category Pages

Available at:

- `/phones`
- `/tablets`
- `/accessories`

Each category page includes:

- A `<h1>` heading: `Phones/Tablets/Accessories page`
- A `ProductsList` displaying all available items.
- A `Loader` shown while fetching data.
- Error handling with a reload button if data fetching fails.
- A message when no products are available.
- A sorting `<select>` dropdown:
  - `Newest` (by age)
  - `Alphabetically` (by title)
  - `Cheapest` (by price)
- Sorting is preserved in the URL via `?sort=value`.
- Pagination with page size options (`4`, `8`, `16`, `All`) and URL synchronization (`?page=2&perPage=8`).
- `Search` input in the header with:
  - Debounced typing.
  - Query value saved in the URL (`?query=value`).
  - Result filtering with fallback message when nothing matches.

---

## 📦 Product Details Page (`/product/:productId`)

- Accessed by clicking on a product image or title.
- Displays a `Loader` while fetching product data.
- Shows detailed product information:
  - Image gallery with selectable thumbnails.
  - Available colors and capacities as radio inputs.
  - Product description (`About` section).
  - Selected `Tech specs`.
- Includes a `Back` button (mimics browser back behavior).
- `You may also like` section shows a few random products via `getSuggestedProducts`.
- Handles product-not-found errors with a dedicated message.

---

## 🛒 Shopping Cart Page (`/cart`)

- Implemented using React Context (or Redux).
- Each `CartItem` stores product data and quantity.
- Features:
  - Add to cart from any `ProductCard`.
  - Prevent adding duplicates (shows `Added to cart`).
  - Remove items with an `x` button.
  - Adjust quantity with `+`/`-` buttons (min quantity: 1).
  - Total price and quantity calculated automatically.
  - Cart count displayed in the header icon.
  - Data is persisted to `localStorage`.
  - `Checkout` button opens a modal:
    - Confirms whether to clear the cart.
    - Clears or keeps items based on user choice.

---

## ❤️ Favorites Page (`/favorites`)

- Implemented using React Context (or Redux).
- Adds/removes products from favorites via heart icon on `ProductCard`.
- Highlights heart icon if already added.
- Displays favorite count in the header icon.
- Favorites list persists in `localStorage`.

---

## 🎨 UI Features

- Responsive layout with smooth hover transitions.
- Product skeletons shown during loading states.
- Light and dark themes (theme switching supported).

---

## 🎨 Design References

- [🔗 Light Theme – Figma](<https://www.figma.com/file/T5ttF21UnT6RRmCQQaZc6L/Phone-catalog-(V2)-Original>)
- [🌙 Dark Theme – Figma](<https://www.figma.com/file/BUusqCIMAWALqfBahnyIiH/Phone-catalog-(V2)-Original-Dark>)

## 🌐 DEMO Link

- [GitHub Pages](https://hryniuktaras.github.io/react_phone-catalog/)

---

## 🛠️ Technologies Used

- **React**
- **Redux**
- **TypeScript**
- **HTML**
- **SCSS**

---

## ✅ Feature Summary

- Image sliders with autoplay and navigation
- Smart sorting and filtering with URL synchronization
- Full-featured product details view
- Cart and favorites functionality with persistence
- Error and empty-state handling
- Mobile-friendly and accessible layout
- Search with debounce and persistent queries
- Skeleton loading for better UX
- Theme switcher support
