# learning-fundamentals-software-architecture

> Tipos de arquitetura

- Software
- Solução
- Tecnológica
- Corporativa

> Arquitetura Tecnológica

- Especialidade em tecnologias específicas de mercado
- Geração de valor baseado em especialidades
- Diversidade de profissionais especialistas
    - Arquiteto Elastic
    - Arquiteto Java
    - SQL Server
    - Oracle
    - SAP


> Arquitetura Corporativa

- Impacta estrategicamente a organização como um todo
- Avaliação de custos
- Avaliação de possíveis novas tecnologias
- Padronização de tecnologias 
- Planejamento de grandes implatanções
    - Sistemas "core"
    - Migrações


> Arquitetura de Soluções

- Fica entre a área de negócios e software
- Transformar requisitos de negócio em solução de software
- Desenhos arquiteturais da solução de um software para reproduzir como ele irá funcionar.
    - C4
    - UML
    - BPMN
- Analisa os impactos comerciais em relação a uma escolha tecnológica 
- Pode participar do processo comercial de pré-venda e venda
- Analisa os impactos dos custos para o negócio


> Arquitetura de Software

- É a relação entre os objetivos de negócio e suas restrições com os componentes
a serem criados e suas responsabilidades visando sua evolução do software.

- E uma "disciplina" da engenharia de software
- Diretamente ligada ao processo de desenvolvimento de software
- Afeta diretamente na estrutura organizacional da empresa
    - Formação de times
    - Estrutura dos componentes do software
    - "Organizações que desenvolvem sistemas de software tendem a produzir sistemas que são cópias das estruturas de comunicação dessas empresas. (Melvin Conway)"


> Papel do Aquiteto(a) de Software

- Transformar requisitos de negócio em padrões arquiteturais
- Orquestrar pessoas desenvolvedores e experts de domínio
- Entender de forma profunda conseitos e modelos arquiteturais
- Auxilia na tomada de decisão nos momentos de crise 
- Reforça boas práticas de desenvolvimento 
- Code reviews

- Apesar de nem todas as organizações possuírem o cargo de arquiteto de software,
normalmente profissionais mais experientes como desenvolvedores seniors e tech leads acabam realizando esse papel 
baseado em suas experiências anteriores.

- Há empresas que apesar de não possuírem o cargo de arquiteto(a) de software, possuem um departamento de arquitetura que auxilia os diversos times da organização como questões arquiteturais.

> Por que aprender arquitetura de software ?

- Poder navegar da visão macro para a visão micro de um ou mais softwares 
- Entender quais são as diversas opções que temos para desenvolver a mesma coisa e escolher a melhor solução para determinado contexto 
- Pensar a longo prazo no projeto e sua sustentabilidade 
- Tomar decisões de forma mais fria e calculada evitando assim ser influenciado(a) por "hypes" de mercado 
- Mergulho em padrões de projeto e de desenvolvimento e suas boas práticas 
- Ter mais clareza do impacto que o software possui na organização como um todo 
- Tomar decisões com mais confiança


> Arquitetura vs Design de software

- Arquitetura: Escopo global ou alto nível 
- Design: Escopo local

- "Atividades relacionadas a arquitetura de software são sempre de design. Entretanto, nem todas atividade de design são sobre arquitetura. O objetivo primário da arquitetura de 
software é garantir que os atributos de qualidade, restrições de alto nível e os objetivos de negócio, sejam atendidos pelo sistema. Qualquer decisão de design que não tenha relação com este objetivo não é arquitetural. Todas as decisões de design para um componente que não sejam "visíveis" fora dele, geralmente, também não são."


> Sustentabilidade 

- Desenvolver software é caro
- Software resolve uma "dor"
- Software precisa se pagar ao longo do tempo 
- Acompanhar a evolução do negócio 
- Quanto mais tempo o software ficar no ar, mais retorno gera 
- A solução precisa ser arquitetada

> Pilares da arquitetura de software

- Estruturação
    - Fácil evolução, componentização para atender os objetivos de negócio.
