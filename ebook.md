---
title: "Shell Script para OSINT com Linux"
subtitle: "Automação da Inteligência de Fontes Abertas utilizando Bash"
volume: "Volume I - Fundamentos"
chapter: 1
chapter_title: "Introdução à Inteligência de Fontes Abertas (OSINT)"
author: "Gildásio Brito"
version: "0.1"
---

# Capítulo 1

# Introdução à Inteligência de Fontes Abertas (OSINT)

## Objetivos

Ao concluir este capítulo, o leitor será capaz de:

- Compreender o conceito de OSINT.
- Diferenciar dado, informação, conhecimento e inteligência.
- Conhecer o ciclo da inteligência.
- Entender as principais fontes abertas.
- Compreender a importância do Linux e do Bash na automação.

---

# 1.1 Introdução

Vivemos na era da informação.

Milhões de documentos, imagens, vídeos, certificados digitais, registros DNS, APIs públicas e repositórios são produzidos diariamente.

A Inteligência de Fontes Abertas (OSINT) consiste na coleta, organização, correlação e análise dessas informações para produzir conhecimento útil, utilizando apenas fontes públicas ou legalmente acessíveis.

Ao longo deste livro aprenderemos não apenas a utilizar ferramentas prontas, mas também a construir nossas próprias soluções em Bash para automatizar tarefas de coleta e análise.

---

# 1.2 O que é Inteligência?

No contexto profissional, inteligência representa o resultado de um processo sistemático de coleta, validação e análise de informações.

Fluxo simplificado:

```text
Dados
  ↓
Informações
  ↓
Conhecimento
  ↓
Análise
  ↓
Inteligência
```

A inteligência apoia decisões técnicas, operacionais e estratégicas.

---

# 1.3 Evolução Histórica

O conceito de utilizar fontes públicas existe há séculos.

Comerciantes, diplomatas e governos sempre utilizaram informações disponíveis para compreender cenários políticos, econômicos e militares.

Com o surgimento da Internet, o volume de dados públicos cresceu exponencialmente, tornando a automação indispensável.

---

# 1.4 O que é OSINT?

OSINT (*Open Source Intelligence*) significa Inteligência de Fontes Abertas.

É importante destacar que "Open Source", neste contexto, não significa software livre.

Refere-se ao uso de informações publicamente disponíveis para responder perguntas específicas.

Exemplos de fontes:

- Sites institucionais
- DNS
- WHOIS
- APIs
- Certificados digitais
- Portais governamentais
- Repositórios públicos
- Redes sociais
- Documentos PDF
- Imagens
- Metadados

---

# 1.5 Áreas de Aplicação

OSINT é utilizado em diversas áreas:

## Segurança da Informação

- Inventário de ativos
- Superfície de ataque
- Monitoramento

## Threat Intelligence

- IOC
- Infraestrutura maliciosa
- Correlação de indicadores

## Resposta a Incidentes

- Enriquecimento de evidências
- Investigação

## Perícia Digital

- Metadados
- Linha do tempo
- Corroboração

## Jornalismo Investigativo

- Verificação de fatos
- Pesquisa documental

## Inteligência Corporativa

- Concorrência
- Monitoramento tecnológico

---

# Resumo

Neste capítulo conhecemos os conceitos fundamentais de Inteligência de Fontes Abertas, sua evolução, aplicações e importância para a Segurança da Informação.

Nos próximos capítulos estudaremos o ciclo da inteligência, fontes abertas, ética, Linux e iniciaremos a construção do framework BashOSINT.

---

# Próximo capítulo

Capítulo 2

O Ciclo da Inteligência

- Planejamento
- Coleta
- Processamento
- Análise
- Disseminação
- Feedback

---
title: "Shell Script para OSINT com Linux"
subtitle: "Automação da Inteligência de Fontes Abertas utilizando Bash"
volume: "Volume I - Fundamentos"
chapter: 2
chapter_title: "O Ciclo da Inteligência"
author: "Gildásio Brito"
version: "0.1"
---

# Capítulo 2

# O Ciclo da Inteligência

> "A inteligência não nasce da quantidade de dados coletados, mas da qualidade da análise realizada."

---

# Objetivos

Ao concluir este capítulo o leitor será capaz de:

- compreender o conceito do Ciclo da Inteligência;
- identificar cada uma das suas etapas;
- compreender sua aplicação em atividades de OSINT;
- entender como a automação pode otimizar cada fase;
- iniciar o desenvolvimento de uma metodologia estruturada para investigações.

