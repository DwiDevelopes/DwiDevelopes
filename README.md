<img align="right" src="https://visitor-badge.laobi.icu/badge?page_id=DwiDevelopes">

<h1 align="center">
  <a href="https://git.io/typing-svg">
   <img src="Programmer.jpg">
    <img src="https://readme-typing-svg.herokuapp.com/?lines=Hello,+There!+👋;This+is+Dwi+Developes....;Nice+to+meet+you+😎;&center=true&size=30">
  </a>
  <h2 align="left">Hi 👋! My name is DwiDevelopes and I'm a Canva Profesional, from Indonesia</h2>

###

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=DwiDevelopes&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=dracula&locale=en&hide_border=false" height="150" alt="stats graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?username=DwiDevelopes&locale=en&hide_title=false&layout=compact&card_width=320&langs_count=5&theme=dracula&hide_border=false" height="150" alt="languages graph"  />
</div>

###

<img align="right" height="150" src="japanese-animation.gif"  />

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg" height="40" alt="bootstrap logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/unrealengine/unrealengine-original.svg" height="40" alt="unrealengine logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="40" alt="html5 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="40" alt="css3 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original-wordmark.svg" height="40" alt="tailwindcss logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/android/android-original.svg" height="40" alt="android logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/fastapi/fastapi-original.svg" height="40" alt="fastapi logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="40" alt="python logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg" height="40" alt="bash logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="40" alt="javascript logo"  />
</div>

###

<br clear="both">

<img src="github-user-contribution.svg" alt="Snake animation" />

###

###
<div align="center">
  <img height="150" src="neko.gif" style="border-radius:50px;" />
</div>

###

<div align="center">
  <a href="https://github.com/DwiDevelopes"><img src="https://img.shields.io/static/v1?message=Github&logo=github&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="Github logo"  /></a>
  <a href="https://wa.me/+6289652969323"><img src="https://img.shields.io/static/v1?message=Whatsapp&logo=whatsapp&label=&color=FF0000&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="youtube logo"  /></a>
  <a href=""><img src="https://img.shields.io/static/v1?message=Discord&logo=discord&label=&color=1DA1F2&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="discord logo"  /></a>
   <a href="https://www.tiktok.com/@royhtml?is_from_webapp=1&sender_device=pc"><img src="https://img.shields.io/static/v1?message=Tiktok&logo=tiktok&label=&color=000&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="tiktok logo"  /></a>
<a href="https://t.me/BangRoy76"><img src="https://img.shields.io/static/v1?message=Telegram&logo=telegram&label=&color=&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="telegram logo"  /></a>
</div

###

<div align="center">
  <img src="https://visitor-badge.laobi.icu/badge?page_id=DwiDevelopes&"  />
</div>

###
### <img src="https://media.giphy.com/media/VgCDAzcKvsR6OM0uWg/giphy.gif" width="50"> AI Google Api Key Me...  

```javascript
const typingForm = document.querySelector(".typing-form");
const chatContainer = document.querySelector(".chat-list");
const suggestions = document.querySelectorAll(".suggestion");
const toggleThemeButton = document.querySelector("#theme-toggle-button");
const deleteChatButton = document.querySelector("#delete-chat-button");

// State variables
let userMessage = null;
let isResponseGenerating = false;

// API configuration
const API_KEY = "AIzaSyA21XveMjweBAaK0W8idmozNdaEGBZPKck"; // Your API key here
const API_URL = `https://generativelanguage.googleapis.com/v1/models/gemini-pro:generateContent?key=${API_KEY}`;

// Load theme and chat data from local storage on page load
const loadDataFromLocalstorage = () => {
  const savedChats = localStorage.getItem("saved-chats");
  const isLightMode = (localStorage.getItem("themeColor") === "light_mode");

  // Apply the stored theme
  document.body.classList.toggle("light_mode", isLightMode);
  toggleThemeButton.innerText = isLightMode ? "dark_mode" : "light_mode";

  // Restore saved chats or clear the chat container
  chatContainer.innerHTML = savedChats || '';
  document.body.classList.toggle("hide-header", savedChats);

  chatContainer.scrollTo(0, chatContainer.scrollHeight); // Scroll to the bottom
}

