# Shopify Developer Assignment — Featured Products with Infinite Scroll

This project is built as part of a Shopify Developer assignment to demonstrate advanced handling of collection pages using Shopify Liquid and JavaScript.

---

## Objective

Implement a Shopify collection page that:

* Prioritizes featured products
* Supports infinite scroll
* Maintains compatibility with sorting and filtering
* Handles large-scale product collections efficiently

---

## Task Requirements

### Collection Setup

* Collection contains 100 products
* Exactly 15 products tagged as `featured`
* Featured products are placed at different positions in Shopify backend

---

### Page Behavior

* On initial load:

  * Display all 15 featured products first
  * Followed by 5 non-featured products (total 20 products)

* On infinite scroll:

  * Load next 20 non-featured products
  * Ensure featured products do not repeat

* Ordering:

  * Featured products always remain at the top
  * Non-featured products follow after featured ones

---

### Functional Requirements

* Infinite scroll loads 20 products per request
* No duplicate products during pagination
* Sorting works normally:

  * Best Selling
  * Price Low to High
  * Price High to Low
* Filtering works correctly
* When sorting or filtering is applied:

  * Default Shopify behavior overrides featured logic

---

## Edge Case Handling

| Scenario                                | Expected Behavior                             |
| --------------------------------------- | --------------------------------------------- |
| Featured products appear in later pages | Moved to top dynamically                      |
| No featured products                    | Normal infinite scroll behavior               |
| Filters applied                         | Featured logic disabled                       |
| Sorting applied                         | Featured logic disabled                       |
| Large collections                       | Optimized using Set and efficient DOM updates |

---

## Features Implemented

### Product Reordering Logic

* Detects products tagged with `featured`
* Maintains global product state using JavaScript
* Dynamically reorders:

  * Featured → Top
  * Normal → Bottom

---

### Infinite Scroll

* Implemented using IntersectionObserver
* Fetches next page asynchronously
* Uses Set to prevent duplicate product rendering

---

### UI Enhancements

* Featured badge displayed on product cards
* Custom loading animation
* Responsive grid layout
* Smooth scroll experience

---

## Screenshots

### Collection Page

![Collection UI](https://github-production-user-asset-6210df.s3.amazonaws.com/108511606/569404390-d7347d29-6f0a-4de2-bda5-e7e21d5e9810.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20260326%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20260326T000008Z&X-Amz-Expires=300&X-Amz-Signature=56cd0b296f0147b0a944e31ef32d86f22b9d0c6c397831fbcefa63e26db99d97&X-Amz-SignedHeaders=host)

### Infinite Scroll

![Infinite Scroll](https://private-user-images.githubusercontent.com/108511606/569409663-5747e088-8007-495a-8ba5-19e3ca7d1c20.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NzQ0ODM4MDMsIm5iZiI6MTc3NDQ4MzUwMywicGF0aCI6Ii8xMDg1MTE2MDYvNTY5NDA5NjYzLTU3NDdlMDg4LTgwMDctNDk1YS04YmE1LTE5ZTNjYTdkMWMyMC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwMzI2JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDMyNlQwMDA1MDNaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jNmVmZmZhMjVkNGZiODk5NWZmY2UwM2VlOWY2Y2U2OGE2MGQyNmI5ZjA2ZTIxNTY4ZjliNGU2ZjcyYjA5ZjMzJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9._Km0Fva_GU5-p-wpLyeYWPdGcnHx3BiSFyvW_2sC0yU)

---

## Tech Stack

* Shopify Liquid
* JavaScript (Vanilla JS)
* CSS
* Shopify CLI

---

## Project Structure

```
SHOPIFY STORE/
│
├── assets/
├── blocks/
├── config/
├── layout/
│   └── theme.liquid
├── locales/
├── sections/
│   └── main-collection-product-grid.liquid
├── snippets/
│   └── product-card.liquid
├── templates/
│   └── collection.json
```

---

## Live Demo

https://featured-assignment-demo.myshopify.com/collections/all-products

---

## Setup Instructions

```bash
npm install -g @shopify/cli
shopify auth login
shopify theme pull --store=featured-assignment-demo.myshopify.com
shopify theme dev --store=featured-assignment-demo.myshopify.com
shopify theme push --nodelete
```

---

## GitHub Setup

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/GuptaRishi0070/shopify-featured-collection.git
git push -u origin main --force
```

---

## Notes

* Shopify restricts deletion of core files like:

  * layout/theme.liquid
  * config/settings_schema.json
* CLI warnings can be ignored
* Infinite scroll works best on collection pages

---

## Author

Rishi Gupta
Shopify Developer

---

## Conclusion

This project demonstrates advanced Shopify development including dynamic product ordering, infinite scroll implementation, and scalable frontend architecture while preserving native Shopify functionality.