---

# Introdução

Toda investigação começa com uma necessidade de informação.

Imagine que uma organização deseje conhecer todos os seus ativos públicos expostos na Internet.

Responder a essa pergunta exige muito mais do que executar algumas consultas DNS ou WHOIS. É necessário seguir um processo estruturado, capaz de transformar dados dispersos em inteligência útil.

Esse processo é conhecido como **Ciclo da Inteligência**.

---

# 2.1 O que é o Ciclo da Inteligência?

O Ciclo da Inteligência é uma metodologia utilizada para transformar necessidades de informação em conhecimento capaz de apoiar decisões.

Embora existam diferentes modelos, todos possuem uma sequência lógica de atividades.

Fluxo simplificado:

```text
Planejamento
      │
      ▼
Coleta
      │
      ▼
Processamento
      │
      ▼
Análise
      │
      ▼
Disseminação
      │
      ▼
Feedback
      │
      └──────────────┐
                     │
                     ▼
              Novo Planejamento
```

Observe que o processo é contínuo.

O feedback gera novos requisitos de inteligência, reiniciando o ciclo.

---

# 2.2 Planejamento

Toda investigação deve começar com uma pergunta clara.

Essa pergunta é chamada de **Requisito de Inteligência**.

Sem planejamento, corre-se o risco de coletar milhares de informações irrelevantes.

## Exemplos

Em vez de perguntar:

> Pesquisar uma empresa.

Defina perguntas específicas:

- Quais domínios pertencem à empresa?
- Quais IPs estão associados?
- Existem subdomínios esquecidos?
- Há serviços expostos?
- Quais tecnologias são utilizadas?
- Existem certificados digitais públicos?
- Existem repositórios públicos relacionados?

Quanto mais específico o objetivo, maior será a qualidade da inteligência produzida.

---

## Boas práticas

Antes de iniciar uma investigação, responda:

- Qual problema desejo resolver?
- Quem utilizará o relatório?
- Quais fontes serão consultadas?
- Qual será o prazo?
- Existem restrições legais?
- Quais ferramentas serão utilizadas?

---

# 2.3 Coleta

Após definir o objetivo, inicia-se a coleta.

Nesta etapa são obtidas informações provenientes de diversas fontes abertas.

Exemplos:

| Fonte | Informações |
|--------|-------------|
| DNS | Registros A, AAAA, MX, TXT |
| WHOIS | Dados do domínio |
| TLS | Certificados |
| APIs | Dados estruturados |
| GitHub | Repositórios |
| Redes sociais | Perfis públicos |
| PDFs | Metadados |
| Wayback Machine | Histórico de páginas |

A coleta deve ser objetiva e direcionada aos requisitos definidos durante o planejamento.

---

# Automatizando a coleta

Uma investigação raramente envolve apenas um domínio.

Frequentemente é necessário consultar dezenas ou centenas de ativos.

É nesse momento que Shell Script se torna indispensável.

Exemplo:

```bash
#!/bin/bash

while read dominio
do
    echo "Consultando $dominio"
    dig +short "$dominio"
done < dominios.txt
```

Embora simples, esse script demonstra como automatizar uma tarefa repetitiva.

Ao longo do livro evoluiremos esse exemplo para um framework completo.

---

# 2.4 Processamento

A coleta produz grande quantidade de dados.

Esses dados normalmente apresentam:

- duplicidades;
- formatos diferentes;
- inconsistências;
- registros desnecessários.

O processamento tem como objetivo organizar essas informações.

Ferramentas importantes:

- grep
- awk
- sed
- sort
- uniq
- cut
- tr
- jq

Exemplo:

```bash
cat dominios.txt | sort | uniq
```

Esse comando remove entradas duplicadas.

---

# 2.5 Análise

Esta é a etapa mais importante do ciclo.

Coletar milhares de informações não produz inteligência.

A inteligência surge quando os dados são interpretados.

Durante a análise procura-se responder perguntas como:

- Existe um padrão?
- Existem inconsistências?
- Existem riscos?
- Existe exposição desnecessária?
- Existem oportunidades de melhoria?

A análise depende de conhecimento técnico e pensamento crítico.

---

# 2.6 Disseminação

Depois da análise, os resultados precisam ser apresentados.

O produto final pode assumir diferentes formatos:

- relatório técnico;
- dashboard;
- planilha;
- PDF;
- HTML;
- JSON;
- CSV.

Uma boa disseminação deve considerar o público-alvo.

