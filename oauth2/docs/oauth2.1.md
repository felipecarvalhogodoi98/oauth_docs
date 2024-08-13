# OAuth 2.1

OAuth 2.1 é um esforço em andamento para consolidar e simplificar os recursos mais usados ​​do OAuth 2.0.

Desde a publicação original do OAuth 2.0 (RFC 6749) em 2012, vários novos RFCs foram publicados que adicionam ou removem funcionalidades da especificação principal, incluindo OAuth 2.0 para aplicativos nativos (RFC 8252), Proof Key for Code Exchange (RFC 7636) ), OAuth para aplicativos baseados em navegador e melhores práticas atuais de segurança do OAuth 2.0.

OAuth 2.1 consolida as alterações publicadas em especificações posteriores para simplificar o documento principal.

As principais diferenças do OAuth 2.0 estão listadas abaixo.

- O PKCE é necessário para todos os clientes OAuth que usam o fluxo de código de autorização
- Os URIs de redirecionamento devem ser comparados usando a correspondência exata de strings
- A concessão implícita (response_type=token) é omitida nesta especificação
- A concessão de credenciais de senha do proprietário do recurso é omitida nesta especificação
- O uso do token de portador omite o uso de tokens de portador na string de consulta de URIs
- Os tokens de atualização para clientes públicos devem ser restritos ao remetente ou de uso único
- As definições de clientes públicos e confidenciais foram simplificadas para se referir apenas se o cliente possui credenciais