# 🎯 JavaScript Event Handling & Interactive Elements Assignment

Welcome to the **ultimate JavaScript playground**! 🎉 This assignment is where we turn boring web pages into dynamic, responsive, *alive* experiences. Get ready to master **event handling**, build **interactive components**, and validate forms like a pro! 💪

## 📁 Assignment Structure

```
📂 js-event-assignment/
├── index.html         # Your playground – where it all comes together
├── style.css          # Keep it cute (optional but encouraged)
└── script.js          # The JavaScript wizardry happens here
```

---

## 🧪 What to Build

Here’s what your interactive bundle of joy should include:

### 1. Event Handling 🎈  
- Button click ✅  
- Hover effects ✅  
- Keypress detection ✅  
- Bonus: A secret action for a *double-click* or *long press* 🤫

### 2. Interactive Elements 🎮  
- A button that changes text or color  
- An image gallery or slideshow  
- Tabs or accordion-style content  
- Bonus: Add some animation using JS or CSS ✨

### 3. Form Validation 📋✅  
- Required field checks  
- Email format validation  
- Password rules (e.g., min 8 characters)  
- Bonus: Real-time feedback while typing

---

## 🧙‍♂️ Pro Tips

- Keep your code clean and commented – your future self will thank you!
- Think about **user experience** – what makes your site more *fun* to use?
- Don’t be afraid to **Google and experiment** – that’s how real developers roll!

---

## 🎉 Now Go Make It Fun!

Remember – this isn't just code. It's your **first step toward creating magical user experiences**. So play around, break stuff (then fix it), and most of all, have FUN! 😄
 index.html
 <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>JS Event Playground</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>🎯 JavaScript Event Playground</h1>

  <!-- Event Handling Section -->
  <section>
    <h2>Event Handling 🎈</h2>
    <button id="clickMe">Click Me!</button>
    <div id="hoverBox">Hover over me!</div>
    <input type="text" id="keypressInput" placeholder="Type something..." />
    <p id="secretAction">🤫 Double-click me!</p>
  </section>

  <!-- Interactive Elements Section -->
  <section>
    <h2>Interactive Elements 🎮</h2>
    <button id="changeColorBtn">Change My Color!</button>
    
    <!-- Simple Image Gallery -->
    <div id="gallery">
      <img id="galleryImage" src="https://placekitten.com/300/200" alt="Cute Kitty" />
      <button id="nextImage">Next Image</button>
    </div>

    <!-- Tabs -->
    <div class="tabs">
      <button class="tab" data-target="tab1">Tab 1</button>
      <button class="tab" data-target="tab2">Tab 2</button>
      <div id="tab1" class="tab-content">Content for Tab 1</div>
      <div id="tab2" class="tab-content">Content for Tab 2</div>
    </div>
  </section>

  <!-- Form Validation Section -->
  <section>
    <h2>Form Validation 📋✅</h2>
    <form id="myForm">
      <label>
        Email:
        <input type="email" id="email" required />
      </label><br />
      <label>
        Password:
        <input type="password" id="password" required />
      </label><br />
      <button type="submit">Submit</button>
    </form>
    <p id="formFeedback"></p>
  </section>

  <script src="script.js"></script>
</body>
</html>
 style.css 
 
body {
  font-family: sans-serif;
  line-height: 1.6;
  margin: 20px;
}

button {
  margin: 10px 0;
  padding: 10px;
  font-size: 1rem;
  cursor: pointer;
}

#hoverBox {
  background-color: #eee;
  padding: 20px;
  width: 200px;
  margin: 10px 0;
}

#hoverBox:hover {
  background-color: lightblue;
  transition: 0.3s;
}

.tab-content {
  display: none;
  margin-top: 10px;
  padding: 10px;
  border: 1px solid #ccc;
}

.tab-content.active {
  display: block;
}
 script.js
// 1. Event Handling 🎈
document.getElementById("clickMe").addEventListener("click", () => {
  alert("You clicked the button!");
});

document.getElementById("hoverBox").addEventListener("mouseenter", () => {
  console.log("Hovering!");
});

document.getElementById("keypressInput").addEventListener("keydown", (e) => {
  console.log("Key pressed:", e.key);
});

document.getElementById("secretAction").addEventListener("dblclick", () => {
  alert("You found the secret action! 🎉");
});

// 2. Interactive Elements 🎮
const changeColorBtn = document.getElementById("changeColorBtn");
changeColorBtn.addEventListener("click", () => {
  changeColorBtn.style.backgroundColor = "#"+((1<<24)*Math.random()|0).toString(16);
});

let galleryIndex = 0;
const images = [
  "https://placekitten.com/300/200",
  "https://placekitten.com/301/200",
  "https://placekitten.com/302/200"
];

document.getElementById("nextImage").addEventListener("click", () => {
  galleryIndex = (galleryIndex + 1) % images.length;
  document.getElementById("galleryImage").src = images[galleryIndex];
});

// Tabs
const tabs = document.querySelectorAll(".tab");
const contents = document.querySelectorAll(".tab-content");

tabs.forEach(tab => {
  tab.addEventListener("click", () => {
    contents.forEach(c => c.classList.remove("active"));
    document.getElementById(tab.dataset.target).classList.add("active");
  });
});

// 3. Form Validation 📋✅
document.getElementById("myForm").addEventListener("submit", function(e) {
  e.preventDefault();
  const email = document.getElementById("email").value;
  const password = document.getElementById("password").value;
  const feedback = document.getElementById("formFeedback");

  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

  if (!emailRegex.test(email)) {
    feedback.textContent = "Please enter a valid email.";
  } else if (password.length < 8) {
    feedback.textContent = "Password must be at least 8 characters long.";
  } else {
    feedback.textContent = "Form submitted successfully!";
  }
});

 
Happy Coding! 💻✨  