Um gestor normalmente necessita de conclusões e riscos.

Um analista técnico pode necessitar de detalhes completos.

---

# 2.7 Feedback

O ciclo não termina após a entrega do relatório.

O cliente poderá solicitar:

- atualização dos dados;
- novas consultas;
- aprofundamento da investigação;
- inclusão de novas fontes.

Esse retorno gera um novo planejamento.

Por isso o Ciclo da Inteligência é considerado um processo contínuo.

---

# Aplicação em OSINT

Durante este livro utilizaremos esse ciclo continuamente.

Exemplo:

Planejamento

↓

Definir o domínio

↓

Coleta

↓

WHOIS

↓

DNS

↓

Subdomínios

↓

HTTP

↓

TLS

↓

Processamento

↓

Organização dos dados

↓

Análise

↓

Correlação

↓

Relatório

↓

Feedback

↓

Nova investigação

---

# Laboratório 1

## Objetivo

Compreender como o planejamento influencia a coleta.

### Exercício

Escolha um domínio público.

Liste:

- objetivo da investigação;
- perguntas que deseja responder;
- possíveis fontes abertas;
- ferramentas Linux que poderão ser utilizadas.

Não execute nenhuma consulta ainda.

Apenas planeje.

---

# Resumo

Neste capítulo estudamos o Ciclo da Inteligência.

Aprendemos que inteligência é resultado de um processo estruturado composto por:

- Planejamento;
- Coleta;
- Processamento;
- Análise;
- Disseminação;
- Feedback.

Também vimos que Bash será utilizado ao longo do livro para automatizar grande parte dessas atividades.

---

# Exercícios

1. Explique a diferença entre coleta e análise.

2. Por que planejamento é importante?

3. Cite cinco fontes abertas.

4. O que caracteriza inteligência?

5. Qual a importância do feedback?

---

# Desafio

Escolha uma organização pública.

Sem utilizar ferramentas automáticas, elabore um plano de investigação contendo:

- objetivo;
- perguntas;
- possíveis fontes;
- limitações;
- produto esperado.

Esse planejamento será utilizado em capítulos futuros.

---

## Capítulo 3

---
title: "Shell Script para OSINT com Linux"
subtitle: "Automação da Inteligência de Fontes Abertas utilizando Bash"
volume: "Volume I - Fundamentos"
chapter: 3
chapter_title: "Linux para OSINT"
author: "Gildásio Brito"
version: "0.1"
---

# Capítulo 3

# Linux para OSINT

> "O sistema operacional é a base sobre a qual toda a investigação será construída."

---

# Objetivos

Ao concluir este capítulo, o leitor será capaz de:

- compreender por que o Linux é amplamente utilizado em atividades de OSINT;
- conhecer as principais distribuições voltadas para segurança da informação;
- entender a filosofia Unix e sua relação com a automação;
- identificar as ferramentas nativas mais importantes para coleta e manipulação de dados;
- preparar uma estação de trabalho para os próximos capítulos.

---

# Introdução

Grande parte das ferramentas modernas de OSINT foi desenvolvida originalmente para sistemas baseados em Linux. Embora muitas delas também estejam disponíveis para Windows e macOS, é no Linux que elas apresentam maior integração, flexibilidade e facilidade de automação.

Isso não acontece por acaso.

O Linux foi projetado com uma filosofia simples e extremamente poderosa: construir pequenas ferramentas que realizem uma única tarefa muito bem e permitir que elas sejam combinadas para resolver problemas complexos.

Essa filosofia influenciará todo o restante deste livro.

Ao longo dos próximos capítulos, veremos como comandos aparentemente simples podem ser encadeados para automatizar investigações inteiras.

---

# 3.1 Por que utilizar Linux?

Existem diversas razões pelas quais profissionais de Segurança da Informação, Forense Digital, DevOps e OSINT utilizam Linux como plataforma principal.

Entre elas destacam-se:

- grande quantidade de ferramentas disponíveis;
- facilidade de automação;
- excelente desempenho em servidores;
- suporte a linguagens de script;
- gerenciamento de pacotes;
- estabilidade;
- flexibilidade.

Além disso, praticamente todas as ferramentas apresentadas neste livro poderão ser instaladas diretamente pelos gerenciadores de pacotes da distribuição.

---

# 3.2 A Filosofia Unix

Para compreender o Linux, é importante conhecer alguns princípios herdados do Unix.

Entre eles:

## Faça uma única coisa muito bem.

