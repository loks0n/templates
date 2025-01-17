# 🤖 Node.js Discord Command Bot Function

Simple command using Discord Interactions.

## 🧰 Usage

### `POST`

Webhook to receive Discord command events. To receive events, you must register your application as a [Discord bot](https://discord.com/developers/applications).

**Parameters**

| Name                  | Description                      | Location | Type   | Sample Value    |
| --------------------- | -------------------------------- | -------- | ------ | --------------- |
| x-signature-ed25519   | Signature of the request payload | Header   | string | `d1efb...aec35` |
| x-signature-timestamp | Timestamp of the request payload | Header   | string | `1629837700`    |
| JSON Body             | GitHub webhook payload           | Body     | Object | See [Discord docs](https://discord.com/developers/docs/interactions/receiving-and-responding) |

**Response**

Sample `200` Response:

Returns a Discord message object.

```json
{
  "type": 4,
  "data": {
    "content": "Hello from Appwrite 👋"
  }
}
```

Sample `401` Response:

```json
{
  "error": "Invalid request signature"
}
```

## ⚙️ Configuration

| Setting           | Value         |
| ----------------- | ------------- |
| Runtime           | Node (18.0)   |
| Entrypoint        | `src/main.js` |
| Build Commands    | `npm install` |
| Permissions       | `any`         |
| Timeout (Seconds) | 15            |

## 🔒 Environment Variables

### DISCORD_PUBLIC_KEY

Discord Public Key to verify request signature.

| Question      | Answer                                                                                                                 |
| ------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Required      | Yes                                                                                                                    |
| Sample Value  | `d1efb...aec35`                                                                                                        |
| Documentation | [Discord Docs](https://discord.com/developers/docs/tutorials/hosting-on-cloudflare-workers#creating-an-app-on-discord) |
