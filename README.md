# Bovenos Fluxo — MVP operacional

Protótipo web acadêmico desenvolvido para o Hackathon Tech FMU 2026.2. O sistema ajuda a registrar e consultar três sinais da operação do salão: tempo de fila por estação, tempo de liberação de mesas e observações da equipe sobre os alimentos.

> **Aviso:** os dados iniciais são fictícios e servem apenas para demonstrar o funcionamento. O protótipo não está conectado à operação real da unidade Augusta.

## O que funciona nesta versão

- Cronômetro manual de fila nas estações Saladas, Pratos quentes, Sobremesas e Churrasqueira.
- Mapa de 12 mesas e fluxo de estados: Disponível → Ocupada → Aguardando limpeza → Em limpeza → Disponível.
- Registro de observações sobre alimentos: sobra percebida, pouca procura, elogio ou reclamação.
- Painel de visão geral e indicadores com históricos.
- Exportação dos registros para CSV.
- Armazenamento local no navegador (LocalStorage), sem servidor.
- Layout responsivo para desktop e celular.

## Como executar

**Opção 1 — abrir direto:** dê dois cliques em `index.html` e abra no Chrome, Edge ou Firefox atualizado.

**Opção 2 — servidor local (recomendado):**

1. Abra o terminal ou Prompt de Comando dentro desta pasta.
2. Execute:

   ```bash
   py -m http.server 8000
   ```

3. Abra `http://localhost:8000` no navegador.

Não é necessário instalar bibliotecas, criar banco de dados ou configurar chaves de API.

## Roteiro rápido de demonstração

1. Na tela **Visão geral**, mostre o tempo médio de fila, as mesas aguardando limpeza e os sinais de qualidade.
2. Abra **Operação do salão** e inicie uma medição na estação Churrasqueira. Aguarde alguns segundos e finalize.
3. No mapa, selecione uma mesa disponível e marque como ocupada. Depois registre a saída, inicie a limpeza e libere a mesa.
4. No formulário, registre uma observação de sobra percebida ou pouca procura para um alimento.
5. Abra **Indicadores** para mostrar os históricos e exporte o CSV.

## Como os dados funcionam

- Os registros ficam no armazenamento local do navegador e do dispositivo utilizados.
- Dados feitos num computador não aparecem automaticamente em outro computador.
- Os cartões iniciais são amostras fictícias para o pitch. Use o botão **Restaurar demonstração** na tela Indicadores para repor os exemplos.
- A exportação CSV permite analisar os dados fora da aplicação.

## Limites declarados

Esta versão não faz reconhecimento de alimentos por IA, não estima o peso de cada ingrediente, não controla balanças, não altera o processo de pesagem, não executa pagamentos e não se integra às comandas eletrônicas. Também não mede automaticamente sobras dos pratos ou o volume das cubas do buffet. As observações de alimentos são inseridas manualmente pela equipe.

Essas limitações são intencionais: a apresentação do desafio pediu manutenção do modelo por quilo e indicou pagamentos, cozinha, compras e estoque fora do escopo. A visão computacional para análise do mix do prato pode ser uma fase futura, após coleta autorizada de imagens, rotulagem, calibração e validação.

## Estrutura do repositório

```text
bovenos-fluxo/
├── index.html
├── README.md
├── Documentacao_MVP_Bovenos_Fluxo_revisada.docx
├── apresentacao_Bovenos_Fluxo.pptx
├── roteiro_pitch.md
└── screenshots/
    ├── 01-visao-geral.png
    ├── 02-operacao.png
    └── 03-indicadores.png
```

## Publicar no GitHub

1. Crie um repositório **público** no GitHub com o nome `bovenos-fluxo`.
2. Coloque nele os arquivos e pastas listados acima.
3. Faça o commit e o push.
4. Abra o repositório numa janela anônima para confirmar que está público.
5. Copie o link do repositório e envie à organização pelo canal indicado no regulamento.

Pelo terminal, se o Git estiver instalado:

```bash
git init
git add .
git commit -m "Entrega do MVP Bovenos Fluxo"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/bovenos-fluxo.git
git push -u origin main
```

Substitua `SEU-USUARIO` pelo usuário real do GitHub. Não coloque senhas ou tokens no repositório.

## Testes executados no protótipo

- Navegação entre as três áreas.
- Renderização das quatro estações e das 12 mesas.
- Início/fim de uma medição de fila e cálculo da duração.
- Ciclo completo de estado de uma mesa e registro da limpeza.
- Cadastro de observação de alimento.
- Atualização dos indicadores e exportação CSV.

## Próximas evoluções

1. Validar o fluxo com funcionários e gerência do restaurante.
2. Adicionar backend, autenticação e base central caso o piloto exija uso simultâneo em vários dispositivos.
3. Estudar visão computacional para o mix do prato com imagens autorizadas e um conjunto rotulado.
4. Estimar pesos por ingrediente apenas após calibração com pesagens de referência.
5. Avaliar integrações com os sistemas atuais somente com documentação e autorização do estabelecimento e dos fornecedores.

## Checklist da equipe

Consulte `CHECKLIST_ENTREGA.md` para separar o que já está pronto do que ainda exige ação da equipe (publicar o repositório, gravar/subir o vídeo e enviar os links).
