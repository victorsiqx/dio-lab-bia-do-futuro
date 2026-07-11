Vic, o Educador Financeiro 💰
Este projeto apresenta o Vic, um agente de IA focado em educação financeira, desenvolvido para auxiliar usuários na compreensão de conceitos básicos de finanças pessoais, análise de perfil de investidor e gestão de transações, de forma didática e segura.

🚀 Funcionalidades
Educação Financeira: Explicação de produtos e conceitos financeiros usando analogias simples.

Personalização: Respostas baseadas nos dados do usuário (perfil, renda e histórico).

Segurança: Agente treinado para filtrar perguntas fora do escopo financeiro e evitar recomendações de investimento direto.

Interface Interativa: Desenvolvida em Python com Streamlit para uma experiência fluida.

🛠️ Tecnologias Utilizadas
Linguagem: Python

Framework de Interface: Streamlit

IA Local: Ollama (rodando modelo llama3:8b)

Manipulação de Dados: Pandas e JSON

📂 Estrutura do Repositório
/src: Código-fonte principal da aplicação (app.py).

/data: Base de conhecimento (JSON/CSV) com perfil, transações e produtos financeiros.

/docs: Documentação completa de projeto, prompts, métricas e pitch.

🏁 Como Rodar
Instale o Ollama e baixe o modelo: ollama run llama3:8b

Instale as dependências: pip install -r requirements.txt

Execute a aplicação: streamlit run src/app.py

💡 Sobre o Projeto
Desenvolvido como parte do laboratório de IA da DIO, este projeto demonstra como integrar LLMs locais a bases de conhecimento estruturadas para criar assistentes educacionais especializados.
