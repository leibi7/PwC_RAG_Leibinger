# Agentic RAG (Local GGUF via llama-cpp + Local PDFs)

Ez a projekt egy **Agentic RAG (Retrieval-Augmented Generation)** prototípus, amely bemutatja az agentikus működést (autonóm döntéshozatal, részfeladat-bontás, visszacsatolás).  
A rendszer kizárólag helyi erőforrásokra épít: PDF dokumentumokból dolgozik, és egy helyi GGUF modell-t használ a `llama-cpp-python` könyvtárral. Nem igényel API-kulcsokat.

---

- Autonóm döntéshozatal (LangGraph)
- Részfeladat-bontás (Planner)
- Visszacsatolás (Critic → refine / next)
- Teljesítménymérés és bottleneck grafikon
- Gyors tesztek (smoke tests)
- Prezentálható notebook, példákkal

---

## Mappa szerkezet
```
agentic_rag_project/
  README.md
  DOCUMENTATION.md
  requirements.txt
  config.yaml
  agentic_rag_refined.ipynb     <-- a fő notebook
  data/
    pdfs/                       <-- ide kerülnek a PDF-ek (Example pdf már benne)
  index/                        <-- FAISS index (futás közben generálódik)
  models/                       <-- itt van a GUFF modell (Cserélhető, de át kell írni a config.yaml-ben a modell nevét)
```

---

## Használat

1. **Modellek és adatok előkészítése**
   - Tedd a feldolgozni kívánt PDF-eket a `./data/pdfs/` mappába.

2. **Környezet létrehozása és telepítés**
   ```bash

   pip install -r requirements.txt

   ```

3. **Notebook futtatása**
   Nyisd meg az `agentic_rag_refined.ipynb` fájlt, és futtasd a cellákat.

---

## Függőségek
A fő könyvtárak:
- `pypdf` (PDF feldolgozás)
- `faiss-cpu` (vektorkeresés)
- `sentence-transformers`, `torch` (embedding és reranker)
- `langgraph`, `langchain` (agentikus logika)
- `llama-cpp-python` (helyi GGUF modell)
- `matplotlib`, `pandas`, `numpy` (elemzés és megjelenítés)

Részletes lista: [requirements.txt](requirements.txt)

---

## Dokumentáció
A rendszer működésének részletes leírását lásd a [Leibinger_RAG_Dokumentacio.pdf](Leibinger_RAG_Dokumentacio.pdf) fájlban.

---
