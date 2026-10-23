# UPSC AI Interview Simulator

A mobile-friendly web app prototype for a 20-minute UPSC-style mock personality test. It has five judge personas, English/Hindi/Marathi language choices, browser text-to-speech, optional browser speech recognition, 25 prepared questions, manual/automatic question mode, and a downloadable feedback report.

## Important limitations

- The frontend is a working prototype; speech recognition availability depends on browser/device support and permissions.
- For dynamic AI questions and substantive answer feedback, configure `OPENAI_API_KEY` on the server. The key must never be placed in browser code.
- The current interface selects one available speech voice per judge. Some phones/browsers may expose only one suitable voice, so five distinct audible voices are not guaranteed.
- It is a practice tool, not an official UPSC system or selection predictor.
- Interview responses may contain personal information. Add a privacy policy, secure hosting, authentication, data retention controls and consent before public deployment. This prototype does not save interview records to a database.

## Run locally

Requires Node.js 18 or later.

1. Unzip the project.
2. In the project folder, run `npm install`.
3. Copy `.env.example` to `.env` and set your API key. The sample server does not load `.env` automatically; either set environment variables in your hosting provider, or install `dotenv` and add `require('dotenv').config()` at the top of `server.js`.
4. Set `OPENAI_API_KEY` in your terminal/hosting environment.
5. Run `npm start`.
6. Open `http://localhost:3000`.

For phone access, deploy the app to a hosting service that supports Node.js and HTTPS. HTTPS is important for microphone access and PWA installation. Do not share the API key.

## Example environment setup

Linux/macOS:
```sh
export OPENAI_API_KEY="your-key"
npm start
```

Windows PowerShell:
```powershell
$env:OPENAI_API_KEY="your-key"
npm start
```

## Android home screen

Once deployed to an HTTPS URL, open the URL in Chrome on Android, open the browser menu, and choose **Add to Home screen** or **Install app** if available.

## Interview flow

- Candidate profile
- 20-minute timer
- Up to 25 questions, with judge roles rotating in blocks of five
- Voice capture where supported; editable answer transcript
- Feedback report and text download

The automatic/manual selector controls the user's question progression; it does not interrupt a candidate mid-speech to force a response.
