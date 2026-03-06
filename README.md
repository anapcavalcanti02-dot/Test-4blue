# Relatório de Testes QA – Microssistema 4blue

**Candidato:** Ana Paula Cavalcanti 
**Data:** 06/03/2025  
**URL do sistema:** https://qa-play-sim.lovable.app/

---

## 1. Bugs identificados

Bugs organizados por tela.

---

### Tela de Login

#### Bug #1

| Campo | Informação |
|-------|------------|
| **Título** | Login permitido com email e senha em branco |
| **Descrição** | Na tela de Login, ao deixar os campos Email e Senha vazios e clicar em "Entrar", o sistema permite o acesso e exibe a tela "Login realizado com sucesso". Não há validação de campos obrigatórios; qualquer usuário pode acessar o sistema sem informar credenciais. |
| **Passos para reproduzir** | 
1. Acessar a tela de Login. 
2. Deixar os campos Email e Senha em branco. 
3. Clicar em "Entrar". |
| **Resultado atual** | O sistema exibe a tela "Login realizado com sucesso" e permite acesso à plataforma. |
| **Resultado esperado** | O sistema deve validar os campos obrigatórios e exibir mensagem solicitando o preenchimento de email e senha antes de prosseguir. |
| **Severidade** | Crítico |
| **Prioridade** | Alta |
| **Link do vídeo** (https://drive.google.com/file/d/1OVgB2p9K6IoWygR35lbmeH2V6jJIBl_Q/view?usp=share_link) | |

#### Bug #2

| Campo | Informação |
|-------|------------|
| **Título** | Mensagem de erro incorreta ao deixar senha em branco no Login |
| **Descrição** | Na tela de Login, ao inserir um email de conta existente mas deixar o campo Senha em branco e clicar em "Entrar", o sistema exibe o alerta "Conta não encontrada. Crie uma conta primeiro." Essa mensagem é incorreta: o problema é a senha em branco, não a inexistência da conta. |
| **Passos para reproduzir** | 
1. Acessar a tela de Login. 
2. Inserir o email de uma conta já criada. 
3. Deixar o campo Senha em branco. 
4. Clicar em "Entrar". |
| **Resultado atual** | Alerta exibido: "Conta não encontrada. Crie uma conta primeiro." |
| **Resultado esperado** | O sistema deve validar o campo Senha e exibir mensagem apropriada, por exemplo: "Por favor, informe sua senha" ou "O campo senha é obrigatório". |
| **Severidade** | Médio |
| **Prioridade** | Média |
| **Link do vídeo** (https://drive.google.com/file/d/1jznfIV02-XlNALNgX15hbe4Mmxsj9IkP/view?usp=share_link) | |

#### Bug #3

| Campo | Informação |
|-------|------------|
| **Título** | Mensagem de erro incorreta ao digitar senha errada no Login |
| **Descrição** | Na tela de Login, ao inserir um email de conta existente com uma senha incorreta e clicar em "Entrar", o sistema exibe o alerta "Conta não encontrada. Crie uma conta primeiro." A mensagem está incorreta: a conta existe, o problema é a senha digitada. |
| **Passos para reproduzir** | 
1. Acessar a tela de Login. 
2. Inserir o email de uma conta já criada. 
3. Inserir uma senha incorreta no campo Senha. 
4. Clicar em "Entrar". |
| **Resultado atual** | Alerta exibido: "Conta não encontrada. Crie uma conta primeiro." |
| **Resultado esperado** | O sistema deve exibir mensagem apropriada, por exemplo: "Senha incorreta" ou "Credenciais inválidas. Verifique seu email e senha." |
| **Severidade** | Médio |
| **Prioridade** | Média |
| **Link do vídeo** (https://drive.google.com/file/d/13YqH7yeRvf92H9hMO7vY93jXgtbsmQIx/view?usp=share_link) | |

#### Bug #4

| Campo | Informação |
|-------|------------|
| **Título** | Mensagem de erro genérica ao digitar email inválido no Login |
| **Descrição** | Na tela de Login, ao inserir um email em formato inválido (ex: sem domínio, sem @, caracteres incorretos) e clicar em "Entrar", o sistema exibe o alerta "Conta não encontrada. Crie uma conta primeiro." Não há validação de formato de email nem mensagem específica para esse caso. |
| **Passos para reproduzir** | 
1. Acessar a tela de Login. 
2. Inserir um email em formato inválido (ex: "teste", "teste@", "teste@email"). 
3. Preencher ou não o campo Senha e clicar em "Entrar". |
| **Resultado atual** | Alerta exibido: "Conta não encontrada. Crie uma conta primeiro." (ou similar). |
| **Resultado esperado** | O sistema deve validar o formato do email e exibir mensagem específica, por exemplo: "Por favor, insira um email válido" ou "Email inválido. Verifique o formato do endereço." |
| **Severidade** | Médio |
| **Prioridade** | Média |
| **Link do vídeo** (https://drive.google.com/file/d/1LgDaf4tqCR3nwPk4p7ESQdtT3luXHmDd/view?usp=share_link) | |

#### Bug #5

| Campo | Informação |
|-------|------------|
| **Título** | Ausência de link "Esqueci minha senha" e uso incorreto do espaço abaixo do campo Senha |
| **Descrição** | Abaixo do campo Senha na tela de Login, é exibido o texto "A senha precisa ter no mínimo 8 caracteres e 1 caractere especial." Esse espaço deveria conter o link/botão "Esqueci minha senha" ou "Recuperar senha". A informação sobre regras de criação de senha é relevante apenas na tela de Criação de Conta, pois na tela de Login o usuário já possui senha definida. Usuários que esquecerem a senha não têm forma de recuperar o acesso à conta. |
| **Passos para reproduzir** | 
1. Acessar a tela de Login. 
2. Observar o conteúdo abaixo do campo Senha. |
| **Resultado atual** | Exibe as regras de criação de senha; não há link para recuperação de senha. |
| **Resultado esperado** | Abaixo do campo Senha: exibir link "Esqueci minha senha" ou similar. As regras de criação de senha devem aparecer somente na tela de Criação de Conta. |
| **Severidade** | Médio |
| **Prioridade** | Média |
| **Link do vídeo** (https://drive.google.com/file/d/1S6rZOeZoub8s2FXDlR4eQLWb7kmgmPel/view?usp=share_link) | |

#### Bug #6

| Campo | Informação |
|-------|------------|
| **Título** | Tecla Enter não dispara a ação de login |
| **Descrição** | Na tela de Login, ao preencher os campos Email e Senha e pressionar a tecla Enter no teclado, a função de login não é executada. O envio do formulário ocorre apenas ao clicar no botão "Entrar". |
| **Passos para reproduzir** | 
1. Acessar a tela de Login. 
2. Preencher os campos Email e Senha. 
3. Pressionar a tecla Enter no teclado (sem clicar no botão). |
| **Resultado atual** | Nada acontece ao pressionar Enter; o login não é processado. |
| **Resultado esperado** | O formulário deve ser submetido ao pressionar Enter (comportamento padrão de formulários web), executando a mesma ação do clique no botão "Entrar". |
| **Severidade** | Médio |
| **Prioridade** | Média |
| **Link do vídeo** *(opcional)* | |

---

### Tela de Criação de Conta

#### Bug #7

| Campo | Informação |
|-------|------------|
| **Título** | Layout inconsistente dos campos: posicionamento e largura (Telefone, Confirmar senha) |
| **Descrição** | Na tela de Criação de Conta, o layout apresenta dois problemas: (1) os campos da coluna direita (Telefone, Confirmar senha) estão posicionados acima dos campos da coluna esquerda (Nome completo, Senha), quebrando a ordem lógica esperada; (2) os campos Telefone e Confirmar senha possuem largura maior que os demais, gerando inconsistência visual. Todos os text fields deveriam seguir um tamanho padrão. |
| **Passos para reproduzir** | 
1. Acessar a tela "Criar conta". 
2. Observar a disposição e a largura dos campos do formulário. |
| **Resultado atual** | Telefone e Confirmar senha aparecem acima/desalinhados em relação aos pares; esses dois campos possuem largura maior que Nome completo, Email e Senha. |
| **Resultado esperado** | Campos alinhados na mesma linha (Nome completo | Telefone, Senha | Confirmar senha) e todos os text fields com largura padronizada. |
| **Severidade** | Médio |
| **Prioridade** | Média |
| **Link do vídeo** (https://drive.google.com/file/d/1uvk1P4yOJ6GJjKBwNQz-qBWjJwA3UOTw/view?usp=share_link) | |

#### Bug #8

| Campo | Informação |
|-------|------------|
| **Título** | Conta é criada com sucesso sem preenchimento dos campos obrigatórios |
| **Descrição** | Na tela de Criação de Conta, ao clicar em "Criar conta" sem informar nenhum dado (Nome completo, Telefone, Email, Senha, Confirmar senha), o sistema aceita o cadastro e exibe a tela de sucesso. Não há validação dos campos obrigatórios. |
| **Passos para reproduzir** | 
1. Acessar a tela "Criar conta". 
2. Não preencher nenhum campo. 
3. Clicar em "Criar conta". |
| **Resultado atual** | A conta é criada e a tela "Conta criada com sucesso" é exibida. |
| **Resultado esperado** | O sistema deve impedir o envio e exibir mensagens indicando quais campos obrigatórios não foram preenchidos. |
| **Severidade** | Crítico |
| **Prioridade** | Alta |
| **Link do vídeo** (https://drive.google.com/file/d/1M2US_46AatzCnJZslVVMu6g_yitY4jlA/view?usp=share_link) | |

#### Bug #9

| Campo | Informação |
|-------|------------|
| **Título** | Campo Telefone sem máscara e aceitando letras |
| **Descrição** | O campo Telefone na tela de Criação de Conta não possui máscara aplicada e aceita letras. O placeholder indica o formato "(00) 00000-0000", mas o usuário pode inserir qualquer sequência de caracteres (números e letras) sem formatação automática nem restrição de tipo. |
| **Passos para reproduzir** | 
1. Acessar a tela "Criar conta". 
2. Clicar no campo Telefone e digitar letras ou texto. 
3. Verificar que a entrada é aceita. |
| **Resultado atual** | O campo aceita entrada livre (números e letras), sem máscara e sem validação de que o valor seja numérico. |
| **Resultado esperado** | O campo deve aceitar apenas números, aplicar máscara no formato (00) 00000-0000 ou similar e rejeitar ou ignorar caracteres não numéricos. |
| **Severidade** | Médio |
| **Prioridade** | Média |
| **Link do vídeo** (https://drive.google.com/file/d/1nMcUNQ9hJtyi7S_KllsdUV78mqyt4c6M/view?usp=share_link) | |

#### Bug #10

| Campo | Informação |
|-------|------------|
| **Título** | Campo Email aceito com formato inválido (ex: sem domínio) |
| **Descrição** | O campo Email não valida o formato do endereço. É possível criar conta com email incompleto, por exemplo sem domínio (ex: "usuario@" ou "usuario"). O botão "Criar conta" aceita o envio. |
| **Passos para reproduzir** | 
1. Acessar a tela "Criar conta". 
2. Preencher o campo Email com formato inválido (ex: "teste" ou "teste@"). 
3. Preencher os demais campos e clicar em "Criar conta". |
| **Resultado atual** | O sistema aceita o cadastro com email em formato inválido. |
| **Resultado esperado** | O sistema deve validar o formato do email e exibir mensagem de erro solicitando um endereço válido (com domínio completo). |
| **Severidade** | Alto |
| **Prioridade** | Alta |
| **Link do vídeo** (https://drive.google.com/file/d/1dCZVivgIorsGTo0MW-QnOsERqANX2EQ3/view?usp=share_link) | |

#### Bug #11

| Campo | Informação |
|-------|------------|
| **Título** | Validação de senha inexistente (requisitos e confirmação) |
| **Descrição** | A tela informa que a senha precisa ter no mínimo 8 caracteres e 1 caractere especial, porém não há validação aplicada. O sistema aceita senhas que não atendem aos requisitos. Além disso, os campos Senha e Confirmar senha podem conter valores diferentes e a conta ainda é criada com sucesso. |
| **Passos para reproduzir** | 
1. Acessar a tela "Criar conta". 
2. Inserir senha com menos de 8 caracteres ou sem caractere especial. 
3. Inserir valor diferente em "Confirmar senha". 
4. Preencher os demais campos e clicar em "Criar conta". |
| **Resultado atual** | A conta é criada mesmo com senha fora dos requisitos e/ou com senhas diferentes nos dois campos. |
| **Resultado esperado** | O sistema deve validar: (a) mínimo 8 caracteres e 1 caractere especial; (b) os campos Senha e Confirmar senha devem ser iguais. Exibir mensagens de erro quando as regras não forem atendidas. |
| **Severidade** | Alto |
| **Prioridade** | Alta |
| **Link do vídeo** (https://drive.google.com/file/d/10lOLUrEC2D5DvBUKUYp-QTCs37jCBdTx/view?usp=share_link) | |

---

### Tela de Sucesso (pós-criação de conta)

#### Bug #12

| Campo | Informação |
|-------|------------|
| **Título** | Inconsistência entre mensagem e opções disponíveis após criar conta |
| **Descrição** | Após concluir o cadastro na tela "Criar conta", o usuário é redirecionado para a tela de sucesso com a mensagem "Sua conta foi criada. Você já pode acessar a plataforma." Porém, o único botão disponível é "Sair da conta". Não há opção para acessar a plataforma. O usuário é obrigado a sair e fazer login novamente para entrar no sistema, o que contradiz a mensagem exibida. |
| **Passos para reproduzir** | 
1. Criar uma conta na tela "Criar conta". 
2. Ser redirecionado para a tela de sucesso. 
3. Observar as opções disponíveis. |
| **Resultado atual** | Apenas o botão "Sair da conta" está disponível; não há forma de acessar a plataforma a partir dessa tela. |
| **Resultado esperado** | Se o usuário está autenticado: incluir botão "Acessar a plataforma" ou "Ir para o início". Se o fluxo exigir novo login: alterar a mensagem (ex: "Conta criada! Faça login para acessar") e incluir botão "Fazer login". |
| **Severidade** | Médio |
| **Prioridade** | Média |
| **Link do vídeo** (https://drive.google.com/file/d/1JpETye3-nbEe_N53171-KaljVCReaQ6E/view?usp=share_link) | |

#### Bug #13

| Campo | Informação |
|-------|------------|
| **Título** | Mensagem "Erro inesperado" exibida após login realizado com sucesso |
| **Descrição** | Ao efetuar login com credenciais válidas, o usuário é redirecionado para a tela de sucesso ("Login realizado com sucesso"). Porém, uma notificação toast aparece no rodapé direito da tela exibindo "Erro inesperado". A mensagem é contraditória: o login foi bem-sucedido, mas o sistema indica um erro. Além disso, a mesma limitação do Bug #11 se aplica: o único botão disponível é "Sair da conta", sem opção para acessar a plataforma. |
| **Passos para reproduzir** | 
1. Acessar a tela de Login. 
2. Inserir email e senha de uma conta válida. 
3. Clicar em "Entrar". 
4. Observar a tela de sucesso e o canto inferior direito. |
| **Resultado atual** | Tela de sucesso exibida, mas notificação "Erro inesperado" aparece no rodapé direito; apenas botão "Sair da conta" disponível. |
| **Resultado esperado** | Após login bem-sucedido: não exibir mensagem de erro; incluir opção para acessar a plataforma (conforme Bug #12). |
| **Severidade** | Alto |
| **Prioridade** | Alta |
| **Link do vídeo** (https://drive.google.com/file/d/1-f_jAorNqa9vpozBhaRWUeON-1kf3FmT/view?usp=share_link) | |

---

## 2. Inconsistências de experiência (UX)

### Tela de Login

1. **Requisitos de senha – espaçamento e legibilidade**  
   O texto "A senha precisa ter no mínimo 8 caracteres e 1 caractere especial." está em fonte menor e muito próximo do campo de senha e do botão "Entrar", o que pode prejudicar a leitura, especialmente em telas pequenas ou por usuários com dificuldade visual. Sugestão: aumentar o espaçamento vertical e, se possível, o tamanho da fonte para melhorar a legibilidade.

2. **Inconsistência de capitalização**  
   Os labels dos campos estão em maiúsculas ("EMAIL", "SENHA"), enquanto o restante da tela (título, subtítulo, texto de requisitos, link "Criar conta") está em capitalização normal. Sugestão: padronizar os labels em capitalização normal ("Email", "Senha") para manter consistência visual e reduzir carga cognitiva.

3. **Texto de regras de senha no lugar inadequado**  
   O texto "A senha precisa ter no mínimo 8 caracteres e 1 caractere especial." aparece abaixo do campo Senha na tela de Login. Essa informação é relevante apenas na tela de Criação de Conta (quando o usuário está definindo a senha). Na tela de Login, o espaço seria mais útil com o link "Esqueci minha senha". Sugestão: remover esse texto da tela de Login e manter apenas na tela de Criação de Conta.

4. **Ausência de ícone para mostrar/ocultar senha**  
   O campo Senha não possui o ícone de olho que permite ao usuário alternar entre mostrar e ocultar o texto digitado. Essa funcionalidade ajuda o usuário a verificar se a senha foi digitada corretamente antes de clicar em "Entrar". Sugestão: adicionar o ícone de olho ao lado do campo Senha, permitindo alternar a visibilidade.

### Tela de Criação de Conta

1. **Inconsistência de capitalização**  
   Todos os labels estão em maiúsculas (NOME COMPLETO, TELEFONE, EMAIL, SENHA, CONFIRMAR SENHA), mesma inconsistência observada na tela de Login. Sugestão: padronizar em capitalização normal para manter consistência entre as telas.

2. **Requisitos de senha – espaçamento e legibilidade**  
   Mesma melhoria sugerida para a tela de Login: aumentar o espaçamento vertical e o tamanho da fonte do texto "A senha precisa ter no mínimo 8 caracteres e 1 caractere especial." para facilitar a leitura.

3. **Responsividade**  
   O formato em duas colunas pode ficar apertado em janelas menores ou monitores com baixa resolução. Como o sistema é exclusivamente web (sem versão mobile), vale conferir o comportamento ao redimensionar a janela do navegador.

---

## 3. Checklist de testes sugeridos

Use este checklist durante a exploração. Marque com [x] os itens testados e registre os bugs no item 1.

### Tela de Login
- [X] Login com credenciais válidas
- [X] Login com email inválido
- [X] Login com senha incorreta
- [X] Login com campos vazios
- [X] Login com senha < 8 caracteres
- [X] Login com senha sem caractere especial
- [X] Inserção de script (XSS) nos campos
- [X] Verificar mensagens de erro exibidas
- [X] Verificar responsividade
- [X] Link "Criar conta" funciona

### Tela de Criação de Conta
- [X] Criação com todos os campos válidos
- [X] Criação com campos obrigatórios vazios
- [X] Senha e Confirmar senha diferentes
- [X] Email em formato inválido
- [X] Telefone em formato inválido
- [X] Senha não atende requisitos (8 chars + especial)
- [X] Verificar validação em tempo real
- [X] Link "Voltar para login" funciona
- [X] Verificar responsividade

### Tela de Sucesso
- [X] Botão "Sair da conta" funciona
- [X] Verificar se mantém sessão ao recarregar
- [X] Verificar se voltar no navegador mantém acesso

### Segurança básica
- [X] Dados sensíveis expostos na URL
- [X] Senha visível ao digitar (ou mascarada)
- [X] Inserção de script (XSS) nos campos

**Resumo – Teste XSS (Cross-Site Scripting):**  
XSS é uma falha em que um atacante insere scripts (ex.: JavaScript) em campos de entrada. Se não tratados, esses scripts podem ser executados no navegador de outros usuários. O teste consiste em inserir payloads como `<script>alert('XSS')</script>` ou `<img src=x onerror=alert('XSS')>` nos campos e verificar se o sistema escapa/sanitiza o conteúdo. Se o script for executado, há vulnerabilidade. A mitigação é sempre escapar ou sanitizar todo input do usuário antes de exibir ou processar.

### UX / Inconsistências
- [X] Mensagens de erro claras e consistentes
- [X] Labels e placeholders adequados
- [X] Feedback visual em ações (loading, sucesso)
- [X] Acessibilidade (contraste, foco, navegação por teclado)
- [X] Ortografia e gramática nos textos

---

## 4. Perguntas finais

### Quais 2 bugs você corrigiria primeiro e por quê?

**Bug 1 a corrigir:** Login permitido com email e senha em branco (Bug #1)  
O sistema permite acesso à plataforma sem informar credenciais, o que representa uma falha grave de segurança. Qualquer pessoa pode acessar o sistema, comprometendo a confidencialidade dos dados e a integridade do controle de acesso. A correção deve ser imediata, implementando validação de campos obrigatórios antes do envio do formulário de login.

**Bug 2 a corrigir:** Conta criada com sucesso sem preenchimento dos campos obrigatórios (Bug #8)  
O sistema aceita a criação de contas sem nenhum dado preenchido, gerando registros inválidos ou incompletos na base de dados. Isso afeta a qualidade dos dados, dificulta operações futuras (ex.: contato, recuperação de senha) e pode indicar falhas na camada de validação que se refletem em outros fluxos. A correção previne a proliferação de contas fantasmas e garante que apenas cadastros válidos sejam persistidos.

---

### Sugestões de melhorias para as telas

1. **Consistência visual e acessibilidade**  
   Padronizar os labels dos campos em capitalização normal (Email, Senha, Nome completo) em vez de maiúsculas, mantendo harmonia entre as telas. Aumentar o espaçamento e o tamanho da fonte do texto de requisitos de senha para melhorar a legibilidade, especialmente para usuários com dificuldade visual.

2. **Ícone para mostrar/ocultar senha**  
   Adicionar o ícone de olho nos campos de senha (Login e Criação de Conta), permitindo ao usuário verificar o que foi digitado antes de enviar o formulário, reduzindo erros e retrabalho.

3. **Tela de Sucesso e fluxo pós-autenticação**  
   Nas telas de sucesso (após login ou criação de conta), incluir botão "Acessar a plataforma" ou "Ir para o início" para que o usuário autenticado possa prosseguir sem precisar sair e fazer login novamente. Isso alinha o fluxo com a mensagem "Você já pode utilizar o sistema".

4. **Feedback visual e validação em tempo real**  
   Implementar validação em tempo real nos formulários, exibindo indicadores de erro ou sucesso conforme o usuário preenche os campos. Incluir feedback de loading no botão "Entrar" e "Criar conta" durante o processamento, evitando múltiplos cliques.

5. **Submissão por teclado**  
   Garantir que o Enter dispare o envio dos formulários (Login e Criação de Conta), seguindo o comportamento padrão esperado em aplicações web e melhorando a acessibilidade para usuários que preferem navegação por teclado.

---

## Referência: Severidade e Prioridade

| Severidade | Critério |
|------------|----------|
| **Crítico** | Sistema inutilizável, perda de dados ou falha grave de segurança |
| **Alto** | Funcionalidade principal quebrada, sem workaround simples |
| **Médio** | Problema relevante, mas com alternativa ou impacto limitado |
| **Baixo** | Erro cosmético, texto, ou inconsistência menor |

| Prioridade | Critério |
|------------|----------|
| **Alta** | Corrigir imediatamente |
| **Média** | Corrigir em breve |
| **Baixa** | Pode ser planejado para versões futuras |
