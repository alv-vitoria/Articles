<p align="center">
<img src="https://github.com/alv-vitoria/Articles/blob/main/assets/capa_artigo_dio_campus_expert16.jpg" 
  height="399px" 
  alt="Banner Embaixadores DIO Expert 16">
</p>

# Engenharia de Prompts: Testando, Comparando e Refinando Perguntas para IA

![Status](https://img.shields.io/badge/Status-Publicado-green)   
[![DIO Campus Expert](https://img.shields.io/badge/DIO%20Campus%20Expert-Embaixadora-6A0DAD?style=for-the-badge&logo=databricks&logoColor=white)](https://web.dio.me/articles/engenharia-de-prompts-testando-comparando-e-refinando-perguntas-para-ia-cc2e5e071bab)  
![IA](https://img.shields.io/badge/IA-Generativa-412991?style=for-the-badge&logo=openai&logoColor=white)
![NotebookLM](https://img.shields.io/badge/NotebookLM-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white)
![Prompt Engineering](https://img.shields.io/badge/Prompt-Engineering-FF6F61?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)

## Sobre o Artigo
Este artigo documenta minha jornada de estudo sobre **Inteligência Artificial e Engenharia de Prompts**, feita com apoio do NotebookLM como ferramenta de curadoria e aprendizagem ativa. O texto reúne os testes que fiz, os erros que cometi no meio do caminho e as lições que ficaram, sempre com um pé na minha origem em Gestão Comercial.

> *"Um prompt mal feito é só uma pergunta. Um prompt bem feito é uma instrução."*

---

## Introdução: a comunicação como tecnologia

Quando escrevi meu primeiro artigo aqui na DIO, falei sobre como dados bem tratados se tornam vantagem competitiva. Na época, eu estava pensando em planilhas, dashboards, funis de venda.

Porém, a mesma lógica também vale para conversar com uma Inteligência Artificial.

Prompt engineering parece, à primeira vista, um assunto 100% técnico, de quem entende de modelos de linguagem. Mas quando comecei a me aprofundar em LLMs, usando o NotebookLM como ferramenta de curadoria, percebi que a base de tudo é a habilidade de **comunicar com contexto, audiência e objetivo claros**. 

Ou seja, o objetivo é orientar um modelo de IA a produzir a resposta mais adequada ao contexto.

---

## O que é, na prática, Prompt Engineering?

Prompt engineering é a prática de formular e refinar as instruções dadas a um modelo de linguagem para obter respostas mais precisas, úteis e adequadas ao contexto. Não é sobre "enganar" a IA, é sobre se comunicar com ela de forma estratégica.

Um bom prompt geralmente carrega quatro elementos:

- **Contexto** - quem você é, qual é a situação
- **Tarefa** - o que você quer que o modelo faça
- **Formato** - como você quer receber a resposta
- **Restrições** - limites de tamanho, tom, audiência

Note que isso é quase idêntico à estrutura de um briefing comercial. A IA só trocou de nome quem recebe a instrução.

---

## Metodologia: testar, comparar, documentar

Em vez de só ler sobre as técnicas, decidi testá-las na prática, sempre comparando uma versão "ingênua" do prompt (v1) com uma versão refinada (v2). Alguns exemplos do que documentei:

### Teste 1: Definição de conceito

**Prompt v1 (genérico):**
```
O que é prompt engineering?
```
Resultado: resposta válida, mas extensa e acadêmica demais para um iniciante.

**Prompt v2 (com contexto e restrição):**
```
Explique o conceito de prompt engineering em até 3 parágrafos, como se estivesse
explicando para alguém que sabe usar ChatGPT mas nunca estudou IA formalmente.
```
Resultado: muito mais direto e útil.

**Lição:** quanto mais contexto você dá sobre *quem vai ler* a resposta, mais calibrada ela fica. Prompt vago gera resposta genérica, em IA e em proposta comercial.

### Teste 2: Chain-of-Thought (raciocínio passo a passo)

**Prompt v1:**
```
Resolva: Se João tem 3 vezes mais maçãs que Maria, e Maria tem 8,
quantas maçãs João tem a mais?
```
Resultado: resposta correta, mas resumida demais para fins de aprendizagem.

**Prompt v2 (Chain-of-Thought explícito):**  
*Solicitei uma explicação passo a passo da solução, em vez de apenas a resposta final.*
```
Resolva o problema abaixo passo a passo, mostrando cada etapa do raciocínio:
"Se João tem 3 vezes mais maçãs que Maria, e Maria tem 8, quantas maçãs João tem a mais?"
```
Resultado: raciocínio auditável, etapa por etapa.

**Dificuldade encontrada:** em problemas mais complexos, o modelo às vezes pulava etapas mesmo com CoT pedido. Solução: adicionar explicitamente `"Não pule nenhuma etapa intermediária."`

### Teste 3: Ancorando respostas nas fontes

**Prompt v1:**
```
Crie um glossário dos termos mais importantes sobre prompt engineering.
```
Resultado: lista genérica, com conceitos mal explicados.

**Prompt v2 (ancorado nos documentos carregados):**
```
Com base apenas nos documentos que estou estudando, liste os 10 termos técnicos
mais relevantes sobre prompt engineering, com definição curta (1-2 linhas) e
a fonte onde cada termo aparece.
```
Resultado: glossário preciso e rastreável.

**Lição:** no NotebookLM (e em qualquer ferramenta com RAG), ancorar o prompt nas fontes carregadas reduz alucinação e aumenta a confiabilidade da resposta.

---

## O que ainda estou aprendendo

- Prompt vago gera resposta vaga, independentemente do contexto
- Definir a audiência muda completamente a qualidade da resposta
- Pedir exemplos lado a lado ensina mais rápido que pedir definições isoladas
- A IA pode 'alucinar' com confiança; por isso, sempre valide o que realmente importa
- Em muitas ferramentas, cada nova conversa começa sem o contexto da anterior, exigindo que as informações relevantes sejam reconstruídas.

---

## Boas práticas que ficaram

- Seja específico sobre o formato de saída esperado
- Defina a audiência (iniciante vs especialista muda tudo)
- Use delimitadores para separar instrução de conteúdo (`"""`, `---`)
- Aprimore continuamente: teste, avalie, refine e nunca pare na primeira resposta.
- Não assuma que o modelo "entende" contexto implícito, sempre explicite tudo

---

## Ferramentas

- **NotebookLM** - curadoria de fontes e estudo ancorado em documentos
- **Modelos de linguagem (LLMs)** - Claude, ChatGPT e similares para testes práticos.
- **Documentação técnica** - Prompt Engineering Guide (DAIR.AI), OpenAI Cookbook, paper de Chain-of-Thought (Wei et al., 2022)

> Ferramenta não é o ponto. O hábito de testar e refinar é.

---

## Conclusão

Se no meu primeiro artigo eu disse que "dados não servem só para medir, servem para posicionar", agora eu diria algo parecido sobre prompts: **um prompt não serve só para perguntar, serve para direcionar**.

A engenharia de prompts não é uma habilidade isolada de quem programa. É uma extensão natural de quem já sabe comunicar com clareza, contexto e objetivo, só que agora aplicada a uma nova interface: a conversa com modelos de IA.

Tecnologia muda a ferramenta. A habilidade de fazer a pergunta certa continua sendo humana.

---

## Autora
Vitória Alvares dos Santos  

> Embaixadora DIO Campus Expert | Estudante de Gestão Comercial | IA Generativa | LLMs | Ciência de Dados  

### Contatos:  
[![E-mail](https://img.shields.io/badge/-Email-000?style=for-the-badge&logo=microsoft-outlook&logoColor=007BFF)](mailto:Alvares26Sa@proton.me)  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/vitória-alvares/)  

**Projeto completo no GitHub:** [notebook-ia-prompt-engineerin](https://github.com/alv-vitoria/notebook-ia-prompt-engineerin)
