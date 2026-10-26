# workbuddy-communicate-chatgpt

Shared file-exchange workspace for the WorkBuddy skill `chatgpt-commander`.

## Purpose

This public repository is the **only** file-transfer channel between:

- **ChatGPT (web, in Chrome)** — the brain / commander.
- **WorkBuddy (local desktop agent)** — the executor / EN-ZH translation bridge.

The ChatGPT web UI can fetch public raw text via `raw.githubusercontent.com`, so WorkBuddy
pushes documents, images and artifacts here and passes the Raw URLs back to ChatGPT in
plain English text. No file/image attachments are ever uploaded to the ChatGPT web UI.

## Layout

```
tasks/<task_id>/
  TASK_MANIFEST.md   # index of every shared file (category, path, summary, timestamp)
  docs/              # long documents + .en.md plain-text companions
  images/            # archived screenshots / charts / deliverable figures
  artifacts/         # generated outputs and deliverables
```

`task_id` format: `YYYYmmdd-HHMMSS-<english-slug>`.

## URLs

| Kind | Pattern |
| :--- | :--- |
| Folder | `https://github.com/pd-java/workbuddy-communicate-chatgpt/tree/<branch>/tasks/<task_id>` |
| Blob | `https://github.com/pd-java/workbuddy-communicate-chatgpt/blob/<branch>/tasks/<task_id>/<category>/<file>` |
| Raw | `https://raw.githubusercontent.com/pd-java/workbuddy-communicate-chatgpt/<branch>/tasks/<task_id>/<category>/<file>` |

## Notes

- Every task gets its own folder; nothing is shared across tasks.
- Binary documents (`.docx` / `.pdf` / `.xlsx` / `.pptx`) are always accompanied by an
  extracted-and-translated `<name>.en.md` so the commander can read them as plain text.