Cada programa deve resolver um problema específico.

Exemplos:

- grep → localizar padrões;
- sort → ordenar linhas;
- uniq → remover duplicidades;
- cut → extrair colunas;
- tr → substituir caracteres.

Separadamente, esses programas parecem simples.

Combinados, tornam-se extremamente poderosos.

---

## Tudo é um arquivo

No Linux, praticamente tudo pode ser tratado como arquivo.

Isso inclui:

- arquivos comuns;
- dispositivos;
- discos;
- terminais;
- sockets;
- pipes.

Essa característica facilita enormemente a automação.

---

## Programas devem cooperar

Em vez de criar aplicações gigantescas, o Unix incentiva que pequenos programas trabalhem juntos.

Exemplo:

```bash
cat dominios.txt | sort | uniq
```

Cada comando realiza uma única função.

O resultado de um é utilizado pelo próximo.

Esse mecanismo é conhecido como **pipeline** e será utilizado constantemente ao longo deste livro.

---

# 3.3 Distribuições Linux

Existem centenas de distribuições Linux.

Neste livro utilizaremos principalmente:

## Ubuntu

Uma das distribuições mais populares.

Indicada para:

- iniciantes;
- servidores;
- desenvolvimento.

---

## Debian

Reconhecida pela estabilidade.

Muito utilizada em servidores.

Grande parte das distribuições deriva do Debian.

---

## Kali Linux

Especializada em Segurança da Informação.

Possui centenas de ferramentas pré-instaladas.

Apesar de sua popularidade, neste livro utilizaremos apenas ferramentas compatíveis com distribuições convencionais.

Assim, os laboratórios poderão ser reproduzidos em Ubuntu, Debian e outras distribuições.

---

## Fedora

Distribuição patrocinada pela Red Hat.

Muito utilizada para desenvolvimento.

---

# 3.4 Estrutura de Diretórios

Antes de iniciar a automação, é importante conhecer alguns diretórios.

| Diretório | Finalidade |
|------------|------------|
| / | raiz do sistema |
| /home | diretórios dos usuários |
| /etc | arquivos de configuração |
| /usr | programas instalados |
| /var | logs e dados variáveis |
| /tmp | arquivos temporários |
| /opt | softwares opcionais |
| /bin | comandos essenciais |
| /sbin | administração do sistema |

Durante o livro trabalharemos frequentemente com esses diretórios.

---

# 3.5 Terminal

O terminal representa uma das maiores vantagens do Linux.

Enquanto muitos sistemas dependem de interfaces gráficas, praticamente toda a administração de um sistema Linux pode ser realizada pela linha de comando.

Essa característica permite:

- automação;
- execução remota;
- criação de scripts;
- integração entre ferramentas.

---

# 3.6 Ferramentas nativas importantes

Algumas ferramentas serão utilizadas praticamente em todos os capítulos.

| Ferramenta | Finalidade |
|------------|------------|
| grep | localizar padrões |
| sed | editar textos |
| awk | manipular colunas |
| cut | extrair campos |
| sort | ordenar |
| uniq | remover duplicidades |
| tr | substituir caracteres |
| xargs | construir comandos |
| find | localizar arquivos |
| jq | manipular JSON |
| curl | realizar requisições HTTP |
| wget | download de arquivos |

Nos próximos capítulos estudaremos cada uma delas detalhadamente.

---

# 3.7 Preparando o ambiente

Nos laboratórios deste livro utilizaremos uma estrutura simples de trabalho.

```text
~/bashosint/

├── scripts/
├── reports/
├── logs/
├── cache/
├── inputs/
├── outputs/
└── config/
```

Essa organização será mantida durante todo o projeto.

---

# Laboratório 1

## Objetivo

Preparar a estação de trabalho.

Crie a estrutura de diretórios:

```bash
mkdir -p ~/bashosint/{scripts,reports,logs,cache,inputs,outputs,config}
```

Verifique o resultado:

```bash
tree ~/bashosint
```

Caso o comando `tree` não esteja instalado:

Ubuntu/Debian:

```bash
sudo apt install tree
```

Fedora:

```bash
sudo dnf install tree
```

---

# Resumo

Neste capítulo compreendemos por que o Linux é a principal plataforma para atividades de OSINT. Conhecemos sua filosofia, as principais distribuições, a estrutura básica do sistema de arquivos e preparamos o ambiente que será utilizado ao longo do livro.

