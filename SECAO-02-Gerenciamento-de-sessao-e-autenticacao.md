## Seção 2: Gerenciamento de Sessão e Autenticação

Slides: https://www.slideshare.net/AlcyonJunior/aula-02-curso-gratuito-ead-de-desenvolvimento-seguro-de-software-com-alcyon-junior

### Objetivos

- identificar problemas envolvidos no uso de senha.
- Aplicar princípios de gerenciamento de senhas.
- Explicar como funciona o gerenciamento de sessão.
- Receonhecer problemas em gerenciamento de sessão.
- Reconhecer as melhores soluções para problemas em gerenciamento de sessão.
- Reconhecer problemas e soluções de CSRF e Clickjacking.

Quando falamos de senhas a parte mais importante ou fundamental é o controle, e quando falamos em controle não é simplesmente ter um usuário com senha, ou campo com criptografia, ssl e esquecer da parte de controle. Nesses controles temos:

### Senhas

- Entropia de Senha
  - Senhas longas versus senhas complexas: Não adianta colocar um senha com 32 caracters que contenha uma palavra grande como por exemplo: incontitucionalicimamente.
    - `Senha longa`: Por mais que ela seja grande com vários digitos se for uma palavra de dicionário ela sera descoberta por meio de um ataque de força bruta que usa exatamente um dicionário.
    - `Senha complexa`: Envolve umaa montagem de uma palavra, montagem de uma senha difícil, porém existem as senhas que possuem nome do filho, data de nascimento, parte do CPF e isso atrapalha um pouco a segurança.
- Mitigações
    - Tentativas de Autenticação 5x vezes erradas, faz o bloqueio
    - Atraso - Você poderá digitar sua senha após x tempo
    - Bloqueio de conta
- Armazenamento de Sennha: A forma que é armazenada nos servidores como por exemplo, `hash` dentro do banco de dados evitando leitura crua dos dados.

### Gerenciamento de sessão

- `Logon Entrar` - Início de Sessão
    - Longa ID de sessão
    - Sem reuso de ID de sessão
    - Enviar cookies via canal encriptado
- `Atualiza Sessão` - Diretro após o log-on
  - Invalida a sessão anterior - Browser aberto por muito tempo.
`Logou Sair`: Invalida a sessão - Mata a sessão e não pode ser utilizada.

### CSRF e Clickjacking
- `Cross-Site Request Forgery (CSRF)` ou Falsificação de Solicitação Cruzada entre Sites
  - Para explorar essa vulnerabilidade, o atacante prepara um link específico para tirar vantagem desta transação: http://bank.co/tranfer.do/acct=hacker&amount=500
- `Clickjacking`: A grosso modo é achar que está clicando em algo conhecido, porém o conteúdo foi alterado.
    - Ou seja pode ter um link na página que redireciona para um servidor falso 