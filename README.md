# Twitch Chat Overlay

A lightweight, customizable Twitch chat overlay for OBS or browser sources.  
Supports Twitch emotes, 7TV emotes, badges, message fading, and automatic reconnect.

---

## Features

- **Twitch emotes** (native support)
- **7TV emotes** (auto-fetched by channel)
- **Badges** (configurable images)
- **Message limit** and **fade-out** (configurable)
- **WebSocket reconnect** with visible error UI
- **Easy configuration** via `config.js`
- **No dependencies** (pure HTML/CSS/JS)

---

## Setup

1. **Clone or download this repository.**
2. **Edit `config.js`**  
   Set your channel, badge URLs, and 7TV emote set ID:
   ```js
   window.chatConfig = {
     channel: "yourchannel",
     seventvEmoteSetId: "YOUR_7TV_EMOTE_SET_ID",
     badgeUrls: {
       moderator: "badges/moderator.png",
       broadcaster: "badges/broadcaster.png",
       vip: "badges/vip.png"
     },
     messageLimit: 30,
     fontSize: "1.2em",
     fadeTime: 0
   };
   ```
3. **Add your badge images** to the `badges/` folder.
4. **Open `chat.html`** in OBS or your browser as a browser source.

---

## Customization

- **Font size, message limit, fade time:**  
  Set in `config.js`.
- **Badges:**  
  Add or update badge images and URLs in `config.js`.
- **Overlay size and style:**  
  Edit `chat.css` for custom appearance.

---

## Troubleshooting

- If emotes or chat do not load, check your browser console for errors.
- The overlay will show a red error bar if it loses connection to Twitch chat and will auto-reconnect.

---

## Extending

- To add BTTV or FFZ emotes, add new parsing functions in the JS.
- For more customization, edit `chat.css` and `config.js`.

---

## License

MIT License

---

## Notes

- **Channel Subscriber Badges:**  
  This overlay does not display Twitch subscriber badges by default, as Twitch does not provide direct public URLs for custom sub badges via IRC tags.  
  If you want to show sub badges, you must manually add your badge images to the `badges/` folder and map them in `config.js` using the correct badge type (e.g., `"subscriber": "badges/subscriber.png"`).  
  These will only display for users with the generic `subscriber` badge tag.

  For advanced sub badge support (tiers, months), you would need to implement Twitch API authentication and badge fetching, which is not included in this overlay.