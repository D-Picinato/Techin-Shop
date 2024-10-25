# Techin Shop

Techin Shop é um e-commerce que foi pensado para solucionar o problema da minha falta de prática com o desenvolvimento de API Restful e arquitetura MVC (Model View Controller), também porque preciso entregar um trabalho de banco de dados daqui 4 dias (29/10/2024); por isso decidi juntar o útil ao agradável e desenvolver o sistema Techin Shop.

A proposta do sistema, é disponibilizar funcionalidades para que qualquer usuário possa se cadastrar no sistema e simular a venda e compra de produtos não tangíveis, usando uma moeda de troca própria chamada **TechinCoin** (TC$).

## TechinCoin

**TechinCoin** (T$) é a moeda de troca dentro do **Techin Shop**. Os usuários podem adquiri-la de maneira simples através de uma área do sistema, onde há um botão interativo que, ao ser clicado, concede uma quantidade fixa de TechinCoins. O diferencial dessa área é que o botão muda de posição a cada clique, adicionando um pequeno desafio dinâmico. Isso permite que os usuários acumulem TechinCoins de uma forma rápida e sem restrições complexas, até mesmo porque o usuário não vai usar o sistema por muito tempo.

# Funcionalidades

## Autenticação de Usuários
A autenticação de usuários é um componente crítico do sistema, garantindo que apenas usuários registrados possam acessar suas contas e realizar transações.

### Requisitos:
- **Registro de Usuário**: O cadastro requer nome de usuário, imagem de perfil (opcional), e-mail e senha. O sistema valida se o e-mail é único e a senha atende a critérios de segurança.
- **Autenticação**: O usuário é autenticado automaticamente após o registro e recebe um token de sessão, que deve ser enviado em cada requisição que requer autenticação.
- **Segurança da Sessão**: O sistema registra o endereço IP do usuário durante o login para monitorar atividades suspeitas e garantir a segurança.
- **Logout**: Permite que o usuário finalize a sessão a qualquer momento, invalidando o token de sessão.
- **Remover Conta**: Os usuários podem solicitar a exclusão de sua conta, sendo necessário confirmar a ação com a senha.

## Cadastro de Produtos
Os usuários têm a capacidade de cadastrar produtos no marketplace para venda. Essa funcionalidade é fundamental para permitir que os usuários interajam ativamente na plataforma, promovendo uma variedade de produtos.

### Requisitos:
- **Informações do Produto**: O cadastro deve incluir nome do produto, descrição, imagens (mínimo de 1, máximo de 5), avaliação (de 1 a 5 estrelas), comentários de usuários (opcional), categoria, fabricante, quantidade disponível e preço.
- **Edição de Produtos**: Os usuários podem editar as informações de produtos já cadastrados a qualquer momento.

## Marketplace
O marketplace do **Techin Shop** é onde a interação entre compradores e vendedores acontece. Ele oferece várias funcionalidades que facilitam a busca e filtragem de produtos.

### Requisitos:
- **Pesquisa de Produtos**: Os usuários podem buscar produtos por nome ou tags, facilitando a localização de itens específicos.
- **Filtros**: O sistema deve permitir que os usuários filtrem os produtos por preço mínimo e máximo, categorias, fabricantes, avaliações e produtos mais ou menos vendidos.

## Carrinho de Compra
O carrinho de compras é uma parte essencial da experiência do usuário, permitindo que os clientes gerenciem os produtos que desejam comprar antes de finalizar a transação.

### Requisitos:
- **Adicionar Produtos**: Os usuários podem adicionar produtos do marketplace ao carrinho.
- **Remover Produtos**: O usuário pode remover produtos do carrinho a qualquer momento.
- **Editar Quantidade**: Os usuários podem editar a quantidade de cada produto no carrinho, garantindo flexibilidade antes da compra.

## Compra e Venda de Produtos
A funcionalidade de compra e venda de produtos é o coração do sistema, permitindo transações entre usuários de forma eficiente e segura.

### Requisitos:
- **Compra Individual**: Os usuários podem comprar produtos diretamente da página do produto.
- **Compra pelo Carrinho**: Os usuários podem finalizar a compra de todos os produtos que adicionaram ao carrinho.
- **Processamento da Compra**: Quando um usuário realiza uma compra, o valor total é descontado do saldo de TechinCoins do comprador, o valor é creditado na conta do vendedor e a quantidade disponível do produto é reduzida de acordo com a quantidade comprada. O sistema deve registrar a transação para futuras referências e relatórios.

# Arquitetura e Tecnologias

O **Techin Shop** é construído com uma arquitetura baseada em **MVC (Model View Controller)**, o que permite uma separação clara das responsabilidades entre as diferentes camadas do sistema. Essa abordagem facilita a manutenção e escalabilidade do aplicativo, além de promover uma melhor organização do código.

## Arquitetura MVC
- **Model**: Representa a estrutura de dados, a lógica de negócios da aplicação e persistência dos dados, responsável por interagir com o banco de dados e realizar operações de CRUD (criação, leitura, atualização e exclusão) de dados.
- **View**: Esta camada é responsável pela apresentação da interface do usuário, utilizando uma abordagem componentizada com a biblioteca React. Os componentes são estilizados de maneira eficiente com SASS, aproveitando suas funcionalidades avançadas, o que garante modularização e fácil manutenibilidade para a estilização dos elementos. Além disso, a escrita em TypeScript proporciona uma tipagem estática que aumenta a robustez e a legibilidade do código.
- **Controller**: Os controllers atuam como intermediários entre as views e os models. Eles processam as entradas do usuário, manipulam os dados através dos modelos e retornam as respostas apropriadas para as views. Os controllers são responsáveis por gerenciar a lógica de fluxo dos dados do sistema.

## Tecnologias Utilizadas
- **Frontend**:
	- **React**: Uma biblioteca JavaScript para construir interfaces de usuário, permitindo o desenvolvimento de componentes reutilizáveis e dinâmicos.
	- **TypeScript**: Uma linguagem de programação que adiciona tipagem estática ao JavaScript, melhorando a robustez e a legibilidade do código.
    - **Vite**: Um bundler de aplicativos que fornece um ambiente de desenvolvimento rápido e otimizado, permitindo compilações mais rápidas e uma experiência de desenvolvimento suave.
    - **React Router Dom**: Uma biblioteca que facilita a navegação entre as diferentes páginas e componentes da aplicação, permitindo a criação de uma experiência de usuário fluida.
    - **React Icons**: Uma biblioteca que fornece ícones facilmente integráveis aos componentes do React, melhorando a estética e a usabilidade da interface.
- **Backend**:
    - **PHP**: Uma linguagem de programação amplamente utilizada para o desenvolvimento de aplicativos web, que permitirá a construção de uma API RESTful eficiente.
- **Banco de Dados**:
    - **MySQL**: Um sistema de gerenciamento de banco de dados relacional que oferece uma maneira eficiente de armazenar e gerenciar dados estruturados.
- **Ambiente de Desenvolvimento**:
    - **Git**: Para controle de versão do código, facilitando o gerenciamento do histórico de alterações.
    - **Thunder Client** ou **Postman**: Para testes de API, permitindo verificar se as rotas e as respostas da API estão funcionando como esperado.

Por [Dimas Picinato](https://dpicinato.com)