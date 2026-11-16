# buscar-leads

Skill para o Claude que procura leads para um negócio e entrega uma planilha pronta para prospecção, com diagnóstico digital, prioridade e mensagem de abordagem para cada lead.

Criada por Guilherme Mella (GODI.A).

## O que a skill faz

1. Pergunta três coisas a quem está usando:
   - com o que a pessoa trabalha (ou o link do site da empresa, de onde a skill extrai os serviços);
   - a área da busca (cidade e, se quiser, bairros);
   - quantos leads quer (10, 20, 30 ou 50).
2. Busca negócios no Google Maps e lê as avaliações de cada um.
3. Descarta negócios fechados, concorrentes diretos e franquias.
4. Monta o diagnóstico digital de cada lead: perfil no Google, avaliações, WhatsApp, site e Instagram.
5. Classifica em quente, morno ou frio, com o motivo.
6. Confere Instagram e site dos leads quentes pelo navegador, quando há um disponível.
7. Escreve uma mensagem de abordagem por lead, para envio manual.
8. Entrega uma planilha ordenada por prioridade, com coluna de status para acompanhar os contatos.

## Regras que a skill segue

- Só entra na planilha o que foi visto em uma fonte consultada. Telefone, site e Instagram nunca são deduzidos.
- Campo não conferido recebe "não verificado"; campo procurado e não achado recebe "não encontrado".
- A skill não lista pessoas físicas. Para quem vende ao consumidor final, ela procura parceiros e empresas que levam clientes até o negócio.
- Avaliação negativa nunca é citada na mensagem enviada ao lead.
- A skill não envia mensagens. O envio é sempre manual.

## Estrutura do repositório

```
buscar-leads/
  SKILL.md              instruções da skill
exemplos/
  exemplo-saida.csv     modelo da planilha, com dados fictícios
README.md
```

## Como instalar

1. Baixe a pasta `buscar-leads` (ou este repositório inteiro).
2. No Claude, adicione a skill a partir do arquivo `buscar-leads/SKILL.md`.
3. Para usar, peça algo como "buscar leads" ou "preciso de leads para o meu negócio".

## Colunas da planilha

| Coluna | Conteúdo |
|---|---|
| Prioridade | Quente / Morno / Frio |
| Motivo | Por que recebeu essa prioridade |
| Negócio | Nome |
| Segmento | Nicho |
| Bairro / Cidade | Localização |
| Telefone / WhatsApp | Como publicado |
| Instagram | @ do perfil, ou não verificado |
| Site | URL, ou não verificado |
| Google | Nota e número de avaliações |
| Diagnóstico | Resumo do que foi observado |
| Sinal de oportunidade | O que liga o lead ao serviço oferecido |
| Serviço indicado | Serviço a oferecer primeiro |
| Mensagem | Texto de abordagem |
| Fonte | Link de onde o lead foi tirado |
| Status | Contatado, Respondeu, Reunião, Fechado ou Sem interesse |

## Limitações conhecidas

- A busca na web quase nunca encontra o Instagram de negócios locais pequenos. A conferência depende de um navegador.
- Um celular divulgado no Google não confirma que o negócio atende por WhatsApp.
- A busca do Google Maps usada nos testes não devolve o site do negócio; ele aparece ao abrir a página do lugar no navegador.

## Histórico de testes

- **16/11/2026, teste 1**: Nova Andradina (MS), 50 leads. Instagram e site não puderam ser verificados pela busca na web. As avaliações do Google se mostraram a melhor fonte de sinais.
- **16/11/2026, teste 2**: mesma busca, já com leitura de avaliações e filtro de franquias. Os leads quentes caíram de 15 para 8. A conferência pelo navegador ficou pendente.

## Aviso sobre dados

O arquivo em `exemplos/` é fictício. Listas reais de leads contêm telefones e observações sobre empresas de terceiros e não devem ser publicadas em repositório público.
