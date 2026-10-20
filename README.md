# MAIA

**Messaging Archive & Information Assistant.** A demo of chat archiving in XENA: chat messages from every channel end up in the same register and object store, with the Office Assistant next to the conversation.

MAIA is part of XENA, alongside the storage demo, MIRA (the assistant in the office suite), TINA (the search portal for residents) and ELSA (e-mail archiving).

> A demo, not a product. People, organisations, messages, phone numbers and reference numbers are made up. Product names are used for recognition only; the demo is not made or endorsed by the vendors.

## What the demo shows

| View | What you see |
|---|---|
| **Conversations** | A chat environment with seven channels: Nextcloud Talk, Element (MijnBureau), Tchap (LaSuite), Microsoft Teams, Slack, WhatsApp Business and Signal. Each message shows whether it is in the archive. The Office Assistant panel shows, per conversation, the channel class, the business/personal choice, the archive participant, capturing a selection, linking to case and file, a sealed conversation record and anonymisation for the Dutch Open Government Act (Woo). |
| **Channels** | Four classes: A (own management), A′ (own management, end-to-end encrypted), B (vendor) and C (device). Per channel: where the original lives, how XENA gets it, how complete, and with what evidential value. |
| **Architecture** | From workplace via the integration layer and the intake per class to the XENA Nextcloud stack, with the steps per kind of message. Product names are generalised. |
| **Technology** | What each channel provides, the object model for chat messages, three ways to run an archive participant, and the open standards. |
| **Growth path** | Six steps, from capturing Teams as a copy to chat archived at the source. |

Use the buttons at the top to jump ahead in time and see what happens after ten days.

## Usage

Open `index.html` in a browser; no server needed. Languages: Dutch, German, English and French; append `#de`, `#en` or `#fr` to the address to pick a language for that link.

## Build

Source in `src/demo.html`, translations in `i18n/<lang>.json` (keys are the Dutch text).

```
python3 build.py
```

writes `index.html` and `MAIA - v<N>.html`. The version number is in `VERSION`.

## Licence

EUPL-1.2, see `LICENSE`.
