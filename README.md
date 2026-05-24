import React, { useState, useEffect, useMemo } from 'react';
import { BookOpen, Check, ChevronRight, Menu, X, Play, ArrowLeft, ArrowUpRight, Sparkles } from 'lucide-react';

// ============================================
// CONTEÚDO EXPANDIDO - ENCCEJA ENSINO MÉDIO
// ============================================

const COURSE_DATA = {
  areas: [
    {
      id: 'linguagens',
      title: 'Linguagens, Códigos e suas Tecnologias',
      shortTitle: 'Linguagens',
      number: '01',
      color: '#FF5252',
      modules: [
        {
          id: 'lng-1',
          title: 'Interpretação de Texto',
          topics: [
            {
              id: 'lng-1-1',
              title: 'Tipos de texto',
              searchQuery: 'tipos de texto narrativo dissertativo Encceja',
              content: `Existem cinco tipos textuais que você precisa identificar de cabeça. **Tipo** é a estrutura interna do texto — o "esqueleto". Não confunda com gênero (que é a forma social, como notícia, carta, poema).

**1. Narrativo**
Conta uma história com personagens, tempo, espaço e enredo. Tem começo, meio e fim. Exemplos: contos, romances, crônicas, fábulas, lendas.
Marcador principal: verbos de ação no passado ("foi", "correu", "disse").

**2. Descritivo**
Descreve em detalhes uma pessoa, lugar, objeto ou cena. Usa muitos adjetivos e dá uma "fotografia" em palavras.
Marcador: predomínio de adjetivos e verbos de estado ("era alto", "tinha olhos verdes").

**3. Dissertativo-argumentativo**
Apresenta uma tese e defende com argumentos. É o tipo cobrado na **redação do Encceja**. Não conta história, não descreve — argumenta.
Marcador: conectivos lógicos ("portanto", "porque", "no entanto").

**4. Expositivo**
Explica um assunto sem opinião do autor. Apenas apresenta informação. Exemplos: verbetes de dicionário, textos didáticos, enciclopédias.
Marcador: linguagem neutra, definições, dados.

**5. Injuntivo (instrucional)**
Dá instruções, orienta o leitor a fazer algo. Exemplos: receitas culinárias, manuais, bulas de remédio, tutoriais.
Marcador: verbos no imperativo ("misture", "adicione", "não exceda").

**Dica de prova:** identifique pela função principal do texto. Se conta uma história → narrativo. Se defende uma ideia → dissertativo-argumentativo. Se ensina a fazer → injuntivo.

**Atenção:** um mesmo texto pode misturar tipos. Uma crônica (narrativa) pode ter trechos descritivos. O Encceja pergunta qual é o tipo **predominante**.`
            },
            {
              id: 'lng-1-2',
              title: 'Gêneros textuais',
              searchQuery: 'gêneros textuais aula',
              content: `**Gênero** é diferente de **tipo**. Tipo é a estrutura interna (narrar, descrever, argumentar). Gênero é a forma social que o texto assume na vida real.

**Gêneros jornalísticos:**
- Notícia: relata fato recente, linguagem objetiva
- Reportagem: notícia aprofundada, com mais contexto e fontes
- Editorial: opinião do veículo (jornal/revista)
- Artigo de opinião: opinião assinada por um autor

**Gêneros literários:**
- Conto, novela, romance: narrativas ficcionais de tamanhos diferentes
- Crônica: texto curto sobre o cotidiano, mistura humor e reflexão
- Poema: usa linguagem figurada, versos, ritmo

**Gêneros visuais (caem muito):**
- Charge: desenho com crítica política/social atual
- Cartum: desenho de humor sem referência ao momento
- Tirinha: pequena história em quadrinhos
- Meme: imagem com humor da internet

**Gêneros do dia a dia:**
- Carta, e-mail, bilhete
- Anúncio publicitário, propaganda
- Postagem de rede social
- Receita, manual de instruções

**O que a prova pergunta:**
1. Qual o gênero do texto apresentado?
2. Qual a função social (informar, convencer, divertir, ensinar)?
3. A quem o texto se dirige (público-alvo)?
4. Qual a intenção do autor?

**Sempre observe:** onde foi publicado, que linguagem usa, e por que foi escrito.`
            },
            {
              id: 'lng-1-3',
              title: 'Ideia principal e secundárias',
              searchQuery: 'como identificar ideia principal texto Encceja',
              content: `**Ideia principal** é o assunto central do texto — aquilo sobre o que ele realmente fala. Geralmente está no primeiro parágrafo ou pode ser resumida em uma única frase.

**Como encontrar a ideia principal:**

1. Leia o texto **inteiro** primeiro, sem grifar nada
2. Pergunte-se: "Sobre o que isso fala, no fundo?"
3. A resposta em uma frase é a ideia principal
4. Confira: as outras frases do texto sustentam essa ideia? Se sim, você acertou.

**Ideias secundárias** sustentam, exemplificam ou desenvolvem a ideia principal. Elas dão detalhes, dados, exemplos.

**Exemplo prático:**

> "A reciclagem é fundamental para o meio ambiente. Reciclar papel economiza árvores. Reciclar plástico reduz a poluição dos oceanos. Reciclar metal poupa energia da mineração. Por isso, todo cidadão deveria separar seu lixo."

- **Ideia principal:** a importância da reciclagem para o meio ambiente
- **Ideias secundárias:** economia de árvores, redução da poluição, economia de energia

**Armadilha clássica do Encceja:**
As alternativas trazem informações verdadeiras do texto, mas que não são a ideia central. Você lê e pensa "isso está no texto, deve ser certo". Cuidado: **detalhe verdadeiro ≠ ideia principal**.

**Dica final:** o título e a primeira frase geralmente apontam a ideia principal. A conclusão também costuma retomar.`
            },
            {
              id: 'lng-1-4',
              title: 'Figuras de linguagem',
              searchQuery: 'figuras de linguagem metáfora metonímia Encceja',
              content: `Figuras de linguagem são recursos que dão expressividade ao texto. As mais cobradas:

**Metáfora:** comparação implícita, sem palavra de comparação.
Ex: "Meu coração é uma fogueira."
(coração não é fogueira, mas a comparação sugere paixão)

**Comparação (símile):** comparação explícita, com "como", "tal qual", "feito".
Ex: "Forte como um touro."

**Metonímia:** parte pelo todo, marca pelo produto, autor pela obra.
Ex: "Comprei uma Coca" (refrigerante, não a marca)
Ex: "Li Machado de Assis" (a obra dele, não a pessoa)

**Hipérbole:** exagero proposital.
Ex: "Já te disse mil vezes."
Ex: "Estou morrendo de fome."

**Ironia:** dizer o oposto do que se pensa, para criticar ou ironizar.
Ex: "Que dia maravilhoso!" (durante uma tempestade)

**Personificação (prosopopeia):** dar características humanas a coisas, animais ou ideias abstratas.
Ex: "O vento sussurrou no meu ouvido."
Ex: "A esperança me abraçou."

**Antítese:** ideias opostas no mesmo trecho.
Ex: "É triste e alegre ao mesmo tempo."
Ex: "Choro de rir."

**Eufemismo:** suavizar uma expressão desagradável.
Ex: "Faltou com a verdade" (em vez de "mentiu")
Ex: "Passou desta para melhor" (em vez de "morreu")

**Pleonasmo:** repetição de ideia para reforço.
Ex: "Vi com meus próprios olhos."

**Onomatopeia:** palavra que imita som.
Ex: "Tic-tac do relógio", "miau", "buuum"

**Dica:** identifique a figura pelo **efeito** que ela cria — exagero (hipérbole), oposição (antítese), substituição (metonímia), comparação implícita (metáfora).`
            }
          ]
        },
        {
          id: 'lng-2',
          title: 'Gramática Essencial',
          topics: [
            {
              id: 'lng-2-1',
              title: 'Classes de palavras',
              searchQuery: 'classes gramaticais português aula completa',
              content: `As 10 classes gramaticais. Você precisa identificar pela **função na frase**, não decorar definições.

**1. Substantivo** — nomeia seres, coisas, sentimentos, lugares.
Ex: casa, amor, João, liberdade, mesa.

**2. Adjetivo** — caracteriza o substantivo.
Ex: bonito, alto, brasileiro, inteligente.

**3. Verbo** — indica ação, estado ou fenômeno.
Ex: correr, ser, estar, chover, existir.

**4. Advérbio** — modifica verbo, adjetivo ou outro advérbio. Indica circunstância (tempo, lugar, modo, intensidade).
Ex: rapidamente, muito, ontem, aqui, bem.

**5. Pronome** — substitui ou acompanha o substantivo.
- Pessoais: eu, tu, ele, nós, vós, eles
- Possessivos: meu, teu, seu, nosso
- Demonstrativos: este, esse, aquele
- Indefinidos: algum, nenhum, todo
- Interrogativos: que, quem, qual

**6. Artigo** — define (o, a, os, as) ou indefine (um, uma, uns, umas) o substantivo.

**7. Numeral** — quantifica ou ordena.
- Cardinais: um, dois, três
- Ordinais: primeiro, segundo
- Multiplicativos: dobro, triplo
- Fracionários: meio, terço

**8. Preposição** — liga palavras estabelecendo relação.
Ex: de, em, para, com, por, sobre, entre.

**9. Conjunção** — liga orações.
- Aditivas: e, nem, mas também
- Adversativas: mas, porém, contudo
- Causais: porque, pois, já que
- Concessivas: embora, apesar de

**10. Interjeição** — expressa emoção súbita.
Ex: Ah!, Oba!, Ufa!, Nossa!

**Dica de prova:** o Encceja foca em identificar a classe pela **função**, não pela aparência.
- "Andando rápido" → "rápido" aqui é **advérbio** (modifica o verbo "andar"), não adjetivo.
- "Vi um homem rápido" → "rápido" aqui é **adjetivo** (caracteriza "homem").
- "O **andar** é bom para a saúde" → "andar" aqui é **substantivo** (o ato de andar).`
            },
            {
              id: 'lng-2-2',
              title: 'Concordância verbal e nominal',
              searchQuery: 'concordância verbal nominal regras Encceja',
              content: `**Concordância verbal:** o verbo concorda com o sujeito em número (singular/plural) e pessoa (1ª, 2ª, 3ª).

- "Os meninos correm." (plural com plural)
- "Eu corro, tu corres, ele corre."

**Regras especiais que caem muito:**

**1. Sujeito coletivo:** verbo no singular.
- "O **grupo** chegou cedo." ✓
- "A **multidão** gritava." ✓

**2. "A maioria de" + plural:** ambos aceitos.
- "A maioria dos alunos foi aprovada." ✓
- "A maioria dos alunos foram aprovados." ✓

**3. Verbo "haver" no sentido de existir:** sempre singular.
- "Havia muitas pessoas." ✓
- "Houve problemas." ✓
(NÃO existe "haviam pessoas")

**4. "Fazer" indicando tempo:** sempre singular.
- "Faz dois anos que estudo." ✓
- "Fazia horas que esperava." ✓

---

**Concordância nominal:** artigos, adjetivos, pronomes e numerais concordam com o substantivo em gênero e número.

- "As casas bonitas estão vendidas."
- "Vi muitas pessoas felizes."

**Casos especiais cobrados:**

**1. "É proibido / É permitido / É necessário":**
- Sem artigo, fica no masculino: "É proibido entrada."
- Com artigo, concorda: "É proibida a entrada."

**2. "Bastante":**
- Pronome (quantifica): plural. "Bastantes pessoas vieram."
- Advérbio (intensifica): invariável. "Elas são bastante inteligentes."

**3. "Anexo" e "incluso":** concordam com o substantivo.
- "Segue anexo o documento." (masculino)
- "Segue anexa a carta." (feminino)

**Erro clássico que cai:** "Fazem dez anos" → ERRADO. O certo é **"Faz dez anos"**.`
            },
            {
              id: 'lng-2-3',
              title: 'Pontuação',
              searchQuery: 'pontuação vírgula regras aula',
              content: `**Vírgula — usos principais:**

**1. Separar itens de uma lista:**
"Comprei pão, leite, ovos e café."
(antes do último "e", não usa vírgula)

**2. Isolar aposto** (explicação do nome):
"Wesley, designer brasileiro, mora em Lages."

**3. Antes de conjunções adversativas** (mas, porém, contudo, todavia):
"Estudei muito, mas não passei."

**4. Separar adjuntos adverbiais deslocados** (tempo, lugar, modo no início da frase):
"Ontem, fui ao mercado."
"Em São Paulo, faz calor."

**5. Vocativo** (chamamento):
"João, venha aqui!"
"Olha, Maria, isso é sério."

---

**Erros clássicos que zeram a redação:**

❌ Vírgula entre sujeito e verbo:
- "O aluno, estudou muito." ERRADO
- "O aluno estudou muito." CERTO

❌ Vírgula entre verbo e complemento:
- "Comprei, um livro novo." ERRADO
- "Comprei um livro novo." CERTO

---

**Outros sinais:**

**Ponto e vírgula (;):** separa ideias longas dentro do mesmo período, ou itens de uma enumeração extensa.

**Dois pontos (:):** introduzem citação, enumeração ou explicação.
- "Comprei três coisas: pão, leite e ovos."

**Travessão (—):** introduz fala em diálogo ou destaca uma informação.
- "Wesley — designer de Lages — criou esta plataforma."

**Reticências (...):** indicam suspensão ou pensamento incompleto.
- "Eu queria dizer que..."

**Aspas (" "):** indicam citação, ironia ou destaque de palavra estrangeira.`
            }
          ]
        },
        {
          id: 'lng-3',
          title: 'Redação Dissertativa-Argumentativa',
          topics: [
            {
              id: 'lng-3-1',
              title: 'Estrutura da redação',
              searchQuery: 'redação Encceja estrutura dissertativa argumentativa',
              content: `A redação do Encceja tem **até 30 linhas** e segue a estrutura clássica de 4 parágrafos. Nota mínima: 5 de 10 pontos.

**1. INTRODUÇÃO (1 parágrafo, 4-6 linhas)**

Apresente o tema e mostre sua **tese** (sua opinião, o que vai defender).

Estrutura sugerida:
- 1ª frase: contextualize o tema (dado, fato histórico, citação)
- 2ª frase: apresente o problema
- 3ª frase: sua tese (o que defende)

Exemplo (tema "Importância da educação"):
> "Desde a Constituição de 1988, a educação é um direito fundamental no Brasil. No entanto, milhões de jovens e adultos ainda não concluíram a escolaridade básica. Diante disso, é necessário valorizar políticas públicas como o Encceja, que abrem portas para quem busca recomeçar."

**2. DESENVOLVIMENTO (2 parágrafos, 6-8 linhas cada)**

Cada parágrafo defende **um argumento diferente**. Use:
- Dados e estatísticas (mesmo aproximados)
- Exemplos do cotidiano
- Fatos históricos
- Citações de pensadores (use poucas e seguras)

Estrutura de cada parágrafo:
- Conectivo + ideia principal
- Argumento/exemplo
- Fechamento que liga ao próximo parágrafo

**3. CONCLUSÃO (1 parágrafo, 4-6 linhas)**

Retome a tese e proponha **uma solução** (intervenção) — quem deve fazer o quê, como, e com qual finalidade.

Exemplo:
> "Portanto, é fundamental que o Estado amplie o acesso a programas como o Encceja, que a sociedade civil divulgue essas oportunidades, e que cada indivíduo busque sua certificação. Só assim será possível construir um país com mais oportunidades para todos."

**Total ideal:** 4 parágrafos, 20-28 linhas. Não deixe a folha em branco. Não passe de 30 linhas.`
            },
            {
              id: 'lng-3-2',
              title: 'Conectivos essenciais',
              searchQuery: 'conectivos textuais redação lista',
              content: `Conectivos ligam ideias e dão fluidez ao texto. Memorize por **função**.

**PARA INICIAR / INTRODUZIR:**
- Inicialmente, primeiramente, em primeiro lugar
- Atualmente, hoje em dia, nos dias de hoje
- Desde então, ao longo da história

**PARA ADICIONAR INFORMAÇÃO:**
- Além disso, ademais, outrossim
- Também, igualmente, do mesmo modo
- Ainda, somado a isso, em adição

**PARA CONTRASTAR / OPOR:**
- Porém, contudo, todavia, entretanto
- No entanto, por outro lado
- Apesar de, embora, ainda que

**PARA CAUSA:**
- Porque, pois, já que, uma vez que
- Visto que, dado que, em razão de

**PARA CONSEQUÊNCIA:**
- Portanto, logo, assim
- Dessa forma, dessa maneira
- Por conseguinte, em vista disso

**PARA EXEMPLIFICAR:**
- Por exemplo, como, isto é
- Ou seja, a saber, tal como

**PARA CONCLUIR:**
- Em suma, em síntese, enfim
- Portanto, dessa forma, em conclusão
- Diante do exposto, dado o exposto

**Dica:** comece **cada parágrafo do desenvolvimento com um conectivo diferente**. Evite repetir "Além disso" ou "Portanto" várias vezes.

**Exemplo de variação:**
- Parágrafo 1 (introdução): "Atualmente..."
- Parágrafo 2: "Em primeiro lugar, é importante destacar que..."
- Parágrafo 3: "Além disso, vale ressaltar que..."
- Parágrafo 4 (conclusão): "Portanto, faz-se necessário..."`
            },
            {
              id: 'lng-3-3',
              title: 'O que NÃO fazer na redação',
              searchQuery: 'erros redação Encceja zerar nota',
              content: `Erros que **zeram** a redação ou reduzem muito a nota.

**❌ FUGIR DO TEMA**
Ler só uma palavra do tema e inventar. Se o tema é "violência contra a mulher" e você escreve sobre "violência" em geral, foge. Sempre leia a proposta inteira, anote palavras-chave, e responda exatamente ao que foi pedido.

**❌ FORMA INADEQUADA**
A redação tem que ser dissertativo-argumentativa. NÃO use:
- Verso ou poema
- Lista, tópicos, bullet points
- Diálogo entre personagens
- Carta, bilhete ou e-mail
- Receita ou instrução

**❌ CÓPIA DA COLETÂNEA**
Mais de 7 linhas copiadas dos textos motivadores **zera** a redação. Use os textos como inspiração, mas escreva com **suas próprias palavras**.

**❌ LINGUAGEM INFORMAL**
- "tipo assim", "né", "vc", "pra", "tá"
- Abreviações: "kkk", "rs", "hj"
- Gírias e expressões coloquiais
- Emojis ou desenhos

**❌ PRIMEIRA PESSOA E OPINIÃO EXPLÍCITA**
Evite "eu acho", "na minha opinião", "eu penso que". Use **terceira pessoa impessoal**:
- "É evidente que..."
- "Observa-se que..."
- "Faz-se necessário..."
- "Pode-se afirmar que..."

**❌ LETRA ILEGÍVEL OU FORA DA MARGEM**
Se o corretor não consegue ler, perde ponto. Escreva pausadamente, com letra legível.

**❌ TEXTO MUITO CURTO OU EM BRANCO**
Mínimo recomendado: 20 linhas. Em branco = zero.

**❌ DESRESPEITO AOS DIREITOS HUMANOS**
Defender violência, discriminação, racismo, homofobia → **zera**. Mesmo que pareça argumento, qualquer proposta que fira direitos humanos elimina a redação.

---

**✅ O QUE FAZER:**
- Use caneta **azul ou preta** não-transparente
- Treine pelo menos **3 redações** antes da prova
- Cronometre: você terá cerca de 1h30 para a redação
- Faça rascunho primeiro
- Releia antes de passar a limpo
- Conte as linhas (entre 20 e 30)`
            }
          ]
        }
      ]
    },
    {
      id: 'matematica',
      title: 'Matemática e suas Tecnologias',
      shortTitle: 'Matemática',
      number: '02',
      color: '#FFD93D',
      modules: [
        {
          id: 'mat-1',
          title: 'Aritmética e Operações',
          topics: [
            {
              id: 'mat-1-1',
              title: 'Frações, decimais e porcentagem',
              searchQuery: 'fração decimal porcentagem Encceja básico',
              content: `**FRAÇÕES**

Uma fração representa uma divisão. Em 3/4, o 3 é o numerador (parte) e o 4 é o denominador (todo).

Conversões mais usadas:
- 1/2 = 0,5 = 50%
- 1/4 = 0,25 = 25%
- 3/4 = 0,75 = 75%
- 1/5 = 0,2 = 20%
- 1/10 = 0,1 = 10%
- 1/3 ≈ 0,333... ≈ 33,3%

**Operações com frações:**

*Soma e subtração* (mesmo denominador): some os numeradores.
- 2/5 + 1/5 = 3/5

*Soma e subtração* (denominadores diferentes): tire o MMC.
- 1/2 + 1/3 = 3/6 + 2/6 = 5/6

*Multiplicação:* multiplique reto.
- 2/3 × 4/5 = 8/15

*Divisão:* multiplique pelo inverso.
- 2/3 ÷ 4/5 = 2/3 × 5/4 = 10/12 = 5/6

---

**CONVERSÕES**

- Fração → decimal: divida numerador pelo denominador.
- Decimal → porcentagem: multiplique por 100.
- Porcentagem → decimal: divida por 100.

---

**PORCENTAGEM (cai muito!)**

Regra de ouro: **"de" vira multiplicação**.
- 20% de 150 = 0,20 × 150 = **30**
- 35% de 200 = 0,35 × 200 = **70**

**Aumento percentual:**
- Aumento de 10% sobre R$ 80 = 80 × 1,10 = **R$ 88**
- Aumento de 25% sobre R$ 200 = 200 × 1,25 = **R$ 250**

**Desconto:**
- Desconto de 15% sobre R$ 200 = 200 × 0,85 = **R$ 170**
- Desconto de 30% sobre R$ 500 = 500 × 0,70 = **R$ 350**

(Truque: 100% - 15% = 85% → multiplica por 0,85)

**Exemplo típico do Encceja:**
"Uma TV custa R$ 1.200. Está com 20% de desconto. Qual o preço final?"
1.200 × 0,80 = **R$ 960**`
            },
            {
              id: 'mat-1-2',
              title: 'Regra de três',
              searchQuery: 'regra de três simples direta inversa',
              content: `A regra de três é uma das ferramentas que mais cai no Encceja. Você tem 4 valores, 3 conhecidos e 1 desconhecido.

**REGRA DE TRÊS DIRETA**

Quando uma grandeza aumenta, a outra também aumenta.

*Exemplo:* Se 3 kg de arroz custam R$ 18, quanto custam 5 kg?

| kg | R$ |
|----|-----|
| 3  | 18 |
| 5  | x  |

x = (5 × 18) ÷ 3 = **R$ 30**

**Como identificar:**
- Mais kg → mais dinheiro → **direta**
- Mais funcionários → mais produção → **direta**

---

**REGRA DE TRÊS INVERSA**

Quando uma grandeza aumenta, a outra diminui.

*Exemplo:* Se 4 trabalhadores fazem uma obra em 12 dias, quantos dias 6 trabalhadores levam?

Mais trabalhadores → menos dias → **inversa**.

| Trab. | Dias |
|-------|------|
| 4     | 12   |
| 6     | x    |

Como é inversa, **invertemos um lado** antes de multiplicar:

x = (4 × 12) ÷ 6 = **8 dias**

---

**REGRA DE TRÊS COM PORCENTAGEM**

*Exemplo:* Em uma turma de 40 alunos, 25% foram aprovados. Quantos foram aprovados?

40 alunos → 100%
x alunos → 25%

x = (40 × 25) ÷ 100 = **10 alunos**

---

**Passo a passo seguro:**

1. Identifique as duas grandezas
2. Coloque os valores conhecidos em colunas
3. Decida se é direta ou inversa
4. Direta: multiplica em cruz. Inversa: inverte uma coluna.
5. Faça a conta e verifique se a resposta faz sentido`
            },
            {
              id: 'mat-1-3',
              title: 'Razão e proporção',
              searchQuery: 'razão proporção escala matemática',
              content: `**RAZÃO**

Razão é a comparação entre dois números por divisão.
- A razão entre 6 e 2 é 6/2 = **3**
- A razão entre 10 e 5 é 10/5 = **2**

**PROPORÇÃO**

Proporção é a igualdade entre duas razões.

a/b = c/d

A regra fundamental: **produto dos meios = produto dos extremos**.
- a × d = b × c

Exemplo: 2/3 = 4/6
- 2 × 6 = 3 × 4
- 12 = 12 ✓

---

**APLICAÇÃO TÍPICA: ESCALA**

A escala mostra a proporção entre o desenho/mapa e a realidade.

*Exemplo:* A escala de um mapa é 1:50.000. Dois pontos estão a 4 cm de distância no mapa. Qual a distância real?

1 cm / 50.000 cm = 4 cm / x

x = 4 × 50.000 = **200.000 cm = 2.000 m = 2 km**

---

**APLICAÇÃO: RECEITA / PROPORÇÕES**

Uma receita usa 2 ovos para 4 pessoas. Quantos ovos para 10 pessoas?

2 / 4 = x / 10
x = (2 × 10) ÷ 4 = **5 ovos**

---

**APLICAÇÃO: DIVISÃO PROPORCIONAL**

João, Maria e Pedro vão dividir R$ 600 na proporção 1:2:3.
Total das partes: 1 + 2 + 3 = 6
Cada parte vale: 600 ÷ 6 = R$ 100

- João: 1 × 100 = **R$ 100**
- Maria: 2 × 100 = **R$ 200**
- Pedro: 3 × 100 = **R$ 300**

(Soma: 100 + 200 + 300 = 600 ✓)`
            }
          ]
        },
        {
          id: 'mat-2',
          title: 'Geometria',
          topics: [
            {
              id: 'mat-2-1',
              title: 'Áreas e perímetros',
              searchQuery: 'área perímetro figuras planas fórmulas',
              content: `**Perímetro** = soma de todos os lados (contorno).
**Área** = espaço interno de uma figura.

---

**FÓRMULAS OBRIGATÓRIAS:**

**Quadrado**
- Lado: L
- Perímetro: P = 4 × L
- Área: A = L²

**Retângulo**
- Base: b | Altura: h
- Perímetro: P = 2 × (b + h)
- Área: A = b × h

**Triângulo**
- Base: b | Altura: h
- Área: A = (b × h) ÷ 2

**Trapézio**
- Base maior: B | Base menor: b | Altura: h
- Área: A = ((B + b) × h) ÷ 2

**Círculo**
- Raio: r | Diâmetro: D = 2r
- Comprimento (perímetro): C = 2 × π × r
- Área: A = π × r²
- Use **π ≈ 3,14**

---

**EXEMPLOS DE PROVA:**

*1) Terreno retangular*
"Um terreno tem 20 m de frente e 50 m de fundo. Qual a área?"
A = 20 × 50 = **1.000 m²**

*2) Quanto cerca de arame para esse terreno?*
P = 2 × (20 + 50) = 140 m de arame

*3) Piscina circular*
"Uma piscina circular tem raio de 3 m. Qual a área?"
A = 3,14 × 3² = 3,14 × 9 = **28,26 m²**

*4) Triângulo*
"Um triângulo tem base 8 cm e altura 5 cm. Área?"
A = (8 × 5) ÷ 2 = **20 cm²**

---

**ATENÇÃO ÀS UNIDADES:**

Sempre verifique se todas as medidas estão na mesma unidade. Se a pergunta pede **m²** e os dados estão em **cm**, converta antes:
- 1 m = 100 cm
- 1 m² = 10.000 cm²
- 1 km² = 1.000.000 m²`
            },
            {
              id: 'mat-2-2',
              title: 'Volume',
              searchQuery: 'volume sólidos geométricos caixa cilindro',
              content: `**Volume** é o espaço que um sólido ocupa.

---

**FÓRMULAS DOS PRINCIPAIS SÓLIDOS:**

**Cubo** (todos os lados iguais)
V = L³ = L × L × L

**Paralelepípedo / Caixa retangular**
V = comprimento × largura × altura
V = c × l × h

**Cilindro** (lata, copo redondo, caixa d'água cilíndrica)
V = π × r² × h
(área da base circular × altura)

**Esfera** (bola)
V = (4/3) × π × r³

**Cone**
V = (π × r² × h) ÷ 3

**Pirâmide**
V = (área da base × altura) ÷ 3

---

**CONVERSÃO ESSENCIAL:**

**1 m³ = 1.000 litros**
**1 dm³ = 1 litro**
**1 cm³ = 1 mililitro**

Memorize isso — cai em quase toda prova com cálculo de capacidade.

---

**EXEMPLOS TÍPICOS:**

*1) Caixa d'água retangular*
"Uma caixa d'água tem 2 m × 1,5 m × 1 m. Quantos litros cabem?"
V = 2 × 1,5 × 1 = 3 m³ = **3.000 litros**

*2) Cubo*
"Um cubo tem aresta de 5 cm. Qual o volume?"
V = 5³ = 125 cm³ = **125 ml**

*3) Cilindro*
"Um tanque cilíndrico tem raio de 2 m e altura de 3 m. Volume?"
V = 3,14 × 2² × 3 = 3,14 × 4 × 3 = **37,68 m³**
Em litros: 37.680 litros

*4) Aplicação prática*
"Uma piscina retangular tem 10 m × 5 m × 1,5 m. Quanto custa enchê-la se a água custa R$ 0,01/litro?"
- Volume: 10 × 5 × 1,5 = 75 m³ = 75.000 litros
- Custo: 75.000 × 0,01 = **R$ 750**`
            },
            {
              id: 'mat-2-3',
              title: 'Teorema de Pitágoras',
              searchQuery: 'teorema de Pitágoras exemplos',
              content: `Em **todo triângulo retângulo** (que tem um ângulo de 90°):

**a² = b² + c²**

Onde:
- **a** é a hipotenusa (lado maior, oposto ao ângulo de 90°)
- **b** e **c** são os catetos (os dois lados que formam o ângulo de 90°)

---

**EXEMPLO CLÁSSICO:**

Uma escada de 5 m está apoiada em uma parede. A base da escada está a 3 m da parede. Que altura a escada alcança?

A escada é a hipotenusa (5 m).
A distância da parede é um cateto (3 m).
A altura é o outro cateto (h).

5² = 3² + h²
25 = 9 + h²
h² = 16
h = √16 = **4 m**

---

**TRIOS PITAGÓRICOS FAMOSOS** (caem prontos na prova):

- **3, 4, 5** → 3² + 4² = 5² (9 + 16 = 25) ✓
- **6, 8, 10** → o dobro do trio acima
- **5, 12, 13** → 5² + 12² = 13² (25 + 144 = 169) ✓
- **8, 15, 17**
- **9, 12, 15** → triplo do 3,4,5

Se você identificar o trio na prova, evita o cálculo de raiz quadrada.

---

**OUTROS EXEMPLOS:**

*1) Rampa*
"Uma rampa tem 13 m de comprimento e a base mede 12 m. Qual a altura?"
13² = 12² + h²
169 = 144 + h²
h² = 25 → h = **5 m**

*2) Distância em diagonal*
"Um retângulo mede 6 m × 8 m. Qual o tamanho da diagonal?"
A diagonal é a hipotenusa.
d² = 6² + 8² = 36 + 64 = 100
d = **10 m**`
            }
          ]
        },
        {
          id: 'mat-3',
          title: 'Funções e Gráficos',
          topics: [
            {
              id: 'mat-3-1',
              title: 'Função do 1º grau',
              searchQuery: 'função do primeiro grau Encceja',
              content: `Função do 1º grau (ou função afim) tem a forma:

**y = ax + b**

Onde:
- **a** é o coeficiente angular (inclinação da reta)
- **b** é o coeficiente linear (onde a reta corta o eixo y)
- **x** é a variável independente
- **y** é a variável dependente (depende de x)

---

**COMPORTAMENTO:**

- Se **a > 0** (positivo): função **crescente** (sobe da esquerda pra direita)
- Se **a < 0** (negativo): função **decrescente** (desce)
- Se **a = 0**: não é função do 1º grau, é constante

---

**APLICAÇÕES NO COTIDIANO:**

*1) Conta de táxi*
"Um táxi cobra R$ 5 de bandeirada + R$ 2 por km rodado."
- Função: y = 2x + 5
- Para 10 km: y = 2(10) + 5 = **R$ 25**
- Para 25 km: y = 2(25) + 5 = **R$ 55**

*2) Conta de luz*
"A conta de luz cobra R$ 30 de taxa fixa + R$ 0,80 por kWh."
- Função: y = 0,80x + 30
- Para 100 kWh: y = 0,80(100) + 30 = **R$ 110**

*3) Salário com comissão*
"Um vendedor ganha R$ 1.500 fixos + R$ 50 por venda."
- Função: y = 50x + 1.500
- Para 20 vendas: y = 50(20) + 1.500 = **R$ 2.500**

---

**LEITURA DO GRÁFICO:**

O gráfico de y = ax + b é sempre uma **reta**.
- O ponto onde a reta cruza o eixo y é **b**.
- A inclinação da reta é **a**.

Exemplo: se a reta cruza o eixo y em 5 e passa por (1, 7):
- b = 5
- a = (7 - 5) / (1 - 0) = 2
- Função: y = 2x + 5`
            },
            {
              id: 'mat-3-2',
              title: 'Leitura de gráficos e tabelas',
              searchQuery: 'interpretação de gráficos Encceja',
              content: `O Encceja adora gráficos do cotidiano: consumo de energia, vendas, temperatura, taxa de desemprego, dados do IBGE.

---

**COMO LER UM GRÁFICO (passo a passo):**

1. **Leia o título** — diz sobre o que é o gráfico
2. **Veja os eixos** — o que cada eixo mede
3. **Identifique as unidades** — reais? milhões? porcentagem?
4. **Procure os pontos altos e baixos** — máximos e mínimos
5. **Observe a tendência** — está subindo? descendo? oscilando?
6. **Só então responda** à pergunta

---

**CUIDADO COM ESCALAS DISTORCIDAS:**

Às vezes o eixo y não começa em zero. Um gráfico que mostra escala de 50 a 100 parece ter variação enorme, mas pode ser pouca diferença na prática. Sempre olhe os números, não confie só na aparência visual.

---

**TIPOS DE GRÁFICO E QUANDO USAR CADA UM:**

**Gráfico de barras / colunas**
Compara categorias (vendas por produto, votos por candidato).
A barra mais alta = maior valor.

**Gráfico de linhas**
Mostra evolução ao longo do tempo (temperatura ao longo do ano, vendas mensais).
Linha subindo = crescimento. Linha descendo = queda.

**Gráfico de pizza (setores)**
Mostra partes de um todo. As porcentagens **sempre somam 100%**.
A fatia maior = maior porcentagem.

**Tabela**
Apresenta dados numéricos exatos em linhas e colunas. Mais precisa, mas exige leitura cruzada.

---

**EXEMPLO TÍPICO DE PROVA:**

Um gráfico mostra o consumo de energia (em kWh) de uma residência ao longo de 6 meses.

Perguntas comuns:
- Em qual mês o consumo foi maior?
- Qual a diferença entre o maior e o menor consumo?
- Qual a média de consumo no período?
- O consumo aumentou ou diminuiu de janeiro a junho?

**Sempre olhe primeiro o eixo y para ver a unidade**, depois localize o ponto pedido no eixo x.`
            }
          ]
        },
        {
          id: 'mat-4',
          title: 'Estatística e Probabilidade',
          topics: [
            {
              id: 'mat-4-1',
              title: 'Média, moda e mediana',
              searchQuery: 'média moda mediana estatística básica',
              content: `As três **medidas de tendência central** mais cobradas.

---

**MÉDIA ARITMÉTICA**

Soma todos os valores e divide pela quantidade.

*Exemplo:* notas 7, 8, 6, 9.
Média = (7 + 8 + 6 + 9) ÷ 4 = 30 ÷ 4 = **7,5**

*Aplicação típica:* "Para passar, preciso de média 6. Já tirei 5, 7 e 4. Quanto preciso na última prova?"
(5 + 7 + 4 + x) ÷ 4 = 6
16 + x = 24
x = **8**

---

**MODA**

Valor que **mais aparece** na lista.

*Exemplo:* 2, 3, 3, 4, 5, 3, 6
Moda = **3** (aparece 3 vezes)

Pode existir:
- Mais de uma moda (bimodal): 2, 3, 3, 4, 4, 5 → modas 3 e 4
- Nenhuma moda (todos diferentes): 1, 2, 3, 4, 5 → sem moda

---

**MEDIANA**

Valor **central** depois de **ordenar** a lista.

*Exemplo 1 (quantidade ímpar):* 1, 3, 5, 7, 9
Mediana = **5** (o do meio)

*Exemplo 2 (quantidade par):* 2, 4, 6, 8
Não tem um do meio, então faz a média dos dois centrais:
Mediana = (4 + 6) ÷ 2 = **5**

*Atenção:* sempre ordene primeiro!
Lista: 5, 2, 8, 1, 9
Ordenada: 1, 2, 5, 8, 9
Mediana = **5**

---

**QUANDO USAR CADA UMA:**

- **Média:** quando os valores são parecidos
- **Mediana:** quando há valores muito extremos que distorcem a média (ex: salários — se uma pessoa ganha milhões e outras ganham pouco, a média não representa)
- **Moda:** quando interessa saber o valor mais comum (ex: tamanho de calçado mais vendido)`
            },
            {
              id: 'mat-4-2',
              title: 'Probabilidade básica',
              searchQuery: 'probabilidade básica casos favoráveis Encceja',
              content: `**Probabilidade = casos favoráveis ÷ casos possíveis**

O resultado é sempre entre 0 (impossível) e 1 (certeza), ou entre 0% e 100%.

---

**EXEMPLOS BÁSICOS:**

*1) Dado*
"Ao jogar um dado, qual a probabilidade de sair número par?"
- Casos favoráveis: {2, 4, 6} → 3 números
- Casos possíveis: {1, 2, 3, 4, 5, 6} → 6 números
- P = 3/6 = 1/2 = **50%**

*2) Dado — número maior que 4*
- Casos favoráveis: {5, 6} → 2 números
- Casos possíveis: 6
- P = 2/6 = 1/3 ≈ **33,3%**

*3) Moeda*
"Qual a probabilidade de sair cara ao jogar uma moeda?"
- 1 caso favorável (cara) em 2 possíveis (cara ou coroa)
- P = 1/2 = **50%**

*4) Baralho*
"Probabilidade de tirar uma carta de copas em um baralho de 52?"
- Casos favoráveis: 13 cartas de copas
- Casos possíveis: 52 cartas
- P = 13/52 = 1/4 = **25%**

---

**EVENTOS INDEPENDENTES (multiplicação):**

Quando um evento não afeta o outro, **multiplique** as probabilidades.

*Exemplo:* "Probabilidade de tirar cara 2 vezes seguidas jogando uma moeda?"
P(cara) × P(cara) = 1/2 × 1/2 = 1/4 = **25%**

*Exemplo:* "Jogando dois dados, qual a probabilidade de sair 6 em ambos?"
P = 1/6 × 1/6 = 1/36 ≈ **2,78%**

---

**EVENTOS COM "OU" (soma):**

"Qual a probabilidade de tirar 2 OU 5 no dado?"
P(2) + P(5) = 1/6 + 1/6 = 2/6 = 1/3 ≈ **33,3%**

---

**APLICAÇÃO TÍPICA:**

"Uma urna tem 10 bolas: 4 vermelhas, 3 azuis e 3 verdes. Qual a probabilidade de tirar uma bola azul?"
P = 3/10 = **30%**`
            }
          ]
        }
      ]
    },
    {
      id: 'ciencias-natureza',
      title: 'Ciências da Natureza e suas Tecnologias',
      shortTitle: 'Ciências da Natureza',
      number: '03',
      color: '#4ECDC4',
      modules: [
        {
          id: 'cn-1',
          title: 'Biologia',
          topics: [
            {
              id: 'cn-1-1',
              title: 'Ecologia e meio ambiente',
              searchQuery: 'ecologia ecossistema cadeia alimentar Encceja',
              content: `**CONCEITOS BÁSICOS DE ECOLOGIA:**

**Ecossistema** = conjunto de seres vivos + ambiente físico onde vivem, interagindo entre si.
Exemplos: floresta amazônica, recife de coral, lagoa, deserto.

**Comunidade** = conjunto de seres vivos de várias espécies que vivem no mesmo local.

**População** = conjunto de indivíduos da **mesma espécie** em um local.

**Habitat** = endereço, onde a espécie vive.
**Nicho ecológico** = profissão, papel que a espécie cumpre no ecossistema.

---

**CADEIA ALIMENTAR:**

Produtores → Consumidores 1º → Consumidores 2º → Consumidores 3º → Decompositores

- **Produtores:** plantas, algas (fazem fotossíntese)
- **Consumidores 1º:** herbívoros (boi, lagarta, gafanhoto)
- **Consumidores 2º:** carnívoros que comem herbívoros (sapo, pequenos peixes)
- **Consumidores 3º:** carnívoros que comem outros carnívoros (cobra, leão)
- **Decompositores:** fungos e bactérias (reciclam matéria orgânica)

A energia diminui a cada nível trófico (90% se perde como calor).

---

**BIOMAS BRASILEIROS** (cai muito!):

- **Amazônia:** maior floresta tropical, biodiversidade gigante, "pulmão" (na verdade fixa CO2)
- **Cerrado:** savana brasileira, vegetação retorcida, fundamental para nascentes de rios
- **Mata Atlântica:** muito desmatada (resta ~12%), litoral brasileiro
- **Caatinga:** semiárido nordestino, plantas com espinhos, único exclusivamente brasileiro
- **Pampa:** campos do Sul, criação de gado
- **Pantanal:** maior planície alagável do mundo, biodiversidade aquática

---

**PROBLEMAS AMBIENTAIS COBRADOS:**

**Efeito estufa:** gases (CO₂, metano, vapor d'água) retêm calor → aquecimento global. Causas: queima de combustíveis fósseis, desmatamento, pecuária.

**Camada de ozônio:** filtra radiação UV. Foi destruída por CFCs (gases de aerossóis antigos). Em recuperação após o Protocolo de Montreal (1987).

**Chuva ácida:** SO₂ e NOₓ da queima de combustíveis fósseis reagem com a água da chuva → ácido sulfúrico → mata florestas e corrói construções.

**Eutrofização:** excesso de nutrientes (esgoto, fertilizantes) em água → explosão de algas → falta de oxigênio → morte de peixes.

**Desmatamento:** perda de biodiversidade, mudanças climáticas, redução de chuvas.

**Lixo e plástico nos oceanos:** microplásticos entram na cadeia alimentar.`
            },
            {
              id: 'cn-1-2',
              title: 'Corpo humano e saúde',
              searchQuery: 'sistemas do corpo humano biologia Encceja',
              content: `**SISTEMAS CORPORAIS MAIS COBRADOS:**

**Sistema digestório:**
Boca → faringe → esôfago → estômago → intestino delgado → intestino grosso → reto → ânus.
- Boca: mastigação + saliva (começa digestão de amido)
- Estômago: ácido clorídrico + pepsina (digestão de proteínas)
- Intestino delgado: principal local de **absorção de nutrientes**
- Intestino grosso: absorve **água** e forma fezes
- Glândulas anexas: fígado (produz bile), pâncreas (enzimas digestivas)

**Sistema circulatório:**
Coração com 4 câmaras: 2 átrios (cima) + 2 ventrículos (baixo).
- **Artérias** levam sangue **do** coração (com pressão alta)
- **Veias** trazem sangue **ao** coração (pressão baixa)
- **Capilares:** vasos finíssimos onde ocorrem as trocas com as células

**Sistema respiratório:**
Nariz → faringe → laringe → traqueia → brônquios → bronquíolos → alvéolos pulmonares.
Nos alvéolos, ocorrem as **trocas gasosas**: O₂ entra no sangue, CO₂ sai.

**Sistema nervoso:**
- Central: cérebro + medula espinhal
- Periférico: nervos pelo corpo
- Cérebro controla pensamento, memória, emoções
- Cerebelo: equilíbrio e coordenação motora

**Sistema reprodutor:**
Conhecer órgãos principais (femininos: ovários, útero, vagina / masculinos: testículos, próstata, pênis) e o ciclo menstrual básico.

---

**DOENÇAS QUE CAEM MUITO:**

**Hipertensão arterial:** pressão alta. Fator de risco para AVC e infarto. Prevenção: dieta com pouco sal, exercício, não fumar.

**Diabetes:** glicose alta no sangue.
- Tipo 1: pâncreas não produz insulina (geralmente desde criança)
- Tipo 2: corpo resiste à insulina (relacionado à obesidade, adultos)

**Doenças cardiovasculares:** infarto, AVC. Principais causas de morte no Brasil.

**Câncer:** crescimento descontrolado de células. Vários tipos (pulmão, mama, próstata, colo de útero). Prevenção: não fumar, alimentação saudável, exames periódicos.

**DSTs (ISTs):**
- HIV/AIDS: ataca sistema imune. Prevenção: preservativo
- HPV: causa câncer de colo de útero. Vacina disponível pelo SUS
- Sífilis, gonorreia, herpes genital, hepatite B

**Doenças do mosquito Aedes aegypti:**
- Dengue, zika, chikungunya, febre amarela urbana
- Prevenção: eliminar água parada

---

**PREVENÇÃO E SAÚDE PÚBLICA:**

- Vacinação: previne sarampo, pólio, COVID-19, HPV, gripe
- Saneamento básico: previne cólera, leptospirose, hepatite A
- Atividade física: previne obesidade, diabetes, hipertensão
- Alimentação saudável: frutas, verduras, menos ultraprocessados`
            },
            {
              id: 'cn-1-3',
              title: 'Genética básica',
              searchQuery: 'genética mendeliana herança DNA',
              content: `**GREGOR MENDEL** (1822-1884): monge que descobriu as leis básicas da genética estudando ervilhas. Considerado o **pai da genética**.

---

**CONCEITOS FUNDAMENTAIS:**

**DNA:** molécula que carrega a informação genética. Está no núcleo das células.

**Gene:** trecho de DNA que determina uma característica.

**Alelo:** variação de um gene. Para cada característica, herdamos um alelo do pai e um da mãe.
- Letra **maiúscula** (A) = alelo **dominante**
- Letra **minúscula** (a) = alelo **recessivo**

**Genótipo:** combinação genética da pessoa (AA, Aa ou aa).
**Fenótipo:** característica visível (a cor dos olhos que você enxerga).

---

**TIPOS DE GENÓTIPO:**

- **AA:** homozigoto dominante (puro dominante)
- **aa:** homozigoto recessivo (puro recessivo)
- **Aa:** heterozigoto (mistura) → expressa o dominante

---

**EXEMPLO CLÁSSICO: cor das ervilhas**

Amarela (A) é dominante sobre verde (a).

Cruzamento Aa × Aa:

|     | A   | a   |
|-----|-----|-----|
| **A** | AA  | Aa  |
| **a** | Aa  | aa  |

Resultado:
- 25% AA (amarela)
- 50% Aa (amarela)
- 25% aa (verde)

**Proporção fenotípica: 3 amarelas : 1 verde**

---

**APLICAÇÕES NO HUMANO:**

- Cor dos olhos: castanho é dominante sobre azul
- Tipo sanguíneo: sistema ABO + Rh
- Daltonismo: ligado ao cromossomo X (mais comum em homens)
- Hemofilia: também ligada ao X

---

**DETERMINAÇÃO DO SEXO:**

- Mulher: XX
- Homem: XY

O **pai** determina o sexo do bebê (transmite X ou Y).

---

**GENÉTICA MODERNA:**

- **Clonagem:** cópia genética idêntica (ovelha Dolly, 1996)
- **Transgênicos:** organismos com gene de outra espécie (soja, milho)
- **Engenharia genética:** modificação direta do DNA
- **Projeto Genoma Humano:** mapeou todos os genes humanos (concluído em 2003)`
            }
          ]
        },
        {
          id: 'cn-2',
          title: 'Química',
          topics: [
            {
              id: 'cn-2-1',
              title: 'Tabela periódica e átomos',
              searchQuery: 'tabela periódica elementos químicos Encceja',
              content: `**O ÁTOMO:**

Estrutura básica:
- **Prótons** (+): no núcleo, carga positiva
- **Nêutrons** (0): no núcleo, sem carga
- **Elétrons** (–): em camadas ao redor do núcleo, carga negativa

Em átomos neutros: nº de prótons = nº de elétrons.

---

**NÚMERO ATÔMICO (Z):**

Quantidade de **prótons** no núcleo. Define qual é o elemento.
- Hidrogênio (H): Z = 1 → 1 próton
- Carbono (C): Z = 6 → 6 prótons
- Oxigênio (O): Z = 8 → 8 prótons

**NÚMERO DE MASSA (A):**

A = prótons + nêutrons

---

**TABELA PERIÓDICA — COMO É ORGANIZADA:**

- **Linhas horizontais** = períodos (1 a 7)
- **Colunas verticais** = grupos ou famílias (1A a 8A, mais grupos B)

Os elementos do mesmo grupo têm propriedades químicas parecidas.

---

**FAMÍLIAS IMPORTANTES:**

**Grupo 1A — Metais alcalinos:** Li, Na, K, Rb, Cs
- Muito reativos, reagem violentamente com água
- Formam +1 (perdem 1 elétron)

**Grupo 2A — Metais alcalino-terrosos:** Be, Mg, Ca, Sr, Ba
- Reativos, formam +2

**Grupo 7A — Halogênios:** F, Cl, Br, I
- Muito reativos, formam sais com metais
- Formam –1 (ganham 1 elétron)

**Grupo 8A — Gases nobres:** He, Ne, Ar, Kr, Xe, Rn
- **Estáveis**, praticamente não reagem
- Têm a camada de valência completa

---

**TIPOS DE LIGAÇÃO QUÍMICA:**

**1. Ligação Iônica:** metal + ametal
- Há **transferência** de elétrons
- Exemplo: NaCl (sal de cozinha) → Na⁺ + Cl⁻
- Forma compostos cristalinos, sólidos, com alto ponto de fusão

**2. Ligação Covalente:** ametal + ametal
- Há **compartilhamento** de elétrons
- Exemplo: H₂O (água), O₂, CO₂
- Pode ser gasoso, líquido ou sólido

**3. Ligação Metálica:** entre metais
- Elétrons "livres" → conduz eletricidade
- Exemplo: ferro, cobre, alumínio

---

**ELEMENTOS DO DIA A DIA:**

- O₂: oxigênio (respiração)
- H₂O: água
- CO₂: dióxido de carbono (efeito estufa, refrigerantes)
- NaCl: sal de cozinha
- Fe: ferro
- Au: ouro
- Ag: prata
- C: carbono (vida orgânica, grafite, diamante)`
            },
            {
              id: 'cn-2-2',
              title: 'Química do cotidiano',
              searchQuery: 'química do cotidiano ácidos bases pH',
              content: `**ÁCIDOS E BASES — pH:**

A escala de pH vai de **0 a 14**.

- **pH < 7:** ÁCIDO
- **pH = 7:** NEUTRO
- **pH > 7:** BÁSICO (ou alcalino)

**Exemplos:**
- Suco gástrico: pH ~1 (muito ácido)
- Limão, vinagre: pH ~2-3
- Café: pH ~5
- Água pura: pH = 7
- Sangue: pH ~7,4
- Sabão: pH ~9-10
- Leite de magnésia: pH ~10
- Soda cáustica: pH ~14 (muito básico)

---

**INDICADORES DE pH:**

Substâncias que mudam de cor conforme o pH:
- Papel tornassol: vermelho em ácido, azul em base
- Repolho roxo: pode dar várias cores (cai em prova!)
- Fenolftaleína: incolor em ácido, rosa em base

---

**REAÇÕES QUÍMICAS COMUNS:**

**1. Combustão:** queima de combustível + oxigênio
Combustível + O₂ → CO₂ + H₂O + energia
Exemplo: queima de gás de cozinha, gasolina, vela.

**2. Oxidação (ferrugem):**
Ferro + O₂ + água → Fe₂O₃ (ferrugem)
Por isso ferro enferruja com umidade.

**3. Fermentação:**
Açúcar (com fermento, sem oxigênio) → álcool + CO₂
Aplicações: pão, cerveja, vinho, cachaça.

**4. Neutralização:** ácido + base → sal + água
Exemplo: HCl + NaOH → NaCl + H₂O
Aplicação: antiácidos estomacais neutralizam acidez do estômago.

---

**MISTURAS:**

**Mistura homogênea (solução):** aparência uniforme, uma fase só.
- Água + sal dissolvido
- Ar atmosférico
- Aço (ferro + carbono)

**Mistura heterogênea:** fases distintas visíveis.
- Água + óleo
- Granito (cristais visíveis)
- Salada

---

**MÉTODOS DE SEPARAÇÃO DE MISTURAS:**

- **Filtração:** sólido + líquido (coar café)
- **Decantação:** líquidos imiscíveis (água + óleo, deixa separar)
- **Destilação:** separa líquidos com pontos de ebulição diferentes (álcool e água, água do mar)
- **Evaporação:** obter sal a partir de água do mar
- **Peneiração:** sólidos de tamanhos diferentes (areia e pedra)
- **Imantação:** separa material magnético (ferro de areia)
- **Catação:** manual (feijão e pedrinhas)

---

**ESTADOS DA MATÉRIA E MUDANÇAS:**

Sólido ⇄ Líquido ⇄ Gasoso

Mudanças:
- Sólido → líquido: **fusão** (gelo derretendo)
- Líquido → gasoso: **vaporização** (água fervendo)
- Gasoso → líquido: **condensação** (vapor virando gota)
- Líquido → sólido: **solidificação** (água virando gelo)
- Sólido → gasoso direto: **sublimação** (gelo seco)`
            }
          ]
        },
        {
          id: 'cn-3',
          title: 'Física',
          topics: [
            {
              id: 'cn-3-1',
              title: 'Cinemática (movimento)',
              searchQuery: 'cinemática velocidade média Encceja',
              content: `**CINEMÁTICA** estuda o movimento dos corpos.

---

**CONCEITOS:**

- **Posição:** onde o objeto está
- **Deslocamento:** mudança de posição
- **Velocidade:** rapidez do deslocamento
- **Aceleração:** mudança da velocidade

---

**VELOCIDADE MÉDIA:**

**V = Δs ÷ Δt**

(velocidade = distância ÷ tempo)

Unidades: m/s ou km/h

**Conversão:**
- 1 m/s = 3,6 km/h
- Para passar de km/h para m/s: ÷ 3,6
- Para passar de m/s para km/h: × 3,6

---

**EXEMPLOS:**

*1)* "Um carro percorre 180 km em 2 horas. Qual a velocidade média?"
V = 180 ÷ 2 = **90 km/h**

*2)* "Um atleta corre 100 m em 10 s. Qual a velocidade?"
V = 100 ÷ 10 = **10 m/s** = 36 km/h

*3)* "A 80 km/h, quanto tempo para percorrer 240 km?"
t = 240 ÷ 80 = **3 horas**

---

**ACELERAÇÃO:**

**a = Δv ÷ Δt**

(variação da velocidade ÷ tempo)

Unidade: m/s²

*Exemplo:* "Um carro vai de 0 a 20 m/s em 5 segundos. Aceleração?"
a = 20 ÷ 5 = **4 m/s²**

---

**TIPOS DE MOVIMENTO:**

**Movimento Uniforme (MU):** velocidade constante, aceleração = 0.
Exemplo: piloto automático em estrada reta.

**Movimento Uniformemente Variado (MUV):** aceleração constante.
- Acelerado: velocidade aumenta
- Retardado: velocidade diminui (freando)

---

**QUEDA LIVRE:**

Todo objeto em queda livre (desprezando o ar) tem aceleração da gravidade **g ≈ 10 m/s²** (no Brasil).

Isso significa que a cada segundo a velocidade aumenta 10 m/s.
- 1 s caindo: 10 m/s
- 2 s caindo: 20 m/s
- 3 s caindo: 30 m/s

Galileu mostrou: **objetos caem na mesma velocidade independente da massa** (no vácuo). Uma pena e uma pedra caem juntas se não tiver ar.`
            },
            {
              id: 'cn-3-2',
              title: 'Energia e trabalho',
              searchQuery: 'energia trabalho potência física',
              content: `**ENERGIA** é a capacidade de realizar trabalho. Existe em várias formas:

---

**TIPOS DE ENERGIA:**

**Energia cinética (Ec):** energia do movimento.
Ec = (m × v²) ÷ 2
- Quanto maior a velocidade, mais energia cinética
- Por isso colisão a 100 km/h é muito pior que a 50 km/h (energia quadrupla, não dobra)

**Energia potencial gravitacional (Ep):** energia da altura.
Ep = m × g × h
- Onde m = massa, g = 10 m/s², h = altura
- Uma pedra no alto tem energia potencial; ao cair vira cinética

**Energia potencial elástica:** mola comprimida ou esticada.

**Outras formas:**
- **Térmica:** calor
- **Elétrica:** corrente elétrica
- **Química:** ligações químicas (alimento, combustível, bateria)
- **Nuclear:** núcleo dos átomos (usina, sol)
- **Sonora:** ondas de som
- **Luminosa:** luz

---

**PRINCÍPIO DA CONSERVAÇÃO DA ENERGIA:**

**A energia não se cria nem se destrói, apenas se transforma.**

Exemplos:
- **Montanha-russa:** no topo, energia potencial máxima. Na descida, vira cinética. No final, parte vira térmica (atrito) e sonora.
- **Hidrelétrica:** água em alta altitude (potencial) → desce e move turbina (cinética) → gera eletricidade.
- **Vela queimando:** química → luminosa + térmica.
- **Lâmpada:** elétrica → luminosa + térmica.
- **Comida:** química (do alimento) → cinética + térmica (corpo).

---

**POTÊNCIA:**

**P = trabalho ÷ tempo**
**P = energia ÷ tempo**

Unidade: **Watt (W)**.
1.000 W = 1 kW

Quanto maior a potência, mais rápido o aparelho consome ou produz energia.

---

**ENERGIA ELÉTRICA EM CASA:**

A conta de luz cobra por **kWh (quilowatt-hora)**:

Energia = Potência × tempo
E (kWh) = P (kW) × t (h)

*Exemplo:* "Um chuveiro de 5.500 W ligado por 2 horas. Quanto consome?"
E = 5,5 × 2 = **11 kWh**

Se o kWh custa R$ 0,80:
Custo = 11 × 0,80 = **R$ 8,80**

---

**APARELHOS QUE MAIS GASTAM EM CASA:**

1. Chuveiro elétrico (5.500 W)
2. Ar-condicionado (1.500-2.000 W)
3. Ferro de passar (1.000 W)
4. Forno elétrico, geladeira
5. Lâmpadas LED (muito econômicas, 10 W)`
            },
            {
              id: 'cn-3-3',
              title: 'Eletricidade básica',
              searchQuery: 'eletricidade corrente tensão lei de Ohm',
              content: `**GRANDEZAS ELÉTRICAS:**

**Tensão (V):** "força" que empurra os elétrons.
- Medida em **volts (V)**
- No Brasil: 110V ou 127V e 220V

**Corrente elétrica (I):** fluxo de elétrons.
- Medida em **ampères (A)**

**Resistência (R):** oposição à passagem da corrente.
- Medida em **ohms (Ω)**
- Resistores como em chuveiros e ferros transformam eletricidade em calor

---

**LEI DE OHM:**

**V = R × I**

A corrente é diretamente proporcional à tensão e inversamente proporcional à resistência.

*Exemplo:* "Em um circuito com tensão de 12V e resistência de 4Ω, qual a corrente?"
I = V ÷ R = 12 ÷ 4 = **3 A**

---

**POTÊNCIA ELÉTRICA:**

**P = V × I**

Unidade: Watt (W).

*Exemplo:* "Um chuveiro de 5.500 W ligado em 220 V. Qual a corrente?"
I = P ÷ V = 5.500 ÷ 220 = **25 A**

Por isso chuveiros precisam de **disjuntor compatível** (geralmente 30 A ou 40 A).

---

**TIPOS DE CORRENTE:**

**Corrente Contínua (CC):** flui sempre no mesmo sentido. Pilhas, baterias, painel solar.

**Corrente Alternada (CA):** muda de sentido várias vezes por segundo (60 vezes/s no Brasil). É a corrente que chega nas tomadas.

---

**CIRCUITOS:**

**Em série:** componentes ligados um após o outro. Se um queima, todos param (pisca-pisca antigo).

**Em paralelo:** componentes em "linhas" separadas. Se um queima, os outros continuam (instalação elétrica das casas).

---

**SEGURANÇA ELÉTRICA — IMPORTANTE!**

- **Nunca** mexer em fios com mãos molhadas (água conduz eletricidade)
- **Aterramento:** desvia descargas para a terra, evita choques
- **Disjuntor:** desliga circuito em caso de sobrecarga
- **Fusível:** queima se passar corrente demais, protege o circuito
- Não usar adaptadores que sobrecarreguem a tomada (T) → risco de incêndio
- Lâmpada queimou? Desligar disjuntor antes de trocar

---

**GERAÇÃO DE ENERGIA NO BRASIL:**

Matriz energética brasileira (principais fontes):
- **Hidrelétrica:** maior fonte (~60%)
- **Térmica:** gás, carvão, biomassa
- **Eólica:** em crescimento (vento)
- **Solar:** em crescimento (placas fotovoltaicas)
- **Nuclear:** Angra 1, 2 (em RJ)`
            }
          ]
        }
      ]
    },
    {
      id: 'ciencias-humanas',
      title: 'Ciências Humanas e suas Tecnologias',
      shortTitle: 'Ciências Humanas',
      number: '04',
      color: '#A78BFA',
      modules: [
        {
          id: 'ch-1',
          title: 'História do Brasil',
          topics: [
            {
              id: 'ch-1-1',
              title: 'Colônia e Império',
              searchQuery: 'Brasil colônia império resumo Encceja',
              content: `**BRASIL COLÔNIA (1500-1822)**

**Chegada dos portugueses:** 22 de abril de 1500, Pedro Álvares Cabral.

**Ciclos econômicos:**
1. **Pau-brasil** (1500-1530): extrativismo, escambo com indígenas
2. **Cana-de-açúcar** (a partir de 1530): engenhos no Nordeste, base da economia colonial
3. **Mineração de ouro** (séc. XVIII): Minas Gerais, deslocamento para o centro-sul
4. **Café** (a partir do séc. XIX): Sudeste, principal produto

**Trabalho na colônia:**
- Inicialmente: escravização indígena
- Depois: tráfico de africanos escravizados (foi a base econômica por mais de 300 anos)
- Brasil foi o último país das Américas a abolir a escravidão (1888)

**Sociedade colonial:**
- Senhores de engenho (elite branca)
- Escravizados (maior parte da população em muitas regiões)
- Indígenas (deslocados, mortos por doenças e violência)
- Jesuítas (catequização, criaram missões)
- Bandeirantes (expedições para capturar indígenas e procurar ouro)

**Movimentos coloniais de resistência:**
- **Quilombo dos Palmares** (sec. XVII): comunidade de escravos fugidos liderada por Zumbi
- **Inconfidência Mineira** (1789): em MG, contra impostos. Tiradentes enforcado.
- **Conjuração Baiana** (1798): inspirada na Revolução Francesa, mais popular.

---

**INDEPENDÊNCIA (1822):**

- Família real portuguesa fugiu para o Brasil em 1808 (fugindo de Napoleão)
- Abriu portos, criou bancos, transformou o Rio de Janeiro
- D. João VI volta a Portugal em 1821
- **7 de setembro de 1822:** D. Pedro I declara independência ("Grito do Ipiranga")

---

**BRASIL IMPÉRIO (1822-1889):**

**1º Reinado (1822-1831) — D. Pedro I:**
- **Constituição de 1824** (outorgada, autoritária)
- Guerra da Cisplatina (perdeu o Uruguai)
- Abdicou em favor do filho

**Período Regencial (1831-1840):**
- D. Pedro II era criança, governaram regentes
- Várias revoltas: Cabanagem (PA), Sabinada (BA), Balaiada (MA), Farroupilha (RS)
- "Golpe da Maioridade" antecipa coroação de Pedro II aos 14 anos

**2º Reinado (1840-1889) — D. Pedro II:**
- Auge do café como produto de exportação
- Guerra do Paraguai (1864-1870): maior conflito da América do Sul, Brasil venceu mas saiu endividado
- **Leis abolicionistas:**
  - 1850: Lei Eusébio de Queirós (proíbe tráfico)
  - 1871: Lei do Ventre Livre (filhos de escravos nasciam livres)
  - 1885: Lei dos Sexagenários (libertava maiores de 60)
  - **1888: Lei Áurea** (Princesa Isabel) — fim da escravidão

**Proclamação da República (15/11/1889):**
- Marechal Deodoro da Fonseca
- Causas: insatisfação militar, fim da escravidão alienou elites, ideias republicanas`
            },
            {
              id: 'ch-1-2',
              title: 'Era Vargas e ditadura militar',
              searchQuery: 'Era Vargas ditadura militar Brasil',
              content: `**REPÚBLICA VELHA (1889-1930):**

- "Política do café com leite": SP e MG se revezam na presidência
- Coronelismo: poder dos grandes fazendeiros no interior
- Crise de 1929 (quebra da bolsa de NY) afeta o café brasileiro

---

**ERA VARGAS (1930-1945):**

**Revolução de 1930:** fim da República Velha. Getúlio Vargas chega ao poder.

**Governo Provisório (1930-1934):** centraliza poder, voto feminino (1932).

**Governo Constitucional (1934-1937):** Constituição de 1934, tensões com extremistas (integralistas à direita, comunistas à esquerda).

**Estado Novo (1937-1945):** ditadura.
- Fechou Congresso, suspendeu eleições
- **Censura** à imprensa, perseguição a opositores
- DIP (Departamento de Imprensa e Propaganda) controlava notícias
- Apoio popular pelo trabalhismo

**Conquistas trabalhistas (legado de Vargas):**
- **CLT (1943):** Consolidação das Leis do Trabalho
- Salário mínimo
- Carteira de trabalho
- Férias remuneradas
- Justiça do Trabalho
- Aposentadoria

**Saída do poder (1945):** deposto por militares no fim da Segunda Guerra.

**Volta eleito (1951-1954):** Vargas presidente democraticamente.
- Cria a **Petrobras** (1953) — "O petróleo é nosso!"
- Pressionado por crises, suicidou-se em **24/08/1954**

---

**DEMOCRACIA (1946-1964):**

- **JK (1956-1961):** "50 anos em 5", construiu **Brasília** (capital inaugurada em 1960), automóveis, estradas
- **Jânio Quadros (1961):** renunciou em 7 meses
- **João Goulart (Jango) (1961-1964):** propunha reformas de base (agrária, urbana, educacional). Visto como "comunista" pelos conservadores.

---

**DITADURA MILITAR (1964-1985):**

**Golpe de 1964:** militares depuseram Jango. Apoio dos EUA (Guerra Fria, medo do comunismo).

**Características:**
- **Atos Institucionais (AI):** AI-1, AI-2, AI-3, AI-4
- **AI-5 (1968):** ápice da repressão. Fechou o Congresso, cassou direitos políticos, censura total.
- Tortura sistemática de opositores políticos
- Mortes e desaparecimentos
- Censura à imprensa, música, teatro, cinema

**Presidentes militares:** Castelo Branco, Costa e Silva, Médici, Geisel, Figueiredo.

**"Milagre econômico" (1969-1973):** crescimento de 10% ao ano + concentração de renda + dívida externa.

**Crise:** choque do petróleo (1973), inflação, dívida explode.

**Abertura "lenta, gradual e segura"** (governo Geisel).

**Movimento Diretas Já (1984):** maior mobilização popular pelo voto direto. Emenda foi derrotada.

**Tancredo Neves** eleito indiretamente em 1985, morre antes de assumir.

**José Sarney** assume → começa Nova República.`
            },
            {
              id: 'ch-1-3',
              title: 'Brasil contemporâneo',
              searchQuery: 'Nova República Constituição 1988 Brasil',
              content: `**NOVA REPÚBLICA (1985-presente):**

**José Sarney (1985-1990):**
- Plano Cruzado (tentou conter inflação)
- **Constituição de 1988** — "Constituição Cidadã"

---

**A CONSTITUIÇÃO DE 1988** (importantíssima, cai muito):

Garante:
- Voto direto e secreto
- Voto a partir dos 16 anos (facultativo)
- Voto obrigatório dos 18 aos 70 anos
- Liberdade de expressão, religião, imprensa
- Direitos sociais: saúde, educação, moradia, trabalho, lazer, segurança, previdência
- **SUS** (Sistema Único de Saúde): saúde gratuita e universal
- Direitos dos trabalhadores, mulheres, crianças (ECA), idosos
- Reconhecimento dos povos indígenas
- Meio ambiente como direito de todos

---

**PRESIDENTES E MARCOS:**

**Fernando Collor (1990-1992):**
- 1º presidente eleito por voto direto pós-ditadura
- Confisco da poupança
- **Impeachment em 1992** por corrupção
- Movimento "Caras-pintadas" (jovens nas ruas pela cassação)

**Itamar Franco (1992-1994):** completa mandato.
- Equipe econômica cria o **Plano Real**

**Fernando Henrique Cardoso (FHC) (1995-2002):**
- Estabilização da moeda (fim da hiperinflação)
- Privatizações
- Reeleição em 1998 (emenda permitiu)

**Lula (2003-2010):**
- 1º operário presidente
- **Bolsa Família**, programas sociais
- Crescimento econômico
- Brasil sai do "Mapa da Fome" da ONU (2014)

**Dilma Rousseff (2011-2016):**
- 1ª mulher presidente
- **Impeachment em 2016**
- Operação Lava-Jato (corrupção)

**Michel Temer (2016-2018):** assume após impeachment.

**Jair Bolsonaro (2019-2022):**
- Pandemia de COVID-19
- Polarização política intensa

**Luiz Inácio Lula da Silva (2023-presente):** 3º mandato.

---

**DESAFIOS DO BRASIL CONTEMPORÂNEO:**

- Desigualdade social
- Violência urbana
- Mudanças climáticas (enchentes no RS em 2024, queimadas)
- Educação pública
- Reforma tributária
- Mercado de trabalho e tecnologia
- Polarização política

---

**MOVIMENTOS SOCIAIS RECENTES:**

- Movimento negro
- Feminismo (Lei Maria da Penha, 2006)
- LGBTQIA+
- Indígena (demarcação de terras)
- Movimento dos Sem Terra (MST)
- Ambientalismo`
            }
          ]
        },
        {
          id: 'ch-2',
          title: 'Geografia',
          topics: [
            {
              id: 'ch-2-1',
              title: 'Geografia do Brasil',
              searchQuery: 'regiões do Brasil clima geografia Encceja',
              content: `**AS 5 REGIÕES DO BRASIL:**

**NORTE** (7 estados: AC, AM, AP, PA, RO, RR, TO)
- Maior em área (45% do território)
- Menor em população
- Floresta Amazônica
- Clima: equatorial (quente e úmido)
- Economia: extrativismo, Zona Franca de Manaus
- Rio Amazonas (maior do mundo em volume)

**NORDESTE** (9 estados: AL, BA, CE, MA, PB, PE, PI, RN, SE)
- Sub-regiões: Zona da Mata (litoral úmido), Agreste (transição), Sertão (semiárido), Meio-Norte
- Clima: tropical no litoral, semiárido no sertão
- Economia: turismo, agricultura, indústria (Recife, Salvador, Fortaleza)
- Cultura: forte (samba, frevo, forró, axé)

**CENTRO-OESTE** (4: GO, MT, MS, DF)
- Cerrado, Pantanal
- Agronegócio (soja, milho, gado)
- Brasília: capital federal (inaugurada em 1960)
- Clima: tropical com estação seca

**SUDESTE** (4: ES, MG, RJ, SP)
- Mais populoso (~42% da população)
- Mais industrializado e rico
- São Paulo: maior cidade, centro financeiro
- Rio de Janeiro: turismo, cultura
- Clima: tropical de altitude, tropical atlântico

**SUL** (3: PR, SC, RS)
- Clima: **subtropical** (único do Brasil)
- Tem 4 estações bem definidas
- Pode nevar no inverno em SC e RS
- Forte colonização europeia (alemães, italianos, poloneses)
- Economia: agricultura, indústria, turismo
- **Lages, SC** está aqui ✓

---

**CLIMA DO BRASIL:**

- **Equatorial** (Norte): quente o ano todo, muita chuva
- **Tropical** (Centro): quente, com chuvas no verão e seca no inverno
- **Tropical de altitude** (Sudeste): mais ameno por causa das serras
- **Semiárido** (Sertão NE): pouca chuva, secas longas
- **Subtropical** (Sul): inverno frio, 4 estações
- **Tropical atlântico** (litoral E): chuvas concentradas

---

**HIDROGRAFIA:**

- **Bacia Amazônica:** maior do mundo, Rio Amazonas
- **Bacia do Tocantins-Araguaia**
- **Bacia do São Francisco:** "rio da integração nacional"
- **Bacia do Paraná:** hidrelétricas como **Itaipu** (maior do mundo em geração)

---

**POPULAÇÃO BRASILEIRA:**

- Aproximadamente **215 milhões** (2024)
- **87% urbana** — Brasil é majoritariamente urbano
- Êxodo rural intensificou a partir dos anos 1950
- Maior cidade: São Paulo (~12 milhões)
- Mais populosas: SP, RJ, Brasília, Salvador, Fortaleza, Belo Horizonte`
            },
            {
              id: 'ch-2-2',
              title: 'Globalização e economia',
              searchQuery: 'globalização blocos econômicos Brasil',
              content: `**GLOBALIZAÇÃO:**

Processo de **integração mundial** em três dimensões:
- **Econômica:** comércio internacional, multinacionais
- **Tecnológica:** internet, comunicação instantânea
- **Cultural:** consumo, ideias e modas circulam pelo mundo

Começou após a Segunda Guerra Mundial, acelerou nos anos 1990 com a internet.

**Aspectos positivos:**
- Acesso a produtos do mundo todo
- Troca cultural
- Avanços tecnológicos compartilhados
- Possibilidade de trabalho remoto

**Aspectos negativos:**
- Desigualdade entre países ricos e pobres
- Perda de empregos em alguns setores
- Homogeneização cultural (perda de identidades locais)
- Crises econômicas globais (efeito dominó)
- Poder excessivo de multinacionais

---

**SETORES DA ECONOMIA:**

**Setor Primário:** extrai diretamente da natureza.
- Agricultura, pecuária, mineração, pesca, extrativismo
- Brasil é forte aqui (soja, minério de ferro, carne)

**Setor Secundário:** transforma matérias-primas em produtos.
- Indústria de transformação, construção civil
- Carro, roupa, alimento industrializado

**Setor Terciário:** serviços, comércio.
- Lojas, escolas, hospitais, transporte
- Setor que mais emprega no Brasil

**Setor Quaternário** (mais recente): conhecimento e tecnologia.
- TI, pesquisa, P&D
- O **Studio Wes** está aqui ✓

---

**BLOCOS ECONÔMICOS:**

**Mercosul** (Mercado Comum do Sul):
- Brasil, Argentina, Uruguai, Paraguai (membros plenos)
- Venezuela (suspensa), Bolívia (em processo)
- Reduz impostos no comércio entre os membros

**União Europeia (UE):**
- 27 países europeus
- Moeda única (euro) na maioria
- Livre circulação de pessoas e mercadorias

**BRICS:**
- **B**rasil, **R**ússia, **Í**ndia, **C**hina, **Á**frica do Sul
- Países emergentes com economias grandes
- Expansão recente (Irã, Egito, Etiópia, Emirados, Arábia)

**Outros:**
- USMCA: EUA, México, Canadá (antigo NAFTA)
- APEC: países do Pacífico
- OPEP: países exportadores de petróleo

---

**ECONOMIA BRASILEIRA HOJE:**

**Exportações principais (commodities):**
- Soja (1º do mundo, junto com EUA)
- Minério de ferro
- Carne bovina e de frango
- Café (tradicional)
- Açúcar e álcool
- Petróleo

**Importações:**
- Eletrônicos
- Medicamentos
- Combustíveis específicos
- Bens de capital (máquinas)

**Principais parceiros comerciais:**
- China (maior parceiro desde 2009)
- EUA
- União Europeia
- Argentina`
            },
            {
              id: 'ch-2-3',
              title: 'Questões ambientais e urbanas',
              searchQuery: 'meio ambiente urbanização problemas Brasil',
              content: `**PROBLEMAS URBANOS BRASILEIROS:**

**Favelas e moradia precária:**
- Cerca de 11 milhões de brasileiros vivem em favelas
- Falta de saneamento, regularização fundiária
- Programas: Minha Casa Minha Vida, regularização

**Mobilidade urbana:**
- Trânsito caótico nas grandes cidades
- Transporte público insuficiente
- Dependência do automóvel
- Soluções: metrô, BRT, ciclovias

**Saneamento básico:**
- ~35 milhões sem água tratada
- ~100 milhões sem coleta de esgoto
- Provoca doenças, polui rios

**Violência urbana:**
- Brasil tem altas taxas de homicídio
- Concentrada em jovens negros das periferias
- Tráfico, milícias

**Outros problemas:**
- Desemprego
- Trabalho informal (>40% dos trabalhadores)
- Acesso desigual a educação e saúde
- Enchentes (impermeabilização do solo)

---

**PROBLEMAS AMBIENTAIS BRASILEIROS:**

**Desmatamento da Amazônia:**
- Causas: pecuária, soja, madeira, grilagem, mineração ilegal
- Consequências: perda de biodiversidade, mudança climática, conflito com povos indígenas

**Queimadas:**
- Cerrado, Pantanal, Amazônia
- Pantanal teve queimadas catastróficas em 2020 e 2024
- Destrói fauna, polui o ar

**Poluição:**
- Rios urbanos (Tietê, Pinheiros, Iguaçu)
- Plástico nos oceanos
- Ar nas grandes cidades

**Mudanças climáticas:**
- Eventos extremos mais frequentes
- **Enchentes no Rio Grande do Sul em 2024** (catástrofe histórica)
- Secas prolongadas
- Aumento da temperatura média

---

**SUSTENTABILIDADE:**

**Definição:** desenvolvimento que atende o presente sem comprometer as futuras gerações.

**Tripé da sustentabilidade:**
1. Econômica (viável)
2. Social (justa)
3. Ambiental (preservar)

**Práticas sustentáveis:**
- **3 Rs:** Reduzir, Reutilizar, Reciclar (alguns falam em 5 Rs)
- Energias limpas: solar, eólica, hidrelétrica, biomassa
- Agricultura sustentável (orgânica, agroecologia)
- Transporte coletivo e bicicleta
- Consumo consciente

**Acordos internacionais:**
- **Protocolo de Kyoto** (1997): reduzir emissões de gases estufa
- **Acordo de Paris** (2015): limitar aquecimento a 1,5°C-2°C
- **COP** (Conferências do Clima da ONU): acontecem anualmente. COP30 em **Belém, no Brasil, em 2025**.

---

**ENERGIAS RENOVÁVEIS NO BRASIL:**

O Brasil tem uma matriz **mais limpa que a média mundial**:
- Hidrelétrica: principal fonte
- Eólica: forte no Nordeste (RN, CE, BA)
- Solar: crescendo rápido
- Biomassa: cana-de-açúcar, etanol`
            }
          ]
        },
        {
          id: 'ch-3',
          title: 'Filosofia e Sociologia',
          topics: [
            {
              id: 'ch-3-1',
              title: 'Filosofia: principais pensadores',
              searchQuery: 'filosofia Sócrates Platão Aristóteles Encceja',
              content: `**FILOSOFIA ANTIGA (GRÉCIA):**

**Sócrates (470-399 a.C.):**
- Não escreveu nada (sabemos dele por Platão)
- Método: **maiêutica** (perguntas que fazem o outro pensar)
- Frase famosa: "Só sei que nada sei"
- Condenado à morte por "corromper a juventude"

**Platão (427-347 a.C.):**
- Discípulo de Sócrates
- Teoria das Ideias: existe um mundo perfeito das ideias, separado do mundo material
- **Alegoria da caverna:** pessoas presas veem só sombras na parede; quem sai vê a realidade verdadeira (a filosofia liberta)
- Fundou a **Academia** em Atenas

**Aristóteles (384-322 a.C.):**
- Discípulo de Platão, professor de Alexandre, o Grande
- Mais "pé no chão" que Platão (conhecimento vem da experiência)
- Criou a **lógica formal**
- Política: o homem é um "animal político"

---

**IDADE MÉDIA:**

**Santo Agostinho** (354-430): conciliou cristianismo com filosofia platônica.

**Santo Tomás de Aquino** (1225-1274): conciliou cristianismo com Aristóteles.

---

**FILOSOFIA MODERNA / ILUMINISMO (séc. XVII-XVIII):**

**René Descartes** (1596-1650):
- Pai da filosofia moderna
- "**Penso, logo existo**" (Cogito, ergo sum)
- Dúvida metódica: duvidar de tudo para encontrar uma certeza

**John Locke** (1632-1704):
- Liberalismo, direitos naturais (vida, liberdade, propriedade)
- Mente humana ao nascer é uma "tábula rasa" (sem ideias prévias)

**Jean-Jacques Rousseau** (1712-1778):
- "O homem nasce bom, a sociedade o corrompe"
- **Contrato social:** sociedade baseada em acordo entre cidadãos
- Inspirou a Revolução Francesa

**Immanuel Kant** (1724-1804):
- **Ética do dever** (imperativo categórico)
- "Aja como se a máxima de tua ação devesse, por tua vontade, tornar-se lei universal"

**Voltaire, Montesquieu, Diderot:** outros iluministas importantes.

---

**FILOSOFIA CONTEMPORÂNEA:**

**Karl Marx** (1818-1883):
- Crítica ao capitalismo
- **Luta de classes** (burguesia × proletariado)
- Materialismo histórico: história é movida pela economia
- Inspirou movimentos socialistas e comunistas

**Friedrich Nietzsche** (1844-1900):
- "Deus está morto" (crítica à moral cristã tradicional)
- Super-homem (transvaloração de valores)
- Crítica à mediocridade da modernidade

**Hannah Arendt** (1906-1975):
- Filósofa alemã, judia que fugiu do nazismo
- **Banalidade do mal:** o mal não vem de monstros, mas de pessoas comuns que não pensam
- Cobertura do julgamento de Eichmann (criminoso nazista)
- Conceito de "totalitarismo"

---

**TEMAS FILOSÓFICOS COBRADOS NO ENCCEJA:**

- Ética (o que é certo e errado)
- Política (poder, democracia, justiça)
- Direitos humanos
- Trabalho (sentido, alienação)
- Liberdade e responsabilidade
- Verdade e conhecimento`
            },
            {
              id: 'ch-3-2',
              title: 'Sociologia: trabalho e sociedade',
              searchQuery: 'sociologia Durkheim Marx Weber Encceja',
              content: `**OS 3 FUNDADORES DA SOCIOLOGIA:**

**Émile Durkheim (1858-1917) — francês:**
- Sociologia como ciência
- **Fato social:** maneiras de agir/pensar/sentir que são externas e exercem coerção sobre o indivíduo (leis, religião, moda)
- **Coesão social** e divisão do trabalho
- Estudou suicídio como fenômeno social, não individual

**Karl Marx (1818-1883) — alemão:**
- Já visto em filosofia (interdisciplinar)
- **Luta de classes** como motor da história
- **Mais-valia:** lucro do capitalista vem do trabalho não pago ao trabalhador
- **Alienação:** trabalhador se separa do produto que faz

**Max Weber (1864-1920) — alemão:**
- **Ação social:** sociologia estuda ações que têm sentido para o indivíduo
- **Tipos de dominação:** tradicional (rei), carismática (líder), legal (burocracia)
- **A Ética Protestante e o Espírito do Capitalismo:** religião protestante influenciou o capitalismo
- Burocracia moderna

---

**CONCEITOS-CHAVE:**

**Cultura:** tudo que o ser humano produz — material (objetos, tecnologia) e simbólico (ideias, valores, religião, arte, língua).

**Etnocentrismo:** julgar outras culturas pelos valores da sua, considerando a sua superior. Errado.

**Relativismo cultural:** entender cada cultura no seu próprio contexto.

**Diversidade cultural:** reconhecimento e valorização das diferenças.

**Identidade cultural:** o que liga indivíduos a um grupo (nacional, étnica, de gênero).

**Estereótipo:** generalização simplificada (e geralmente errada) sobre um grupo.

**Preconceito:** atitude negativa baseada em estereótipo.

**Discriminação:** ação concreta de tratar diferente baseado em preconceito.

---

**DESIGUALDADE SOCIAL:**

**Estratificação:** divisão da sociedade em camadas (classes).

**Classes sociais:** divisão pela posição na economia (renda, propriedade, trabalho).

**Índices de desigualdade:**
- Índice de Gini (0 = igualdade total, 1 = desigualdade total). Brasil tem Gini alto.
- IDH (Índice de Desenvolvimento Humano): saúde + educação + renda

**Mobilidade social:** capacidade de mudar de classe (ascender ou descer).

---

**MOVIMENTOS SOCIAIS:**

**Movimento operário:** sindicatos, direitos trabalhistas.

**Feminismo:**
- 1ª onda: voto feminino (Brasil em 1932)
- 2ª onda: igualdade no trabalho, direitos reprodutivos
- 3ª onda: interseccionalidade (raça, classe, gênero)

**Movimento negro:**
- Luta pela igualdade racial
- 20 de novembro: Dia da Consciência Negra (morte de Zumbi dos Palmares)
- **Lei 10.639/03:** ensino de história e cultura afro-brasileira obrigatório

**LGBTQIA+:**
- Casamento homoafetivo (decisão do STF, 2011)
- Criminalização da homofobia (decisão do STF, 2019)

**Indígena:**
- Demarcação de terras
- Proteção cultural
- Saúde e educação específicas

**Ambiental:** preservação, comunidades tradicionais.

---

**TRABALHO E SOCIEDADE HOJE:**

- Trabalho formal vs informal
- Trabalho remoto (pós-pandemia)
- Uberização: aplicativos como iFood, Uber (sem vínculo empregatício)
- Inteligência artificial e o futuro do trabalho`
            },
            {
              id: 'ch-3-3',
              title: 'Cidadania e direitos humanos',
              searchQuery: 'cidadania direitos humanos Constituição Brasil',
              content: `**DIREITOS HUMANOS:**

**Declaração Universal dos Direitos Humanos** (1948, ONU):
- Criada após a Segunda Guerra Mundial (em resposta ao Holocausto)
- 30 artigos
- "Todos os seres humanos nascem livres e iguais em dignidade e direitos"

**Princípios fundamentais:**
- Universais (para todos)
- Indivisíveis (não dá pra escolher quais respeitar)
- Inalienáveis (não podem ser tirados)
- Imprescritíveis (não vencem)

---

**GERAÇÕES DE DIREITOS:**

**1ª geração — Direitos Civis e Políticos** (Liberdade):
- Vida, liberdade, segurança
- Liberdade de expressão, religião
- Voto, participação política
- Igualdade perante a lei

**2ª geração — Direitos Sociais, Econômicos e Culturais** (Igualdade):
- Saúde, educação, moradia
- Trabalho digno, salário
- Previdência social
- Acesso à cultura

**3ª geração — Direitos Difusos** (Fraternidade):
- Meio ambiente saudável
- Paz
- Desenvolvimento sustentável
- Direitos coletivos

**4ª geração:** democracia, informação, bioética.

---

**DIREITOS NO BRASIL — Constituição de 1988:**

A Constituição garante todos esses direitos e prevê leis específicas:

**Estatuto da Criança e do Adolescente (ECA, 1990):**
- Crianças (até 12) e adolescentes (12-18) como sujeitos de direitos
- Proteção integral
- Educação obrigatória dos 4 aos 17 anos
- Combate ao trabalho infantil (proibido para menores de 14)

**Estatuto do Idoso (2003):**
- Pessoas com 60+ anos
- Atendimento prioritário
- Combate à violência contra idosos

**Lei Maria da Penha (2006):**
- Combate à violência contra mulher (doméstica e familiar)
- Medidas protetivas

**Estatuto da Igualdade Racial (2010):**
- Combate ao racismo
- Promoção da igualdade

**Lei de Cotas (2012):**
- 50% das vagas em universidades federais para escola pública
- Cotas raciais e sociais
- Inclui também concursos federais

**Estatuto da Pessoa com Deficiência (2015):**
- Direitos, acessibilidade
- Inclusão social

---

**CIDADANIA — DIREITOS E DEVERES:**

**Direitos do cidadão brasileiro:**
- Votar e ser votado
- Acesso à saúde (SUS), educação pública
- Liberdade de expressão e organização
- Justiça gratuita (se necessário)
- Defesa do consumidor

**Deveres:**
- Cumprir a lei
- Pagar impostos
- Votar (obrigatório 18-70)
- Respeitar os direitos dos outros
- Preservar o meio ambiente
- Servir o Exército (homens, em tese, mas pouca convocação efetiva)

---

**FORMAS DE PARTICIPAÇÃO POLÍTICA:**

1. **Voto** (eleições)
2. **Plebiscito:** consulta antes da lei (ex: o plebiscito do desarmamento)
3. **Referendo:** consulta após a lei
4. **Iniciativa popular:** projeto de lei assinado por cidadãos (Lei Ficha Limpa, por exemplo)
5. **Manifestações, protestos**
6. **Sindicatos e associações**
7. **Conselhos populares** (saúde, educação)
8. **Ouvidorias e canais de denúncia**

---

**DEMOCRACIA:**

"Governo do povo, pelo povo, para o povo." Pressupõe:
- Eleições livres e periódicas
- Separação de poderes (Executivo, Legislativo, Judiciário)
- Liberdade de expressão e imprensa
- Respeito às minorias
- Estado de Direito (todos sujeitos à lei)

**Tipos:**
- **Direta:** povo decide diretamente (rara)
- **Representativa:** povo elege representantes
- **Participativa:** mistura representação + mecanismos diretos

---

**EXERCÍCIO DA CIDADANIA EXIGE:**
- Informação (saber o que está em jogo)
- Pensamento crítico
- Diálogo e tolerância
- Participação ativa`
            }
          ]
        }
      ]
    }
  ]
};