Nos próximos capítulos começaremos a explorar o Bash e os conceitos fundamentais de Shell Script, que servirão como base para a automação das tarefas de coleta, processamento e análise de informações.

---

# Exercícios

1. Explique a filosofia "Faça uma única coisa e faça bem".

2. O que significa dizer que "tudo é um arquivo" no Linux?

3. Qual a vantagem dos pipelines?

4. Cite três distribuições Linux adequadas para atividades de OSINT.

5. Qual a finalidade do diretório `/etc`?

---

# Desafio

Pesquise outras distribuições Linux utilizadas em Segurança da Informação, como Parrot Security OS e BlackArch Linux.

Compare suas características com Ubuntu, Debian e Kali Linux, destacando vantagens, desvantagens e possíveis cenários de uso.

---

# Conexão com o Projeto BashOSINT

Neste capítulo iniciamos a estrutura do projeto.

Criamos a árvore de diretórios que será utilizada durante todo o livro:

```text
bashosint/

├── scripts/
├── reports/
├── logs/
├── cache/
├── inputs/
├── outputs/
└── config/
```

# CAPÍTULO 4

---
title: "Shell Script para OSINT com Linux"
subtitle: "Automação da Inteligência de Fontes Abertas utilizando Bash"
volume: "Volume I - Fundamentos"
chapter: 4
chapter_title: "Bash para Analistas de Inteligência"
author: "Gildásio Brito"
version: "0.1"
---

# Capítulo 4

# Bash para Analistas de Inteligência

> "A automação começa quando deixamos de repetir comandos manualmente."

---

# Objetivos

Ao concluir este capítulo, o leitor será capaz de:

- compreender o papel do Bash na automação de tarefas de OSINT;
- conhecer a estrutura básica de um script Shell;
- entender o funcionamento do interpretador (Shell);
- utilizar variáveis, comentários e permissões;
- criar o primeiro script do projeto BashOSINT.

---

# Problema Real

Imagine que você seja um analista de Segurança da Informação.

Todos os dias, ao iniciar o expediente, você precisa executar a seguinte sequência de comandos:

```bash
date
hostname
whoami
pwd
ip addr
```

Depois copiar essas informações para um relatório.

No primeiro dia isso leva poucos segundos.

Após um mês, você terá executado a mesma sequência dezenas de vezes.

Após um ano, centenas de vezes.

A pergunta é simples:

**Por que repetir uma tarefa que pode ser automatizada?**

É exatamente para responder a esse tipo de necessidade que existe o Shell Script.

---

# 4.1 O que é um Shell?

O Shell é um programa responsável por interpretar comandos enviados pelo usuário e solicitar ao sistema operacional que os execute.

Em outras palavras, ele funciona como uma interface entre o usuário e o kernel do Linux.

Fluxo simplificado:

```text
Usuário
   │
   ▼
Shell (Bash)
   │
   ▼
Kernel Linux
   │
   ▼
Hardware
```

Sempre que digitamos um comando, ele é interpretado pelo Shell antes de ser executado.

---

# 4.2 O que é o Bash?

O Bash (*Bourne Again SHell*) é o interpretador de comandos padrão da maioria das distribuições Linux.

Além de permitir a execução de comandos interativos, ele possibilita a criação de scripts para automatizar tarefas repetitivas.

O Bash oferece recursos como:

- variáveis;
- estruturas condicionais;
- laços de repetição;
- funções;
- manipulação de arquivos;
- redirecionamentos;
- pipelines.

Ao longo deste livro utilizaremos o Bash como linguagem principal para desenvolver o framework BashOSINT.

---

# 4.3 O primeiro Script

Crie um arquivo chamado:

```text
hello.sh
```

Conteúdo:

```bash
#!/bin/bash

echo "Olá, OSINT!"
```

Salve o arquivo.

Agora conceda permissão de execução:

```bash
chmod +x hello.sh
```

Execute:

```bash
./hello.sh
```

Saída esperada:

```text
Olá, OSINT!
```

---

# Entendendo o Script

Primeira linha:

```bash
#!/bin/bash
```

Essa linha é chamada de **Shebang**.

Ela informa ao sistema qual interpretador deverá executar o script.

Sem ela, o comportamento poderá variar de acordo com o ambiente.

---

Segunda linha:

```bash
echo "Olá, OSINT!"
```

O comando `echo` envia uma mensagem para a saída padrão (terminal).

Embora seja um exemplo simples, esse comando será utilizado frequentemente para exibir mensagens, registrar informações e gerar relatórios.

---

