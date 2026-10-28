# AI Meeting Minutes

> 🇧🇷 [Versão em português abaixo](#-português)

Every evening, Zoom transcripts become formatted meeting minutes, go out for e-signature, and the signed PDF is filed automatically. In production since Oct 2026.

```
Zoom API (transcripts) ──► Gemini (minutes) ──► Google Docs template ──► DOCX + transcript on Drive
                                                                     └──► AI meeting feedback (with approval)
Autentique webhook (signed) ──► find the meeting folder ──► save "SIGNED.pdf" (fallback folder + Chat alert)
```

## Impact

**20 min → 0 min of manual work per meeting, 20+ meetings/month (~7 h/month saved, estimated).**

## Workflows

| File | What it does |
|---|---|
| `01-zoom-to-minutes-gemini` | Daily: fetch transcripts, generate the minutes with Gemini, fill the Docs template, save DOCX + transcript |
| `02-esignature-webhook-filing` | Receives the signed-document webhook and files the PDF in the right meeting folder |
| `03-recordings-to-youtube-private` | Moves recordings from Drive to private YouTube to free storage, logging each upload |

**Stack:** n8n, Zoom API, Gemini, Google Docs/Drive, Autentique (webhooks), YouTube Data API.

Credentials, IDs, e-mails, URLs and names were replaced with placeholders.

---

## 🇧🇷 Português

Toda noite as transcrições do Zoom viram ATA formatada no modelo da empresa, vão para assinatura eletrônica e o PDF assinado é arquivado na pasta da reunião. **Impacto:** 20 min → 0 min de trabalho manual por ATA, com mais de 20 ATAs por mês. Workflows sanitizados.