// ============================================
// COMPONENTE PRINCIPAL
// ============================================

export default function EnccejaRetroPlatform() {
  const [currentView, setCurrentView] = useState('home');
  const [currentAreaId, setCurrentAreaId] = useState(null);
  const [currentTopicId, setCurrentTopicId] = useState(null);
  const [completedTopics, setCompletedTopics] = useState(new Set());
  const [mobileMenuOpen, setMobileMenuOpen] = useState(false);

  useEffect(() => {
    try {
      const saved = localStorage.getItem('encceja-progress-v2');
      if (saved) setCompletedTopics(new Set(JSON.parse(saved)));
    } catch (e) {}
  }, []);

  const toggleComplete = (topicId) => {
    const newSet = new Set(completedTopics);
    if (newSet.has(topicId)) newSet.delete(topicId);
    else newSet.add(topicId);
    setCompletedTopics(newSet);
    try {
      localStorage.setItem('encceja-progress-v2', JSON.stringify([...newSet]));
    } catch (e) {}
  };

  const allTopics = useMemo(() =>
    COURSE_DATA.areas.flatMap(a => a.modules.flatMap(m => m.topics.map(t => ({ ...t, areaId: a.id })))),
    []
  );

  const totalProgress = Math.round((completedTopics.size / allTopics.length) * 100);

  const currentArea = currentAreaId ? COURSE_DATA.areas.find(a => a.id === currentAreaId) : null;
  const currentTopic = currentTopicId ? allTopics.find(t => t.id === currentTopicId) : null;

  const goHome = () => {
    setCurrentView('home');
    setCurrentAreaId(null);
    setCurrentTopicId(null);
    window.scrollTo(0, 0);
  };

  const goArea = (id) => {
    setCurrentAreaId(id);
    setCurrentTopicId(null);
    setCurrentView('area');
    window.scrollTo(0, 0);
  };

  const goTopic = (areaId, topicId) => {
    setCurrentAreaId(areaId);
    setCurrentTopicId(topicId);
    setCurrentView('topic');
    window.scrollTo(0, 0);
  };

  // ====== ESTILOS RETRO COMPARTILHADOS ======
  const colors = {
    bg: '#FFF8E7',
    bgAlt: '#FFE9C7',
    ink: '#1A1A1A',
    paper: '#FFFFFF',
    red: '#FF5252',
    yellow: '#FFD93D',
    teal: '#4ECDC4',
    purple: '#A78BFA',
    pink: '#FF8FB1',
    green: '#7BC950'
  };

  const RetroWindow = ({ title, children, accent = colors.red, style = {} }) => (
    <div style={{
      background: colors.paper,
      border: `2.5px solid ${colors.ink}`,
      boxShadow: `5px 5px 0 ${colors.ink}`,
      ...style
    }}>
      {/* Title bar */}
      <div style={{
        background: accent,
        borderBottom: `2.5px solid ${colors.ink}`,
        padding: '0.5rem 0.75rem',
        display: 'flex',
        alignItems: 'center',
        gap: '0.5rem'
      }}>
        <div style={{ display: 'flex', gap: '0.4rem' }}>
          <div style={{ width: 12, height: 12, borderRadius: '50%', background: colors.paper, border: `1.5px solid ${colors.ink}` }} />
          <div style={{ width: 12, height: 12, borderRadius: '50%', background: colors.paper, border: `1.5px solid ${colors.ink}` }} />
        </div>
        {title && (
          <div className="retro-mono" style={{ fontSize: '0.75rem', fontWeight: 700, color: colors.ink, flex: 1, textAlign: 'center', paddingRight: '2rem' }}>
            {title}
          </div>
        )}
      </div>
      <div>{children}</div>
    </div>
  );

  return (
    <div style={{ minHeight: '100vh', background: colors.bg, color: colors.ink }}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Rubik+Mono+One&family=Bricolage+Grotesque:opsz,wght@12..96,400;12..96,500;12..96,700;12..96,800&family=JetBrains+Mono:wght@400;700&display=swap');
        
        * { box-sizing: border-box; }
        body { margin: 0; font-family: 'Bricolage Grotesque', system-ui, sans-serif; }
        
        .retro-display { font-family: 'Rubik Mono One', monospace; letter-spacing: -0.01em; }
        .retro-mono { font-family: 'JetBrains Mono', monospace; }
        
        .squiggle {
          background-image: linear-gradient(45deg, transparent 33.33%, ${colors.ink} 33.33%, ${colors.ink} 50%, transparent 50%, transparent 83.33%, ${colors.ink} 83.33%, ${colors.ink} 100%);
          background-size: 12px 4px;
          height: 4px;
        }
        
        .grid-bg {
          background-color: ${colors.bg};
          background-image:
            linear-gradient(${colors.ink}15 1px, transparent 1px),
            linear-gradient(90deg, ${colors.ink}15 1px, transparent 1px);
          background-size: 24px 24px;
        }

        .retro-btn {
          background: ${colors.paper};
          border: 2.5px solid ${colors.ink};
          box-shadow: 4px 4px 0 ${colors.ink};
          padding: 0.6rem 1.1rem;
          font-family: 'Bricolage Grotesque', sans-serif;
          font-weight: 700;
          font-size: 0.95rem;
          cursor: pointer;
          color: ${colors.ink};
          transition: transform 0.1s, box-shadow 0.1s;
          display: inline-flex;
          align-items: center;
          gap: 0.5rem;
        }
        .retro-btn:hover { transform: translate(2px, 2px); box-shadow: 2px 2px 0 ${colors.ink}; }
        .retro-btn:active { transform: translate(4px, 4px); box-shadow: 0 0 0 ${colors.ink}; }

        .retro-btn-primary { background: ${colors.red}; color: ${colors.paper}; }
        .retro-btn-success { background: ${colors.green}; color: ${colors.ink}; }
        
        .content-prose p { margin: 0 0 1.1em 0; line-height: 1.7; font-size: 1.05rem; }
        .content-prose strong { font-weight: 800; background: ${colors.yellow}; padding: 0 3px; }
        .content-prose table { border-collapse: collapse; margin: 1em 0; }
        .content-prose td { border: 1.5px solid ${colors.ink}; padding: 0.4rem 0.75rem; }
        
        @keyframes bounce-in {
          0% { opacity: 0; transform: translateY(15px); }
          100% { opacity: 1; transform: translateY(0); }
        }
        .fade-in { animation: bounce-in 0.4s ease forwards; }
        
        .area-tile { transition: transform 0.15s ease; }
        .area-tile:hover { transform: translate(-2px, -2px); }
        .area-tile:hover .tile-shadow { transform: translate(2px, 2px); }
        
        @media (max-width: 768px) {
          .desktop-only { display: none !important; }
        }
        @media (min-width: 769px) {
          .mobile-only { display: none !important; }
        }
      `}</style>

      {/* ============ HEADER ============ */}
      <header style={{
        position: 'sticky', top: 0, zIndex: 100,
        background: colors.bg,
        borderBottom: `2.5px solid ${colors.ink}`,
        padding: '0.85rem 1.25rem',
        display: 'flex', alignItems: 'center', justifyContent: 'space-between'
      }}>
        <div onClick={goHome} style={{ cursor: 'pointer', display: 'flex', alignItems: 'center', gap: '0.75rem' }}>
          <div style={{
            width: 42, height: 42,
            background: colors.red,
            border: `2.5px solid ${colors.ink}`,
            display: 'flex', alignItems: 'center', justifyContent: 'center',
            boxShadow: `3px 3px 0 ${colors.ink}`
          }}>
            <BookOpen size={20} color={colors.paper} strokeWidth={2.5} />
          </div>
          <div>
            <div className="retro-display" style={{ fontSize: '1.05rem', lineHeight: 1 }}>ENCCEJA</div>
            <div className="retro-mono" style={{ fontSize: '0.65rem', opacity: 0.7, marginTop: 2 }}>v2026 · ENSINO MÉDIO</div>
          </div>
        </div>

        <div style={{ display: 'flex', alignItems: 'center', gap: '0.85rem' }}>
          <div className="desktop-only retro-mono" style={{ 
            background: colors.yellow, 
            border: `2px solid ${colors.ink}`,
            padding: '0.35rem 0.75rem',
            fontSize: '0.75rem',
            fontWeight: 700
          }}>
            {totalProgress}% · {completedTopics.size}/{allTopics.length}
          </div>
          <button
            className="mobile-only retro-btn"
            onClick={() => setMobileMenuOpen(!mobileMenuOpen)}
            style={{ padding: '0.4rem 0.6rem' }}
          >
            {mobileMenuOpen ? <X size={18} /> : <Menu size={18} />}
          </button>
        </div>
      </header>

      {/* Mobile menu */}
      {mobileMenuOpen && (
        <div className="mobile-only" style={{
          background: colors.bgAlt,
          borderBottom: `2.5px solid ${colors.ink}`,
          padding: '1rem 1.25rem'
        }}>
          <button onClick={() => { goHome(); setMobileMenuOpen(false); }} className="retro-btn" style={{ width: '100%', marginBottom: '0.5rem', justifyContent: 'flex-start' }}>
            🏠 Início
          </button>
          {COURSE_DATA.areas.map(area => (
            <button key={area.id} onClick={() => { goArea(area.id); setMobileMenuOpen(false); }} className="retro-btn" style={{ width: '100%', marginBottom: '0.5rem', background: area.color, justifyContent: 'flex-start' }}>
              {area.number} · {area.shortTitle}
            </button>
          ))}
        </div>
      )}

      {/* ============ HOME VIEW ============ */}
      {currentView === 'home' && (
        <main className="fade-in grid-bg" style={{ minHeight: 'calc(100vh - 70px)', padding: '2.5rem 1.5rem' }}>
          <div style={{ maxWidth: 1100, margin: '0 auto' }}>
            
            {/* HERO */}
            <div style={{
              display: 'grid',
              gridTemplateColumns: 'repeat(auto-fit, minmax(280px, 1fr))',
              gap: '2rem',
              alignItems: 'center',
              marginBottom: '3.5rem'
            }}>
              <div>
                <div className="retro-mono" style={{ 
                  display: 'inline-block',
                  background: colors.yellow,
                  border: `2px solid ${colors.ink}`,
                  padding: '0.25rem 0.6rem',
                  fontSize: '0.7rem',
                  fontWeight: 700,
                  marginBottom: '1rem'
                }}>
                  ★ PLATAFORMA GRATUITA ★
                </div>
                <h1 className="retro-display" style={{
                  fontSize: 'clamp(2.5rem, 7vw, 4.5rem)',
                  lineHeight: 0.95,
                  margin: '0 0 1.25rem 0'
                }}>
                  Tudo que cai no <span style={{ background: colors.teal, padding: '0 0.2em', display: 'inline-block', transform: 'rotate(-2deg)' }}>Encceja</span>,
                  organizado pra você.
                </h1>
                <p style={{ fontSize: '1.15rem', lineHeight: 1.55, margin: '0 0 1.75rem 0', fontWeight: 500 }}>
                  Conteúdo das <strong style={{ background: colors.yellow, padding: '0 4px' }}>4 áreas oficiais</strong> da prova, com módulos, tópicos e vídeo-aulas do YouTube. Progresso salvo automático.
                </p>
                <div style={{ display: 'flex', gap: '0.75rem', flexWrap: 'wrap' }}>
                  <button className="retro-btn retro-btn-primary" onClick={() => goArea('linguagens')}>
                    Começar agora <ArrowUpRight size={18} />
                  </button>
                  <button className="retro-btn" onClick={() => document.getElementById('areas')?.scrollIntoView({ behavior: 'smooth' })}>
                    Ver áreas
                  </button>
                </div>
              </div>

              {/* Decorative window with stats */}
              <RetroWindow title="status.app" accent={colors.purple}>
                <div style={{ padding: '1.25rem' }}>
                  <div style={{ display: 'grid', gridTemplateColumns: '1fr 1fr', gap: '1rem' }}>
                    <div style={{ background: colors.yellow, padding: '0.85rem', border: `2px solid ${colors.ink}` }}>
                      <div className="retro-mono" style={{ fontSize: '0.65rem', fontWeight: 700 }}>DATA</div>
                      <div className="retro-display" style={{ fontSize: '1.3rem', marginTop: 4 }}>23/08</div>
                      <div style={{ fontSize: '0.75rem', marginTop: 2 }}>2026</div>
                    </div>
                    <div style={{ background: colors.teal, padding: '0.85rem', border: `2px solid ${colors.ink}` }}>
                      <div className="retro-mono" style={{ fontSize: '0.65rem', fontWeight: 700 }}>MÍNIMA</div>
                      <div className="retro-display" style={{ fontSize: '1.3rem', marginTop: 4 }}>100</div>
                      <div style={{ fontSize: '0.75rem', marginTop: 2 }}>pts/área</div>
                    </div>
                    <div style={{ background: colors.pink, padding: '0.85rem', border: `2px solid ${colors.ink}` }}>
                      <div className="retro-mono" style={{ fontSize: '0.65rem', fontWeight: 700 }}>QUESTÕES</div>
                      <div className="retro-display" style={{ fontSize: '1.3rem', marginTop: 4 }}>120</div>
                      <div style={{ fontSize: '0.75rem', marginTop: 2 }}>+ redação</div>
                    </div>
                    <div style={{ background: colors.green, padding: '0.85rem', border: `2px solid ${colors.ink}` }}>
                      <div className="retro-mono" style={{ fontSize: '0.65rem', fontWeight: 700 }}>PROGRESSO</div>
                      <div className="retro-display" style={{ fontSize: '1.3rem', marginTop: 4 }}>{totalProgress}%</div>
                      <div style={{ fontSize: '0.75rem', marginTop: 2 }}>concluído</div>
                    </div>
                  </div>
                </div>
              </RetroWindow>
            </div>

            <div className="squiggle" style={{ marginBottom: '3rem' }} />

            {/* ÁREAS */}
            <div id="areas">
              <div style={{ display: 'flex', alignItems: 'center', gap: '1rem', marginBottom: '1.5rem' }}>
                <h2 className="retro-display" style={{ fontSize: 'clamp(1.5rem, 4vw, 2.25rem)', margin: 0 }}>
                  Áreas do conhecimento
                </h2>
                <div style={{ flex: 1, height: '2.5px', background: colors.ink }} />
                <Sparkles size={24} />
              </div>

              <div style={{ display: 'grid', gridTemplateColumns: 'repeat(auto-fit, minmax(280px, 1fr))', gap: '1.5rem' }}>
                {COURSE_DATA.areas.map(area => {
                  const areaTopics = area.modules.flatMap(m => m.topics);
                  const areaCompleted = areaTopics.filter(t => completedTopics.has(t.id)).length;
                  const progress = Math.round((areaCompleted / areaTopics.length) * 100);

                  return (
                    <div key={area.id} className="area-tile" style={{ position: 'relative' }}>
                      <div className="tile-shadow" style={{ 
                        position: 'absolute', 
                        inset: 0, 
                        background: colors.ink, 
                        transform: 'translate(6px, 6px)', 
                        transition: 'transform 0.15s',
                        zIndex: 0
                      }} />
                      <button
                        onClick={() => goArea(area.id)}
                        style={{
                          position: 'relative',
                          width: '100%',
                          background: area.color,
                          border: `2.5px solid ${colors.ink}`,
                          padding: 0,
                          cursor: 'pointer',
                          fontFamily: 'inherit',
                          color: colors.ink,
                          textAlign: 'left',
                          zIndex: 1
                        }}
                      >
                        {/* fake title bar */}
                        <div style={{
                          background: colors.ink,
                          color: colors.paper,
                          padding: '0.4rem 0.75rem',
                          display: 'flex',
                          alignItems: 'center',
                          gap: '0.5rem'
                        }}>
                          <div style={{ display: 'flex', gap: '0.3rem' }}>
                            <div style={{ width: 9, height: 9, borderRadius: '50%', background: colors.red }} />
                            <div style={{ width: 9, height: 9, borderRadius: '50%', background: colors.yellow }} />
                            <div style={{ width: 9, height: 9, borderRadius: '50%', background: colors.green }} />
                          </div>
                          <div className="retro-mono" style={{ fontSize: '0.7rem', fontWeight: 700 }}>
                            area-{area.number}.html
                          </div>
                        </div>

                        <div style={{ padding: '1.5rem 1.25rem 1.25rem' }}>
                          <div className="retro-mono" style={{ fontSize: '0.7rem', fontWeight: 700, opacity: 0.7, marginBottom: '0.4rem' }}>
                            ÁREA {area.number}
                          </div>
                          <div className="retro-display" style={{ fontSize: '1.5rem', lineHeight: 1.05, marginBottom: '1rem' }}>
                            {area.shortTitle}
                          </div>
                          
                          <div style={{ 
                            background: colors.paper, 
                            border: `2px solid ${colors.ink}`, 
                            padding: '0.5rem 0.75rem',
                            display: 'flex',
                            justifyContent: 'space-between',
                            alignItems: 'center'
                          }}>
                            <span className="retro-mono" style={{ fontSize: '0.7rem', fontWeight: 700 }}>
                              {area.modules.length} módulos · {areaTopics.length} tópicos
                            </span>
                            <span className="retro-mono" style={{ fontSize: '0.85rem', fontWeight: 700 }}>
                              {progress}%
                            </span>
                          </div>

                          <div style={{
                            marginTop: '0.75rem',
                            display: 'flex',
                            alignItems: 'center',
                            justifyContent: 'flex-end',
                            gap: '0.4rem',
                            fontWeight: 700,
                            fontSize: '0.9rem'
                          }}>
                            Estudar <ArrowUpRight size={16} strokeWidth={2.5} />
                          </div>
                        </div>
                      </button>
                    </div>
                  );
                })}
              </div>
            </div>

            {/* DICA */}
            <RetroWindow title="dica-de-estudo.txt" accent={colors.green} style={{ marginTop: '3rem' }}>
              <div style={{ padding: '1.5rem' }}>
                <div className="retro-mono" style={{ fontSize: '0.7rem', fontWeight: 700, marginBottom: '0.75rem', opacity: 0.7 }}>
                  // ESTRATÉGIA RECOMENDADA
                </div>
                <p style={{ fontSize: '1.1rem', lineHeight: 1.55, margin: 0, fontWeight: 500 }}>
                  Estude <strong style={{ background: colors.yellow, padding: '0 4px' }}>1 a 2 tópicos por dia</strong>. Assista à vídeo-aula do tópico antes de ler o texto. Em 3 meses você cobre tudo com folga e ainda sobra tempo pra revisar e fazer provas anteriores.
                </p>
              </div>
            </RetroWindow>

          </div>
        </main>
      )}

      {/* ============ AREA VIEW ============ */}
      {currentView === 'area' && currentArea && (
        <main className="fade-in" style={{ padding: '2rem 1.5rem', minHeight: 'calc(100vh - 70px)' }}>
          <div style={{ maxWidth: 900, margin: '0 auto' }}>
            <button onClick={goHome} className="retro-btn" style={{ marginBottom: '1.5rem' }}>
              <ArrowLeft size={16} /> Voltar
            </button>

            <div style={{
              background: currentArea.color,
              border: `2.5px solid ${colors.ink}`,
              padding: '1.75rem',
              boxShadow: `6px 6px 0 ${colors.ink}`,
              marginBottom: '2.5rem'
            }}>
              <div className="retro-mono" style={{ fontSize: '0.75rem', fontWeight: 700, marginBottom: '0.5rem' }}>
                ÁREA {currentArea.number} · ENSINO MÉDIO
              </div>
              <h1 className="retro-display" style={{
                fontSize: 'clamp(1.75rem, 5vw, 2.75rem)',
                lineHeight: 1,
                margin: 0
              }}>
                {currentArea.title}
              </h1>
            </div>

            {currentArea.modules.map((module, mIdx) => (
              <div key={module.id} style={{ marginBottom: '2.5rem' }}>
                <div style={{ display: 'flex', alignItems: 'baseline', gap: '0.75rem', marginBottom: '1.25rem' }}>
                  <div className="retro-mono" style={{
                    background: colors.ink,
                    color: colors.paper,
                    padding: '0.2rem 0.5rem',
                    fontSize: '0.85rem',
                    fontWeight: 700
                  }}>
                    {String(mIdx + 1).padStart(2, '0')}
                  </div>
                  <h2 className="retro-display" style={{ fontSize: '1.4rem', margin: 0 }}>
                    {module.title}
                  </h2>
                  <div style={{ flex: 1, height: '2.5px', background: colors.ink }} />
                </div>

                <div style={{ display: 'grid', gap: '0.6rem' }}>
                  {module.topics.map(topic => {
                    const done = completedTopics.has(topic.id);
                    return (
                      <button
                        key={topic.id}
                        onClick={() => goTopic(currentArea.id, topic.id)}
                        style={{
                          display: 'flex', alignItems: 'center', justifyContent: 'space-between',
                          background: colors.paper,
                          border: `2.5px solid ${colors.ink}`,
                          boxShadow: `3px 3px 0 ${colors.ink}`,
                          padding: '0.85rem 1.1rem',
                          cursor: 'pointer',
                          fontFamily: 'inherit',
                          fontSize: '1rem',
                          color: colors.ink,
                          textAlign: 'left',
                          fontWeight: 500,
                          transition: 'transform 0.1s, box-shadow 0.1s'
                        }}
                        onMouseEnter={e => { e.currentTarget.style.transform = 'translate(-2px, -2px)'; e.currentTarget.style.boxShadow = `5px 5px 0 ${colors.ink}`; }}
                        onMouseLeave={e => { e.currentTarget.style.transform = 'translate(0, 0)'; e.currentTarget.style.boxShadow = `3px 3px 0 ${colors.ink}`; }}
                      >
                        <div style={{ display: 'flex', alignItems: 'center', gap: '0.75rem' }}>
                          <div style={{
                            width: 22, height: 22,
                            border: `2px solid ${colors.ink}`,
                            background: done ? colors.green : colors.paper,
                            display: 'flex', alignItems: 'center', justifyContent: 'center'
                          }}>
                            {done && <Check size={14} strokeWidth={3} />}
                          </div>
                          <span>{topic.title}</span>
                        </div>
                        <ChevronRight size={18} strokeWidth={2.5} />
                      </button>
                    );
                  })}
                </div>
              </div>
            ))}
          </div>
        </main>
      )}

      {/* ============ TOPIC VIEW ============ */}
      {currentView === 'topic' && currentTopic && currentArea && (
        <main className="fade-in" style={{ padding: '2rem 1.5rem', minHeight: 'calc(100vh - 70px)' }}>
          <div style={{ maxWidth: 780, margin: '0 auto' }}>
            <button onClick={() => goArea(currentArea.id)} className="retro-btn" style={{ marginBottom: '1.5rem' }}>
              <ArrowLeft size={16} /> {currentArea.shortTitle}
            </button>

            {/* Title card */}
            <div style={{
              background: currentArea.color,
              border: `2.5px solid ${colors.ink}`,
              padding: '1.5rem',
              boxShadow: `6px 6px 0 ${colors.ink}`,
              marginBottom: '2rem'
            }}>
              <div className="retro-mono" style={{ fontSize: '0.7rem', fontWeight: 700, marginBottom: '0.4rem' }}>
                {currentArea.shortTitle.toUpperCase()}
              </div>
              <h1 className="retro-display" style={{
                fontSize: 'clamp(1.6rem, 4.5vw, 2.4rem)',
                lineHeight: 1.05,
                margin: 0
              }}>
                {currentTopic.title}
              </h1>
            </div>

            {/* YOUTUBE EMBED */}
            <RetroWindow title="video-aula.youtube" accent={colors.red} style={{ marginBottom: '2rem' }}>
              <div style={{ padding: '0.5rem' }}>
                <div style={{
                  position: 'relative',
                  paddingBottom: '56.25%',
                  height: 0,
                  overflow: 'hidden',
                  border: `2px solid ${colors.ink}`
                }}>
                  <iframe
                    style={{ position: 'absolute', top: 0, left: 0, width: '100%', height: '100%', border: 0 }}
                    src={`https://www.youtube.com/embed?listType=search&list=${encodeURIComponent(currentTopic.searchQuery)}`}
                    title={currentTopic.title}
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    allowFullScreen
                  />
                </div>
                <div style={{ 
                  marginTop: '0.6rem',
                  display: 'flex',
                  justifyContent: 'space-between',
                  alignItems: 'center',
                  gap: '0.5rem',
                  flexWrap: 'wrap'
                }}>
                  <div className="retro-mono" style={{ fontSize: '0.7rem', fontWeight: 700, opacity: 0.7 }}>
                    🎬 vídeos atualizados do YouTube
                  </div>
                  <a 
                    href={`https://www.youtube.com/results?search_query=${encodeURIComponent(currentTopic.searchQuery)}`} 
                    target="_blank" 
                    rel="noopener noreferrer"
                    className="retro-btn"
                    style={{ fontSize: '0.8rem', padding: '0.4rem 0.75rem', textDecoration: 'none' }}
                  >
                    <Play size={14} /> Ver mais
                  </a>
                </div>
              </div>
            </RetroWindow>

            {/* CONTENT */}
            <RetroWindow title={`${currentTopic.title}.md`} accent={colors.yellow}>
              <div style={{ padding: '1.75rem 1.5rem' }}>
                <div className="content-prose">
                  {currentTopic.content.split('\n\n').map((para, i) => {
                    const html = para
                      .replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>')
                      .replace(/\n/g, '<br/>');
                    return <p key={i} dangerouslySetInnerHTML={{ __html: html }} />;
                  })}
                </div>
              </div>
            </RetroWindow>

            {/* Mark complete */}
            <div style={{ 
              marginTop: '2rem', 
              display: 'flex', 
              justifyContent: 'space-between', 
              alignItems: 'center', 
              flexWrap: 'wrap', 
              gap: '1rem' 
            }}>
              <button
                onClick={() => toggleComplete(currentTopic.id)}
                className={`retro-btn ${completedTopics.has(currentTopic.id) ? 'retro-btn-success' : 'retro-btn-primary'}`}
                style={{ fontSize: '1rem' }}
              >
                <Check size={18} strokeWidth={2.5} />
                {completedTopics.has(currentTopic.id) ? 'Tópico concluído!' : 'Marcar como concluído'}
              </button>

              <div className="retro-mono" style={{ 
                background: colors.yellow, 
                border: `2px solid ${colors.ink}`,
                padding: '0.35rem 0.75rem',
                fontSize: '0.75rem',
                fontWeight: 700
              }}>
                {totalProgress}% concluído
              </div>
            </div>
          </div>
        </main>
      )}

      {/* Footer squiggle */}
      <div className="squiggle" style={{ marginTop: '3rem' }} />
      <footer style={{ 
        padding: '1.5rem', 
        textAlign: 'center', 
        background: colors.bgAlt,
        borderTop: `2.5px solid ${colors.ink}`
      }}>
        <div className="retro-mono" style={{ fontSize: '0.75rem', fontWeight: 700 }}>
          ★ FEITO COM ❤ PARA ESTUDANTES DO ENCCEJA 2026 ★
        </div>
      </footer>
    </div>
  );
}
