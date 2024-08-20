# OAuth 2.0 Architecture Overview

A arquitetura do OAuth 2.0 é baseada em um conjunto de componentes principais que interagem para permitir o acesso seguro a recursos protegidos. Esses componentes trabalham juntos para garantir que aplicativos possam acessar dados em nome de um usuário sem expor suas credenciais.

Principais Componentes:

- **Resource Owner**: O usuário que possui o recurso.
- **Client**: A aplicação que deseja acessar o recurso.
- **Authorization Server**: O servidor que autentica o usuário e emite tokens.
- **Resource Server**: O servidor que hospeda o recurso protegido e valida os tokens emitidos.

![abstract](./img/oauth-abstract.png)

## Fluxo de Interações na Arquitetura OAuth 2.0
O fluxo básico de interações na arquitetura OAuth 2.0 segue os seguintes passos:

1. **Solicitação de Autorização**: O Client redireciona o Resource Owner para o Authorization Server, solicitando permissão para acessar os recursos protegidos.

2. **Autenticação e Autorização**: O Resource Owner autentica-se no Authorization Server e concede ou nega a autorização ao Client.

3. **Emissão de Token**: Se autorizado, o Authorization Server emite um Access Token (e opcionalmente um Refresh Token) e o fornece ao Client.

4. **Acesso ao Recurso**: O Client usa o Access Token para fazer uma solicitação ao Resource Server. O Resource Server valida o token e, se válido, concede acesso ao recurso solicitado.

5. **Atualização de Token (opcional)**: Se o Access Token expirar, o Client pode usar o Refresh Token para solicitar um novo Access Token ao Authorization Server.
