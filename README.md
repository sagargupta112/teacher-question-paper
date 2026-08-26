[README.md](https://github.com/user-attachments/files/31454382/README.md)
# teacher-question-paper# VedaAI Answer Sheet Review

Static frontend prototype for the VedaAI hiring assignment.

## Included
- Question paper + student answer sheet upload UI
- File validation (PDF/images, 25 MB)
- Processing progress states
- Printed question list with labelled sub-parts (e.g. 3(a), 3(b))
- Out-of-order/unanswered states represented in the review model
- Side-by-side question/answer review workspace
- Exact answer-region highlight interaction
- Per-question score and AI-style feedback panel
- Responsive layout

## Production OCR/AI integration
The demo currently uses a deterministic sample review dataset so the UI is fully runnable without API keys. For production, replace the processing handler with:
1. PDF/image rasterization (PDF.js)
2. OCR (Tesseract.js or a vision API)
3. Question segmentation preserving printed numbering and sub-parts
4. Handwriting OCR with word/line bounding boxes
5. LLM/embedding answer mapping, including out-of-order and unmatched answers
6. Region aggregation from matched OCR boxes, with page number + normalized coordinates
7. Grading/feedback model

The highlight UI already accepts normalized `top/left/width/height` coordinates and can be driven directly from OCR bounding boxes.

## Deploy
Upload the folder to Vercel, Netlify, GitHub Pages, or any static host. `index.html` is the entry point.
