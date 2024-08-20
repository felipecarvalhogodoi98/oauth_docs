# Escopos

O escopo é um mecanismo no OAuth 2.0 para limitar o acesso de um aplicativo à conta de um usuário. Uma aplicação pode solicitar um ou mais escopos, esta informação é então apresentada ao usuário na tela de consentimento, e o token de acesso emitido para a aplicação será limitado aos escopos concedidos.

Quando um cliente solicita autorização para acessar os dados de um usuário, ele deve especificar quais escopos de acesso ele precisa. Esses escopos são definidos no momento da solicitação de autorização e são enviados ao servidor de autorização.

Por exemplo, ao autorizar uma aplicação de terceiros, um usuário pode ver uma lista de escopos que a aplicação está solicitando, como "leitura de e-mails", "acesso ao perfil", ou "escrita de arquivos". O usuário pode então decidir se concede ou nega esses acessos.

Exemplos:

1 - Perfil do Usuário

  - `profile`: Acesso ao perfil básico do usuário, como nome, foto, e-mail.
  - `email`: Acesso ao endereço de e-mail do usuário.

2 - Recursos de API Específicos

  - `read`: Permite operações de leitura em recursos específicos.
  - `write`: Permite operações de escrita em recursos específicos.
  - `delete`: Permite a exclusão de recursos.

3 - Escopos de Serviços Específicos

  - `calendar.read`: Leitura dos eventos do calendário do usuário.
  - `drive.readonly`: Acesso de leitura aos arquivos do Google Drive.
  - `photos.upload`: Permite o upload de fotos para um serviço.

4 - Escopos de Controle Total

  - `admin`: Acesso completo para administrar todos os recursos e configurações.
  - `superuser`: Acesso de superusuário, com permissões para realizar qualquer ação.  