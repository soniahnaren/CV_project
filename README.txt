SignTalk (web) - one file, no install
=====================================
index.html is the whole app. Hand tracking runs in the browser (MediaPipe via CDN).

TRY IT ON YOUR COMPUTER
  Camera access only works on https:// or http://localhost, not by double-clicking the file.
  In this folder run:      python3 -m http.server 8000
  then open:               http://localhost:8000

PUT IT ON THE INTERNET (free, gives you an https link)
  Netlify Drop : go to app.netlify.com/drop, drag this whole folder onto the page.
  GitHub Pages : new repo -> upload index.html -> Settings > Pages > deploy from main branch.
  Cloudflare Pages / Vercel / Hugging Face (Static Space) also work: upload index.html.

FIRST USE
  1. Start camera, allow access.
  2. Teach it: pick A, press Record, hold the sign for 4 seconds (move the hand slightly).
     Repeat for each sign (it moves to the next one for you). Press R as a shortcut.
  3. Once 2+ signs are taught, hold a sign steady until the bar fills and it is typed.

NOTES
  - Letters A-Z and digits 0-9 work out of the box with the pretrained model (models/asl_mlp.onnx,
    huggingface.co/nocontextdoruk/asl-landmark-mlp, CC BY-NC 4.0). Teaching your own signs is optional.
  - Samples are stored in the visitor's own browser (localStorage). Each person teaches their own signs.
  - Export CSV / Import file are compatible with the Python desktop app's dataset/gestures.csv.
  - Needs internet on first load (hand model ~8 MB from Google/jsDelivr), then it is cached.
  - Speech uses the browser's built-in voice (Chrome, Edge, Safari).
