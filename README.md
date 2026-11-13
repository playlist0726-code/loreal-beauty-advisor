## Portfolio context

**[Interface demo](https://playlist0726-code.github.io/loreal-beauty-advisor/)** · [Project index](https://playlist0726-code.github.io/projects/) · [Portfolio](https://playlist0726-code.github.io/)

A Global Career Accelerator educational chat-interface project by Junsu (Michael) Kim. **Live AI is not connected:** the instructor-provided Worker endpoint is still needed. The demo shows “Connection pending” and does not invent replies. This is not an official L’Oréal product or client commission. Setup and security requirements below remain applicable.

---

# L'Oréal Beauty Advisor - Project 8

An independent student prototype by Michael Kim. HTML, CSS and beginner-friendly JavaScript; no frontend packages or API keys.

## Current status

The interface, conversation handling and Worker helper are implemented. **Live AI is not connected yet.** The course repository refers to a class-hosted Worker but does not provide its actual URL. The page explicitly shows "Connection pending" and never fabricates a response.

## Connect the advisor

1. Ask the instructor for the class Cloudflare Worker URL. Students should not handle API keys; follow the course's `AGENTS.md` guidance.
2. In `index.html`, set the `content` value of `<meta name="chat-endpoint" content="">` to the supplied HTTPS Worker URL. It is a public address, not a secret.
3. Commit and push the change. Confirm the Worker permits the origin `https://playlist0726-code.github.io`.
4. If the instructor directs a separate Worker deployment, `RESOURCE_cloudflare-worker.js` is prepared for Cloudflare. It reads an existing `OPENAI_API_KEY` Worker secret at runtime. Do not put credentials in this repository, in the browser, or in chat.

## Included LevelUps

- Conversation history: successful question/answer pairs are included in subsequent requests. History is held in memory and is cleared by reload or New conversation.
- Latest question: a separate panel displays only the current question and updates for every new question.
- Conversation bubbles: user and assistant turns have distinct labels, alignment and colors.

## Other behavior

Responsive desktop/mobile layouts, keyboard submission, IME composition support, character limit, pending state, duplicate-submit prevention, retry, error handling, reduced-motion support and safe text rendering. The Worker helper enforces a server-side beauty-focused system prompt, validates input and limits CORS to the project origin. CORS is not authentication or a spending limit; an instructor-managed endpoint should enforce its own usage controls.

## Verification

Run `node /absolute/path/to/test-chatbot.cjs` from the project parent directory. Checks use simulated API responses, not live OpenAI calls. Browser layout and real AI behavior still require verification after the endpoint is configured.

Before submission, verify on the live page:

- Ask for a routine, provide preferences, and ask a follow-up that refers to them.
- Give a name and ask the advisor to recall it.
- Ask an unrelated question and confirm a polite redirect to beauty.
- Try all four topic buttons, retry after a failure, and reset the conversation.
- Check a narrow phone viewport and a desktop viewport.
- Open the GitHub Pages URL in a private browser window.

## References

- Course starter: https://github.com/GCA-Classroom/08-prj-loreal-chatbot
- Branding: https://www.futurebrand.com/our-work/loreal
- Typography reference supplied in the worksheet: https://hello.monotype.com/rs/800-DWE-978/images/BrandReview_LOREAL.pdf
- OpenAI Chat Completions: https://developers.openai.com/api/reference/resources/chat/subresources/completions/methods/create
- Cloudflare secrets: https://developers.cloudflare.com/workers/configuration/secrets/

The provided L'Oréal logo belongs to its owner. This is an educational project and does not claim affiliation or official advice.
