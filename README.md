# Memoteca <a name="readme-top"></a>
![Static Badge](https://img.shields.io/badge/status-completed-green?style=for-the-badge)

## Introduction
**Memoteca** is an interface for collecting memories and thoughts, allowing users to store and organize their memories intuitively. The application was developed with HTML, CSS, and JavaScript, providing an interactive and visually appealing experience.

## Live Application
[Shopping list Demonstration](https://memoteca-rust.vercel.app)

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Technologies](#technologies)
- [Contributors](#contributors)

## Installation

### Prerequisites
- Web browser
- Node.js installed (to run the JSON Server)

### Steps to run
1. Clone the repository:
```bash
git clone https://github.com/victorhubarb/memoteca.git
cd memoteca
```
2. Install the dependencies:
```bash
npm install
```
3. Start the JSON Server to load the initial data from the `db.json` file in the **Backend** folder:
```bash
npx json-server --watch Backend/db.json
```
4. Then, open the `index.html` file in the browser to access the application.

## Usage
**Memoteca** allows users to create, view, and organize their memories and thoughts. With a user-friendly interface, it is possible to record different types of memories, categorizing them as needed.

## Features
- **Create Memories**: Easily add new memories.
- **Edit Memories**: Update the content of existing memories.
- **Favorite Memories**: Mark memories as favorites for easy access.
- **Delete Memories**: Remove memories from the list when needed.
- **Responsive Design**: Compatible with a variety of devices and screen sizes.

## Technologies
- **HTML5**
- **CSS3**
- **JavaScript**

## Contributors
- [Victor Barbosa](https://github.com/victorhubarb)
<p align="right">(<a href="#readme-top">back to top</a>)</p>
