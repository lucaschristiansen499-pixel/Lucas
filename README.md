# Lucas — School Support Tools

Reference materials and a small assistive tool built to support Lucas at school, consolidated per `docs/lucas_support_tools_build_requirements.md`.

## Contents

- **`notecard/lucas_notecard.html`** — source for "Lucas's Notecard," a private Claude Artifact with two modes:
  - *Lecture notes*: turns an AI Pocket transcript/summary into a structured study card (TL;DR, terms, numbered steps, worked examples, watch-outs, a homework checklist, and a flagged "unclear — don't guess" section).
  - *Break it down*: turns an assignment or brain-dump into a short, checkable list of concrete steps.
  - Live artifact: https://claude.ai/artifact/W9gNFyg4QHN7y6i1Mq3QUf (private — share with Lucas's account before he can use it independently).
- **`notecard/build_quickguide.py`** — generates `Lucas_Notecard_QuickGuide.docx`, a printable one-page quick-reference for Lucas covering both modes step by step. Regenerate with `python3 notecard/build_quickguide.py`.
- **`support-overview/build_lucas_doc.py`** — generates `Lucas_Support_Overview.docx`, a working reference covering background, the neuropsychological evaluation, current Marmion Academy accommodations and gaps, the in-progress AI Pocket accommodation request, the PlusPortals→Google Calendar reminder setup, this toolkit, and open items. Regenerate after editing with:
  ```
  pip install python-docx
  python3 support-overview/build_lucas_doc.py
  ```
- **`docs/lucas_support_tools_build_requirements.md`** — the original requirements/spec this project was built against.

## Note on sensitive content

`support-overview/Lucas_Support_Overview.docx` contains detailed medical and evaluation information. It's included in this repo at the account owner's request; treat repo access accordingly.
