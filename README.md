# Mini-RAG-Covid-19 

**Mini-RAG-Covid-19** คือระบบตอบคำถามอัตโนมัติ (Question Answering System) ที่พัฒนาด้วยเทคนิค **GraphRAG** (Graph Retrieval-Augmented Generation) เพื่อให้ข้อมูลเกี่ยวกับ COVID-19 ได้อย่างแม่นยำ โดยผสานพลังระหว่างความสัมพันธ์ของข้อมูล (Graph) และการค้นหาเชิงความหมาย (Semantic Search)

โปรเจกต์นี้เน้นความรวดเร็ว (Low Latency) และความถูกต้องของบริบทภาษาไทย

## Tech Stack

* **LLM (Reasoning):** [Google Gemini 2.5 Flash-Lite](https://ai.google.dev/) - โมเดลที่รวดเร็วและประหยัดทรัพยากร
* **Database:** [Neo4j](https://neo4j.com/) - Graph Database สำหรับเก็บข้อมูลแบบ Nodes และ Relationships พร้อม Vector Index
* **Embedding:** `sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2` - แปลงข้อความเป็น Vector (รองรับภาษาไทย)
* **Vector Search:** Neo4j Vector Index (FAISS)
* **Framework:** LangChain & Python

## Prerequisites
* Python 3.9 ขึ้นไป
* บัญชี [Neo4j AuraDB](https://neo4j.com/cloud/platform/aura-graph-database/) (ฟรี) หรือ Neo4j Desktop
* Google AI Studio API Key
## การตั้งค่า Environment Variables (Configuration)



โปรเจกต์นี้จำเป็นต้องใช้ API Keys เพื่อเชื่อมต่อกับ Neo4j และ Google Gemini

    ```

    NEO4J_URI=bolt://your-neo4j-uri:7687

    NEO4J_USERNAME=neo4j

    NEO4J_PASSWORD=your-secure-password

    GOOGLE_API_KEY=your-google-api-key

    ```