- Componentização
- Relacionamento entre sistemas
- Governança

> Requisitos arquiteturais (RAs)

- Performance
- Armazenamento de dados
- Escalabilidade
- Segurança
- Legal
- Audit
- Marketing

> Características arquiteturais

- Operacionais
- Estruturais
- Cross-Cutting

> Características Operacionais

- Disponibilidade
- Recuperação de desastres
- Performance
- Recuperação (backup)
- Confiabilidade e segurança
- Robustes
- Escalabilidade

> Características Estruturais

- Configurável
- Extensibilidade
- Fácil instalação
- Reuso de componentes
- Internacionalização
- Fácil manunteção
- Portabilidade (diversos bancos de dados)
- Fácil suporte (logs, debugging)

> Características Cross-Cutting

- Acessibilidade
- Processo de rentenção e recuperação de dados (quanto tempo os dados serão mantidos)
- Autenticação e Autorização
- Legal
- Privacidade 
- Segurança
- Usabilidade

> Perspectivas para arquitetar software de qualidade

- Performance
- Escalabilidade
- Resiliência

> Performance

- É o desempenho que um software possui para completar um determinado workload
- As unidades de medida para avaliarmos a performance de um software são:
    - Latência ou "response time"
    - Throughput
- Ter um software perfomático é diferente de ter um software escalável

> Métricas para medir a performance

- Dimunindo a latência
    - Normalmente medida em milliseconds 
    - É afetada pelo tempo de processamento da aplicação, rede e chamadas externas

- Aumentando o throughput
    - Quantidade de requisições
    - Diretamente ligado a latência

> Principais razões para baixa performance 

- Processamento Ineficiente 
- Recursos computacionais limitados
- Trabalhar de forma bloqueante 
- Acesso serial a recursos

> Principais formas para aumentar a eficiência

- Escala de capacidade computacional (CPU, Disco, Memória, Rede)
- Lógica por trás do software (Algoritmos, queries, overhead de frameworks)
- Concorrência e paralelismo 
- Banco de dados (tipos de bancos, schema)
- Caching 

> Diferença entre concorrência e paralelismo

Concorrência é sobre lidar com muitas coisas ao mesmo tempo.
Paralelismo é fazer muitas coisas ao mesmo tempo.
~Rob Pike

> Caching

- Cache na borda / Ege computing
- Dados estáticos
- Páginas web
- Funções internas
    - Evita reprocessamento de algoritmos pesados
    - Acesso ao bando de dados
- Objetos

> Caching: Exclusivo vs Compartilhado

- Exclusivo
    - Baixa latência
    - Duplicado entre os nós
    - Problemas relacionado a sessões

- Compartilhado
    - Maior latência
    - Não há duplicação
    - Sessões compartilhadas
    - Banco de dados externo
        - MySQL
        - Redis
        - Memcache

> Caching: Edge computing 

- Cache realizado mais próximo ao usuário
- Evitar a requisição chegar até o Cloud Provider / Infra
- Normalmente arquivos estáticos
- CDN - Content Delivery Network
- Cloudflare workers
- Vercel
- Akamai

> Escalabilidade

Escalabilidade é a capacidade de sistemas suportarem o aumento
(ou a redução) dos workloads incrementando (ou reduzindo) o custo em
menor ou igual proporção.

> Escalabilidade vs Performance

Enquanto performance tem o foco em reduzir a latência e aumentar o throughput,
a escalabilidade visa termos a possibilidade de aumentar ou diminuir o throughput adicionando ou removendo a capacidade 
computacional.


> Escalando software

- Escala Vertical
    - Aumento de recursos computacionais
        - Aumento de memória
        - Aumento de CPU
        - Aumento de disco
        - Aumento de velocidade em disco
        - etc...

- Escala Horizontal
    - Aumento de quantidade de máquinas rodando o projeto adicionando loadbalancer ou um proxi reverso para rotear as requisições para as máquinas.


> Problemas da escala vertical

