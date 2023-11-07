## Documentação de api com Swagger

> Passo 1: Instalar o pacote do swagger no projeto.

`$ yarn add swagger-ui-express` <br>
<br>

> Passo 2: Instalando a tipagem do pacote como dependência de desenvolvimento. <br> OBS: esse passo deve ser feito se estiver ultilizando typescript no projeto.

`$ yarn add @types/swagger-ui-express -D`
<br><br>

> Passo 3: Configurar o swagger no projeto

- Dentro do arquivo de configuração do servidor ou seja de onde se faz a intância de execução do projeto <br>
deve importar o swagger

```js
import swaggerUI from "swagger-ui-express";
import swaggerFile from "./swagger.json"; // O arquivo swagger.json deve ser criado.
```
<br>

- Antes de instanciar as rotas deve se criar um server para colocar as informações da documentação da API. <br> 
O bacana do swagger é que se dá para passar uma url onde será exibida a documentação da API e dá para passar um <br>
setup que é um arquivo json onde será escrita as documentações das rotas.

```js
app.use("/api-docs", swaggerUI.serve, swaggerUI.setup(swaggerFile));
```
<br>

> Passo 4: Configurar o arquivo tsconfig.json adionando true para a propiedade abaixo.

```json
"resolveJsonModule":true
```






