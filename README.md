Telegram AI Agent with DALL·E-3

Your personal AI assistant on Telegram — remembers you, draws for you, answers anything.

> "Draw me a cat astronaut" → Gets a custom DALL·E-3 image
> "What did I ask yesterday?" → Remembers last 10 messages

![Demo](https://img.shields.io/badge/%F0%9F%A4%96%20AI%20Agent-FF6B6B?style=for-the-badge&logo=telegram) ![DALL·E](https://img.shields.io/badge/%F0%9F%96%BC%EF%B8%8F%20DALL%C2%B7E--3-00D26A?style=for-the-badge) ![Memory](https://img.shields.io/badge/%F0%9F%A7%A0%20Memory-FFD60A?style=for-the-badge)



 Features

| Check | Feature |
|-------|--------|
| Check | GPT-4o via OpenAI |
| Check | DALL·E-3 image generation |
| Check | 10-message memory (Window Buffer) |
| Check | Personalized replies (uses your name) |
| Check | Sends images directly in chat |
| Check | No code — Just import & run |



 How to Use

 1. Import Workflow
→ Click [telegram-ai-agent-dalle.json](telegram-ai-agent-dalle.json) → Copy all  
→ In n8n: New → Import from Clipboard (or drag file)

 2. Fix Red Warnings (Credentials)

| Credential | Name |
|----------|------|
| OpenAI API | `Ted's Tech Talks OpenAi` |
| Telegram Bot | `Chat & Sound` |

How to set up:

 OpenAI
1. Go to [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
2. Copy your API key
3. In n8n → Credentials → OpenAI API
4. Name: `Ted's Tech Talks OpenAi` → Paste key

 Telegram Bot
1. Talk to [@BotFather](https://t.me/BotFather)
2. `/newbot` → Get token
3. In n8n → Credentials → Telegram API
4. Name: `Chat & Sound` → Paste token

 3. Activate & Test

1. Click "Activate" in n8n
2. Open Telegram → Search your bot → Say:
   > `Hi! My name is Alex`

3. Ask:
   > `Draw me a robot playing guitar`

Bot replies with image + text
---

 Live Bot Example

Try it now:  
[@YourBotName](https://t.me/YourBotName) (after deployment)

> Replace with your actual bot username after setup.


How It Works

```mermaid
graph TD
    A[User Message] --> B[Telegram Trigger]
    B --> C[AI Agent + Memory]
    C --> D{Image Request?}
    D -->|Yes| E[DALL·E-3 API]
    D -->|No| F[GPT-4o Reply]
    E --> G[Send Image]
    F --> H[Send Text]
    G --> I[Final Reply]
    H --> I