- Chega um momento em que o hardware não suporta o poder computacional que o problema exige.
- Se a máquina cair o sistema cai em 100%


> Descentralização 

- Para a escala horizintal funcionar
    - Disco efêmero (Tudo que for salvo em disco na máquina possa ser apagado a hora que precisar)
    - Servidor de aplicação vs Servidor de assets
    - Cache centralizado
    - Sessões centralizadas
    - Upload / Gravação de Arquivos
    - Tudo pode ser removido e criado facilmente

> Escala de banco de dados

- Aumentando recursos computacionais 
- Distribuindo responsabilidades (escrita vs leitura)
- Shards de forma horizontal
- Serverless

> Otimização de queries e Índices

- Trabalhe com índices de forma consciente
- APM (Application performance monitoring) nas queries
- Explain na queries
- CQRS (Command Query Responsability Segregation)

> Proxy reverso

Um proxy reverso é um servidor que fica na frente dos servidores web e 
encaminha as solicitações do cliente (por exemplo, navegador web) para esses
servidores web.

> Soluções populares de Proxy Reverso

- Nginx
- HAProxy (HA= High Availability)
- Traefik

> Resiliência

- Resiliência é um conjunto de estratégias adotadas intencionalmente para a 'adaptação' 
de um sistema quando uma falha ocorre.

- Ter estratégias de resiliência nos possibilita minimizar os riscos de perda de dados e transações importantes 
para o negócio.


> Proteger e ser Protegido

- Um sistema em uma arquitetura distribuída precisa adotar mecanismos de 
autopreservação para garantir ao máximo sua operação com qualidade.

- Um sistema precisa não pode ser "egoísta" ao ponto de realizar mais
requisições em um sistema que está falhando.

- Um sistema lento no ar muitas vezes é pior do que um sistema fora do ar.
(Efeito dominó)

> Health check

- Sem sinais vitais, nãe é possível saber a "saúde" de um sistema

- Um sistema que não está saudável possui uma chance de se recuperar caso o 
tráfego pare de ser direcionado a ele temporariamente.

- Health check de qualidade

> Rate Limiting

- Protege o sistema baseado no que ele foi projetado para suportar

- Preferência programada por tipo de client

> Circuit breaker

- Protege o sistema fazendo com que as requisições feitas para ele sejam negadas. Ex: 500
- Circuito fechado = Requisições chegam normalmente
- Circuito aberto = Requisições não chegam ao sistema. Erro instatâneo ao client 
- Meio aberto = Permite uma quantidade limitada de requisições para verificação se o 
sistema tem condições de voltar ao ar integralmente

> API Gateway

- Garante que requisições "inapropriadas" cheguem até o sistema:
Ex: usuário não autenticado

- Implementa políticas de Rate Limiting, Health check, etc.

> Service Mesh

- Controla o tráfego de rede
- Evita implementações de proteção pelo própio sistema.
- mTLS
- Circuit breaker, retry, timeout, fault injection, etc.


> Trabalhar de forma assíncrona

- Evita perda de dados
- Não há perda de dados no envio de uma transação deo server estiver fora
- Servidor pode processar a transação em seu tempo quando estiver online
- Entender com profundidade o message broker / sistema de stream

> Garantias de entrega: Retry

- Exponencial Backoff - linear
- Exponencial Backoff - jitter

> Garantias de entrega: Kafka (Delivery guarantees)

- message broker

- Ack 0 - None : apenas o broker leader recebe a mensagem e não retorna que a menssagem chegou ( alta velocidade menor garantia que a mensagem será entregue no final)
- Ack 1 - Leader : apenas o broker leader recebe e retorna que está com a mensagem (velocidade moderada / garantia moderada que a mensagem será entregue no final)
- Ack- 1 - All : Todos os brokers recebem a mensagem e retorna que está com ela (menor velocidade / mais garantia que a mensagem será entregue no final)

> Situações complexas 

- O que acontece se o message broker cair ?
- Haverá perda de mensagens ?
- Seu sistema ficará fora do ar ?
- Como garantir resiliência ?