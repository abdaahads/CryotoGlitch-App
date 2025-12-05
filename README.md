# CryptoGlitch: AI-Powered Market Tracker 🔮

# 

**Live Demo:** https://gemini.google.com/share/747f22717fcf

**CryptoGlitch** is a "Data-Heavy" dashboard built for the Vibe Coding Assignment. It combines real-time cryptocurrency data with a cynical AI personality ("Glitch") that analyzes market sentiment on demand.

The goal was to move beyond a boring spreadsheet view and create a tool that feels alive, using a Cyber-Industrial aesthetic and generative AI to provide context to the numbers.

## 🚀 Features

# 

*   **⚡ Real-Time Data:** Fetches live price, 24h change, and market cap for the top 50 coins via CoinGecko.
    
*   **🧠 AI Vibe Check:** Integrated **Google Gemini API** to generate snarky, cyberpunk-style market summaries.
    
*   **🔍 Individual Asset Scan:** Click the "Sparkles" icon on any coin to get an instant AI analysis of that specific asset.
    
*   **💾 Local Persistence:** Watchlist favorites are saved to `localStorage`, so your portfolio is remembered without a login.
    
*   **🛡️ Smart Fallback:** If the public API hits a rate limit, the app gracefully switches to cached data so the UI never breaks.
    
*   **📱 Mobile Responsive:** Data tables adapt to screen size, hiding non-essential columns on mobile.
    

## 🛠 Tools Used

# 

*   **Frontend:** React.js, Tailwind CSS
    
*   **Icons:** Lucide React
    
*   **Data API:** CoinGecko (Public/Free Tier)
    
*   **AI Logic:** Google Gemini API (`gemini-2.5-flash-preview`)
    
*   **Development:** AI-assisted workflow (as per course guidelines)
    

## 🤖 The "Vibe Coding" Process

# 

This project was built by acting as a "Senior Architect" and guiding the AI through iterations.

### 1\. The "Golden Prompt" (Best Result)

# 

This prompt established the core logic and aesthetic in one go:

> **Role:** Senior React Developer **Task:** Build a crypto dashboard called "CryptoGlitch". **Vibe:** Dark mode, industrial, Zinc-900 backgrounds, Emerald-500 accents. **Context:** This is a Data-Heavy assignment.**Requirements:**
> 
> 1.  Fetch top 50 coins from CoinGecko.
>     
> 2.  Add a search bar that filters the list instantly.
>     
> 3.  Add a "Star" button to save favorites to `localStorage`.
>     
> 4.  **CRITICAL:** Handle API errors gracefully. If CoinGecko 429s (rate limits), show a "Simulation Mode" warning and use hardcoded fallback data.
>     
> 5.  Make it mobile responsive.
>     

**Why it worked:** It combined style ("Zinc-900"), logic ("localStorage"), and failure handling ("fallback data") in the initial context, preventing the "blank screen error" problem later.

### 2\. The Failed Prompt (And the Fix)

# 

**The Attempt:** *"Add an AI feature that tells me if I should buy."* **The Result:** The AI refused to give financial advice and wrote a generic disclaimer that broke the layout. **The Fix:** I pivoted to "Vibe" instead of "Advice".

> *"Change the AI persona. You are 'Glitch', a cynical cyberpunk analyst. Don't give financial advice. Instead, give a 'Vibe Check' based on the gainers and losers. Use slang like 'rekt', 'moon', and 'fud'. Keep it under 3 sentences."*

### 3\. Iteration & Refinement

# 

*   **Challenge:** The CoinGecko API is strict (10-30 calls/minute).
    
*   **Solution:** I asked the AI to implement a `lastUpdated` timestamp and only auto-refresh every 60 seconds, adding a manual refresh button for impatient users.
    
*   **Styling:** Initially, the table looked like a spreadsheet. I prompted: *"Make the table rows look like card slots. Add a subtle hover glow effect using Tailwind's group-hover."*
    

## 🧠 Learnings & Challenges

# 

*   **Prompting Personality:** I learned that LLMs are much better when you give them a specific "Character Card" (e.g., "Cynical Cyberpunk Analyst") rather than just asking for "summary text."
    
*   **Data vs. Vibe:** Balancing a raw data table with aesthetic design is hard. Using "Badges" and color-coding (Green/Red) helped make the data readable at a glance.
    
*   **State Management:** Combining `localStorage` (synchronous) with API data (asynchronous) required careful `useEffect`hooks to ensure favorites didn't disappear during loading states.
    

## 📦 Setup Instructions

# 

1.  **Clone the repo:**
    
    ```
    git clone [https://github.com/abdaahads/CryotoGlitch-App](https://github.com/abdaahads/CryotoGlitch-App)
    cd CryptoGlitch
    ```
    
2.  **Install dependencies:**
    
    ```
    npm install
    ```
    
3.  **Run locally:**
    
    ```
    npm run dev
    ```
    
4.  **Note on API Keys:** The CoinGecko API is public (no key needed). The Gemini API key is currently set to use the environment's provided key. For local development, you may need to add your own key in the code.
    

## 🐛 Known Limitations

# 

*   **Rate Limiting:** If you refresh too quickly, you will see the "Using cached fallback data" warning. This is a CoinGecko limitation, not a bug.
    
*   **Currency:** Currently locked to USD.
    
*   **Audio:** The "AI Neural Link" is text-only for now; text-to-speech is a planned future update.