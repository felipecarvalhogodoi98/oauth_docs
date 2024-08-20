# JSON Web Token

JSON Web Token (JWT, RFC 7519) é uma forma de codificar declarações em um documento JSON que é então assinado.

JWTs podem ser usados ​​como OAuth [Bearer Tokens](/bearer_token) para codificar todas as partes relevantes de um token de acesso no próprio token de acesso, em vez de armazená-los em um banco de dados.

O JWT é uma das soluções mais implementadas para autenticação e autorização de Api's. O que você deve saber do JWT:

- Oferecem uma maneira estruturada e stateless de guardar informações de autorização de um usuário.
- Permite que a aplicação client guarde as permissões do usuário.
- Podem ser encriptados e cryptographically signed para evitar adulterações.
- Podem escalar horizontalmente.
- Possibilita criar serviços verdadeiramente RESTful.
- Expiração interna.
- São independentes.

Um JWT possui o seguinte aspecto:

<span style="color: #f00921">eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9</span>.<span style="color: #5242eb">eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkJydW5vIiwiaWF0IjoxNTE2MjM5MDIyfQ</span>..<span style="color: #16cd1e">YDN0wJHLzyzmqdwycv4wgh-RMBwQR4C_0uehWmo_77ZrAB46YnPYmzJJ2Lb36GyyDXDwRP9Bt759hcVmUiGWEg</span>.

Há três seções nesta string, separado por ponto. <span style="color: #f00921">Header</span>, <span style="color: #5242eb">Payload</span> e <span style="color: #16cd1e">Signature</span>.

## Header
O **Header** é um JSON que possui informações sobre o tipo de token e o algoritmo de criptografia utilizado.

## Payload
Também é um objeto JSON, mas que contém as Claims do usuário. Elas são classificadas em três tipos Reserved, Public e Private

- Reserved claims
    - Atributos reservados pela JWT, recomendados, que são utilizados na validação do Token. As mais comuns são iss (issuer), exp (expiration time), sub (subject), aud (audience). Para consultar todos, acesse rfc7519 - Section 4.1
- Public claims

    -Informações que serão utilizados na aplicação para autorizar os recursos que o usuário tem acesso.

- Private claims
    - Usadas para compartilhar informações entre aplicações.

## Signature
Para criar a assinatura precisa codificar o Header e o Payload em base64, uma senha e utilizar o algoritmo de criptografia especificado no Header, após isso deverá assinar com a chave de criptografia.

Dessa forma previne ataques do tipo man-in-the-middle, garantindo que as informações dentro do token são confiáveis.

Veja mais sobre [JSON Web Token](https://auth0.com/docs/secure/tokens/json-web-tokens)