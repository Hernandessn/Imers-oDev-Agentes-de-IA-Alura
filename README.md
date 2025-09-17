
# Imersão Dev Agentes de IA – Alura + Google Gemini

Este projeto é resultado da **Imersão Dev Agentes de IA** realizada entre 9 e 15 de setembro, ministrada pela **Alura** em parceria com **Google Gemini**, com os professores **Vini, Carol e Fabrício**.

O objetivo do projeto foi aprender na prática a criar **agentes inteligentes** capazes de automatizar processos e integrar **IA generativa** com bases de conhecimento.

---

## 💻 Tecnologias Utilizadas

* **Python**
* **LangChain** – Para criação e integração de agentes de IA.
* **LangGraph** – Para orquestração do fluxo de decisões do agente.
* **Google Gemini API** – Modelo de linguagem generativa para respostas inteligentes.
* **Pydantic** – Para validação de saída estruturada do agente.
* **FAISS** – Armazenamento de embeddings para RAG (retrieval-augmented generation).
* **PyMuPDF** – Carregamento e leitura de PDFs para construção da base de conhecimento.

---

## ⚙️ Funcionalidades

1. **Triagem automática de solicitações**

   * Classifica pedidos em: `AUTO_RESOLVER`, `PEDIR_INFO` ou `ABRIR_CHAMADO`.
   * Define urgência e campos faltantes, quando aplicável.

2. **RAG (Retrieval-Augmented Generation)**

   * Consulta documentos internos (PDFs) para fornecer respostas precisas e contextualizadas.

3. **Orquestração com LangGraph**

   * Define nós de fluxo: `triagem`, `auto_resolver`, `pedir_info`, `abrir_chamado`.
   * Conecta decisões condicionais para simular um agente inteligente real.

4. **Testes práticos**

   * Perguntas simuladas para validar comportamento do agente.
   * Exibição de respostas e citações dos documentos consultados.

---

## 📝 Exemplo de Uso

```python
from agent_module import grafo

pergunta = "Posso reembolsar a internet?"
resposta_final = grafo.invoke({"pergunta": pergunta})

print(resposta_final["resposta"])
if resposta_final.get("citacoes"):
    for c in resposta_final["citacoes"]:
        print(f"{c['documento']} - Página {c['pagina']}: {c['trecho']}")
```

---

## 🎯 Aprendizados

* Integração de **IA generativa** com fluxos de trabalho reais.
* Uso de **embeddings e RAG** para fornecer respostas contextualizadas.
* Estruturação de agentes complexos e orquestração de decisões.
* Prática com **LangChain, LangGraph e Google Gemini**.

---

## 📌 Observações

* O código está configurado para rodar em **Google Colab**.
* É necessário configurar a variável de ambiente `GEMINI_API_KEY` com sua chave do Google Gemini.




