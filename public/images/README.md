# Replaceable DOWNTOWN image slots

Replace an image at its local path to update the app without editing React
components. Keep the existing filename and format unless you also update
`src/image-assets.js`.

| # | UI slot | Local image path |
| --- | --- | --- |
| 1 | Home promotional hero | `home/promo-hero.png` |
| 2 | Food categories | `categories/pizza.svg`, `categories/burger.svg`, `categories/drinks.svg` |
| 3 | Restaurant card covers | `restaurants/covers/<restaurant-id>.jpg` |
| 4 | Restaurant logos | `restaurants/logos/<restaurant-id>.svg` |
| 5 | Food item photos | `food/<menu-item-id>.jpg` (the three unavailable source photos use `.svg`) |
| 6 | Special-offer banner | `offers/special-offer.jpg` |
| 7 | Featured restaurant images | `featured-restaurants/<restaurant-id>.jpg` |
| 8 | Popular-food section images | `popular-food/<menu-item-id>.jpg` (the three unavailable source photos use `.svg`) |
| 9 | City/location promotion artwork | `locations/<city>.jpg` (mapped in `src/image-assets.js`; source and license credits in `locations/ATTRIBUTION.md`) |
| 10 | Profile/avatar fallback | `placeholders/profile.svg` |
| 11 | Empty-state illustration | `placeholders/empty-state.svg` |
| 12 | Splash/opening background and logo | Background styling: `src/styles.css` (`.splash-screen-background`); supplied logo: `brand/downtown-emblem.png`; welcome hero: `opening/welcome-food.png` |

The location banner uses a locally stored, city-specific photo for each city
in the app's location list. Other city names use the local Nepal Himalaya photo
as a fallback. The splash background remains a CSS gradient because no separate splash
background image was supplied. Its logo and the welcome hero use only the
provided local assets and deliberately do not fall back to generic imagery.
Other image slots use `ContentImage` with local fallbacks; if both the selected
image and its fallback fail, the component renders an unavailable-image icon.

Restaurant IDs and menu item IDs match the records in `src/main.jsx`. The home
hero, offer banner, featured-restaurant images, and popular-food images are
independent local copies so each slot can be replaced without changing another.
