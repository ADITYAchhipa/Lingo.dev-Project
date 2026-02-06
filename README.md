# 🌐 **TalentIQ (Meetio)**  



## 🌍 Seamless Video Conferencing with Real-Time Translation  

---

### 💡 About The Project

**TalentIQ** is a next-generation video conferencing platform designed to **eliminate language barriers**. By integrating **real-time translation** into chat, live captions, and collaborative notes, participants can communicate naturally in their own language.

---

# 🚀 Key Features

## 🗣️ Real-Time Live Captions

Understanding different accents and languages can be challenging. TalentIQ provides **live translated captions** for every speaker.

- ⚡ **Instant Translation** — Speak in Hindi, a Spanish user reads Spanish captions  
- 🎙️ **Accent Handling** — Advanced speech recognition adapts to various accents  
- ♿ **Accessibility** — Inclusive for hearing-impaired users and non-native speakers  

---

## 💬 Multilingual Chat Translation

No more switching tabs to translation tools.

- 🌐 **Auto-Translation** — Messages are instantly translated into the receiver's preferred language  
- 🤝 **Seamless Experience** — Everyone reads chat in their native language  

---

## 📝 Collaborative Translated Notes

Never miss key information during meetings.

- 🧑‍🤝‍🧑 **Synced Editing** — Real-time collaborative editor (like Google Docs)  
- 🌎 **Personalized View** — Same notes displayed in each user’s selected language  
- 🔄 **Zero Information Loss** — Notes sync and translate instantly  

---

## 📹 Crystal Clear Video Calls

- 🚀 **Low Latency** — Optimized streaming for smooth communication  
- 🔒 **Secure Sessions** — End-to-end encrypted signals  
- 🙌 **Interactive Tools** — Raise hand, screen sharing, reactions  

---

# 🏗️ System Architecture

Our system handles **real-time streams for video, audio, and text**, while orchestrating translation services dynamically.

```mermaid
graph TD
UserA[User A (English)] <-->|WebSocket| SocketServer[Socket.IO Server]
UserB[User B (Spanish)] <-->|WebSocket| SocketServer

subgraph Frontend [React PWA]
UI[Video Interface]
Speech[Web Speech API]
Editor[Quill Editor]
end

subgraph Backend [Node.js Cluster]
SocketServer
Auth[Auth Service]
Trans[Lingo Translation Service]
DB[(MongoDB)]
end

UserA -- Audio/Video --> StreamSDK[Stream.io Servers] -- Audio/Video --> UserB
Speech -- "Audio Text (en)" --> SocketServer
SocketServer -- "Translate (en->es)" --> Trans
Trans -- "Translated Text (es)" --> SocketServer
SocketServer -- "Caption (es)" --> UserB
Editor -- "Note Update (en)" --> SocketServer
SocketServer -- "Translate (en->es)" --> Trans
Trans -- "Translated Note (es)" --> SocketServer
SocketServer -- "Sync Update (es)" --> UserB
