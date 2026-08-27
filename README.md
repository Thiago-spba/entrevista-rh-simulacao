# 💼 Simulador de Entrevistas Corporativas — RH & Competências

Uma aplicação web *single-page* em formato de flashcards interativos, desenvolvida para guiar a equipe gestora e pedagógica na condução de simulações de entrevistas de emprego para estudantes do Ensino Médio e Técnico.

---

## 🎯 Sobre o Projeto

O projeto simula o processo seletivo da empresa fictícia **Nexus Virtual Solutions** (focada no desenvolvimento de sistemas web, mobile e softwares), avaliando candidatos para vagas de **Estágio e Desenvolvedor(a) Júnior**. 

A ferramenta foi projetada para uso direto no celular dos entrevistadores (direção escolar/RH), oferecendo uma dinâmica ágil (3 a 5 minutos por candidato), intuitiva e sem necessidade de folhas impressas.

---

## 🚀 Funcionalidades da Aplicação

- **Flashcards em 3 Etapas:**
  1. **Passo 1 (Situação):** Contexto e pergunta para leitura ao candidato.
  2. **Passo 2 (Alternativas):** Quatro opções de múltipla escolha para orientar a resposta do aluno.
  3. **Passo 3 (Gabarito & Dica RH):** Resposta correta acompanhada de pontos-chave para a direção avaliar a postura, comunicação e raciocínio.
- **Sorteio Inteligente Sem Repetição:** Sistema em JavaScript que gerencia o banco de questões ativas e descartadas, garantindo que candidatos consecutivos não recebam as mesmas perguntas.
- **Cronômetro Integrado:** Timer de 3 e 5 minutos com alertas visuais para controle do tempo da dinâmica.
- **Interface *Warm Tech*:** Design moderno com paleta suave em tons creme/bege, proporcionando leitura agradável e sem ofuscamento em ambientes iluminados.
- **Filtros por Categoria:** Navegação entre questões Comportamentais (*Soft Skills*) e Técnicas (*Hard Skills*).

---

## 📚 Eixos Pedagógicos Avaliados

As questões do simulador foram extraídas dos materiais curriculares das seguintes disciplinas:

1. **Competências e Habilidades no Mercado de Trabalho:**
   - Persona profissional, etiqueta diária e *dress code*.
   - Comunicação corporativa (formalidade suave, clareza em e-mails e chats corporativos).
   - Postura, recepção de feedback (Modelos SCI e Sanduíche), ética profissional e proatividade.

2. **Desenvolvimento de Sistemas (Lógica e Python):**
   - Vetores e listas unidimensionais (indexação base 0, laço `for`, `len()` e busca linear).
   - Matrizes bidimensionais (tabelas 2D, índices `[linha][coluna]` e laços aninhados).
   - Modularização e funções (`def`, parâmetros, argumentos, `return` e escopo local vs. global).

---

## 🛠️ Como Publicar no GitHub Pages

Por ser um arquivo único (`index.html`), a publicação é simples e gratuita:

1. Crie um novo repositório no seu GitHub (ex.: `simulador-entrevista`).
2. Faça o upload do arquivo `index.html` e deste `README.md`.
3. No repositório, acesse **Settings** > **Pages** (no menu lateral esquerdo).
4. Na seção **Branch**, selecione `main` (ou `master`) e clique em **Save**.
5. Em poucos instantes, o GitHub gerará um link público (ex.: `https://seu-usuario.github.io/simulador-entrevista/`), pronto para ser acessado pelo celular da direção ou via QR Code.

---

## 👨‍🏫 Idealização e Autoria

* **Prof. Thiago Fernando**
  * Graduando em Engenharia de Computação
  * Licenciado em Matemática
  * Componentes: *Carreiras e Competências* & *Desenvolvimento de Sistemas*
  * Rede Estadual de Ensino de São Paulo / Educação Profissional Paulista

---

## 📄 Licença

Projeto desenvolvido para fins educacionais e pedagógicos. Livre para adaptação e aplicação em sala de aula.