# 4.4 Comentários

Comentários são utilizados para documentar o código.

Exemplo:

```bash
#!/bin/bash

# Primeiro script do livro

echo "Bem-vindo ao BashOSINT"
```

Comentários são ignorados pelo interpretador.

---

# 4.5 Variáveis

Variáveis armazenam informações que poderão ser utilizadas posteriormente.

Exemplo:

```bash
#!/bin/bash

NOME="Analista"

echo "Bem-vindo, $NOME"
```

Saída:

```text
Bem-vindo, Analista
```

---

Outro exemplo:

```bash
DATA=$(date)

echo "$DATA"
```

O Bash executa o comando `date` e armazena seu resultado na variável `DATA`.

---

# 4.6 Variáveis de Ambiente

O Linux possui diversas variáveis já disponíveis.

Exemplos:

```bash
echo $HOME
echo $USER
echo $PATH
echo $PWD
echo $SHELL
```

Essas variáveis serão utilizadas constantemente durante a construção do framework.

---

# 4.7 Permissões

Para executar um script é necessário conceder permissão.

```bash
chmod +x script.sh
```

Verifique:

```bash
ls -l script.sh
```

Saída:

```text
-rwxr-xr-x
```

O primeiro grupo refere-se ao proprietário do arquivo.

Os demais representam grupo e outros usuários.

---

# Na Prática

Nosso objetivo é evitar repetir comandos manualmente.

Vamos automatizar a coleta de algumas informações do sistema.

Crie o arquivo:

```text
system_info.sh
```

Conteúdo:

```bash
#!/bin/bash

echo "=============================="
echo "Informações do Sistema"
echo "=============================="

echo "Usuário : $USER"
echo "Hostname: $(hostname)"
echo "Data    : $(date)"
echo "Kernel  : $(uname -r)"
echo "Diretório Atual: $(pwd)"
```

Execute:

```bash
./system_info.sh
```

Esse será o primeiro script realmente útil do livro.

---

# Boas Práticas

- Utilize nomes descritivos para variáveis.
- Comente apenas quando necessário.
- Organize o código em blocos.
- Evite repetir comandos.
- Sempre utilize o Shebang.

---

# Armadilhas Comuns

❌ Esquecer de conceder permissão de execução.

❌ Inserir espaços na atribuição de variáveis.

Errado:

```bash
NOME = "João"
```

Correto:

```bash
NOME="João"
```

---

# Laboratório 1

Objetivo:

Criar um script que apresente:

- usuário;
- data;
- hostname;
- versão do kernel;
- tempo de atividade (`uptime`);
- memória disponível (`free -h`).

Salve esse script em:

```text
~/bashosint/scripts/
```

---

# Conexão com o Projeto BashOSINT

Neste capítulo nasce oficialmente o framework.

Estrutura atual:

```text
bashosint/

├── scripts/
│   ├── hello.sh
│   └── system_info.sh
│
├── reports/
├── logs/
├── cache/
├── config/
├── inputs/
└── outputs/
```

Esses scripts serão utilizados como base para os módulos que construiremos ao longo do livro.

---

# Resumo

Neste capítulo aprendemos:

- o que é um Shell;
- o que é o Bash;
- como funciona um script;
- o papel do Shebang;
- variáveis;
- comentários;
- permissões de execução;
- criação dos primeiros scripts.

A partir do próximo capítulo iniciaremos o desenvolvimento de scripts mais robustos, incorporando estruturas condicionais, parâmetros de linha de comando e funções reutilizáveis.

---

# Exercícios

1. Explique a função do Shebang.
2. Qual a diferença entre uma variável criada pelo usuário e uma variável de ambiente?
3. Por que um script precisa de permissão de execução?
4. Escreva um script que exiba a data, o usuário e o diretório atual.
5. Modifique o script `system_info.sh` para exibir também o espaço livre em disco (`df -h`).

---

# Desafio

Desenvolva um script chamado `coleta_basica.sh` que gere um relatório contendo:

- Data e hora;
- Nome do host;
- Usuário atual;
- Kernel;
- Interfaces de rede;
- Espaço em disco;
- Memória disponível.

Salve o relatório no diretório:

```text
~/bashosint/reports/
```

Utilize um nome baseado na data, por exemplo:

```text
relatorio_2026-07-23.txt
```

Esse será o primeiro relatório automatizado do projeto BashOSINT.

---

# Próximo Capítulo

## Capítulo 5 — Shell Script: Estruturas Fundamentais

