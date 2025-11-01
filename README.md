# 🔍 GitHub Pages Repos Finder

A simple, straightforward web application to **discover which of a GitHub user's repositories have GitHub Pages enabled**.

---

## ✨ Features

* **Quick Search:** Find all repositories with active GitHub Pages for any public user.
* **Direct Links:** Provides direct links to the live GitHub Pages site for each enabled repository.
* **User-Friendly Interface:** A clean, minimal design for a smooth search experience.

---

## 💻 How to Use

1.  **Enter a GitHub Username:** Type the desired GitHub username into the input field.
2.  **Click "Search":** Hit the **Search** button.
3.  **View Results:** The application will list all the user's repositories that have the `has_pages` flag set to true, along with a link to the live page (e.g., `username.github.io/repo-name`).

If a user has no GitHub Pages enabled repos, a message will indicate that.

---

## 🚀 Getting Started (Local Setup)

This application is a single HTML file with embedded CSS and JavaScript, making it incredibly easy to set up.

1.  **Clone the repository** (or copy the HTML content).
2.  Save the content as an HTML file (e.g., `index.html`).
3.  **Open the file in your web browser.** That's it!

### Dependencies

This project relies only on the **GitHub REST API** to fetch repository data. No other libraries or frameworks are required.
https://api.github.com/users/<username>/repos?per_page=100

GitHub limits responses to **100 repositories per page**, so if a user has more, the app fetches additional pages dynamically using the `page` parameter:

https://api.github.com/users/<username>/repos?per_page=100&page=2
https://api.github.com/users/<username>/repos?per_page=100&page=3

The app continues until all repositories are retrieved, ensuring that even users with hundreds of repositories are fully covered.

Each repo is checked for the field:

```json
"has_pages": true
If true, it means the repository has GitHub Pages enabled, and its site is available at:

https://<username>.github.io/<repo-name>/
```

## 🛠️ Built With

* **HTML5** - For the structure of the application.
* **CSS3** - For styling and layout.
* **Vanilla JavaScript** - For fetching data from the GitHub API and rendering the results.

---

## 👤 Author

* **Info X Max** - [https://github.com/InfoXMax/]

---

## 📄 License

This project is licensed under the MIT License