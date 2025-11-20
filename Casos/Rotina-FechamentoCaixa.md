-------------------------------------------
## ✅ CENÁRIO 05 – FECHAMENTO DE CAIXA
-------------------------------------------
### Caso de Teste 01: Fechar caixa com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C05-CT01	 | Caixa do dia fechado e registrado.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Haver pelo menos uma venda no dia.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o usuário abre o Livro Caixa
QUANDO clicar em “Fechar Caixa”
ENTÃO o caixa deve ser finalizado.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|O dia fica bloqueado para novas movimentações.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1EqRbj1dYfjwWkRD4YJMZPMXzAfUdeVEA/view?usp=drive_link)|

### Caso de Teste 02: Tentar fechar caixa sem vendas no dia
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C05-CT02	 | Sistema deve permitir fechamento vazio.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma venda registrada.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que usuário tenta fechar caixa
QUANDO clicar em Fechar
ENTÃO deve permitir fechar o caixa.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|permitir fechar.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1Td42s1ceNUtr8-TZi0JNNGBeACqNP8-D/view?usp=drive_link)|

### Caso de Teste 03: Retirada de valores com sucesso
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C05-CT03	 | Retirada registrada e visível no livro caixa.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Caixa aberto.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o usuário acessa “Retirar Valores”
E clica em Novo
QUANDO preencher Valor e Histórico
ENTÃO retirada deve aparecer registrada.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Entrada listada corretamente.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1FEhJ5eIBwrrfgFAR9ypVsj2U6iwzFW3V/view?usp=drive_link)|

### Caso de Teste 04: Retirada sem preencher campos obrigatórios
| ID       | Descrição                                                        |
| :------- | :---------------------------------------------------------------- |
|C05-CT04	 | Sistema deve bloquear retirada incompleta.|

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
|Nenhuma.|

| **Passos**                                             |
| :------------------------------------------------------------ |
DADO que o usuário deixa historico sem nada
QUANDO tentar salvar
ENTÃO deve exibir alerta de obrigatoriedade.

| **Critérios de Aceitação**                                             |
| :------------------------------------------------------------ |
|Retirada não registrada.|

| **Video**                                         |
| :------------------------------------------------------------ |
|[Video](https://drive.google.com/file/d/1AQgFPL8m_BPdeFna5xlyBWzhY4uDRz8b/view?usp=drive_link)|