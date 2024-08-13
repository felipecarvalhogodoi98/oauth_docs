# Definição de termos e funções no OAuth 2.0

O protocolo OAuth 2.0 envolve vários atores e termos específicos que desempenham papéis críticos na sua operação. Compreender esses papéis e a terminologia associada é fundamental para implementar o OAuth 2.0 de forma eficaz e segura. Abaixo estão as descrições detalhadas dos principais termos e papéis envolvidos no processo:

**1. Resource Owner (Proprietário do Recurso)**
O Resource Owner é a entidade que possui e controla o acesso aos recursos protegidos. Em contextos comuns, o Resource Owner é o usuário final, que possui dados pessoais ou outras informações que podem ser acessadas por meio de APIs. Esse usuário pode conceder ou revogar permissões para que um Client acesse seus recursos. No fluxo típico, o Resource Owner interage com o Authorization Server para autorizar o Client a obter um Access Token.

**Exemplo**: Um usuário de uma rede social que concede a um aplicativo de terceiros acesso à sua lista de amigos.

**2. Client (Cliente)**
O Client é a aplicação que deseja acessar recursos protegidos em nome do Resource Owner. Para fazer isso, o Client deve primeiro obter autorização do Resource Owner, normalmente por meio do Authorization Server. Dependendo da natureza da aplicação, o Client pode ser:

**Confidencial**: Uma aplicação que pode proteger suas credenciais, como um backend seguro.
**Pública**: Uma aplicação que não pode proteger suas credenciais, como uma aplicação móvel ou um Single Page Application (SPA).

**Exemplo**: Um aplicativo de terceiros que deseja postar atualizações em uma conta de rede social em nome do usuário.

**3. Authorization Server (Servidor de Autorização)**
O Authorization Server é o componente responsável por autenticar o Resource Owner e emitir os tokens necessários para o Client. Este servidor gerencia a autorização e é responsável por garantir que apenas os Clients autenticados e autorizados possam acessar os recursos protegidos.

**Emissão de Access Tokens**: O Authorization Server emite um Access Token ao Client, que permite o acesso aos recursos protegidos.
**Emissão de Refresh Tokens**: O Authorization Server pode também emitir um Refresh Token, que permite ao Client obter novos Access Tokens quando necessário, sem exigir uma nova autorização do Resource Owner.

**Exemplo**: Um servidor de autenticação como o OAuth 2.0 do Google, que permite que usuários façam login em diferentes aplicativos usando suas credenciais do Google.

**4. Resource Server (Servidor de Recursos)**
O Resource Server hospeda os recursos protegidos que o Client deseja acessar. Ele é responsável por validar o Access Token recebido do Client e garantir que este token seja válido e emitido por um Authorization Server confiável. Se o token for válido, o Resource Server permite que o Client acesse os recursos solicitados.

**Exemplo**: O servidor de API de uma rede social que fornece dados de perfil de usuário para aplicativos autorizados.

**5. Access Token (Token de Acesso)**
O Access Token é uma credencial que o Client usa para acessar recursos protegidos no Resource Server. Este token é emitido pelo Authorization Server após o Resource Owner conceder a autorização. O Access Token contém informações que permitem ao Resource Server validar a identidade do Client e as permissões concedidas.

**Formato**: Pode ser uma string opaca ou um JWT (JSON Web Token), dependendo da implementação.
**Validade**: Os Access Tokens têm uma duração limitada, após a qual se tornam inválidos e devem ser renovados.

**Exemplo**: Um token JWT contendo as permissões concedidas a um aplicativo para acessar a lista de contatos de um usuário.

**6. Refresh Token (Token de Atualização)**
O Refresh Token é uma credencial que o Client pode usar para obter novos Access Tokens sem precisar que o Resource Owner realize uma nova autenticação. Isso é útil para manter sessões longas sem exigir que o usuário autentique repetidamente.

**Segurança**: Refresh Tokens devem ser protegidos rigorosamente, pois podem ser usados para prolongar o acesso aos recursos protegidos.
**Revogação**: O Authorization Server pode revogar Refresh Tokens para encerrar a sessão de um Client.

**Exemplo**: Um Refresh Token que permite a um aplicativo de e-mail sincronizar mensagens em segundo plano sem exigir que o usuário faça login repetidamente.

**7. Authorization Grant (Concessão de Autorização)**
A Authorization Grant é um conjunto de credenciais que o Client usa para obter um Access Token do Authorization Server. Existem diferentes tipos de grants, dependendo do fluxo OAuth 2.0 em uso:

**Authorization Code**: Usado principalmente por aplicações confidenciais, onde o código de autorização é trocado por um Access Token.
**Implicit**: Utilizado por aplicações públicas, onde o Access Token é retornado diretamente.
**Resource Owner Password Credentials**: Usado quando o Client obtém as credenciais do Resource Owner diretamente, geralmente em cenários de confiança elevada.
**Client Credentials**: Usado quando o Client atua em seu próprio nome, em vez de em nome de um Resource Owner.

**Exemplo**: O Authorization Code é obtido quando um usuário consente em permitir que um aplicativo acesse seus dados durante o fluxo de autorização.

**8. Scope (Escopo)**
O Scope define o nível de acesso ou os recursos específicos que o Client está solicitando. Durante o processo de autorização, o Client especifica quais Scopes ele precisa, e o Resource Owner pode consentir ou restringir esse acesso. O Authorization Server então emite um Access Token que é limitado aos Scopes concedidos.

**Exemplo**: Um Client pode solicitar acesso de leitura ao perfil de usuário e à lista de amigos, mas o Resource Owner pode optar por conceder apenas acesso de leitura ao perfil.

**9. State (Estado)**
O parâmetro State é utilizado para proteger o processo de autorização contra ataques de falsificação de solicitação entre sites (CSRF). Quando o Client inicia uma solicitação de autorização, ele pode incluir um parâmetro state, que é devolvido inalterado pelo Authorization Server após a conclusão do processo de autorização. Isso permite ao Client verificar se a resposta corresponde à solicitação original.

**Exemplo**: O Client gera um valor único para o parâmetro state ao iniciar o fluxo de autorização, que é então verificado após a resposta do Authorization Server.

**10. Redirect URI (URI de Redirecionamento)**
A Redirect URI é a URL para a qual o Authorization Server redireciona o Resource Owner após a autorização, enviando o Authorization Code ou o Access Token. Para prevenir ataques, o Authorization Server deve verificar se a Redirect URI registrada corresponde àquela fornecida na solicitação.

**Exemplo**: Uma URL no domínio do aplicativo Client para onde o Authorization Server redireciona o usuário após a autorização.