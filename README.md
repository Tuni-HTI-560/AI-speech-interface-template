# Pipecat-based conversational speech interface template

**HTI.560 Conversational Interaction with AI** (Tampere University)

A minimal voice conversation template demonstrating Pipecat Flows, WebRTC, and real-time UI state management. Students working on projects, who are interested in trying out a Pipecat-based solution, can adapt this for any domain (cooking, shopping, healthcare, etc.) by editing config files. No code changes needed.

Requires API keys: [OpenAI](https://platform.openai.com/api-keys) (for the LLM) and a speech provider for voice input (STT/ASR) and output (TTS). You can use API keys from any service provider directly, eg. [Azure](https://portal.azure.com), [Deepgram](https://console.deepgram.com), or [OpenAI](https://platform.openai.com/api-keys).

**Configure API keys as needed (see `backend/.env.example`).**

## Structure

**Backend (using [Pipecat](https://docs.pipecat.ai/) - an open-source framework for voice AI):**
- **Pipecat Flows** ([docs](https://docs.pipecat.ai/)): Non-linear conversation state machines with LLM function calling
- **WebRTC**: Real-time audio streaming (STT/TTS)
- **RTVI Protocol**: Backend-to-frontend state synchronization
- **Provider Flexibility**: Swap STT/TTS services via environment variables

**Frontend (React + Typescript + Pipecat Client SDK):**
- **Real-time state management**: React hooks with WebRTC events
- **Audio Visualization**: Web Audio API, RMS calculation, waveform rendering
- **UI/UX**: Responsive components, conversation flow visualization

## Quick Start

```bash
# Backend
cd backend
pip install -r requirements.txt
python webrtc_server.py

# Frontend
cd frontend
npm install && npm run dev
```


## Adapt for your conversational task:

****
1. Edit `backend/conversation_config.py` (topics, prompts)
2. Edit `frontend/src/conversationInfoDisplayed.tsx` (UI text, images)
3. Configure STT/TTS providers via environment variables
4. Customize colors, visualizer in `CUSTOMIZATION.md`



