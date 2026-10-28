# Memoteca

A notebook for short thoughts and quotes, built with vanilla JavaScript. You can add, edit, delete and favorite entries, and search them by text or author. The data lives in a REST API served by json-server, and Axios makes the requests.

## What's inside

- **Full CRUD over HTTP.** `js/api.js` is the only file that talks to the server: `GET`, `POST`, `PUT`, `PATCH` (favorite toggle) and `DELETE` on `/pensamentos`, all through Axios with `async/await`.
- **Separated layers.** `api.js` never touches the DOM, `ui.js` renders and fills the form, and `main.js` wires the two together with event listeners.
- **Validation before saving.** The content needs at least 10 characters and the author name 3 to 15 letters, both checked with regular expressions. Duplicates (same text and author) are caught with a `Set` of keys, and future dates are checked too.
- **Search.** Filters entries by content or author as you type.
- **Dates.** Stored as ISO strings in the API and converted to `Date` objects for display.
- **ES modules.** The scripts are loaded as modules, and Axios comes from a CDN.

The interface is in Portuguese.

## Run it locally

Needs Node.js (for the API) and any static file server (ES modules do not load from `file://`).

```bash
git clone https://github.com/victorhubarb/memoteca.git
cd memoteca

# terminal 1: the API on http://localhost:3000/pensamentos
cd backend
npx json-server --watch db.json --port 3000

# terminal 2: the page, then open http://localhost:8080
cd ..
npx http-server -p 8080
```

## Project structure

```
index.html
js/        api.js, ui.js, main.js
css/       styles.css
assets/    Icons and images
backend/   db.json (seed data) and package.json
```

## Known gaps

- The API address is hardcoded as `http://localhost:3000`, which is why there is no live demo link: a deployed page would have no server to talk to.
- `backend/package.json` does not list `json-server` as a dependency, so `npm start` only works if it is installed globally. The `npx` command above avoids that.
- The error handlers in `api.js` use `catch { ... throw error }` without naming the error, so a failed request raises a `ReferenceError` instead of rethrowing the original one.
- The content regex accepts only letters and spaces, so it would reject some of the quotes in the seed data. When the date is in the future the form shows an alert but still saves, because the handler does not return.
- The duplicate check is built once, when the page loads.
- The layout has no media queries.

---

Victor Hugo Barbosa · [GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