// Create a new message element and return it
const createMessageElement = (content, ...classes) => {
  const div = document.createElement("div");
  div.classList.add("message", ...classes);
  div.innerHTML = content;
  return div;
}

// Show typing effect by displaying words one by one
const showTypingEffect = (text, textElement, incomingMessageDiv) => {
  const words = text.split(' ');
  let currentWordIndex = 0;

  const typingInterval = setInterval(() => {
    // Append each word to the text element with a space
    textElement.innerText += (currentWordIndex === 0 ? '' : ' ') + words[currentWordIndex++];
    incomingMessageDiv.querySelector(".icon").classList.add("hide");

    // If all words are displayed
    if (currentWordIndex === words.length) {
      clearInterval(typingInterval);
      isResponseGenerating = false;
      incomingMessageDiv.querySelector(".icon").classList.remove("hide");
      localStorage.setItem("saved-chats", chatContainer.innerHTML); // Save chats to local storage
    }
    chatContainer.scrollTo(0, chatContainer.scrollHeight); // Scroll to the bottom
  }, 75);
}

// Fetch response from the API based on user message
const generateAPIResponse = async (incomingMessageDiv) => {
  const textElement = incomingMessageDiv.querySelector(".text"); // Getting text element

  try {
    // Send a POST request to the API with the user's message
    const response = await fetch(API_URL, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({ 
        contents: [{ 
          role: "user", 
          parts: [{ text: userMessage }] 
        }] 
      }),
    });

    const data = await response.json();
    if (!response.ok) throw new Error(data.error.message);

    // Get the API response text and remove asterisks from it
    const apiResponse = data?.candidates[0].content.parts[0].text.replace(/\*\*(.*?)\*\*/g, '$1');
    showTypingEffect(apiResponse, textElement, incomingMessageDiv); // Show typing effect
  } catch (error) { // Handle error
    isResponseGenerating = false;
    textElement.innerText = error.message;
    textElement.parentElement.closest(".message").classList.add("error");
  } finally {
    incomingMessageDiv.classList.remove("loading");
  }
}

// Show a loading animation while waiting for the API response
const showLoadingAnimation = () => {
  const html = `<div class="message-content">
                  <img class="avatar" src="anim.webp" alt="Gemini avatar">
                  <p class="text"></p>
                  <div class="loading-indicator">
                    <div class="loading-bar"></div>
                    <div class="loading-bar"></div>
                    <div class="loading-bar"></div>
                  </div>
                </div>
                <span onClick="copyMessage(this)" class="icon material-symbols-rounded">content_copy</span>`;

  const incomingMessageDiv = createMessageElement(html, "incoming", "loading");
  chatContainer.appendChild(incomingMessageDiv);

  chatContainer.scrollTo(0, chatContainer.scrollHeight); // Scroll to the bottom
  generateAPIResponse(incomingMessageDiv);
}

// Copy message text to the clipboard
const copyMessage = (copyButton) => {
  const messageText = copyButton.parentElement.querySelector(".text").innerText;

  navigator.clipboard.writeText(messageText);
  copyButton.innerText = "done"; // Show confirmation icon
  setTimeout(() => copyButton.innerText = "content_copy", 1000); // Revert icon after 1 second
}

// Handle sending outgoing chat messages
const handleOutgoingChat = () => {
  userMessage = typingForm.querySelector(".typing-input").value.trim() || userMessage;
  if(!userMessage || isResponseGenerating) return; // Exit if there is no message or response is generating

  isResponseGenerating = true;

  const html = `<div class="message-content">
                  <img class="avatar" src="anim2.webp" alt="User avatar">
                  <p class="text"></p>
                </div>`;

  const outgoingMessageDiv = createMessageElement(html, "outgoing");
  outgoingMessageDiv.querySelector(".text").innerText = userMessage;
  chatContainer.appendChild(outgoingMessageDiv);
  
  typingForm.reset(); // Clear input field
  document.body.classList.add("hide-header");
  chatContainer.scrollTo(0, chatContainer.scrollHeight); // Scroll to the bottom
  setTimeout(showLoadingAnimation, 500); // Show loading animation after a delay
}

