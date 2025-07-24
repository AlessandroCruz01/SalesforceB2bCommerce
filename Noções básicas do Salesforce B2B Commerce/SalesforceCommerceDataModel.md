# Salesforce Commerce Data Model

O modelo de dados do Commerce é um conjunto de objetos da Salesforce Platform concebido para apoiar as funções de negócios B2B.

O modelo de loja do Commerce é criado em um modelo de dados pré-configurado. O modelo de dados é compatível com objetos de negócios padronizados e personalizáveis para uma variedade de relacionamentos comerciais e interoperabilidade com o **B2B Commerce**, o **Salesforce Order Management** e o **Service Cloud**.

O modelo de dados do Commerce conecta os objetos da loja B2B. Os relacionamentos de objetos padrão são compatíveis com uma experiência completa de loja B2B.

Quando você cria uma loja B2B, um conjunto comum de objetos padrão é adicionado à sua organização. O conjunto inclui:

- **Catalog**: ( Catálogo ) O catálogo é a coleção completa de produtos oferecidos na loja.
- **Category**: ( Categoria ) Um agrupamento lógico de produtos. Crie várias categorias para uma hierarquia navegável.
- **Entitlement Policy**: ( Política de direitos ) O “segurança” do cliente B2B que gerencia o acesso a produtos e preços.
- **Product**: ( Produto ) Os produtos que estão disponíveis para os clientes.
- **Price Book**: ( Catálogo de preços ) O preço negociado para compradores.
- **Buyer Account**: ( Conta do comprador ) Os dados de B2B que representam um comprador específico.
- **Buyer Group**: ( Grupo de compradores ) Um agrupamento de compradores B2B que compartilham características comuns.

## Objeto Store (Loja)

O objeto Loja representa seu site. Pense no objeto Loja como o centro de transações comerciais, com elementos de transação colocados ao redor dele como raios. Essa estrutura oferece a você a máxima flexibilidade para seus requisitos comerciais.

Por padrão, os dados abaixo estão associados ao objeto Loja.

- Uma experiência de loja padrão
- Um conjunto de idiomas compatíveis
- Um conjunto de moedas compatíveis

As lojas (sites) B2B usam uma abordagem baseada em componente e modelo para a experiência de compra front-end. Os operadores comerciais do Commerce usam os modelos e os componentes Lightning Web Runtime (LWR) para exibir produtos, organizar informações para compradores e processar pedidos para sua loja.

Depois que você configurou uma loja B2B, ela se torna um contêiner para seus dados comerciais mantidos nestes objetos: **Catálogos**, **Categorias**, **Catálogo de preços**, **Produtos**, **Compradores**, **Grupos de compradores** e **Políticas de direitos**. As estratégias de engajamento do cliente, merchandising e processamento de pedidos determinam a configuração desses objetos do modelo de dados de comércio.

![dataModelB2B](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/b2b2c-commerce-basics/b2b2c-data-model/images/pt-BR/1e993ea106d9d2a368aa19021bf8eef1_kix.dk8bp4a1kmie.png)

### Catalog

Catálogos são o objeto organizacional que permite oferecer produtos em uma loja. Cada loja B2B tem um catálogo específico de produtos.

### Category

As categorias desempenham um papel crucial na organização e apresentação de produtos aos clientes. No modelo de dados do aplicativo Commerce, o objeto Category (Categoria) representa categorias e subcategorias. Esse objeto controla como os clientes pesquisam um produto.

As categorias têm uma estrutura hierárquica que normalmente representa um relacionamento pai-filho. Um único catálogo inclui categorias e subcategorias de até cinco níveis. Use a estrutura em forma de árvore para criar agrupamentos de produtos que facilitam a navegação dos clientes e a localização de produtos semelhantes ou que pertencem a uma categoria específica.

![DataModelCategory](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/b2b2c-commerce-basics/b2b2c-data-model/images/pt-BR/e8c10a4117000c248bf3fe44963b18c4_kix.4jorgkz50iqf.jpg)

### Product

Produtos são as coisas que você vende. O objeto Produto lista cada um dos produtos em forma de um registro. O registro do produto contém dados como descrições do produto, especificações e links para mídia do produto que ajudam os clientes a tomar decisões fundamentadas. Cada produto tem seu próprio número de identificação da Unidade de manutenção de estoque (SKU).

### Price Book

O objeto Catálogo de preços gerencia e organiza os preços dos produtos. Ele desempenha um papel crucial na determinação dos preços unitários de produtos ou serviços. É necessário um catálogo de preços para exibir preços de oportunidades, cotações e pedidos.

O modelo de dados aceita um catálogo de preços padrão juntamente com catálogos de preços personalizados vinculados a grupos de compradores. Você também pode configurar um catálogo de preços com preços riscados que destaca preços reduzidos para clientes.

![dataModelPriceBook](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/b2b2c-commerce-basics/b2b2c-data-model/images/pt-BR/63dd76520afa89c50519babe98d4b58d_kix.h8j3q24k5d1j.png)

### Buyer Account

Um comprador é uma pessoa ou um contato associado a uma empresa ou organização que compra produtos ou serviços. Os compradores recebem funções, responsabilidades e permissões relacionadas ao processo de compra. Um comprador pode ser associado a uma conta específica ou a um grupo de compradores.

### Buyer Group

Um grupo de compradores é uma coleção de compradores individuais que compartilham características ou atributos comuns. Os grupos de compradores geralmente são organizados com base em fatores como o tipo de empresa, setor ou preferências de compra. Os grupos de compradores simplificam o gerenciamento de compradores com necessidades semelhantes, portanto, considere reunir compradores com as mesmas funções, políticas de direitos e preços de contrato em um grupo de compradores.

### Entitlement Policy

Uma Política de direitos é um objeto que aplica condições específicas para o acesso do comprador a determinados _produtos_ e _preços_. Os grupos de compradores são vinculados às políticas de direitos. Por exemplo, uma política de direitos pode especificar que um grupo de compradores em um determinado nível ou com um nível de assinatura específico tem direito a acessar produtos ou serviços premium.

![dataModelPolicy](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/b2b2c-commerce-basics/b2b2c-data-model/images/pt-BR/ecbcc61278e9ff83b3c3acb84b01ea22_kix.sts8ocuvqxcx.png)

### Como reunir tudo para conectar os dados

O modelo de dados do Commerce inclui objetos, objetos subjacentes e recursos que apoiam as funções de negócios B2B. Tendo a loja como hub, organize seus produtos em categorias que melhoram a navegação do cliente e a pesquisa de produtos.

O objeto Produto inclui registros que detalham cada produto, incluindo descrições e SKUs. Todos os produtos são vinculados a catálogos de preços padrão e riscados. Os catálogos de preços personalizados, por sua vez, são compatíveis com políticas de direitos que oferecem aos grupos de compradores B2B acesso a produtos e preços selecionados.
