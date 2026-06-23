# Cape Town Food Fest Ticket Landing Page

An interactive Vue.js landing page for the **Cape Town Food Fest 🎉** showcasing ticket tiers (Bronze, Silver, Gold) with prices, benefits, and engagement features.
This project simulates a modern event promotion site and lays the foundation for a future ticketing system.

___

## Features
- Ticket tiers displayed as reusable Vue components.
- Each card shows **name, price, and benefits**.
- **Featured tier** (Silver) styled differently to stand out.
- **Notify Me** call-to-action button.
- Sorting and filtering controls:
  - Sort by price
  - Show Featured Only
  - Reset
- **Dark/Light mode toggle** for modern UI feel.
- Responsive layout for desktop and mobile.
- All styling handled inside Vue companents ('<style scoped>'), no external CSS file required.

___

## Project Structure

food-fest-ticket-landing-page/
|---public/
|---src/
    |---components/
    |   |___TicketCard.vue
    |--data/
    |  |___tickets.js
    |--App.vue
    |--main.js
|---package.json
|---vite.config.js
|---README.md

---
## Screen shot 

   ![Cape Town Food Fest Landing Page](./public/Screenshot%202026-06-23%20143135.png)


### Installation & Run Instructions

 **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/food-fest-ticket-landing-page.git
   cd food-fest-ticket-landing-page
   npm install
   npm run dev
   http://localhost:5173








