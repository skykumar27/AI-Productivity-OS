# AI Productivity OS

A personal productivity platform that turns notes and meetings into prioritized tasks, auto-generated timetables, and smart reminders.

## Features
- AI Task Generator (notes → actionable tasks)
- Meeting Summarizer (audio/text → summary, decisions, action items)
- Auto Time-table Generator (calendar-aware scheduling)
- Smart Reminders & Notifications

## Architecture
- Frontend: React + Tailwind
- Backend: Java Spring Boot (APIs, auth)
- ML Microservices: Python (FastAPI) running Transformer models (T5/BART), Whisper for ASR
- DB: MongoDB (notes/tasks), Postgres (users)
- Storage: S3-compatible
- Queue: Redis + Celery

## Getting Started
1. Clone repo
2. Start services via Docker Compose: `docker-compose up`
3. Set environment variables for DB, S3, OAuth
4. Start ML services (see `/ml/README.md`) — includes pretrained model endpoints
5. Run frontend: `cd frontend && npm start`

## Model & Data
- Summarizer: fine-tuned `facebook/bart-large-cnn`
- Task extractor: fine-tuned `t5-small` (training scripts in `/ml/train_task_extractor.ipynb`)
- Datasets: CNN/DailyMail (summarization), AMI Meeting Corpus (meeting data). Custom labeled dataset for note→task mapping in `/data/tasks`.

## Contributing
PRs welcome. For dataset contributions, follow `/data/README.md`.

## Demo
Include GIF or link to deployed demo.

## License
MIT
