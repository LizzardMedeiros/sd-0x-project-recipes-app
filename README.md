# Boas vindas ao repositório do projeto de Receitas!

Você já usa o GitHub diariamente para desenvolver os exercícios, certo? Agora, para desenvolver os projetos, você deverá seguir as instruções a seguir. Fique atento a cada passo, e se tiver qualquer dúvida, nos envie por _Slack_! #vqv 🚀

Aqui você vai encontrar os detalhes de como estruturar o desenvolvimento do seu projeto a partir desse repositório, utilizando uma branch específica e um _Pull Request_ para colocar seus códigos.

---

# HABILIDADES

Nesse projeto você será capaz de:

  - Utilizar a Context API do React para gerenciar estado
  - Utilizar o React Hook useState
  - Utilizar o React Hook useContext
  - Utilizar o React Hook useEffect
  - Criar Hooks customizados

---

## SUMÁRIO

- [O que deverá ser desenvolvido](#o-que-deverá-ser-desenvolvido)
  - [Protótipo do projeto](#protótipo-do-projeto)
- [Data de entrega](#data-de-entrega)
- [Como desenvolver](#como-desenvolver)
  - [Antes de começar a desenvolver](#antes-de-começar-a-desenvolver)
- [Requisitos do projeto](#requisitos-do-projeto)
  - [Linter](#linter)
  - [Execução de testes de requisito](#execução-de-testes-de-requisito)
  - [API's](#apis)
  - [TheMealDB API](#themealdb-api)
  - [The CockTailDB API](#the-cocktaildb-api)
  - [Grupos de prioridade](#grupos-de-prioridade)
  - [Observações técnicas](#observações-técnicas)
    - [Rotas](#rotas)
    - [localStorage](#localStorage)
    - [Ícones](#icones)
- [Lista de requisitos](#lista-de-requisitos)
  <details>
    <summary>Testes unitários</summary>

    <!-- - [Testes unitários](#testes-unitários) -->
    - [1 - Desenvolva os testes unitários de maneira que a seja de, no mínimo, 90%](#1---a-cobertura-de-testes-unit%C3%A1rios-deve-ser-de-no-m%C3%ADnimo-90)

  </details>

  <details>
    <summary>Tela de Login</summary>

    <!-- - [Tela de login](#tela-de-login) -->
    - [2 - Crie todos os elementos que devem respeitar os atributos descritos no protótipo para a tela de login](#2---crie-todos-os-elementos-que-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-de-login)
    - [3 - Desenvolva a tela de maneira que a pessoa deve conseguir escrever seu email no input de email](#3---a-pessoa-deve-conseguir-escrever-seu-email-no-input-de-email)
    - [4 - Desenvolva a tela de maneira que a pessoa deve conseguir escrever sua senha no input de senha](#4---a-pessoa-deve-conseguir-escrever-sua-senha-no-input-de-senha)
    - [5 - Desenvolva a tela de maneira que o formulário só seja válido após um email válido e uma senha de mais de 6 caracteres serem preenchidos](#5---o-formulário-só-fica-válido-após-um-email-válido-e-uma-senha-de-mais-de-6-caracteres-serem-preenchidos)
    - [6 - Salve 2 tokens no localStorage após a submissão, identificados pelas chaves mealsToken e cocktailsToken](#6---após-a-submissão-2-tokens-devem-ser-salvos-em-localstorage-identificados-pelas-chaves-mealstoken-e-cocktailstoken)
    - [7 - Salve o e-mail da pessoa usuária no localStorage na chave user após a submissão](#7---após-a-submissão-o-e-mail-de-pessoa-usuária-deve-ser-salvo-em-localstorage-na-chave-user)
    - [8 - Redirecione a pessoa usuária para a tela principal de receitas de comidas após a submissão e validação com sucesso do login](#8---após-a-submissão-e-validação-com-sucesso-do-login-o-usuário-deve-ser-redirecionado-para-a-tela-principal-de-receitas-de-comidas)
  </details>

  <details>
    <summary>Header</summary>

    - [9 - Implemente os elementos do header na tela principal de receitas, respeitando os atributos descritos no protótipo](#9---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-o-header-disponível-na-tela-principal-de-receitas)
    - [10 - Implemente um ícone para a tela de perfil, um título e um ícone para a busca, caso exista no protótipo](#10---deve-apresentar-um-ícone-para-a-tela-de-perfil-um-título-e-um-ícone-para-a-busca-caso-exista-no-protótipo)
    - [11 - Redirecione a pessoa usuária para a tela de perfil ao clicar no botão de perfil](#11---ao-clicar-no-botão-de-perfil-deve-se-ir-para-a-tela-de-perfil)
    - [12 - Desenvolva o botão de busca que, ao ser clicado, a barra de busca deve aparecer. O mesmo serve para escondê-la](#12---ao-clicar-no-botão-de-busca-a-barra-de-busca-deve-aparecer-o-mesmo-serve-para-escondê-la)
  </details>

  <details>
    <summary>Barra de busca</summary>

    <!-- - [Barra de busca - Header](#barra-de-busca---header) -->
    - [13 - Implemente os elementos da barra de busca respeitando os atributos descritos no protótipo](#13---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-barra-de-busca)
    - [14 - Posicione a barra logo abaixo do header e implemente 3 radio buttons: Ingrediente, Nome e Primeira letra](#14---a-barra-de-busca-deve-ficar-logo-abaixo-do-header-e-deve-possuir-3-radio-buttons-ingrediente-nome-e-primeira-letra-eles-devem-mudar-a-forma-como-serão-filtradas-as-receitas)
    - [15 - Busque na API de comidas caso a pessoa esteja na página de comidas e na de bebidas caso esteja na de bebidas](#15---a-busca-deve-ocorrer-na-api-de-comidas-caso-a-pessoa-esteja-na-página-de-comidas-e-na-de-bebidas-caso-esteja-na-de-bebidas)
    - [16 - Redirecione para a tela de detalhes da receita caso apenas uma receita seja encontrada, com o ID da mesma na URL](#16---caso-apenas-uma-receita-seja-encontrada-a-rota-deve-mudar-para-a-tela-de-detalhes-da-receita-com-o-id-da-mesma-na-url)
    - [17 - Mostre as receitas em cards caso mais de uma receita seja encontrada](#17---caso-mais-de-uma-receita-seja-encontrada-mostrar-as-receitas-em-cards-da-mesma-maneira-que-a-tela-principal-de-receitas)
    - [18 - Exiba um `alert` caso nenhuma receita seja encontrada](#18---caso-nenhuma-receita-seja-encontrada-um-alert-contendo-o-texto-sinto-muito-não-encontramos-nenhuma-receita-para-esses-filtros-deve-ser-exibido)
  </details>

  <details>
    <summary>Menu inferior</summary>
  
    - [19 - Implemente os elementos do menu inferior respeitando os atributos descritos no protótipo](#19---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-o-menu-inferior-disponível-na-tela-principal-de-receitas)
    - [20 - Posicione o menu inferior de forma fixa e apresente 3 ícones: um para comidas, um para bebidas e outro para exploração](#20---deve-ser-fixo-e-apresentar-3-ícones-um-para-comidas-um-para-bebidas-e-outro-para-exploração)
    - [21 - Exiba o menu inferior apenas nas telas indicadas pelo protótipo](#21---o-menu-inferior-só-deve-aparecer-apenas-nas-telas-indicadas-pelo-protótipo)
    - [22 - Redirecione a pessoa usuária para uma lista de cocktails ao clicar no ícone de bebidas](#22---ao-clicar-no-ícone-de-bebidas-a-pessoa-deve-ser-redirecionada-para-uma-lista-de-cocktails)
    - [23 - Redirecione a pessoa usuária para a tela de explorar ao clicar no ícone de exploração](#23---ao-clicar-no-ícone-de-exploração-a-rota-deve-mudar-para-a-tela-de-explorar)
    - [24 - Redirecione a pessoa usuárua para uma lista de comidas ao clicar no ícone de comidas](#24---ao-clicar-no-ícone-de-comidas-a-pessoa-deve-ser-redirecionada-para-uma-lista-de-comidas)
  </details>

  <details>
    <summary>Tela principal de receitas</summary>

    - [25 - Implemente os elementos da tela principal de receitas respeitando os atributos descritos no protótipo](#25---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-principal-de-receitas)
    - [26 - Carregue as 12 primeiras receitas de comidas ou bebidas, uma em cada card](#26---devem-ser-carregadas-as-12-primeiras-receitas-de-comidas-ou-bebidas-uma-em-cada-card)
    - [27 - Implemente os botões de categoria para serem utilizados como filtro](#27---a-tela-deve-possuir-botões-de-categoria-para-serem-utilizados-como-filtro)
    - [28 - Implemente o filtro das receitas através da API ao clicar no filtro de categoria](#28---ao-clicar-no-filtro-de-categoria-todas-as-receitas-devem-mudar-para-os-dados-filtrados-da-api) 
    - [29 - Implemente o filtro como um toggle, que se for selecionado de novo, o app deve retornar as receitas sem nenhum filtro](#29---caso-o-filtro-selecionado-no-momento-seja-selecionado-de-novo-o-app-deve-retornar-as-receitas-sem-nenhum-filtro-como-se-fosse-um-toggle)
    - [30 - Apenas um filtro de categoria deve poder ser selecionado por vez](#30---apenas-um-filtro-de-categoria-deve-poder-ser-selecionado-por-vez)
    - [31 - No filtro de categorias deve existir a opção de filtrar por todas as categorias](#31---no-filtro-de-categorias-deve-existir-a-opção-de-filtrar-por-todas-as-categorias)
    - [32 - Ao clicar no card, a rota deve mudar para a tela de detalhes da receita com o ID da mesma na URL](#32---ao-clicar-no-card-a-rota-deve-mudar-para-a-tela-de-detalhes-da-receita-com-o-id-da-mesma-na-url)
  </details>

    <details>
    <summary>Tela de detalhes de uma receita</summary>

    - [33 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de detalhes de uma receita](#33---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-de-detalhes-de-uma-receita)
    - [34 - Uma request para a API deve ser feita passando o `id` da receita que deve estar disponível nos parâmetros da URL](#34---uma-request-para-a-api-deve-ser-feita-passando-o-id-da-receita-que-deve-estar-disponível-nos-parâmetros-da-url)
    - [35 - Essa tela deve conter uma imagem da receita, o título, a categoria (ou se é ou não alcoólico), uma lista de ingredientes seguidos pelas quantidades, instruções, um vídeo do youtube "embedado" e recomendações](#35---essa-tela-deve-conter-uma-imagem-da-receita-o-título-a-categoria-ou-se-é-ou-não-alcoólico-uma-lista-de-ingredientes-seguidos-pelas-quantidades-instruções-um-vídeo-do-youtube-embedado-e-recomendações)
    - [36 - As recomendações para receitas de comida deverão ser bebidas e vice-versa](#36---as-recomendações-para-receitas-de-comida-deverão-ser-bebidas-e-vice-versa)
    - [37 - Deverão ser mostrados 6 cards de recomendação, onde apenas 2 são mostrados e o scroll é horizontal, similar a um `carousel`](#37---deverão-ser-mostrados-6-cards-de-recomendação-onde-apenas-2-são-mostrados-e-o-scroll-é-horizontal-similar-a-um-carousel)
    - [38 - Um botão de nome "Iniciar Receita" deve ficar fixo na parte de baixo da tela o tempo todo](#38---um-botão-de-nome-iniciar-receita-deve-ficar-fixo-na-parte-de-baixo-da-tela-o-tempo-todo)
    - [39 - Caso a receita já tenha sido feita, o botão "Iniciar Receita" deve sumir](#39---caso-a-receita-já-tenha-sido-feita-o-botão-iniciar-receita-deve-sumir)
    - [40 - Caso a receita tenha sido iniciada mas não finalizada, o texto do botão deve ser "Continuar Receita"](#40---caso-a-receita-tenha-sido-iniciada-mas-não-finalizada-o-texto-do-botão-deve-ser-continuar-receita)
    - [41 - Quando o botão "Iniciar Receita" for clicado, a rota deve mudar para a tela de receita em processo](#41---quando-o-botão-iniciar-receita-for-clicado-a-rota-deve-mudar-para-a-tela-de-receita-em-processo)
    - [42 - Um botão de compartilhar e um de favoritar a receita devem estar disponíveis](#42---um-botão-de-compartilhar-e-um-de-favoritar-a-receita-devem-estar-disponíveis)
    - [43 - Ao clicar no botão de compartilhar, o link da receita dentro do app deve ser copiado para o clipboard e uma mensagem avisando que o link foi copiado deve aparecer](#43---ao-clicar-no-botão-de-compartilhar-o-link-da-receita-dentro-do-app-deve-ser-copiado-para-o-clipboard-e-uma-mensagem-avisando-que-o-link-foi-copiado-deve-aparecer)
    - [44 - O ícone do coração (favorito) deve vir preenchido caso a receita esteja favoritada e "despreenchido" caso contrário](#44---o-ícone-do-coração-favorito-deve-vir-preenchido-caso-a-receita-esteja-favoritada-e-despreenchido-caso-contrário)
    - [45 - Ao clicar no botão de favoritar, o ícone do coração deve mudar de seu estado atual, caso esteja preenchido deve mudar para "despreenchido" e vice-versa](#45---ao-clicar-no-botão-de-favoritar-o-ícone-do-coração-deve-mudar-de-seu-estado-atual-caso-esteja-preenchido-deve-mudar-para-despreenchido-e-vice-versa)
    - [46 - As receitas favoritas devem ser salvas em `localStorage` na chave `favoriteRecipes`](#46---as-receitas-favoritas-devem-ser-salvas-em-localstorage-na-chave-favoriterecipes)
    </details>
  
  <details>
    <summary>Tela de receita em progresso</summary>

    - [47 - Essa tela deve conter uma imagem da receita, seu titulo, sua categoria (ou se a bebida é alcoólica ou não) uma lista de ingredientes com suas respectivas quantidade e suas instruções](#47---essa-tela-deve-conter-uma-imagem-da-receita-seu-titulo-sua-categoria-ou-se-a-bebida-é-alcoólica-ou-não-uma-lista-de-ingredientes-com-suas-respectivas-quantidade-e-suas-instruções)
    - [48 - A lista de ingredientes deve conter um checkbox para cada um dos items](#48---a-lista-de-ingredientes-deve-conter-um-checkbox-para-cada-um-dos-items)
    - [49 - Ao clicar no checkbox de um ingrediente, o nome dele deve ser "riscado" da lista](#49---ao-clicar-no-checkbox-de-um-ingrediente-o-nome-dele-deve-ser-riscado-da-lista)
    - [50 - O estado do progresso deve ser mantido caso a pessoa atualize a página ou volte para a mesma receita](#50---o-estado-do-progresso-deve-ser-mantido-caso-a-pessoa-atualize-a-página-ou-volte-para-a-mesma-receita)
    - [51 - A mesma lógica de favoritar e compartilhar da tela de detalhes de uma receita se aplica aqui](#51---a-mesma-lógica-de-favoritar-e-compartilhar-da-tela-de-detalhes-de-uma-receita-se-aplica-aqui)
    - [52 - O botão de finalizar receita só pode estar habilitado quando todos os ingredientes estiverem _"checkados"_ (marcados)](#52---o-botão-de-finalizar-receita-só-pode-estar-habilitado-quando-todos-os-ingredientes-estiverem-checkados-marcados)
    - [53 - Após clicar no botão "Finalizar receita", a rota deve mudar para a página de receitas feitas, cuja rota deve ser `/receitas-feitas`](#53---após-clicar-no-botão-finalizar-receita-a-rota-deve-mudar-para-a-página-de-receitas-feitas-cuja-rota-deve-ser-receitas-feitas)
  </details>

  <details>
    <summary>Tela de receitas feitas</summary>

    - [54 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de receitas feitas](#54---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-de-receitas-feitas)
    - [55 - Caso a receita do card seja uma comida, ela deve possuir: a foto da receita, o nome, a categoria, a area, a data em que a pessoa fez a receita, as 2 primeiras tags retornadas pela API e um botão de compartilhar](#55---caso-a-receita-do-card-seja-uma-comida-ela-deve-possuir-a-foto-da-receita-o-nome-a-categoria-a-area-a-data-em-que-a-pessoa-fez-a-receita-as-2-primeiras-tags-retornadas-pela-api-e-um-botão-de-compartilhar)
    - [56 - Caso a receita do card seja uma bebida, ela deve possuir: a foto da receita, o nome, se é alcoólica, a data em que a pessoa fez a receita e um botão de compartilhar](#56---caso-a-receita-do-card-seja-uma-bebida-ela-deve-possuir-a-foto-da-receita-o-nome-se-é-alcoólica-a-data-em-que-a-pessoa-fez-a-receita-e-um-botão-de-compartilhar)
    - [57 - O botão de compartilhar deve copiar a URL da tela de detalhes da receita para o clipboard](#57---o-botão-de-compartilhar-deve-copiar-a-url-da-tela-de-detalhes-da-receita-para-o-clipboard)
    - [58 - Devem existir 2 botões que filtram as receitas por comida ou bebida e um terceiro que remove todos os filtros](#58---devem-existir-2-botões-que-filtram-as-receitas-por-comida-ou-bebida-e-um-terceiro-que-remove-todos-os-filtros)
    - [59 - Ao clicar na foto ou no nome da receita, a rota deve mudar para a tela de detalhes daquela receita](#59---ao-clicar-na-foto-ou-no-nome-da-receita-a-rota-deve-mudar-para-a-tela-de-detalhes-daquela-receita)
  </details>

  <details>
    <summary>Tela de receitas favoritas</summary>

    - [60 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de receitas favoritas (cumulativo com os atributos em comum com a tela de receitas feitas)](#60---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-de-receitas-favoritas-cumulativo-com-os-atributos-em-comum-com-a-tela-de-receitas-feitas)
    - [61 - Caso a receita do card seja uma comida, ela deve possuir: a foto da receita, o nome, a categoria, a area, um botão de compartilhar e um de "desfavoritar"](#61---caso-a-receita-do-card-seja-uma-comida-ela-deve-possuir-a-foto-da-receita-o-nome-a-categoria-a-area-um-botão-de-compartilhar-e-um-de-desfavoritar)
    - [62 - Caso a receita do card seja uma bebida, ela deve possuir: a foto da receita, o nome, se é alcoólica ou não, um botão de compartilhar e um de "desfavoritar"](#62---caso-a-receita-do-card-seja-uma-bebida-ela-deve-possuir-a-foto-da-receita-o-nome-se-é-alcoólica-ou-não-um-botão-de-compartilhar-e-um-de-desfavoritar)
    - [63 - O botão de compartilhar deve copiar a URL da tela de detalhes da receita para o clipboard](#63---o-botão-de-compartilhar-deve-copiar-a-url-da-tela-de-detalhes-da-receita-para-o-clipboard)
    - [64 - O botão de "desfavoritar" deve remover a receita da lista de receitas favoritas do `localStorage` e da tela](#64---o-botão-de-desfavoritar-deve-remover-a-receita-da-lista-de-receitas-favoritas-do-localstorage-e-da-tela)
    - [65 - Devem existir 2 botões que filtram as receitas por comida ou bebida e um terceiro que remove todos os filtros](#65---devem-existir-2-botões-que-filtram-as-receitas-por-comida-ou-bebida-e-um-terceiro-que-remove-todos-os-filtros)
    - [66 - Ao clicar na foto ou no nome da receita, a rota deve mudar para a tela de detalhes daquela receita](#66---ao-clicar-na-foto-ou-no-nome-da-receita-a-rota-deve-mudar-para-a-tela-de-detalhes-daquela-receita)
  </details>

  <details>
    <summary>Tela de explorar</summary>

    - [67 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de explorar](#67---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-de-explorar)
    - [68 - A tela deve ter dois botões: um para explorar comidas e o outro para explorar bebidas. O nomes dos botões devem ser "Explorar Comidas" e "Explorar Bebidas", respectivamente](#68---a-tela-deve-ter-dois-botões-um-para-explorar-comidas-e-o-outro-para-explorar-bebidas-o-nomes-dos-botões-devem-ser-explorar-comidas-e-explorar-bebidas-respectivamente)
    - [69 - Ao clicar em um dos botões, a rota deve mudar para a página de explorar comidas ou de explorar bebidas](#69---ao-clicar-em-um-dos-botões-a-rota-deve-mudar-para-a-página-de-explorar-comidas-ou-de-explorar-bebidas)

  </details>
  
  <details>
    <summary>Tela de explorar bebidas ou comidas</summary>

    - [70 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de explorar bebidas ou comidas](#70---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-de-explorar-bebidas-ou-comidas)
    - [71 - A tela deve ter três botões: um para explorar por ingrediente, um para explorar por local de origem e um para pegar uma receita aleatória](#71---a-tela-deve-ter-três-botões-um-para-explorar-por-ingrediente-um-para-explorar-por-local-de-origem-e-um-para-pegar-uma-receita-aleatória)
    - [72 - Ao clicar em "Por Ingredientes", a rota deve mudar para tela de explorar ingredientes](#72---ao-clicar-em-por-ingredientes-a-rota-deve-mudar-para-tela-de-explorar-ingredientes)
    - [73 - Ao clicar em "Por Local de Origem", a rota deve mudar para tela de explorar por local de origem](#73---ao-clicar-em-por-local-de-origem-a-rota-deve-mudar-para-tela-de-explorar-por-local-de-origem)
    - [74 - Ao clicar em "Me Surpreenda!", a rota deve mudar para a tela de detalhes de uma receita, que deve ser escolhida de forma aleatória através da API](#74---ao-clicar-em-me-surpreenda-a-rota-deve-mudar-para-a-tela-de-detalhes-de-uma-receita-que-deve-ser-escolhida-de-forma-aleatória-através-da-api)
  </details>

  <details>
    <summary>Tela de explorar ingredientes</summary>

    - [75 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de explorar ingredientes](#75---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-de-explorar-ingredientes)
    - [76 - A tela deve ter cards para os 12 primeiros ingredientes, de forma que cada card contêm: o nome do ingrediente e uma foto](#76---a-tela-deve-ter-cards-para-os-12-primeiros-ingredientes-de-forma-que-cada-card-contêm-o-nome-do-ingrediente-e-uma-foto)
    - [77 -  Ao clicar no card do ingrediente a rota deve mudar para tela principal de receitas, mas mostrando apenas as receitas que contém o ingrediente escolhido](#77----ao-clicar-no-card-do-ingrediente-a-rota-deve-mudar-para-tela-principal-de-receitas-mas-mostrando-apenas-as-receitas-que-contém-o-ingrediente-escolhido)
  </details>

  <details>
    <summary>Tela de explorar por local de origem/area</summary>

  - [78 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de explorar por local de origem](#78---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-de-explorar-por-local-de-origem)
  - [79 - A tela segue as mesmas especificações da tela de receitas principal, a única diferença é que os filtros de categoria são substituídos por um dropdown](#79---a-tela-segue-as-mesmas-especificações-da-tela-de-receitas-principal-a-única-diferença-é-que-os-filtros-de-categoria-são-substituídos-por-um-dropdown)
  - [80 - No dropdown devem estar disponíveis todas as áreas retornadas da API, incluindo a opção "All", que retorna as receitas sem nenhum filtro](#80---no-dropdown-devem-estar-disponíveis-todas-as-áreas-retornadas-da-api-incluindo-a-opção-all-que-retorna-as-receitas-sem-nenhum-filtro)
  - [81 - A rota deve ser apenas `/explorar/comidas/area`](#81---a-rota-deve-ser-apenas-explorarcomidasarea)
  </details>

  <details>
    <summary>Tela de perfil</summary>

  - [82 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de perfil](#82---todos-os-elementos-devem-respeitar-os-atributos-descritos-no-protótipo-para-a-tela-de-perfil)
  - [83 - O e-mail da pessoa usuária deve estar visível](#83---o-e-mail-da-pessoa-usuária-deve-estar-visível)
  - [84 - Essa tela deve conter 3 botões: um de nome "Receitas Feitas", um de nome "Receitas Favoritas" e um de nome "Sair"](#84---essa-tela-deve-conter-3-botões-um-de-nome-receitas-feitas-um-de-nome-receitas-favoritas-e-um-de-nome-sair)
  - [85 - Ao clicar no botão de "Receitas Favoritas", a rota deve mudar para a tela de receitas favoritas](#85---ao-clicar-no-botão-de-receitas-favoritas-a-rota-deve-mudar-para-a-tela-de-receitas-favoritas)
  - [86 - Ao clicar no botão de "Receitas Feitas", a rota deve mudar para a tela de receitas feitas](#86---ao-clicar-no-botão-de-receitas-feitas-a-rota-deve-mudar-para-a-tela-de-receitas-feitas)
  - [87 - Ao clicar no botão de "Sair", o `localStorage` deve ser limpo e a rota deve mudar para a tela de login](#87---ao-clicar-no-botão-de-sair-o-localstorage-deve-ser-limpo-e-a-rota-deve-mudar-para-a-tela-de-login)
  </details>

- [Instruções para entregar seu projeto](#instruções-para-entregar-seu-projeto)
  - [Durante o desenvolvimento](#durante-o-desenvolvimento)
  - [Depois de terminar o desenvolvimento (opcional)](#depois-de-terminar-o-desenvolvimento-opcional)
  - [Revisando um Pull Request](#revisando-um-pull-request)
- [Avisos finais](#avisos-finais)

---

## O QUE DEVERÁ SER DESENVOLVIDO

Você irá desenvolver um app de receitas, utilizando o que há de mais moderno dentro do ecossistema React: Hooks e Context API!

Nela será possível ver, buscar, filtrar, favoritar e acompanhar o processo de preparação de receitas e drinks!

A base de dados serão 2 APIs distintas, uma para comidas e outra para bebidas.

O layout tem como foco dispositivos móveis, então todos os protótipos vão estar desenvolvidos em telas menores.

### Protótipo do projeto

Você pode acessar um protótipo no link abaixo:

https://www.figma.com/file/WatDxtKl7g54QxhDi9qdbq/App-Receitas?node-id=0%3A1

Lembre-se de escrever testes unitários e sinta-se livre para alterar a UI, só respeite os atributos `data-testid`, eles serão usados na correção do exercício.

Você pode ler mais sobre atributos para testes [nesse link](https://www.eduardopedroso.com.br/?p=494)

#### ⚠️ Lembre-se de escrever testes unitários e sinta-se livre para alterar a UI, só respeite os atributos `data-testid`, eles serão usados na correção do exercício.

#### ⚠️ Para ver os comentários sobre cada componente, basta clicar no ícone de comentários no Figma (lado esquerdo superior).

![image](https://res.cloudinary.com/drdpedroso/image/upload/c_scale,w_400/v1575815877/Screenshot_2019-12-08_at_11.37.25_kzt7rl.png)

---

## DATA DE ENTREGA

Projeto em grupo.

Serão dez dias de projeto.

O projeto tem até a seguinte data: dd/mm/yyyy - 14:00h para ter entregue a avaliação final.

---

## COMO DESENVOLVER

Este repositório **já conta com uma `main-group` para cada grupo**, identificada como `main-group-1` para o grupo 1, `main-group-2` para o grupo 2, e assim por diante. Para desenvolver, você sempre deve:

* **Criar sua branch de desenvolvimento a partir da sua branch main**. Para isso, clone este repositório, faça o `git checkout main-group-XX && git pull` e em seguida o `git checkout -b main-group-XX-minha-feature`.
* Para criar uma Pull Request para fazer **Code Review**, entitule-a `[GRUPO XX] Meu título` e **sempre aponte a Pull Request da sua branch para a branch `main-group-XX` do seu grupo, como no exemplo abaixo:**

![Exemplo de como apontar uma Pull Request para a branch main do grupo](pull-request-para-branch-do-grupo.png)

* Quando várias pessoas desenvolvem para um mesmo projeto podem ocorrer **conflitos de merge** que precisarão ser resolvidos. Prestem atenção a isso!

⚠ **ATENÇÃO! É POSSÍVEL COMMITAR, POR ENGANO, NA BRANCH DE OUTRO GRUPO, ENTÃO TOME MUITO CUIDADO** ⚠

### ANTES DE COMEÇAR A DESENVOLVER:

### Antes de começar a desenvolver:

1. Clone o repositório
  * `git clone git@github.com:tryber/sd-0x-recipes-app-N.git`.
  * Entre na pasta do repositório que você acabou de clonar:
    * `cd sd-0x-recipes-app-N`
  * Vá para a branch do seu grupo, com `git checkout main-group-XX && git pull`, onde `XX` é o número do seu grupo. Exemplos: `main-group-1`, `main-group-22`.

2. Instale as dependências e inicialize o projeto
  * Instale as dependências:
    * `npm install`
  * Inicialize o projeto:
    * `npm start` (uma nova página deve abrir no seu navegador com um texto simples)

3. Faça alterações separadas por novas branchs criadas a partir da branch `main-group-XX`, criando uma nova branch para cada demanda
  * Verifique que você está na branch `main-group-XX`
    * Exemplo: `git branch`
  * Se não estiver, mude para a branch `main-group-XX`
    * Exemplo: `git checkout main-group-XX && git pull`
  * Agora, crie uma branch para a demanda que você vai desenvolver do seu projeto
    * Você deve criar uma branch com uma breve descrição da demanda a ser desenvolvida
    * Exemplo: `git checkout -b main-group-XX-cria-campo-de-input`

4. Adicione as mudanças ao _stage_ do Git e faça um `commit`
  * Verifique que as mudanças ainda não estão no _stage_
    * Exemplo: `git status` (devem aparecer listadas as novas alterações em vermelho)
  * Adicione o arquivo alterado ao _stage_ do Git
      * Exemplo:
        * `git add .` (adicionando todas as mudanças - _que estavam em vermelho_ - ao stage do Git)
        * `git status` (devem aparecer listadas as novas alterações em verde)
  * Faça seus `commit`
      * Exemplo:
        * `git commit -m 'cria componente de input`
        * `git status` (deve aparecer uma mensagem tipo _nothing to commit_ )

5. Adicione a sua branch com o novo `commit` ao repositório remoto
  * Usando o exemplo anterior: `git push -u origin main-group-XX-cria-campo-de-input`

6. Crie um novo `Pull Request` _(PR)_
  * Vá até a página de _Pull Requests_ do [repositório no GitHub](https://github.com/tryber/sd-0x-recipes-app-N/pulls)
  * Clique no botão verde _"New pull request"_
  * Clique na caixa de seleção _"Compare"_ e escolha a branch do grupo, `main-group-XX`, e a sua branch **com atenção**
  * Coloque um título para a sua _Pull Request_
    * Exemplo: _"[GRUPO XX] Cria tela de busca"_
  * Clique no botão verde _"Create pull request"_
  * Adicione uma descrição para o _Pull Request_ e clique no botão verde _"Create pull request"_
  * **Não se preocupe em preencher mais nada por enquanto!**
  * Volte até a [página de _Pull Requests_ do repositório](https://github.com/tryber/sd-0x-recipes-app-N/pulls) e confira que o seu _Pull Request_ está criado

7. Assim que aprovado por pelo menos duas pessoas do seu grupo e o _Linter_ estiver adereçado, acesse **SEU** _Pull Request_ e clique no botão _"Merge pull request"_

---

## REQUISITOS DO PROJETO

Para o bom andamento deste projeto disponibilizamos, além do README a seguir, um quadro Kanban com as demandas a realizar para o projeto ser concluído com sucesso. Confira o Slack para saber como acessar o quadro! É de suma importância que o grupo se organize utilizando o quadro para maior eficiência e para que se minimizem os conflitos que a união de vários códigos trará.

Além disso, você verá que os requisitos do projeto tem, além das observações técnicas e do que será validado, descrições tais quais se veriam em um projeto real. É muito importante ser capaz de ler descrições como essa e transformá-las em produtos ou, se houver dúvida, saber tirar tais dúvidas! Seguimos à disposição no Slack para isso.


Este repositório já contem um _template_ com um App React criado, configurado e com os testes automatizados que fazem parte da correção. Ele também conta com uma branch **main-group** para cada grupo, identificada como `main-group-1` para o grupo 1, `main-group-2` para o grupo 2 e assim por diante.

### Linter

Para garantir a qualidade do seu código de forma a tê-lo mais legível, de mais fácil manutenção e seguindo as boas práticas de desenvolvimento nós utilizamos neste projeto o linter `ESLint`. Para rodar o linter localmente no seu projeto, execute o comando abaixo:

```bash
npm run lint
```

⚠ **PULL REQUESTS COM ISSUES DE LINTER NÃO SERÃO AVALIADAS. ATENTE-SE PARA RESOLVÊ-LAS ANTES DE FINALIZAR O DESENVOLVIMENTO!** ⚠

### Execução de testes de requisito

Para o projeto ser validado, todos os testes de comportamento devem passar. É possível testar isso local rodando `npm run cy`. Esse comando roda a suite de testes do Cypress que valida se o fluxo geral e os requisitos funcionais estão funcionando como deveriam. Você pode também executar o comando `npm run cy:open` para ter um resultado visual dos testes executados.

Esses testes não consideram o layout de maneira geral, mas sim os atributos e informações corretas, então preste atenção nisso! Os testes te darão uma mensagem de erro caso não estejam passando (seja qual for o motivo). 😉

**Atenção:** Sua aplicação deve estar rodando para o Cypress no terminal poder testar.

## APIs

### TheMealDB API

O [TheMealDB](https://www.themealdb.com/) é um banco de dados aberto, mantido pela comunidade, com receitas e ingredientes de todo o mundo.

Os end-points são bastante ricos, você pode [vê-los aqui](https://www.themealdb.com/api.php)

O modelo de resposta para uma `meal` é o seguinte:
  <details>
    <summary>Ver modelo de resposta para uma meal</summary>

  ```json
    {
      "meals":[
          {
            "idMeal":"52882",
            "strMeal":"Three Fish Pie",
            "strDrinkAlternate":null,
            "strCategory":"Seafood",
            "strArea":"British",
            "strInstructions":"Preheat the oven to 200C\/400F\/Gas 6 (180C fan).\r\nPut the potatoes into a saucepan of cold salted water. Bring up to the boil and simmer until completely tender. Drain well and then mash with the butter and milk. Add pepper and taste to check the seasoning. Add salt and more pepper if necessary.\r\nFor the fish filling, melt the butter in a saucepan, add the leeks and stir over the heat. Cover with a lid and simmer gently for 10 minutes, or until soft. Measure the flour into a small bowl. Add the wine and whisk together until smooth.\r\nAdd the milk to the leeks, bring to the boil and then add the wine mixture. Stir briskly until thickened. Season and add the parsley and fish. Stir over the heat for two minutes, then spoon into an ovenproof casserole. Scatter over the eggs. Allow to cool until firm.\r\nSpoon the mashed potatoes over the fish mixture and mark with a fork. Sprinkle with cheese.\r\nBake for 30-40 minutes, or until lightly golden-brown on top and bubbling around the edges.",
            "strMealThumb":"https:\/\/www.themealdb.com\/images\/media\/meals\/spswqs1511558697.jpg",
            "strTags":"Fish,Seafood,Dairy,Pie",
            "strYoutube":"https:\/\/www.youtube.com\/watch?v=Ds1Jb8H5Sg8",
            "strIngredient1":"Potatoes",
            "strIngredient2":"Butter",
            "strIngredient3":"Milk",
            "strIngredient4":"Gruy\u00e8re",
            "strIngredient5":"Butter",
            "strIngredient6":"Leek",
            "strIngredient7":"Plain Flour",
            "strIngredient8":"White Wine",
            "strIngredient9":"Milk",
            "strIngredient10":"Parsley",
            "strIngredient11":"Salmon",
            "strIngredient12":"Haddock",
            "strIngredient13":"Smoked Haddock",
            "strIngredient14":"Eggs",
            "strIngredient15":"",
            "strIngredient16":"",
            "strIngredient17":"",
            "strIngredient18":"",
            "strIngredient19":"",
            "strIngredient20":"",
            "strMeasure1":"1kg",
            "strMeasure2":"Knob",
            "strMeasure3":"Dash",
            "strMeasure4":"50g",
            "strMeasure5":"75g",
            "strMeasure6":"2 sliced",
            "strMeasure7":"75g",
            "strMeasure8":"150ml",
            "strMeasure9":"568ml",
            "strMeasure10":"2 tbs chopped",
            "strMeasure11":"250g",
            "strMeasure12":"250g",
            "strMeasure13":"250g",
            "strMeasure14":"6",
            "strMeasure15":"",
            "strMeasure16":"",
            "strMeasure17":"",
            "strMeasure18":"",
            "strMeasure19":"",
            "strMeasure20":"",
            "strSource":"https:\/\/www.bbc.co.uk\/food\/recipes\/three_fish_pie_58875",
            "dateModified":null
          }
      ]
    }
  ```
  </details>

Os ingredientes seguem uma ordem lógica onde o nome dele (`strIngredient1`) e a quantidade (`strMeasure1`) tem o mesmo número no final (1, nesse caso).

É possível listar todas as `categorias`, `áreas` e `ingredientes`:

```
categorias: https://www.themealdb.com/api/json/v1/1/list.php?c=list
areas: https://www.themealdb.com/api/json/v1/1/list.php?a=list
ingredientes: https://www.themealdb.com/api/json/v1/1/list.php?i=list
```

As fotos dos ingredientes vêm de um end-point padronizado com a seguinte lógica:

```
https://www.themealdb.com/images/ingredients/{nome-do-ingrediente}.png
// exemplo com "lime
https://www.themealdb.com/images/ingredients/Lime.png
```

### The CockTailDB API

Bem similar (inclusive mantida pela mesma entidade) a TheMealDB API, só que focado em bebidas.

Os end-points também são bastante ricos, você pode [vê-los aqui](https://www.thecocktaildb.com/api.php)

As respostas seguem a mesma estrutura, com algumas particularidade relativas as bebidas (como ser ou não alcoólica, por exemplo)

  <details>
    <summary>Ver modelo de resposta para drinks</summary>

  ```json
    {
      "drinks":[
          {
            "idDrink":"17256",
            "strDrink":"Martinez 2",
            "strDrinkAlternate":null,
            "strDrinkES":null,
            "strDrinkDE":null,
            "strDrinkFR":null,
            "strDrinkZH-HANS":null,
            "strDrinkZH-HANT":null,
            "strTags":null,
            "strVideo":null,
            "strCategory":"Cocktail",
            "strIBA":null,
            "strAlcoholic":"Alcoholic",
            "strGlass":"Cocktail glass",
            "strInstructions":"Add all ingredients to a mixing glass and fill with ice.\r\n\r\nStir until chilled, and strain into a chilled coupe glass.",
            "strInstructionsES":null,
            "strInstructionsDE":"Alle Zutaten in ein Mischglas geben und mit Eis f\u00fcllen. Bis zum Abk\u00fchlen umr\u00fchren und in ein gek\u00fchltes Coup\u00e9glas abseihen.",
            "strInstructionsFR":null,
            "strInstructionsZH-HANS":null,
            "strInstructionsZH-HANT":null,
            "strDrinkThumb":"https:\/\/www.thecocktaildb.com\/images\/media\/drink\/fs6kiq1513708455.jpg",
            "strIngredient1":"Gin",
            "strIngredient2":"Sweet Vermouth",
            "strIngredient3":"Maraschino Liqueur",
            "strIngredient4":"Angostura Bitters",
            "strIngredient5":null,
            "strIngredient6":null,
            "strIngredient7":null,
            "strIngredient8":null,
            "strIngredient9":null,
            "strIngredient10":null,
            "strIngredient11":null,
            "strIngredient12":null,
            "strIngredient13":null,
            "strIngredient14":null,
            "strIngredient15":null,
            "strMeasure1":"1 1\/2 oz",
            "strMeasure2":"1 1\/2 oz",
            "strMeasure3":"1 tsp",
            "strMeasure4":"2 dashes",
            "strMeasure5":null,
            "strMeasure6":null,
            "strMeasure7":null,
            "strMeasure8":null,
            "strMeasure9":null,
            "strMeasure10":null,
            "strMeasure11":null,
            "strMeasure12":null,
            "strMeasure13":null,
            "strMeasure14":null,
            "strMeasure15":null,
            "strCreativeCommonsConfirmed":"No",
            "dateModified":"2017-12-19 18:34:15"
          }
      ]
    }
  ```
  </details>

Os ingredientes seguem uma ordem lógica onde o nome dele (`strIngredient1`) e a quantidade (`strMeasure1`) tem o mesmo número no final (1, nesse caso).

---

### Grupos de prioridade

#### ---- FAZER GRUPOS DE PRIORIDADE ----

## Observações técnicas

Algumas coisas devem seguir um padrão pré-estabelecido para que os teste de correção funcionem corretamente.

⚠️ Leia-os atentamente e siga à risca o que for pedido. O não cumprimento de um requisito, total ou parcialmente, impactará em sua avaliação. ⚠️

* Os requisitos do seu projeto são avaliados automaticamente, sendo utilizada a resolução de tela de `360 x 640` (360 pixels de largura por 640 pixels de altura).

    - ⚠️ Logo, recomenda-se desenvolver seu projeto usando a mesma resolução, via instalação [deste plugin](https://chrome.google.com/webstore/detail/window-resizer/kkelicaakdanhinjdeammmilcgefonfh?hl=en) do `Chrome` para facilitar a configuração da resolução. ⚠️

### Rotas

As rotas a serem utilizadas na aplicação devem ser as seguintes:

* Tela de login: `/`;
* Tela principal de receitas de comidas: `/comidas`;
* Tela principal de receitas de bebidas: `/bebidas`;
* Tela de detalhes de uma receita de comida: `/comidas/{id-da-receita}`;
* Tela de detalhes de uma receita de bebida: `/bebidas/{id-da-receita}`;
* Tela de receita em processo de comida: `/comidas/{id-da-receita}/in-progress`;
* Tela de receita em processo de bebida: `/bebidas/{id-da-receita}/in-progress`;
* Tela de explorar: `/explorar`;
* Tela de explorar comidas: `/explorar/comidas`;
* Tela de explorar bebidas: `/explorar/bebidas`;
* Tela de explorar comidas por ingrediente: `/explorar/comidas/ingredientes`;
* Tela de explorar bebidas por ingrediente: `/explorar/bebidas/ingredientes`;
* Tela de explorar comidas por local de origem: `/explorar/comidas/area`;
* Tela de perfil: `/perfil`;
* Tela de receitas feitas: `/receitas-feitas`;
* Tela de receitas favoritas: `/receitas-favoritas`.

### `localStorage`

O uso de `localStorage` é necessário para que as informações não se percam caso a pessoa atualize a página.
O correto é usar os valores para iniciar sua store ou seu context.

No `localStorage` do navegador:

* a chave `mealsToken` deve conter a seguinte estrutura:
```
1
```

* a chave `cocktailsToken` deve conter a seguinte estrutura:
```
1
```

* a chave `user` deve conter a seguinte estrutura:
```
{
    email: email-da-pessoa
}
```

* a chave `doneRecipes` deve conter a seguinte estrutura:
```
[{
    id: id-da-receita,
    type: comida-ou-bebida,
    area: area-da-receita-ou-texto-vazio,
    category: categoria-da-receita-ou-texto-vazio,
    alcoholicOrNot: alcoholic-ou-non-alcoholic-ou-texto-vazio,
    name: nome-da-receita,
    image: imagem-da-receita,
    doneDate: quando-a-receita-foi-concluida,
    tags: array-de-tags-da-receita-ou-array-vazio
}]
```

* a chave `favoriteRecipes` deve conter a seguinte estrutura:
```
[{
    id: id-da-receita,
    type: comida-ou-bebida,
    area: area-da-receita-ou-texto-vazio,
    category: categoria-da-receita-ou-texto-vazio,
    alcoholicOrNot: alcoholic-ou-non-alcoholic-ou-texto-vazio,
    name: nome-da-receita,
    image: imagem-da-receita
}]
```

* a chave `inProgressRecipes` deve conter a seguinte estrutura:
```
{
    cocktails: {
        id-da-bebida: [lista-de-ingredientes-utilizados],
        ...
    },
    meals: {
        id-da-comida: [lista-de-ingredientes-utilizados],
        ...
    }
}
```

**Observações técnicas** 

* `id-da-bebida` e `id-da-comida` representam o ID de uma bebida e comida, respectivamente, e cada item da lista de ingredientes da respectiva receita deve ser representado apenas pelo número do ingrediente no formato numérico.

### Ícones

Os ícones a serem utilizados na aplicação estão disponíveis do diretório `src/image/`. Esses ícones serão utilizados pelos testes da avaliação automatizada, então certifique-se de utilizá-los nos requisitos e de não renomeá-los.

Os ícones são:

* `profileIcon.svg`;
* `searchIcon.svg`;
* `drinkIcon.svg`;
* `exploreIcon.svg`;
* `mealIcon.svg`;
* `shareIcon.svg`;
* `whiteHeartIcon.svg`;
* `blackHeartIcon.svg`.

---

### LISTA DE REQUISITOS

Nesse projeto, a pessoa que estiver utilizando o app pode procurar uma receita especifica, explorar receitas baseado em diferentes critérios, favoritar e fazer as receitas entre outras funcionalidades.

As telas sofrem variações dependendo do tipo da receita (se é comida ou bebida, no caso).


## Testes unitários

### 1 - Desenvolva os testes unitários de maneira que a seja de, no mínimo, 90%

## Tela de login

### 2 - Crie todos os elementos que devem respeitar os atributos descritos no protótipo para a tela de login

  **Observações técnicas**

  * O input de email deve possuir o atributo `data-testid="email-input"`;
  * O input de senha deve possuir o atributo `data-testid="password-input"`;
  * O botão "Entrar" deve possuir o atributo `data-testid="login-submit-btn"`.

### 3 - Desenvolva a tela de maneira que a pessoa deve conseguir escrever seu email no input de email

### 4 - Desenvolva a tela de maneira que a pessoa deve conseguir escrever sua senha no input de senha

### 5 - Desenvolva a tela de maneira que o formulário só seja válido após um email válido e uma senha de mais de 6 caracteres serem preenchidos

O formulário só fica válido após um email válido e uma senha de mais de 6 caracteres serem preenchidos. Caso o formulário esteja inválido, o botão de submeter deve estar desativado, contendo a propriedade `disabled`. Caso contrário, deve estar ativado, não contendo a propriedade `disabled`.

  **Observações técnicas**

  * O botão deve estar desativado se o email for inválido;
  * O botão deve estar desativado se a senha deve tiver 6 caracteres ou menos;
  * O botão deve estar ativado se o email e a senha forem válidos.


### 6 - Salve 2 tokens no localStorage após a submissão, identificados pelas chaves mealsToken e cocktailsToken

  **Observações técnicas**

  * O token de teste é sempre `1`.

### 7 - Salve o e-mail da pessoa usuária no localStorage na chave user após a submissão

  **Observações técnicas**

  * Após a submissão, o e-mail de pessoa usuária deve ser salvo em `localStorage` na chave `user` no formato `{ email: email-da-pessoa }`.

### 8 - Redirecione a pessoa usuária para a tela principal de receitas de comidas após a submissão e validação com sucesso do login

  **Observações técnicas**

  * A rota muda para a tela principal de receitas de comidas.

## Header

### 9 - Implemente os elementos do header na tela principal de receitas, respeitando os atributos descritos no protótipo

  **Observações técnicas**

  * Possui os data-testids `profile-top-btn`, `page-title` e `search-top-btn`.


### 10 - Implemente um ícone para a tela de perfil, um título e um ícone para a busca, caso exista no protótipo

Todas as [rotas](#rotas) serão verificadas. Os ícones podem ser encontrados em `src/images/profileIcon.svg` e em `src/images/searchIcon.svg`.

  **Observações técnicas**

  * Não tem header na tela de login;
  * O header tem os ícones corretos na tela de principal de receitas de comidas;
  * O header tem os ícones corretos na tela de principal de receitas de bebidas;
  * Não tem header na tela de detalhes de uma receita de comida;
  * Não tem header na tela de detalhes de uma receita de bebida;
  * Não tem header na tela de receita em processo de comida;
  * Não tem header na tela de receita em processo de bebida;
  * O header tem os ícones corretos na tela de explorar;
  * O header tem os ícones corretos na tela de explorar comidas;
  * O header tem os ícones corretos na tela de explorar bebidas;
  * O header tem os ícones corretos na tela de explorar comidas por ingrediente;
  * O header tem os ícones corretos na tela de explorar bebidas por ingrediente;
  * O header tem os ícones corretos na tela de explorar comidas por local de origem;
  * O header tem os ícones corretos na tela de perfil;
  * O header tem os ícones corretos na tela de receitas feitas;
  * O header tem os ícones corretos na tela de receitas favoritas.

### 11 - Redirecione a pessoa usuária para a tela de perfil ao clicar no botão de perfil

  **Observações técnicas**

  * A mudança de tela ocorre.

### 12 - Desenvolva o botão de busca que, ao ser clicado, a barra de busca deve aparecer. O mesmo serve para escondê-la

  **Observações técnicas**
  
  * Ao clicar no botão de busca pela primeira vez a barra de busca aparece;
  * Ao clicar no botão de busca pela segunda vez a barra de busca desaparece.

## Barra de busca - Header

### 13 - Implemente os elementos da barra de busca respeitando os atributos descritos no protótipo

Deve existir os data-testids tanto da barra de busca quanto de todos os radio-buttons.

  **Observações técnicas**

  * O input de busca deve possuir o atributo `data-testid="search-input"`;
  * O radio button de busca de ingrediente deve possuir o atributo `data-testid="ingredient-search-radio"`;
  * O radio button de busca da primeira letra deve possuir o atributo `"data-testid="first-letter-search-radio"`.

### 14 - Posicione a barra logo abaixo do header e implemente 3 radio buttons: Ingrediente, Nome e Primeira letra

A barra de busca deve ficar logo abaixo do header e deve possuir 3 _radio buttons_: `Ingrediente`, `Nome` e `Primeira letra`. Eles, em conjunto com a `search-input`, devem mudar a forma como serão filtradas as receitas após clicar no botão `Buscar`.  Os _endpoints_ da API que você deve usar podem ser consultados [aqui para a API de comidas](https://www.themealdb.com/api.php) e [aqui para a API de bebidas](https://www.thecocktaildb.com/api.php).

  **Observações técnicas**

  * Se o radio selecionado for `Ingrediente`, a busca na API é feita corretamente pelo ingrediente. O endpoint utilizado deve ser `https://www.themealdb.com/api/json/v1/1/filter.php?i={ingrediente}`;
  * Se o radio selecionado for `Nome`, a busca na API é feita corretamente pelo nome. O endpoint utilizado deve ser `https://www.themealdb.com/api/json/v1/1/search.php?s={nome}`;
  * Se o radio selecionado for `Primeira letra`, a busca na API é feita corretamente pelo primeira letra. O endpoint utilizado deve ser `https://www.themealdb.com/api/json/v1/1/search.php?f={primeira-letra}`;
  * Se o radio selecionado for `Primeira letra` e a busca na API for feita com mais de uma letra, deve-se exibir um `alert` com a mensgem "Sua busca deve conter somente 1 (um) caracter".

##### Exemplo: Ao selecionar `Ingrediente` e buscar por `chicken`, deve-se utilizar o endpoint `https://www.themealdb.com/api/json/v1/1/filter.php?i=chicken`.

##### Observação: Para esse requisito será verificada apenas a tela principal de receitas de comidas.

### 15 - Busque na API de comidas caso a pessoa esteja na página de comidas e na de bebidas caso esteja na de bebidas

  **Observações técnicas**

  * Na tela de bebidas, se o radio selecionado for `Ingrediente`, a busca na API é feita corretamente pelo ingrediente. O endpoint utilizado deve ser `https://www.thecocktaildb.com/api/json/v1/1/filter.php?i={ingrediente}`;
  * Na tela de bebidas, se o radio selecionado for `Nome`, a busca na API é feita corretamente pelo nome. O endpoint utilizado deve ser `https://www.thecocktaildb.com/api/json/v1/1/search.php?s={nome}`;
  * Na tela de bebidas, se o radio selecionado for Primeira letra, a busca na API é feita corretamente pelo primeira letra. O endpoint utilizado deve ser `https://www.thecocktaildb.com/api/json/v1/1/search.php?f={primeira-letra}`;
  * Na tela de bebidas, se o radio selecionado for `Primeira letra` e a busca na API for feita com mais de uma letra, deve-se exibir um `alert` com a mensgem "Sua busca deve conter somente 1 (um) caracter".
##### Observação: Para esse requisito será verificada apenas a tela principal de receitas de bebidas, já que a de comidas já foi verificada no requisito 15.

### 16 - Redirecione para a tela de detalhes da receita caso apenas uma receita seja encontrada, com o ID da mesma na URL

  **Observações técnicas**

  * Caso apenas uma comida seja encontrada, deve-se ir para sua rota de detalhes (`/comidas/{id-da-receita}`);
  * Caso apenas uma bebida seja encontrada, deve-se ir para sua rota de detalhes (`/bebidas/{id-da-receita}`).

### 17 - Mostre as receitas em cards caso mais de uma receita seja encontrada

  Mostre as receitas em cards como as da tela principal, caso mais de uma receita seja encontrada.

  **ObservaçÕes técnicas**

  * Caso mais de uma comida seja encontrada, mostrar as 12 primeiras (ou menos, se não hoverem 12);
  * Caso mais de uma bebida seja encontrada, mostrar as 12 primeiras (ou menos, se não hoverem 12).

### 18 - Exiba um `alert` caso nenhuma receita seja encontrada

  O alert deve contendo o texto "Sinto muito, não encontramos nenhuma receita para esses filtros."

  **Observações técnicas**

  * Caso nenhuma comida seja encontrada o alert deve ser exibido;
  * Caso nenhuma bebida seja encontrada o alert deve ser exibido.

## Menu inferior

### 19 - Implemente os elementos do menu inferior respeitando os atributos descritos no protótipo

  Todos os elementos devem respeitar os atributos descritos no protótipo para o menu inferior disponível na tela principal de receitas

  **Observações técnicas**

  * O menu inferior deve ter possuir o atributo `data-testid="footer"`;
  * O elemento que leva para a página de drinks deve possuir o atributo `data-testid="drinks-bottom-btn"`;
  * O elemento que leva para a página de explorar deve possuir o atributo `data-testid="explore-bottom-btn"`;
  * O elemento que leva para a página de comidas deve possuir o atributo `data-testid="food-bottom-btn"`.

### 20 - Posicione o menu inferior de forma fixa e apresente 3 ícones: um para comidas, um para bebidas e outro para exploração

  **Observações técnicas**

  * O menu inferior deve ficar fixado sempre ao final da página;
  * Apresenta os ícones corretos (drinkIcon.svg, exploreIcon.svg e mealIcon.svg, disponíveis na pasta `src/images/`).

### 21 - Exiba o menu inferior apenas nas telas indicadas pelo protótipo

O menu inferior deve aparecer somente nas telas indicas no protótipo, como a de comida, de explorar e de perfil.

  **Observações técnicas**

  * Não tem footer na tela de login;
  * Tem footer na tela de principal de receitas de comidas;
  * Tem footer na tela de principal de receitas de bebidas;
  * Não tem footer na tela de detalhes de uma receita de comida;
  * Não tem footer na tela de detalhes de uma receita de bebida;
  * Não tem footer na tela de receita em processo de comida;
  * Não tem footer na tela de receita em processo de bebida;
  * Tem footer na tela de explorar;
  * Tem footer na tela de explorar comidas;
  * Tem footer na tela de explorar bebidas;
  * Tem footer na tela de explorar comidas por ingrediente;
  * Tem footer na tela de explorar bebidas por ingrediente;
  * Tem footer na tela de explorar comidas por local de origem;
  * Tem footer na tela de perfil;
  * Não tem footer na tela de receitas feitas;
  * Não tem footer na tela de receitas favoritas.

### 22 - Redirecione a pessoa usuária para uma lista de cocktails ao clicar no ícone de bebidas

### 23 - Redirecione a pessoa usuária para a tela de explorar ao clicar no ícone de exploração

### 24 - Redirecione a pessoa usuárua para uma lista de comidas ao clicar no ícone de comidas

## Tela principal de receitas

### 25 - Implemente os elementos da tela principal de receitas respeitando os atributos descritos no protótipo

  **Observações técnicas**

  * A tela tem os data-testids de todos os 12 cards da tela de comidas;
  * A tela tem os data-testids de todos os 12 cards da tela de bebidas.

### 26 - Carregue as 12 primeiras receitas de comidas ou bebidas, uma em cada card

O Card de receita deve conter sua foto (`strMealThumb` ou `strDrinkThumb`) e seu nome (`strMeal` ou `strDrink`).

  **Observações técnicas**

  * Caso as receitas sejam de comida, deve-se carregar as 12 primeiras receitas obtidas através do endpoint `https://www.themealdb.com/api/json/v1/1/search.php?s=`;
  * Caso as receitas sejam de bebida, deve-se carregar as 12 primeiras receitas obtidas através do endpoint `https://www.thecocktaildb.com/api/json/v1/1/search.php?s=`.

### 27 - Implemente os botões de categoria para serem utilizados como filtro

Cada botão deve conter o atributo prefixado `data-testid=${categoryName}-category-filter` e devem ser exibidas apenas as 5 primeiras categorias retornadas da API.

  **Observações técnicas**

  * Caso as receitas sejam de comida, deve-se exibir as 5 primeiras categorias de comida obtidas através do endpoint `https://www.themealdb.com/api/json/v1/1/list.php?c=list`;
  * Caso as receitas sejam de bebida, deve-se exibir as 5 primeiras categorias de bebida obtidas através do endpoint `https://www.thecocktaildb.com/api/json/v1/1/list.php?c=list`.

### 28 - Implemente o filtro das receitas através da API ao clicar no filtro de categoria

As categorias disponíveis devem ser obtidas através da API de [comidas](https://www.themealdb.com/api.php) ou [bebidas](https://www.thecocktaildb.com/api.php).

  **Observações técnicas**

  * Caso as receitas sejam de comida e a categoria seja "Beef", deve-se carregar as 12 primeiras receitas de "Beef";
  * Caso as receitas sejam de comida e a categoria seja "Breakfast", deve-se carregar as 12 primeiras receitas de "Breakfast";
  * Caso as receitas sejam de comida e a categoria seja "Chicken", deve-se carregar as 12 primeiras receitas de "Chicken";
  * Caso as receitas sejam de comida e a categoria seja "Dessert", deve-se carregar as 12 primeiras receitas de "Dessert";
  * Caso as receitas sejam de comida e a categoria seja "Goat", deve-se carregar as 12 primeiras receitas de "Goat";
  * Caso as receitas sejam de bebida e a categoria seja "Ordinary Drink", deve-se carregar as 12 primeiras receitas de "Ordinary Drink";
  * Caso as receitas sejam de bebida e a categoria seja "Cocktail", deve-se carregar as 12 primeiras receitas de "Cocktail";
  * Caso as receitas sejam de bebida e a categoria seja "Milk / Float / Shake", deve-se carregar as 12 primeiras receitas de "Milk / Float / Shake";
  * Caso as receitas sejam de bebida e a categoria seja "Other/Unknown", deve-se carregar as 12 primeiras receitas de "Other/Unknown";
  * Caso as receitas sejam de bebida e a categoria seja "Cocoa", deve-se carregar as 12 primeiras receitas de "Cocoa".

### 29 - Implemente o filtro como um toggle, que se for selecionado de novo, o app deve retornar as receitas sem nenhum filtro

  **Observações técnicas**

  * Caso as receitas sejam de comida e o filtro tenha sido selecionado novamente, deve-se retornar as 12 primeiras receitas sem filtro;
  * Caso as receitas sejam de bebida e o filtro tenha sido selecionado novamente, deve-se retornar as 12 primeiras receitas sem filtro.

### 30 - Apenas um filtro de categoria deve poder ser selecionado por vez

Ou seja, se outro filtro de categoria for selecionado, ele deve substituir o anterior.

  **Observações técnicas**

  * Caso as receitas sejam de comida apenas um filtro de categoria deve poder ser selecionado por vez;
  * Caso as receitas sejam de bebida apenas um filtro de categoria deve poder ser selecionado por vez.

### 31 - No filtro de categorias deve existir a opção de filtrar por todas as categorias

Ou seja, retornando novamente todas as receitas. O nome do filtro deve ser "All".

  **Observações técnicas**

  * Caso as receitas sejam de comida deve existir a opção de filtrar por todas as categorias;
  * Caso as receitas sejam de bebida deve existir a opção de filtrar por todas as categorias.

### 32 - Ao clicar no card, a rota deve mudar para a tela de detalhes da receita com o ID da mesma na URL

  Além de dizer se a pessoa veio da tela de comidas ou de bebidas. Exemplo: `/comidas/{id-da-receita}`.

  **Observações técnicas**

  * Caso as receitas sejam de comida a rota deve mudar para a tela de detalhes da receita;
  * Caso as receitas sejam de bebida a rota deve mudar para a tela de detalhes da receita.

## Tela de detalhes de uma receita

### 33 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de detalhes de uma receita

A verificação será feita a partir dos atributos data-testids:

  * A foto deve possuir o atributo `data-testid="recipe-photo"`;
  * O título deve possuir o atributo `data-testid="recipe-title"`;
  * O botão de compartilhar deve possuir o atributo `data-testid="share-btn"`;
  * O botão de compartilhar deve possuir o atributo `data-testid="favorite-btn"`;
  * O texto da categoria deve possuir o atributo `data-testid="recipe-category"`;
  * Os ingredientes devem possuir o atributo `data-testid="${index}-ingredient-name-and-measure"`;
  * O texto de instruções deve possuir o atributo `data-testid="instructions"`;
  * O vídeo, presente somente na tela de comidas, deve possuir o atributo `data-testid="video"`;
  * O card de receitas recomendadas deve possuir o atributo `data-testid="${index}-recomendation-card"`;
  * O botão de iniciar receita deve possuir o atributo `data-testid="start-recipe-btn"`;

  **Observações técnicas**

  * A tela de comida possui todos os atributos data-testid;
  * A tela de bebidas possui todos os atributos data-testid.

### 34 - Uma request para a API deve ser feita passando o `id` da receita que deve estar disponível nos parâmetros da URL

  **Observações técnicas**

  * Verifica se a requisição para a API de comidas foi realizada. O endpoint utilizado deve ser `https://www.themealdb.com/api/json/v1/1/lookup.php?i={id-da-receita}`;
  * Verifica se a requisição para a API de bebidas foi realizada. O endpoint utilizado deve ser `https://www.thecocktaildb.com/api/json/v1/1/lookup.php?i={id-da-receita}`.

### 35 - Essa tela deve conter uma imagem da receita, o título, a categoria (ou se é ou não alcoólico), uma lista de ingredientes seguidos pelas quantidades, instruções, um vídeo do youtube "embedado" e recomendações

A verificação será feita através das receitas retornadas pela API, como por exemplo, o texto dos ingredientes e das instruções.

  Lembre-se: O vídeo do youtube só deve estar disponível para receitas de comida, já que não é retornado pela [API de bebidas](https://www.thecocktaildb.com/api.php).

  **Observações técnicas**

  * Verifica se os elementos descritos no protótipo existem na tela de detalhes de comida;
  * Verifica se os elementos descritos no protótipo existem na tela de detalhes de bebida.

### 36 - As recomendações para receitas de comida deverão ser bebidas e vice-versa

  **Observações técnicas**

  * Verifica se a requisição para a API de bebidas foi realizada. O endpoint utilizado deve ser `https://www.thecocktaildb.com/api/json/v1/1/search.php?s=`;
  * Verifica se a requisição para a API de comidas foi realizada. O endpoint utilizado deve ser `https://www.themealdb.com/api/json/v1/1/search.php?s=`.

### 37 - Deverão ser mostrados 6 cards de recomendação, onde apenas 2 são mostrados e o scroll é horizontal, similar a um `carousel`

  **Observações técnicas**

  * Verifica se existem todas as recomendações na tela de detalhes de uma comida. Apenas as 6 primeiras bebidas devem ser exibidas;
  * Verifica se existem todas as recomendações na tela de detalhes de uma bebida. Apenas as 6 primeiras comidas devem ser exibidas.

### 38 - Um botão de nome "Iniciar Receita" deve ficar fixo na parte de baixo da tela o tempo todo

  **Observações técnicas**

  * Verifica posicionamento do botão na tela de detalhes de comida;
  * Verifica posicionamento do botão na tela de detalhes de bebida.

### 39 - Caso a receita já tenha sido feita, o botão "Iniciar Receita" deve sumir

  **Observações técnicas**

  * Verifica se botão de iniciar receita não é visível na tela de detalhes de uma comida;
  * Verifica se botão de iniciar receita não é visível na tela de detalhes de uma bebida.

### 40 - Caso a receita tenha sido iniciada mas não finalizada, o texto do botão deve ser "Continuar Receita"

  **ObservaçÕes técnicas**

  * Verifica botão de "Continuar Receita" na tela de detalhes de uma comida;
  * Verifica botão de "Continuar Receita" na tela de detalhes de uma bebida

### 41 - Quando o botão "Iniciar Receita" for clicado, a rota deve mudar para a tela de receita em processo

  **Observações técnicas**

  * Redireciona para tela de receita da comida em processo;
  * Redireciona para tela de receita da bebida em processo.

### 42 - Um botão de compartilhar e um de favoritar a receita devem estar disponíveis

  **Observações técnicas**

  * Verifica se os botões estão disponíveis na tela de detalhes de uma comida;
  * Verifica se os botões estão disponíveis na tela de detalhes de uma bebida.

### 43 - Ao clicar no botão de compartilhar, o link da receita dentro do app deve ser copiado para o clipboard e uma mensagem avisando que o link foi copiado deve aparecer

O ícone do botão de compartilhar pode ser encontrado em `src/images/shareIcon.svg`.

  **Observações técnicas**

  * Verifica a mensagem "Link copiado!" e se o link da receita da comida foi copiado para o clipboard;
  * Verifica a mensagem "Link copiado!" e se o link da receita da bebida foi copiado para o clipboard.

### 44 - O ícone do coração (favorito) deve vir preenchido caso a receita esteja favoritada e "despreenchido" caso contrário

Os ícones dos botões podem ser encontrados em `src/images/whiteHeartIcon.svg` e em `src/images/blackHeartIcon.svg`, respectivamente.

  **Observações técnicas**

  * Verifica se a comida favoritada vem com o coração preenchido;
  * Verifica se a comida não favoritada vem com o coração "despreenchido";
  * Verifica se a bebida favoritada vem com o coração preenchido;
  * Verifica se a bebida não favoritada vem com o coração "despreenchido".

### 45 - Ao clicar no botão de favoritar, o ícone do coração deve mudar de seu estado atual, caso esteja preenchido deve mudar para "despreenchido" e vice-versa

  **Observações técnicas**

  * Favorita a comida;
  * Desfavorita a comida;
  * Favorita a bebida;
  * Desfavorita a bebida.

### 46 - As receitas favoritas devem ser salvas em `localStorage` na chave `favoriteRecipes` 

  * O formato deve ser `[{ id, type, area, category, alcoholicOrNot, name, image }]`. 
  * As receitas feitas devem ser salvas em `localStorage` na chave `doneRecipes` no formato `[{ id, type, area, category, alcoholicOrNot, name, image, doneDate, tags }]`.

  **Observações técnicas**

  * Verifica se após favoritar receita de uma comida, ela é salva corretamente no localStorage;
  * Verifica se após favoritar receita de uma bebida, ela é salva corretamente no localStorage.

<!-- ### 47 - A cobertura de testes unitários deve ser de no mínimo 90% -->

## Tela de receita em progresso

### 47 - Essa tela deve conter uma imagem da receita, seu titulo, sua categoria (ou se a bebida é alcoólica ou não) uma lista de ingredientes com suas respectivas quantidade e suas instruções

Verifica se os atributos data-testid estão presentes na tela com suas respectivas quantidades:

  * A foto deve possuir o atributo `data-testid="recipe-photo"`;
  * O título deve possuir o atributo `data-testid="recipe-title"`;
  * O botão de compartilhar deve possuir o atributo `data-testid="share-btn"`;
  * O botão de favoritar deve possuir o atributo `data-testid="favorite-btn"`;
  * O texto da categoria deve possuir o atributo `data-testid="recipe-category"`;
  * Os ingredientes devem possuir o atributo `data-testid=${index}-ingredient-step`, a verificação será feita pelo length do atributo.
  * O elemento de instruções deve possuir o atributo `data-testid="instructions"`;
  * O botão para finalizar a receita deve possuir o atributo `data-testid="finish-recipe-btn"`.

  **Observações técnicas**

  * Verifica elementos de uma receita de comida;
  * Verifica elementos de uma receita de bebida.

### 48 - A lista de ingredientes deve conter um checkbox para cada um dos items

  **Observações técnicas**

  * Todos os ingredientes de uma receita de comida possuem um checkbox;
  * Todos os ingredientes de uma receita de bebida possuem um checkbox.

### 49 - Ao clicar no checkbox de um ingrediente, o nome dele deve ser "riscado" da lista

Ao clicar no checkbox, o item deve ser riscado, mostrando que esse passo foi finalizado

  **Observações técnicas**

  * Verifica se é possível marcar todos os passos da receita de comida;
  * Verifica se é possível marcar todos os passos da receita de bebida.

### 50 - O estado do progresso deve ser mantido caso a pessoa atualize a página ou volte para a mesma receita 

O progresso das receitas devem ser salvos em `localStorage` na chave` inProgressRecipes` no formato especificado na seção [`localStorage`](#localStorage);

  **Observações técnicas**

- Salva o progresso de uma receita de comida em andamento;
- Salva o progresso de uma receita de bebida em andamento;

### 51 - A mesma lógica de favoritar e compartilhar da tela de detalhes de uma receita se aplica aqui

  **Observações técnicas**

  * Verifica se os botões estão disponíveis na tela de detalhes de uma comida;
  * Verifica se os botões estão disponíveis na tela de detalhes de uma bebida;
  * Verifica a mensagem "Link copiado!" e se o link da receita da comida foi copiado para o clipboard;
  * Verifica a mensagem "Link copiado!" e se o link da receita da bebida foi copiado para o clipboard;
  * Verifica comida favoritada;
  * Verifica comida não favoritada;
  * Verifica bebida favoritada;
  * Verifica bebida não favoritada;
  * Favorita comida;
  * Desfavorita comida;
  * Favorita bebida;
  * Desfavorita bebida;
  * Favorita receita de uma comida;
  * Favorita receita de uma bebida.

### 52 - O botão de finalizar receita só pode estar habilitado quando todos os ingredientes estiverem _"checkados"_ (marcados)

  O botão deve ficar desabilitado em quanto todos os checkboxs não forem marcados.

  **Observações técnicas**

  * Verifica se botão para finalizar está desabilitado em receitas de comidas;
  * Verifica se botão para finalizar está desabilitado em receitas de bebidas;
  * Verifica se botão para finalizar está habilitado em receitas de comidas;
  * Verifica se botão para finalizar está habilitado em receitas de bebidas.

### 53 - Após clicar no botão "Finalizar receita", a rota deve mudar para a página de receitas feitas, cuja rota deve ser `/receitas-feitas`

  **Observações técnicas**

  * Redireciona após concluir uma receita de comida;
  * Redireciona após concluir uma receita de bebida.

## Tela de receitas feitas

### 54 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de receitas feitas

  **Observações técnicas**

  * Todos os data-testids estão presentes:
    * O botão de filtro `All` deve ter o atributo `data-testid="filter-by-all-btn"`;
    * O botão de filtro `Food` deve ter o atributo `data-testid="filter-by-food-btn"`;
    * O botão de `Drinks` deve ter o atributo `data-testid="filter-by-drink-btn"`;
    * O imagem do card de receita deve ter o atributo `data-testid="${index}-horizontal-image"`;
    * O texto da categoria da receita deve ter o atributo `data-testid="${index}-horizontal-top-text"`;
    * O texto do nome da receita deve ter o atributo `data-testid="${index}-horizontal-name"`;
    * O texto da data que a receita foi feita deve ter o atributo `data-testid="${index}-horizontal-done-date"`;
    * O elemento de compartilhar a receita deve ter o atributo `data-testid="${index}-horizontal-share-btn"`;
    * As `tags` da receita devem possuir o atributo `data-testid=${index}-${tagName}-horizontal-tag`;

### 55 - Caso a receita do card seja uma comida, ela deve possuir: a foto da receita, o nome, a categoria, a area, a data em que a pessoa fez a receita, as 2 primeiras tags retornadas pela API e um botão de compartilhar

O ícone do botão de compartilhar pode ser encontrado em `src/images/shareIcon.svg`.

  **ObservaçÕes técnicas**

  * O card possui os atributos corretos de uma comida

### 56 - Caso a receita do card seja uma bebida, ela deve possuir: a foto da receita, o nome, se é alcoólica, a data em que a pessoa fez a receita e um botão de compartilhar

O ícone do botão de compartilhar pode ser encontrado em `src/images/shareIcon.svg`.

  **Observações técnicas**

  * O card possui os atributos corretos de uma bebida.

### 57 - O botão de compartilhar deve copiar a URL da tela de detalhes da receita para o clipboard

  **ObservaçÕes técnicas**

  * Ao clicar no botão de compartilhar deve aparecer a mensagem "Link copiado!";
  * A URL da tela de detalhes da receita é copiada para o clipboard.

### 58 - Devem existir 2 botões que filtram as receitas por comida ou bebida e um terceiro que remove todos os filtros

Os nomes dos botões devem ser "Food", "Drinks" e "All", respectivamente.

  **Observações técnicas**

  * Ao clicar no botão "Food" as receitas devem ser filtradas por comidas;
  * Ao clicar no botão "Drinks" as receitas devem ser filtradas por bebidas;
  * Ao clicar no botão "All" o filtro deve ser removido.

### 59 - Ao clicar na foto ou no nome da receita, a rota deve mudar para a tela de detalhes daquela receita

  **Observações técnicas**

  * Ao clicar na foto da receita, a rota deve mudar para a tela de detalhes daquela receita;
  * Ao clicar no nome da receita, a rota deve mudar para a tela de detalhes daquela receita.

## Tela de receitas favoritas

### 60 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de receitas favoritas (cumulativo com os atributos em comum com a tela de receitas feitas)

### 61 - Caso a receita do card seja uma comida, ela deve possuir: a foto da receita, o nome, a categoria, um botão de compartilhar e um de "desfavoritar"

Os ícones dos botões podem ser encontrados em `src/images/shareIcon.svg` e em `src/images/blackHeartIcon.svg`, respectivamente.

  **Observações técnicas**

  * O card possui os atributos corretos de uma comida.

### 62 - Caso a receita do card seja uma bebida, ela deve possuir: a foto da receita, o nome, se é alcoólica ou não, um botão de compartilhar e um de "desfavoritar"

Os ícones dos botões podem ser encontrados em `src/images/shareIcon.svg` e em `src/images/blackHeartIcon.svg`, respectivamente.

  **Observações técnicas**

  * O card possui os atributos corretos de uma bebida.

### 63 - O botão de compartilhar deve copiar a URL da tela de detalhes da receita para o clipboard

  **Observações técnicas**

  * Ao clicar no botão de compartilhar deve aparecer a mensagem "Link copiado!";
  * A URL da tela de detalhes da receita é copiada para o clipboard.

### 64 - O botão de "desfavoritar" deve remover a receita da lista de receitas favoritas do `localStorage` e da tela

  **Observações técnicas**

  * Ao clicar no botão de "desfavoritar" a respectiva receita é removida da tela;
  * Ao clicar no botão de "desfavoritar" a respectiva receita é removida do `localStorage`.

### 65 - Devem existir 2 botões que filtram as receitas por comida ou bebida e um terceiro que remove todos os filtros

Os nomes dos botões devem ser "Food", "Drinks" e "All", respectivamente

  **ObservaçÕes técnicas**

 * Ao clicar no botão "Food" as receitas devem ser filtradas por comidas;
 * Ao clicar no botão "Drinks" as receitas devem ser filtradas por bebidas;
 * Ao clicar no botão "All" o filtro deve ser removido.

### 66 - Ao clicar na foto ou no nome da receita, a rota deve mudar para a tela de detalhes daquela receita

  **Observações técnicas**

 * Ao clicar na foto da receita, a rota deve mudar para a tela de detalhes daquela receita;
 * Ao clicar no nome da receita, a rota deve mudar para a tela de detalhes daquela receita.

## Tela de explorar

### 67 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de explorar

  **Observações técnicas**

  * Tem os data-testids explore-food e explore-drinks. 

### 68 - A tela deve ter dois botões: um para explorar comidas e o outro para explorar bebidas. O nomes dos botões devem ser "Explorar Comidas" e "Explorar Bebidas", respectivamente

Verifica se o atributo `data-testid="explore-drinks"` possui o texto "Explorar Comidas" e se o `data-testid="explore-drinks"` possui o texto "Explorar Bebidas".

  **Observações técnicas**

  * O nomes dos botões devem ser "Explorar Comidas" e "Explorar Bebidas".

### 69 - Ao clicar em um dos botões, a rota deve mudar para a página de explorar comidas ou de explorar bebidas

  **Observações técnicas**

  * Ao clicar no botão "Explorar Comidas" a rota muda para a página de explorar comidas;
  * Ao clicar no botão "Explorar Bebidas" a rota muda para a página de explorar bebidas.

## Tela de explorar bebidas ou comidas

### 70 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de explorar bebidas ou comidas

  **Observações técnicas**

  * Tem os data-testids corretos para a tela de explorar comidas;
  * Tem os data-testids corretos para a tela de explorar bebidas.

### 71 - A tela deve ter três botões: um para explorar por ingrediente, um para explorar por local de origem e um para pegar uma receita aleatória

O nomes dos botões devem ser "Por Ingredientes" com o atributo `data-testid="explore-by-ingredient"`, "Por Local de Origem" com o atributo `data-testid="explore-by-area"` e "Me Surpreenda!" com o atributo `data-testid="explore-surprise"`, respectivamente.
Obs: se a opção escolhida for explorar bebidas, o botão para explorar por local de origem não deve estar disponível.

  **Observações técnicas**

  * Tem os botões "Por Ingredientes", "Por Local de Origem" e "Me Surpreenda!" para a tela de explorar comidas;
  * Tem apenas os botões "Por Ingredientes" e "Me Surpreenda!" para a tela de explorar bebidas.

### 72 - Ao clicar em "Por Ingredientes", a rota deve mudar para tela de explorar ingredientes

  **Observações técnicas**

  * Ao clicar no botão "Por Ingredientes" da tela de explorar comidas a rota muda para a página de explorar comidas por ingrediente;
  * Ao clicar no botão "Explorar Bebidas" da tela de explorar bebidas a rota muda para a página de explorar bebidas por ingrediente.

### 73 - Ao clicar em "Por Local de Origem", a rota deve mudar para tela de explorar por local de origem

### 74 - Ao clicar em "Me Surpreenda!", a rota deve mudar para a tela de detalhes de uma receita, que deve ser escolhida de forma aleatória através da API

  **Observações técnicas**

  * Ao clicar no botão "Por Ingredientes" da tela de explorar comidas a rota muda para a página de detalhes de uma comida aleatória obtida através do endpoint `https://www.themealdb.com/api/json/v1/1/random.php`;
  * Ao clicar no botão "Explorar Bebidas" da tela de explorar bebidas a rota muda para a página de detalhes de uma bebida aleatória obtida através do endpoint `https://www.thecocktaildb.com/api/json/v1/1/random.php`.

## Tela de explorar ingredientes

### 75 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de explorar ingredientes

  A tela deve possuir os atributos `data-testid="${index}-ingredient-card"`, `data-testid="${index}-card-img"` e `data-testid="${index}-card-name"`, que estão relacionados ao card, imagem e nome do ingrediente respectivamente.

  **Observações técnicas**

  * Tem os data-testids corretos para a tela de explorar comidas por ingredientes;
  * Tem os data-testids corretos para a tela de explorar bebidas por ingredientes.

### 76 - A tela deve ter cards para os 12 primeiros ingredientes, de forma que cada card contêm: o nome do ingrediente e uma foto

  **Observações técnicas**

  * Tem o nome e a foto corretos para a tela de explorar comidas por ingredientes;
  * Tem o nome e a foto corretos para a tela de explorar bebidas por ingredientes.

### 77 -  Ao clicar no card do ingrediente a rota deve mudar para tela principal de receitas, mas mostrando apenas as receitas que contém o ingrediente escolhido

  **Observações técnicas**

  * Ao clicar no card do ingrediente da tela de explorar comidas por ingrediente a rota muda para a tela principal de receitas filtrada pelo ingrediente;
  * Ao clicar no card do ingrediente da tela de explorar bebidas por ingrediente a rota muda para a tela principal de receitas filtrada pelo ingrediente.

## Tela de explorar por local de origem/area

### 78 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de explorar por local de origem

  O elemento de dropdown deve possuir o atributo `data-testid="explore-by-area-dropdown"` e suas opções devem possuir o atributo `[data-testid="${area}-option"]`.

  **Observações técnicas**

  * A tela tem os data-testids de todos os 12 cards e de todos os locais de origem.

### 79 - A tela segue as mesmas especificações da tela de receitas principal, a única diferença é que os filtros de categoria são substituídos por um dropdown

  O elemento de dropdown deve possuir o atributo `data-testid="explore-by-area-dropdown"`.

  **Observações técnicas**

  * Devem ser carregadas as 12 primeiras receitas de comidas;
  * Ao selecionar um filtro de local de origem, todas as receitas devem mudar para os dados filtrados da API;
  * Ao clicar no card, a rota deve mudar para a tela de detalhes da receita com o ID da mesma na URL.

### 80 - No dropdown devem estar disponíveis todas as áreas retornadas da API, incluindo a opção "All", que retorna as receitas sem nenhum filtro

  **Observações técnicas**

  * No dropdown devem estar disponíveis todas as áreas retornadas da API, incluindo a opção "All";
  * A opção "All" retorna as receitas sem nenhum filtro.

### 81 - A rota deve ser apenas `/explorar/comidas/area`

A rota `/explorar/bebidas/area` não deve estar disponível, retornando um erro de "Not Found".

  **Observações técnicas**

  * Ao acessar a rota ela retorna um erro de "Not Found".

## Tela de perfil

### 82 - Todos os elementos devem respeitar os atributos descritos no protótipo para a tela de perfil

  **Observações técnicas**

  * Todos o data-testid do email e de todos os botões
    * O elemento de email deve possuir o atributo `data-testid="profile-email"`;
    * O botão com as "Receitas Feitas" deve possuir o atributo `data-testid="profile-done-btn"`;
    * O botão com as "Receitas Favoritas" deve possuir o atributo `data-testid="profile-favorite-btn"`;
    * O botão de sair deve possuir o atributo `data-testid="profile-logout-btn"`.

### 83 - O e-mail da pessoa usuária deve estar visível

### 84 - Essa tela deve conter 3 botões: um de nome "Receitas Feitas", um de nome "Receitas Favoritas" e um de nome "Sair"

  **Observações técnicas**

  * A tela contêm todos os 3 botões.

### 85 - Ao clicar no botão de "Receitas Favoritas", a rota deve mudar para a tela de receitas favoritas

  **Observações técnicas**

  * Redireciona para a rota correta.

### 86 - Ao clicar no botão de "Receitas Feitas", a rota deve mudar para a tela de receitas feitas

  **Observações técnicas**

  * Redireciona para a rota correta.

### 87 - Ao clicar no botão de "Sair", o `localStorage` deve ser limpo e a rota deve mudar para a tela de login

  **Observações técnicas**

  * Limpa todas as chaves da localStorage;
  * A rota muda para a tela de login.

---

***Obs: A maneira como as APIs devem ser estruturadas segue os seguintes modelos: https://www.themealdb.com/api.php e https://www.thecocktaildb.com/api.php***

### DURANTE O DESENVOLVIMENTO

* ⚠ **LEMBRE-SE DE CRIAR TODOS OS ARQUIVOS DENTRO DA PASTA COM O SEU NOME** ⚠


* Faça `commits` das alterações que você fizer no código regularmente

* Lembre-se de sempre após um (ou alguns) `commits` atualizar o repositório remoto

* Os comandos que você utilizará com mais frequência são:

1. `git status` _(para verificar o que está em vermelho - fora do stage - e o que está em verde - no stage)_

2. `git add` _(para adicionar arquivos ao stage do Git)_

3. `git commit` _(para criar um commit com os arquivos que estão no stage do Git)_

4. `git push -u nome-da-branch` _(para enviar o commit para o repositório remoto na primeira vez que fizer o `push` de uma nova branch)_

5. `git push` _(para enviar o commit para o repositório remoto após o passo anterior)_

---

### DEPOIS DE TERMINAR O DESENVOLVIMENTO (OPCIONAL)

Para sinalizar que o seu projeto está pronto para o _"Code Review"_ dos seus colegas, faça o seguinte:

* Vá até a página **DO SEU** _Pull Request_, adicione a label de _"code-review"_ e marque seus colegas:

  * No menu à direita, clique no _link_ **"Labels"** e escolha a _label_ **code-review**;

  * No menu à direita, clique no _link_ **"Assignees"** e escolha **o seu usuário**;

  * No menu à direita, clique no _link_ **"Reviewers"** e digite `students`, selecione o time `tryber/students-sd-0x`.

Caso tenha alguma dúvida, [aqui tem um video explicativo](https://vimeo.com/362189205).

---

### REVISANDO UM PULL REQUEST

Use o conteúdo sobre [Code Review](https://course.betrybe.com/real-life-engineer/code-review/) para te ajudar a revisar os _Pull Requests_.

#VQV 🚀


<!-- ======== -->

## Desenvolvimento e testes

Este repositório já contem um _template_ com um App React criado, configurado e com os testes da avaliação automatizada.

Esses [testes E2E](https://www.guru99.com/end-to-end-testing.html) automatizados podem ser utilizados para ajudar a validar as funcionalidades do projeto localmente. É possível executar esses testes via `npm run cy:open`. Esse comando abre a interface que permite rodar a suite de testes do [Cypress](https://www.cypress.io/how-it-works/) que valida o fluxo geral e os requisitos funcionais do projeto.

Esses testes não consideram o layout de maneira geral, mas sim os atributos e informações corretas, então preste atenção nos atributos definidos no protótipo.

Os testes te darão uma mensagem de erro caso não estejam passando (seja qual for o motivo). 😉

#### Além dos testes da avaliação automatizada, um dos requisitos do projeto se baseia em **escrever testes unitários que cubram pelo menos 90% do projeto**. Na [documentação do Jest CLI](https://jestjs.io/docs/en/cli) é possível ver como essa cobertura é coletada.


<!-- ==== -->
