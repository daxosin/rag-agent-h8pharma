# rag-agent-h8pharma
rag-agent-h8pharma/
│
├── /backend/                 → Code Flask LangChain sur Replit (serveur RAG)
│   ├── app.py
│   ├── rag_pipeline.py
│   └── requirements.txt
│
├── /supabase/               → SQL schema + scripts d’indexation + accès API
│   ├── schema.sql
│   ├── insert_example_data.sql
│   └── supabase.env.example
│
├── /n8n/                    → JSON templates des workflows
│   └── ingest_google_drive_to_supabase.json
│
├── /docs/                   → Captures écran, tutoriels, configs
│   ├── setup_supabase.md
│   ├── setup_replit.md
│   └── setup_n8n.md
│
├── /examples/               → Données de test
│   └── exemple_contrat.pdf
│
├── prompts.md               → Prompts utilisés pour la génération RAG
├── README.md                → Présentation du projet
└── LICENSE
