
# ET Money Mentor — AI Financial Advisor

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Made with HTML/CSS/JS](https://img.shields.io/badge/Made%20with-HTML%2FCSS%2FJS-blue)](https://developer.mozilla.org/en-US/) [![Powered by WebSockets](https://img.shields.io/badge/Powered%20by-WebSockets-green)](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)

**ET Money Mentor** is an AI-powered financial wellness platform built for the Economic Times AI Hackathon (Avataar.ai × Economic Times). It provides free, personalized financial guidance, planning, and tax optimization tools for Indian users. The application is a comprehensive, interactive financial dashboard that simulates the role of a digital financial advisor, covering everything from tax planning to portfolio analysis and retirement planning.

![ET Money Mentor Hero Section](https://via.placeholder.com/800x400/09101E/F0F4FF?text=ET+Money+Mentor+Screenshot) *(Replace with an actual screenshot of your app)*

## 🚀 Live Demo
[Link to your live demo if deployed]

## ✨ Key Features

The platform is packed with advanced financial tools, each designed to address a critical need for Indian investors.

### 1.  📊 Money Health Score
- **5-minute financial wellness assessment.** Get a score out of 100 across 6 key dimensions: Emergency Fund, Insurance, Investments, Debt, Tax Efficiency, and Retirement Readiness.
- **Personalized insights.** Receive a list of actionable steps to improve your financial health, from building an emergency fund to increasing SIPs.

### 2.  🔥 FIRE Path Planner
- **Plan for Financial Independence, Retire Early (FIRE).** Input your age, target FIRE age, income, expenses, and risk profile.
- **Dynamic roadmap.** See your required monthly SIP, projected corpus, asset allocation, and a detailed month-by-month action plan to achieve your FIRE number.

### 3.  💬 Life Event Financial Advisor (AI-Powered)
- **Get personalized advice for major life events.** Chat with the AI about scenarios like receiving a bonus, getting married, having a baby, inheriting money, or changing jobs.
- **Context-aware.** The AI uses optional user-provided context (income, age, tax bracket) to deliver highly specific financial plans.
- **Powered by WebSockets.** Real-time streaming responses for a seamless conversational experience.

### 4.  🧾 Tax Wizard (Old vs New Regime)
- **Compare tax regimes side-by-side.** Input your salary, HRA, rent, and deductions to instantly see your tax liability under both the Old and New tax regimes.
- **Find missed opportunities.** The tool highlights potential savings in sections like 80C, 80D, NPS, and home loan interest, helping you maximize your take-home pay.

### 5.  📄 Form 16 Analyser 
- **Deep-dive into your salary structure.** Enter detailed components from your Form 16 (Basic, HRA, LTA, allowances, etc.).
- **Uncover hidden deductions.** The AI identifies every missed deduction, models both tax regimes with exact numbers, and ranks tax-saving investments based on your risk profile.
- **Actionable insights.** Get personalized recommendations for salary restructuring, missed HRA/LTA claims, and optimal use of sections like 80CCD(1B).

### 6.  🔬 MF Portfolio X-Ray 
- **Analyze your mutual fund portfolio.** Get a true XIRR (Extended Internal Rate of Return) calculation, accounting for the timing of every SIP.
- **Stock-level overlap heatmap.** Identify if your "diversified" portfolio is just holding the same top 5 stocks across multiple funds.
- **Expense ratio drag.** Calculate exactly how much you are losing to commissions in regular plans vs. direct plans.
- **Specific rebalancing plan.** Get a tax-aware rebalancing recommendation with exact buy/sell actions, including capital gains implications.

### 7.  💑 Couple's Planner
- **India's first AI-powered joint financial plan.** Input both partners' financial profiles and joint goals (retirement, child education, home purchase).
- **Optimize for two.** The AI provides a combined net worth projection, an optimized SIP split, and tax regime recommendations for both partners.

## 🛠️ Built With

- **Frontend:** HTML5, CSS3, Vanilla JavaScript
- **Styling:** CSS Grid, Flexbox, Custom Properties (CSS Variables)
- **Typography:** Google Fonts (Fraunces, DM Sans)
- **AI / Backend Simulation:** WebSockets (`wss://backend.buildpicoapps.com/api/chatbot/chat`)
- **Hosting:** [Your hosting platform, e.g., GitHub Pages, Netlify, Vercel]

## 🚦 How to Use

The application is designed to be intuitive. Simply navigate using the sidebar.

1.  **Start with the Money Health Score:** Click on "Home" and then "Get My Free Score" to get a baseline understanding of your finances.
2.  **Explore Tools:** Use the sidebar to try out different tools:
    - **Tax Wizard:** If you have your salary and deduction details handy.
    - **Form 16 Analyser:** For a more in-depth tax analysis.
    - **MF Portfolio X-Ray:** If you have mutual fund investments.
    - **Life Advisor:** For specific life event questions.
    - **FIRE Planner:** For retirement planning.
    - **Couple's Planner:** If you are planning finances with a partner.
3.  **Input Your Data:** Fill in the forms with your financial information. The more accurate the input, the more precise the output.
4.  **Analyze:** Click the primary button (e.g., "Calculate My Score", "Analyse My Form 16") to generate your personalized report and AI insights.

## 📁 Project Structure

The project is a single HTML file (`index.html`) with embedded CSS and JavaScript. The structure is logically organized:

- `<!DOCTYPE html>` to `</head>`: Contains the page title, Google Fonts links, and all CSS styles.
- `<body>`: Contains the main HTML structure.
    - `.header`: The top bar with the logo.
    - `.layout`: Contains the sidebar and main content.
    - `main.content`: Holds all the pages, each as a `.page` div.
        - `page-home`: The landing page with feature cards.
        - `page-score`: The Money Health Score tool.
        - `page-fire`: The FIRE Planner tool.
        - `page-advisor`: The Life Advisor chat interface.
        - `page-tax`: The Tax Wizard tool.
        - `page-form16`: The Form 16 Analyser tool.
        - `page-xray`: The MF Portfolio X-Ray tool.
        - `page-couple`: The Couple's Planner tool.
- `<script>`: Contains all the JavaScript functions, including:
    - Navigation logic.
    - Core calculation functions for tax, FIRE, and scoring.
    - The `callClaude` function for AI interactions via WebSockets.
    - Specific logic for each tool (e.g., `calcScore()`, `analyseForm16()`, `runXray()`).

## 🧠 Core Logic & AI Integration

The project uses a mix of client-side JavaScript for deterministic calculations (like tax, XIRR, FIRE projections) and an AI WebSocket service for generating personalized narratives, strategies, and advice.

- **AI Service (`callClaude`):** A wrapper function that connects to `wss://backend.buildpicoapps.com/api/chatbot/chat`. It sends a user's prompt along with a detailed system prompt that instructs the AI to act as an Indian financial expert. This is used in the Life Advisor, Tax Wizard (for suggestions), Form 16 Analyser (for AI insights), Couple's Planner, and MF X-Ray (for deep analysis).
- **Key Financial Calculations:**
    - `calcOldTax()` / `calcNewTax()`: Implements Indian income tax slabs for FY 2024-25.
    - `calcXIRR()`: A Newton-Raphson method implementation to calculate the true annualized return of a portfolio.
    - `calcHRAExemption()`: Calculates the tax-exempt portion of House Rent Allowance (HRA).
    - `calcScore()`: A custom algorithm that scores six dimensions of financial health.
    - `calcFIRE()`: Projects corpus and SIP requirements for early retirement.

## 💡 Key Insights & Differentiators

This project stands out because it goes beyond simple calculators to offer **actionable, integrated advice**.

1.  **Holistic View:** It combines investment planning, tax optimization, insurance, and retirement into a single platform.
2.  **Actionable Output:** Every tool produces a list of specific, numbered steps, not just numbers.
3.  **Real-World Accuracy:** The Form 16 and MF X-Ray tools are built around the actual structure of Indian salary slips and CAMS statements, making them highly practical.
4.  **Tax-Aware Recommendations:** The MF X-Ray rebalancing plan includes specific capital gains tax calculations, advising users on whether to wait for LTCG status before switching funds.
5.  **Advanced Overlap Analysis:** The portfolio X-Ray doesn't just show overlap; it quantifies the impact and recommends which specific funds to merge.
6.  **Clean, Professional UI:** The design mimics a modern financial app with a dark theme, clear typography, and intuitive navigation.

## ⚠️ Important Disclaimers

This application is a **hackathon prototype** and is provided for **educational and informational purposes only**. It does not constitute licensed financial advice under SEBI (Investment Advisers) Regulations, 2013.

- All projections, calculations, and AI-generated insights are based on the information provided by the user and are for illustrative purposes only.
- Mutual fund investments are subject to market risks. Past performance is not indicative of future results.
- Tax calculations are indicative and based on FY 2024-25 slabs. Consult a Chartered Accountant for your actual ITR filing.
- The AI guidance is not a substitute for consulting with a SEBI-registered financial advisor.

## 🗺️ Future Roadmap

-  **Backend Integration:** Replace the WebSocket service with a dedicated backend (e.g., Node.js, Python) for more control and data persistence.
-  **User Accounts:** Allow users to save their profiles and track their progress over time.
-  **Real Market Data:** Integrate live market data for more accurate portfolio valuations and benchmarks.
-  **Exportable Reports:** Allow users to download their financial plans and analysis as PDFs.
-  **Mobile App:** Develop a companion mobile app for on-the-go access.

## 🤝 Contributing

This project was created for a hackathon. For major changes, please open an issue first to discuss what you would like to change.

## 📝 License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## 📧 Contact

Pabitra Khandual - khandualapabitra29@gmail.com

---

**Developed with passion for the Economic Times AI Hackathon 2026.**
