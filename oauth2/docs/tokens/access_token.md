# Access token

Um token de acesso OAuth é uma string que o cliente OAuth usa para fazer solicitações ao servidor de recursos.

Access tokens não precisam estar em nenhum formato específico e, na prática, vários servidores OAuth escolheram muitos formatos diferentes para seus tokens de acesso.

Access tokens podem ser `bearer tokens` ou tokens `sender-constrained`. Sender-constrained tokens exigem que o cliente OAuth prove a posse de uma chave privada de alguma forma para usar o token de acesso, de modo que o token de acesso por si só não seja utilizável.

Há uma série de propriedades de tokens de acesso que são fundamentais para o modelo de segurança do OAuth:

- Access tokens não devem ser lidos ou interpretados pelo cliente OAuth. O cliente OAuth não é o público-alvo do token.
- Access tokens não transmitem a identidade do usuário ou qualquer outra informação sobre o usuário ao cliente OAuth.
- Access tokens só devem ser usados ​​para fazer solicitações ao servidor de recursos. Além disso, os tokens de ID não devem ser usados ​​para fazer solicitações ao servidor de recursos.