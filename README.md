# [Airtable #278 Issue Repro](https://github.com/Airtable/airtable.js/issues/278)

## Installation Instruction

1. Install dependencies

   ```bash
   yarn
   npm i
   ```

2. Rename `.env.example` file to `.env`

   ```bash
   mv .env.example .env
   ```

3. Fill `.env` enviroment variables

   ```dotenv
   VITE_AIRTABLE_API_KEY=key16asd6a4d
   VITE_AIRTABLE_BASE_ID=app16a5sd16as
   ```

4. Running the Project

   ```
   yarn dev
   npm run dev
   ```

5. See error on browser console:

   - Go to [http://localhost:3000](http://localhost:3000) in browser.
   - Open devtools with <kbd>F12</kbd> or <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>I</kbd>.
   - Go to the **`Console`** tab of the devtools.
   - See error:

   ```log
   Uncaught Error: Module "stream" has been externalized for browser compatibility and cannot be accessed in client code.
     at Object.get (airtable.js?v=3059accc:1137)
     at node_modules/node-fetch/lib/index.mjs (airtable.js?v=3059accc:1730)
     at __init (chunk-EB7XYW2R.js?v=3059accc:9)
     at node_modules/airtable/lib/fetch.js (airtable.js?v=3059accc:2240)
     at __require2 (chunk-EB7XYW2R.js?v=3059accc:12)
     at node_modules/airtable/lib/base.js (airtable.js?v=3059accc:3486)
     at __require2 (chunk-EB7XYW2R.js?v=3059accc:12)
     at node_modules/airtable/lib/airtable.js (airtable.js?v=3059accc:3639)
     at __require2 (chunk-EB7XYW2R.js?v=3059accc:12)
     at airtable.js?v=3059accc:3711
   ```
