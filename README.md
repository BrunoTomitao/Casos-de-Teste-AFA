# 🟦 CENÁRIO 01: Inventário de Estoque
Caso de Teste 01: Importação de XML válida e geração da compra.
ID	Descrição
C01-CT01	Importar um XML válido e gerar a compra com entrada correta no estoque.
Pré-condições
O arquivo XML deve ser válido e conter produtos corretamente.
Passos
DADO que o usuário acessa Pedidos > Importar XML de Compra
E preenche CFOP, Grupo e ST Entrada
E seleciona um XML válido ao clicar em “Importar XML”
QUANDO clicar em “Gerar Compra” e depois “Finalizar”
ENTÃO a compra deve ser confirmada e os produtos inseridos no estoque
Critérios de aceitação
A compra deve aparecer com status CONFIRMADA e o estoque atualizado.
Teste passou com sucesso.
Caso de Teste 02: Tentativa de importar XML inválido.
ID	Descrição
C01-CT02	O sistema deve rejeitar arquivos XML inválidos ou corrompidos.
Pré-condições
O arquivo XML está corrompido ou com estrutura incompatível.
Passos
DADO que o usuário acessa a tela de importação de XML
E seleciona um XML inválido
QUANDO clicar em “Importar XML”
ENTÃO deve ser exibida uma mensagem de erro adequado
Critérios de aceitação
A importação deve ser bloqueada e o XML não pode ser processado.
Teste passou com sucesso.
Caso de Teste 03: Tentativa de importação sem preencher CFOP ou Grupo.
ID	Descrição
C01-CT03	A importação deve ser bloqueada se campos obrigatórios estiverem em branco.
Pré-condições
Nenhuma.
Passos
DADO que o usuário acessa a tela de importação
E deixa CFOP ou Grupo em branco
QUANDO tentar clicar em “Importar XML”
ENTÃO o sistema deve exibir mensagens de “campo obrigatório”
Critérios de aceitação
A importação só pode ocorrer com todos os campos preenchidos.
Teste passou com sucesso.
Caso de Teste 04: Geração de compra sem confirmação de entrada.
ID	Descrição
C01-CT04	A compra deve permanecer pendente caso o usuário não confirme a entrada.
Pré-condições
Um XML válido foi importado e gerou uma compra.
Passos
DADO que o usuário gerou a compra após a importação do XML
QUANDO sair da tela sem mudar o status para “CONFIRMADA”
ENTÃO a compra deve permanecer pendente e o estoque não deve ser alterado
Critérios de aceitação
Estoque inalterado e compra marcada como pendente.
Teste passou com sucesso.
# 🟦 CENÁRIO 02: Processamento de Venda (PDV)
Caso de Teste 01: Realização de venda completa com sucesso.
ID	Descrição
C02-CT01	Registrar uma venda completa com produtos, finalização e caixa.
Pré-condições
Cliente, funcionário e produtos devem estar cadastrados.
Passos
DADO que o usuário acessa o módulo de vendas
E clica em “Novo”
E seleciona cliente, funcionário e data
E insere produtos com quantidade e preço
QUANDO clicar em “Finalizar” e selecionar pagamento
ENTÃO a venda deve ser registrada no Livro Caixa
Critérios de aceitação
Venda registrada e estoque atualizado.
Teste passou com sucesso.
Caso de Teste 02: Tentativa de vender produto sem estoque.
ID	Descrição
C02-CT02	O sistema deve impedir venda de produtos com estoque zerado.
Pré-condições
Produto com quantidade = 0 no estoque.
Passos
DADO que o usuário tenta inserir um produto sem estoque
QUANDO selecionar a quantidade
ENTÃO o sistema deve exibir “Estoque insuficiente”
Critérios de aceitação
O produto não deve ser incluído na venda.
Teste passou com sucesso.
Caso de Teste 03: Aplicar desconto total quando já existe desconto por item.
ID	Descrição
C02-CT03	O sistema deve bloquear desconto geral quando já há desconto por item.
Pré-condições
Venda contendo ao menos um item com desconto.
Passos
DADO que um item da venda possui desconto individual
QUANDO o usuário tentar aplicar desconto total
ENTÃO o sistema deve exibir alerta e impedir a ação
Critérios de aceitação
Desconto total deve ser bloqueado.
Teste passou com sucesso.
Caso de Teste 04: Finalização da venda sem selecionar tipo de documento.
ID	Descrição
C02-CT04	O sistema deve impedir finalização da venda sem informar tipo de pagamento.
Pré-condições
Venda iniciada e pronta para finalização.
Passos
DADO que o usuário tenta finalizar a venda
QUANDO clicar em “Salvar” sem selecionar tipo de documento
ENTÃO o sistema deve exibir uma mensagem de erro
Critérios de aceitação
A venda só deve ser finalizada após o preenchimento correto.
Teste passou com sucesso.
# 🟦 CENÁRIO 03: Compra por Fornecedor
Caso de Teste 01: Realizar compra completa com entrada no estoque.
ID	Descrição
C03-CT01	Registrar compra, finalizar e atualizar estoque.
Pré-condições
Fornecedor e produtos devem estar cadastrados.
Passos
DADO que o usuário cria uma nova compra
E informa fornecedor, condição e data
E insere produtos com quantidade, frete e desconto
QUANDO clicar em “Finalizar”
ENTÃO o estoque deve ser atualizado após a confirmação
Critérios de aceitação
Compra confirmada e estoque atualizado.
Teste passou com sucesso.
Caso de Teste 02: Tentativa de criar compra sem fornecedor.
ID	Descrição
C03-CT02	O sistema deve impedir compra sem fornecedor.
Pré-condições
Nenhuma.
Passos
DADO que o usuário tenta criar uma compra
QUANDO clicar em “Salvar” sem informar fornecedor
ENTÃO o sistema deve exibir erro de campo obrigatório
Critérios de aceitação
A compra não deve ser criada.
Teste passou com sucesso.
Caso de Teste 03: Tentativa de inserir tipo de documento inválido para compra a prazo.
ID	Descrição
C03-CT03	O sistema deve impedir tipos de pagamento que alimentam caixa em compras a prazo.
Pré-condições
Compra registrada como “A Prazo”.
Passos
DADO que o usuário tenta inserir tipo de documento inválido
QUANDO selecionar um documento que alimenta caixa
ENTÃO deve aparecer alerta e bloquear a ação
Critérios de aceitação
Bloqueio da seleção inadequada.
Teste passou com sucesso.
# 🟦 CENÁRIO 04: Gestão de Clientes
Caso de Teste 01: Cadastro de cliente Pessoa Física com sucesso.
ID	Descrição
C04-CT01	Realizar cadastro simples de cliente Pessoa Física.
Pré-condições
Nenhuma.
Passos
DADO que o usuário clica em “Novo”
E preenche Nome, Tipo, CEP e Endereço
QUANDO clicar em “Salvar”
ENTÃO o cliente deve aparecer na listagem
Critérios de aceitação
Cadastro salvo com sucesso.
Teste passou com sucesso.
Caso de Teste 02: Tentativa de cadastrar cliente com campos obrigatórios vazios.
ID	Descrição
C04-CT02	O sistema deve bloquear cadastro incompleto.
Pré-condições
Nenhuma.
Passos
DADO que o usuário deixa Nome ou CEP em branco
QUANDO tentar salvar
ENTÃO o sistema deve exibir mensagem de erro
Critérios de aceitação
Cadastro não deve ser realizado.
Teste passou com sucesso.
Caso de Teste 03: Venda acima do limite de crédito.
ID	Descrição
C04-CT03	Sistema deve alertar, mas permitir continuar via Contas a Receber.
Pré-condições
Cliente com limite de crédito ativo.
Passos
DADO que o cliente possui limite de crédito definido
QUANDO a venda ultrapassar esse valor
ENTÃO deve exibir alerta e abrir fluxo de contas a receber
Critérios de aceitação
Venda pode prosseguir após confirmação.
Teste passou com sucesso.
Caso de Teste 04: Cadastro de dependente corretamente.
ID	Descrição
C04-CT04	Usuário deve conseguir vincular dependentes a um cliente.
Pré-condições
Cliente principal já cadastrado.
Passos
DADO que o usuário acessa a aba Dependentes
QUANDO clicar em “Novo” e selecionar o dependente
ENTÃO o dependente deve aparecer vinculado na lista
Critérios de aceitação
Dependente vinculado com sucesso.
Teste passou com sucesso.
# 🟦 CENÁRIO 05: Fechamento de Caixa
Caso de Teste 01: Fechar caixa com sucesso.
ID	Descrição
C05-CT01	O fechamento do caixa deve ser registrado corretamente.
Pré-condições
Deve haver ao menos uma venda no dia.
Passos
DADO que o usuário acessa o Livro Caixa
QUANDO clicar em “Fechar Caixa”
ENTÃO o caixa deve ser finalizado e nenhuma nova ação permitida
Critérios de aceitação
Caixa encerrado e bloqueado para movimentações.
Teste passou com sucesso.
Caso de Teste 02: Tentativa de fechar caixa sem vendas.
ID	Descrição
C05-CT02	O sistema deve impedir fechamento sem movimentações.
Pré-condições
Não existe venda registrada no dia.
Passos
DADO que o usuário tenta fechar o caixa
QUANDO clicar em “Fechar Caixa”
ENTÃO deve ser exibido aviso de ausência de movimentações
Critérios de aceitação
Fechamento deve ser bloqueado.
Teste passou com sucesso.
Caso de Teste 03: Realizar retirada de valores do caixa.
ID	Descrição
C05-CT03	Registrar retirada de valores com sucesso.
Pré-condições
Caixa deve estar aberto.
Passos
DADO que o usuário acessa “Retirar Valores”
E clica em “Novo”
QUANDO preencher Valor, Tipo de Documento e Histórico
ENTÃO a retirada deve ser exibida no Livro Caixa
Critérios de aceitação
Registro correto da retirada.
Teste passou com sucesso.
Caso de Teste 04: Tentativa de retirada sem preencher campos obrigatórios.
ID	Descrição
C05-CT04	O sistema deve bloquear retirada incompleta.
Pré-condições
Nenhuma.
Passos
DADO que o usuário tenta registrar retirada
E deixa Valor ou Tipo de Documento em branco
QUANDO clicar em “Salvar”
ENTÃO deve ser exibida mensagem de erro
Critérios de aceitação
O registro não pode ser efetuado.
Teste passou com sucesso.
