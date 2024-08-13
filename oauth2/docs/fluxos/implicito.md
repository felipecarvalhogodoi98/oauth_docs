# Fluxo Implícito

O fluxo implícito foi criado principalmente para aplicativos públicos, como Single Page Applications (SPAs) ou aplicativos móveis, onde o Client não pode manter em segredo o client secret. Diferentemente do fluxo de autorização via código, o fluxo implícito simplifica o processo de obtenção de um Access Token ao eliminar a etapa intermediária de troca de um Authorization Code. Nesse fluxo, o Access Token é retornado diretamente ao Client após a autorização do usuário, sem a necessidade de um servidor back-end para processar a troca do código por um token.

No entanto, devido a preocupações de segurança, o fluxo implícito é considerado menos seguro do que outros fluxos, e seu uso é desencorajado em novas implementações. Em vez disso, o uso do fluxo de autorização via código com PKCE (Proof Key for Code Exchange) é recomendado para situações onde o fluxo implícito seria tradicionalmente usado.

## Visão Geral do Fluxo
O fluxo implícito segue os seguintes passos principais:

**Solicitação de Autorização**: O Client redireciona o Resource Owner para o Authorization Server, solicitando um Access Token diretamente.

**Consentimento e Emissão de Token**: O Resource Owner autentica-se e, se autorizar a solicitação, o Authorization Server emite um Access Token e o envia de volta ao Client na URL de redirecionamento.

**Acesso ao Recurso**: O Client usa o Access Token para acessar os recursos protegidos no Resource Server.