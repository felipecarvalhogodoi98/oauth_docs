# Fluxo de Autorização via Código

O fluxo de código de autorização é o fluxo mais amplamente utilizado no OAuth 2.0 devido à sua segurança e flexibilidade. Este fluxo é ideal para aplicativos confidenciais, como servidores back-end, que podem manter em segredo o client secret. Ele envolve uma interação em duas etapas, onde o Authorization Code é trocado por um Access Token, garantindo que o Access Token nunca seja exposto diretamente ao usuário final ou a um ambiente inseguro, como o navegador.

## Visão Geral do Fluxo
O Authorization Code Flow segue os seguintes passos principais:

**Solicitação de Autorização**: O Client redireciona o Resource Owner para o Authorization Server, solicitando permissões para acessar recursos protegidos.

**Consentimento e Código de Autorização**: O Resource Owner autentica-se e, se concordar em conceder as permissões solicitadas, o Authorization Server emite um Authorization Code e redireciona o Resource Owner de volta ao Client.

**Troca de Código por Token**: O Client envia o Authorization Code juntamente com sua client secret ao Authorization Server para obter um Access Token.

**Acesso ao Recurso**: O Client usa o Access Token para acessar os recursos protegidos no Resource Server.
