# Gym Tracker Bot - Guia do Usuário

## Como Acessar

Acesse o bot diretamente no Telegram clicando no link abaixo ou buscando pelo nome:

**[@meu_gym_tracker_bot](https://t.me/meu_gym_tracker_bot)**

Ou busque por `@meu_gym_tracker_bot` na barra de pesquisa do Telegram.

---

## O que é o Gym Tracker?

O **Gym Tracker** é um bot de Telegram que funciona como seu assistente pessoal de treino. Ele permite que você registre seus exercícios de forma simples e natural, usando texto ou áudio, e acompanhe sua evolução ao longo do tempo.

### Principais funcionalidades:

- **Registro natural**: Envie mensagens como "supino reto 3x10 60kg" ou grave um áudio descrevendo seu treino
- **Estatísticas detalhadas**: Veja seu progresso, recordes pessoais e volume de treino
- **Consultas inteligentes**: Pergunte qualquer coisa sobre seus treinos usando linguagem natural
- **Metas e lembretes**: Defina objetivos e receba lembretes nos dias de treino
- **Exportação de dados**: Baixe seu histórico completo em CSV ou JSON
- **Gamificação**: Acompanhe sua sequência de treinos consecutivos

---

## Comandos Disponíveis

### Comandos Básicos

#### `/start`
Inicia o bot e cadastra você como usuário. Este é o primeiro comando que você deve usar.

```
/start
```

**Resposta:** Mensagem de boas-vindas com a lista de comandos disponíveis.

---

#### `/help`
Mostra a lista completa de comandos disponíveis.

```
/help
```

---

#### `/status`
Mostra o status do seu treino atual, incluindo todas as séries registradas na sessão.

```
/status
```

**Exemplo de resposta:**
```
📊 Treino em andamento

Supino Reto: 3x10 60kg
Agachamento: 4x8 80kg
Rosca Direta: 3x12 15kg

Total: 10 séries
```

---

#### `/fim`
Finaliza o treino atual manualmente. Use quando terminar sua sessão de treino.

```
/fim
```

**Resposta:** Resumo do treino finalizado com duração, exercícios realizados e sua sequência de treinos.

---

### Estatísticas

#### `/stats`
Mostra um resumo geral dos seus treinos (total de sessões, exercícios e séries).

```
/stats
```

**Exemplo de resposta:**
```
📊 Suas estatísticas gerais

Total de treinos: 45
Total de exercícios: 320
Total de séries: 1.280
```

---

#### `/stats <exercício>`
Mostra estatísticas detalhadas de um exercício específico.

```
/stats supino reto
```

**O que mostra:**
- Total de séries realizadas
- Média de repetições
- Peso máximo levantado
- Peso médio
- 1RM estimado (repetição máxima)
- Volume total (reps × peso)

**Exemplo de resposta:**
```
📊 Estatísticas: Supino Reto

Séries: 89
Reps (média): 10
Peso máximo: 80kg
Peso médio: 62kg
1RM estimado: 107kg
Volume total: 55.180kg
```

---

#### `/frequencia`
Mostra sua frequência de treinos semanal e mensal.

```
/frequencia
```

**Exemplo de resposta:**
```
📅 Frequência de treinos

Esta semana: 3 treinos
Este mês: 12 treinos
Média semanal: 3.2 treinos
```

---

#### `/recordes`
Lista seus 10 maiores pesos por exercício (recordes pessoais).

```
/recordes
```

**Exemplo de resposta:**
```
🏆 Seus recordes pessoais

1. Agachamento: 120kg
2. Supino Reto: 80kg
3. Levantamento Terra: 140kg
...
```

---

#### `/grafico`
Gera gráficos visuais da sua evolução. Você pode escolher entre três tipos:

```
/grafico
```

**Opções disponíveis:**
- **Peso**: Evolução do peso máximo por exercício ao longo do tempo
- **Volume**: Volume total (reps × peso) por dia de treino
- **Frequência**: Quantidade de dias de treino por semana

---

#### `/sequencia`
Mostra sua sequência atual de treinos consecutivos (streak).

```
/sequencia
```

**Exemplo de resposta:**
```
🔥 Sua sequência de treinos

Sequência atual: 7 dias
Recorde pessoal: 14 dias
Próximo marco: 14 dias

Continue assim! 💪
```

**Marcos de sequência:** 7, 14, 30, 60 e 100 dias consecutivos.

---

### Consultas Inteligentes

#### `/query <pergunta>`
Faça qualquer pergunta sobre seus treinos usando linguagem natural. O bot usa IA para entender e responder.

```
/query qual meu maior peso no supino?
```

```
/query quantos treinos fiz este mês?
```

```
/query qual exercício eu mais fiz na última semana?
```

```
/query qual foi meu volume total de peito ontem?
```

**Limite:** 5 consultas por hora para manter a qualidade do serviço.

---

#### `/insight`
Gera uma análise automática e inteligente dos seus treinos.

```
/insight
```

**O que mostra:**
- Progresso recente
- Consistência de treino
- Equilíbrio muscular
- Destaques e conquistas
- Sugestões de melhoria

---

### Exportação

#### `/export`
Exporta seu histórico completo de treinos. Você pode escolher o formato.

```
/export
```

**Formatos disponíveis:**
- **CSV**: Planilha compatível com Excel, Google Sheets, etc.
- **JSON**: Formato estruturado para desenvolvedores

**Limite:** 3 exportações por hora.

---

### Histórico

#### `/sessions`
Lista suas sessões de treino recentes.

```
/sessions
```

**Exemplo de resposta:**
```
📜 Últimos treinos

1. 28/02 - 45min - 12 séries
2. 26/02 - 50min - 15 séries
3. 24/02 - 40min - 10 séries
...
```

---

#### `/session <dia/mês>`
Mostra os detalhes completos de um treino em uma data específica.

```
/session 15/01
```

```
/session 28/02
```

**Exemplo de resposta:**
```
📋 Treino de 28/02

Duração: 45 minutos

Exercícios:
• Supino Reto: 4x10 70kg
• Supino Inclinado: 3x12 50kg
• Crucifixo: 3x15 20kg
• Tríceps Corda: 4x12 25kg

Total: 14 séries
```

---

#### `/evolucao <exercício>`
Mostra a evolução de peso de um exercício ao longo do tempo.

```
/evolucao agachamento
```

```
/evolucao supino reto
```

**Exemplo de resposta:**
```
📈 Evolução: Agachamento

Jan/26: 80kg → 90kg (+12.5%)
Fev/26: 90kg → 100kg (+11.1%)

Progresso total: +25% em 2 meses
```

---

### Correção de Exercícios

#### `/corrigir`
Permite corrigir exercícios da última mensagem enviada. Use quando cometer um erro no registro.

**Listar exercícios para correção:**
```
/corrigir
```

**Mudar o nome do exercício:**
```
/corrigir 1 nome "Supino Inclinado"
```

**Mudar número de séries:**
```
/corrigir 2 series 4
```

**Mudar repetições:**
```
/corrigir 1 reps 12
```

**Mudar peso:**
```
/corrigir 1 peso 50
```

**Remover exercício:**
```
/corrigir 1 deletar
```

**Nota:** O número (1, 2, etc.) refere-se à posição do exercício na lista mostrada por `/corrigir`.

---

### Metas

#### `/meta <exercício> <peso>kg`
Define uma meta de peso para um exercício.

```
/meta supino reto 100kg
```

```
/meta agachamento 150kg
```

**Resposta:** Confirmação da meta criada com seu progresso atual.

---

#### `/meta remover <exercício>`
Remove uma meta existente.

```
/meta remover supino reto
```

---

#### `/metas`
Lista todas as suas metas ativas com o progresso de cada uma.

```
/metas
```

**Exemplo de resposta:**
```
🎯 Suas metas

Supino Reto: 80kg / 100kg (80%)
████████░░

Agachamento: 120kg / 150kg (80%)
████████░░
```

---

### Lembretes

#### `/lembrete`
Mostra a configuração atual de lembretes.

```
/lembrete
```

---

#### `/lembrete <dias> <hora>`
Configura lembretes de treino para dias e horários específicos.

```
/lembrete seg,qua,sex 18:00
```

```
/lembrete ter,qui 07:30
```

**Dias disponíveis:** `seg`, `ter`, `qua`, `qui`, `sex`, `sab`, `dom`

**Exemplo:** O comando acima configura lembretes para segunda, quarta e sexta às 18:00.

---

#### `/lembrete off`
Desativa todos os lembretes.

```
/lembrete off
```

---

### Templates

#### `/template`
Acessa seus templates de treino. Templates são rotinas pré-definidas que permitem registrar exercícios rapidamente.

```
/template
```

**Funcionalidades:**
- Ver lista de templates salvos
- Executar um template (registra todos os exercícios automaticamente)
- Criar novos templates
- Editar templates existentes
- Excluir templates

**Exemplo de uso:** Se você sempre faz "Supino 4x10, Crucifixo 3x12, Tríceps 4x15" no dia de peito, crie um template "Peito" e execute-o com um clique.

---

## Como Registrar Exercícios

Você pode registrar exercícios de duas formas:

### Por Texto
Simplesmente envie uma mensagem descrevendo seu exercício:

```
supino reto 3x10 60kg
```

```
agachamento 4x8 80kg
```

```
rosca direta 3 séries de 12 repetições com 15kg
```

```
Fiz leg press com 200kg, 4 séries de 10
```

### Por Áudio
Grave um áudio descrevendo seu treino. O bot transcreve automaticamente e registra os exercícios.

**Dica:** Fale de forma clara e inclua o nome do exercício, séries, repetições e peso.

---

## Dicas de Uso

1. **Seja consistente:** Use sempre o mesmo nome para cada exercício (ou crie aliases)
2. **Finalize seus treinos:** Use `/fim` para registrar a duração correta
3. **Configure lembretes:** Nunca esqueça um treino com `/lembrete`
4. **Acompanhe seu progresso:** Use `/evolucao` e `/grafico` regularmente
5. **Defina metas:** Mantenha-se motivado com `/meta`
6. **Exporte seus dados:** Faça backup periódico com `/export`

---

## Suporte

Encontrou um bug ou tem sugestões? Entre em contato com o administrador do bot.
