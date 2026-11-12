# PennyOS V2 — Personal Money Planner

PennyOS V2 කියන්නේ personal income / expense tracking, budgets, savings goals, planned payments සහ reports තියෙන responsive web app එකක්. UI එක playful cartoon style එකට හදලා තියෙනවා.

## 1. Local preview එක run කරන්න

AI නැති dashboard features බලන්න `index.html` එක browser එකෙන් open කළත් පුළුවන්. AI connection එක local preview එකේ වැඩ කරන්න නම් Vercel local server එක භාවිතා කරන්න:

1. Node.js 20 හෝ අලුත් version එක install කරගන්න.
2. Terminal එක project folder එකේ open කරන්න.
3. `npm i -g vercel` run කරන්න.
4. `.env.example` copy කරලා `.env.local` කියලා rename කරන්න.
5. `.env.local` file එකේ `GEMINI_API_KEY=` පස්සේ ඔයාගේ private Gemini API key එක දාන්න.
6. `vercel dev` run කරලා එන local URL එක browser එකෙන් open කරන්න.

## 2. GitHub + Vercel එකෙන් host කරන්න

1. GitHub එකේ අලුත් repository එකක් හදන්න.
2. මේ project folder එකේ **සියලු files සහ `api` folder එකත්** repository එකට upload කරන්න. `index.html` එක විතරක් upload කරන්න එපා.
3. Vercel එකට sign in වෙලා **Add New → Project → Import Git Repository** තෝරන්න.
4. PennyOS repository එක select කරලා deploy කරන්න. Build command එකක් අවශ්‍ය නැහැ.
5. Vercel → Project → **Settings → Environment Variables** යන්න.
6. මේ variable එක add කරන්න:
   - Name: `GEMINI_API_KEY`
   - Value: ඔයාගේ Google AI Studio Gemini API key එක
7. Optional variable එකක් ලෙස `GEMINI_MODEL` = `gemini-3.8-flash` දාන්න පුළුවන්. Default එකත් ඒකමයි.
8. Environment variable එක save කළාට පස්සේ **Redeploy** කරන්න.
9. Website එකේ **AI money buddy → Check connection** click කරන්න.

## API key එක ගැන වැදගත්

API key එක `index.html` එකට, browser input එකකට, localStorage එකට හෝ GitHub repository එකට දාන්න එපා. එහෙම කළොත් වෙන කෙනෙකුට key එක බලලා ඔයාගේ quota එක භාවිතා කරන්න පුළුවන්. Vercel Environment Variables එකේ දාන්න; `api/ai.js` ඒක server-side විතරක් කියවයි.

**GitHub Pages පමණක් භාවිතා කළොත් AI endpoint එක run වෙන්නේ නැහැ.** GitHub repository එක source code තබාගන්න භාවිතා කරලා Vercel හරහා app එක deploy කරන්න. Hosted URL එක public එකට share කිරීමට කලින් access protection / authentication සහ rate limiting එකක් එකතු කරන්න. දැනට same-origin check එක තියෙනවා, නමුත් ඒක user login එකක් නොවෙයි.

## දැනට ඇතුළත් features

- Overview dashboard: total account balance, monthly income, expenses, net cash flow
- Income / expense / transfer entries
- Reason field එකට default suggestions සහ තමන්ට කැමති text එකක් type කිරීම
- Food, groceries, transport, education, shopping, tech, bills, health, subscriptions ඇතුළු categories
- Cash / bank / savings accounts සහ opening balances
- Category budgets create / edit / delete
- Savings goals සහ progress updates
- Planned payments, recurring schedules සහ mark-as-paid action
- Search, type / category / date filters
- CSV transaction export සහ JSON backup / restore
- Colour palettes 6ක්, custom accent colour, light / dark mode
- Responsive desktop / mobile navigation සහ animations
- Gemini AI money buddy (secure server-side endpoint)

## Data / privacy

Transactions සහ settings දැනට browser `localStorage` එකේ පමණක් save වෙනවා. Device අතර cloud sync තවම නැහැ. Browser data clear කරන්න කලින් **Settings → Data & privacy → Download full backup** භාවිතා කරන්න.

AI එකට යවන්නේ total balance, මේ මාසයේ income / expenses, grouped spending reasons, category totals, budgets, goals සහ upcoming payments වගේ aggregated summary එකක් විතරයි; raw transaction list එක හෝ notes යවන්නේ නැහැ. Card numbers, passwords හෝ bank login details app එකට ඇතුළත් කරන්න එපා. Gemini API usage සහ data handling Google API terms වලට යටත්.

PennyOS යනු personal tracking tool එකක් මිස bank එකක් හෝ financial institution එකක් නොවේ. Reports වල data හරිද කියලා පරීක්ෂා කරලා භාවිතා කරන්න.
