# Comunicação Entre Sistemas

> Comunicação Síncrona

- É a comunicação que acontece em tempo real.

> Comunicação Assíncrona

- É o tipo de comunicação na qual não é necessário ter a resposta em tempo real.

# REST

- Representational state of transfer
- Surgiu em 2000 por Roy Fielding em uma dissertação de doutorado
- Simplicidade
- Stateless
- Cacheável

## Níveis de Maturidade

> Nível 0: The Swamp of POX

> Nível 1: Ultilização de resources

| Verbo  | URI         | Operação |
| ------ | ----------- | -------- |
| GET    | /producst/1 | Buscar   |
| POST   | /products   | Inserir  |
| PUT    | /products/1 | Alterar  |
| DELETE | /products/1 | Remover  |

> Nível 2: Verbos HTTP

| Verbo  | Ultilização          |
| ------ | -------------------- |
| GET    | Recuperar Informação |
| POST   | Inserir              |
| PUT    | Alterar              |
| DELETE | Remover              |

> Nível 3: HATEOAS: Hypermedia as the Engine of Application State

```json
HTTP/1.1 200 OK
Content-Type: application/vnd.acme.account+json
Content-Length:...

{
    "account": {
        "account_number": 12345,
        "balance": {
            "currency": "usd",
            "value":100.00
        },
        "links": {
            "deposit": "/accounts/12345/deposit",
            "withdraw": "/accounts/12345/withdraw",
            "transfer": "/accounts/12345/transfer",
            "close": "/accounts/12345/close",
        }
    }
}
```

> Uma boa API REST

- Ultiliza URIs únicas para serviõs e itens que expostos para esses serviços
- Ultiliza todos os verbos HTTP para realizar as operações em seus recursos, incluindo caching
- Provê links relacionais para os recursos exemplificando o que pode ser feito

### HAL, Collection+JSON e Siren

- JSON não provê um padrão de hipermídia para realizar a linkagem
- HAL: Hypermedia Application Language
- Siren

> HAL

- Média type = applicationhal+json

```json
{
  "_links": {
    "self": {
      "href": "http://accounts.com.br/api/user/anderson"
    }
  },
  "id": "anderson",
  "name": "Anderson Santos",
  "_embedded": {
    "family": {
      "_links": {
        "self": {
          "href": "http://accounts.com.br/api/user/ivan"
        }
      },
      "id": "ivan",
      "name": "Ivan"
    }
  }
}
```

> HTTP Method Negotiation

- HTTP possui um outro método: OPTIONS. Esse método nos permite informar quais métodos são
  permitidos ou não em determinado recurso.

```bash
OPTIONS /api/product HTTP/1.1
Host: acounts.com.br
```

- Resposta pode ser:

```bash
HTTP/1.1 200 OK
Allow: GET, POST
```

- Caso envie a requisição em outro formato:

```bash
HTTP/1.1 405 Not Allowed
Allow: GET, POST
```

> Content Negotiation

- O processo de content negotiation é baseado na requisição que o cliente está fazendo para o server.  
  Nesse caso ele solicita o que e como ele quer a resposta. O server então retornará ou não a informação no formato desejado.

**Accept Negotiation**

- Cliente solicita a informação e o tipo de retorno pelo server baseado no media type informado por ordem de prioridade.

```bash
GET /product
Accept: application/json
```

Resposta pode ser o retorno dos dados ou:

```bash
HTTP/1.1 406 Not Acceptable
```

**Content-Type Negotiation**

- Através de um content-type np header da request, o servidor consegue verificar se ele irá conseguir processar
  a informação para retornar a informação desejada.

```json
POST /product HTTP/1.1
Accept: application/json
Content-Type: application/json

{
    "name": "Product 1"
}
```

Caso o servidor não aceite o content type, ele poderá retornar:

```bash
HTTP/1.1 415 Unsupported Media Type
```
