# Энергоприбор.AI — CRM с AI-ассистентом

**Авторы:** Шашура Сергей, Гесть Анна

## Описание проекта

SaaS CRM-система нового поколения для предприятия «Энергоприбор» и малого/среднего бизнеса СНГ.  
**Ключевая фича** — встроенный AI-ассистент, который:
- обучает сотрудников работе с CRM в реальном времени
- помогает изучать технический английский (терминология термопар, датчиков Pt100, ТХК и др.)

**Цели:** сократить время внедрения CRM на 40%, снизить затраты на обучение.

## Документация проекта

[Технико-экономическое обоснование](docs/4_1.pdf)  
[Техническое задание](docs/4_2.pdf)  
[Прототип интерфейса](docs/4_3.pdf)  
[Проектирование API](docs/4_4.pdf)

## Стек технологий

| Слой           | Технологии                                  |
|----------------|---------------------------------------------|
| Frontend       | React 18 + TypeScript + Vite + Tailwind CSS|
| Backend        | Python 3.11 + FastAPI + SQLAlchemy 2.0     |
| База данных    | PostgreSQL + Alembic                        |
| AI-ассистент   | LangChain + Ollama (Llama 3.2) / Grok API   |
| Деплой         | Docker + Docker Compose      |        

## Как запустить проект

```bash
# 1. Клонировать
git clone https://github.com/ваш-логин/energopribor-crm-ai.git
cd energopribor-crm-ai

# 2. Запуск через Docker
docker-compose up --build

# Или локально:

# Frontend
cd frontend
npm install
npm run dev    # http://localhost:5173

# Backend
cd ../backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload --port=8000

# AI-ассистент
cd ../ai_assistant
pip install -r requirements.txt
python main.py