// Toggle between light and dark themes
toggleThemeButton.addEventListener("click", () => {
  const isLightMode = document.body.classList.toggle("light_mode");
  localStorage.setItem("themeColor", isLightMode ? "light_mode" : "dark_mode");
  toggleThemeButton.innerText = isLightMode ? "dark_mode" : "light_mode";
});

// Delete all chats from local storage when button is clicked
deleteChatButton.addEventListener("click", () => {
  if (confirm("Are you sure you want to delete all the chats?")) {
    localStorage.removeItem("saved-chats");
    loadDataFromLocalstorage();
  }
});

// Set userMessage and handle outgoing chat when a suggestion is clicked
suggestions.forEach(suggestion => {
  suggestion.addEventListener("click", () => {
    userMessage = suggestion.querySelector(".text").innerText;
    handleOutgoingChat();
  });
});

// Prevent default form submission and handle outgoing chat
typingForm.addEventListener("submit", (e) => {
  e.preventDefault(); 
  handleOutgoingChat();
});

loadDataFromLocalstorage();
```

<img src="kawai.gif" width="60"> <em><b>I love connecting with different people</b> so if you want to say <b>hi, I'll be happy to meet you more!</b> :)</em>

---
<h3 align="left">🔥   My Stats :</h3>

###

<div align="center">
  <img src="https://streak-stats.demolab.com?user=DwiDevelopes&locale=en&mode=daily&theme=dark&hide_border=false&border_radius=5&order=3" height="220" alt="streak graph"  />
</div>

###
###
###

<div align="center">
  <a href="spotify.com"><img src="https://spotify-recently-played-readme.vercel.app/api?user=31kxw76ecqglvlnrxpnn7jriocve" alt="Spotify recently played"  /></a>
</div>

###

###

###
<div align="center">
<p style="font-size:20px;">
  
I really like programming and I learned a lot of things and I mastered it and I also received an award from the government thanks to my professional achievements in Canva design.
</p>
</div>
<div align="center">
  <img height="150" src="game-gaming.gif" style="border-radius:50px;" />
</div>

###

<div align="center">
  <a href="https://portofolio-dwi-bakti-n-dev-liard.vercel.app/playfrom.html"><img src="https://img.shields.io/static/v1?message=Download&logo=&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="Github logo"  /></a>
</div
<div style="margin:flex;">
  <img height="150" src="games dwi bakti n dev.svg" style="border-radius:50px;" />
   <img height="150" src="games dwi bakti n dev.svg" style="border-radius:50px;" />
   <img height="150" src="games dwi bakti n dev.svg" style="border-radius:50px;" />
</div>

### 
<div align="center">
  
```javascript
The cat is sad coz it’s not getting likes
　　　　　／＞　　フ
　　　　　| 　_　 _ l
　 　　　／` ミ＿xノ
　　 　 /　　　 　 |
　　　 /　 ヽ　　 ﾉ
　 　 │　　| | |
```
</div>

<div align="center">
  <a href="https://cat-nime-movies-romance.vercel.app/"><img src="https://img.shields.io/static/v1?message=Catnime Movies&logo=&label=&color=000&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="Github logo"  /></a>

</h1>
<h2 align="center">🐱 Language Skills 🐱</h2>
<img src="HTML.jpg">
<h2 align="center">⚡ Statistic ⚡</h2>
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=DwiDevelopes&theme=react-dark&bg_color=20232a&hide_border=true" width="100%"/>
</p>



<!--
**DwiDevelopes/DwiDevelopes** is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
