# Refresh token

Um Refresh Token OAuth é uma string que o cliente OAuth pode usar para obter um novo token de acesso sem a interação do usuário.

Clientes públicos e confidenciais podem usar refresh token. Se um token de atualização emitido para um cliente público for roubado, o invasor poderá se passar pelo cliente e usar o token de atualização sem ser detectado. Também é possível vincular refresh token à instância pública do cliente usando DPoP, o que pode conter esse ataque. Os clientes confidenciais precisam se autenticar no servidor de autorização para usar o token de atualização, portanto, o risco de refresh token roubados é menor para esse tipo de cliente.

Um Refresh Token não deve permitir que o cliente obtenha acesso além do escopo da concessão original. O token de atualização existe para permitir que os servidores de autorização usem tempos de vida curtos para tokens de acesso sem a necessidade de envolver o usuário quando o token expirar.