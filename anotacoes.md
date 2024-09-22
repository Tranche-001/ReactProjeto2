# CSS in JS
- styled components
- escrever o css da nossa aplicação no estiloo do javascript
- declarações de tipagem fica em outra pacote

- O que o styled components resolve?
- estilização em javascript

# Template literals
- ` `


# ThemeProvider
- Não vai ser uma div
- recebe uma propriedade chamada theme

# d.ts
- só vou ter códigos de tipo do javascript

# podemos definir estilos globais


# ES Linnt
- linting é validar que seu código está seguindo padrões estipulados pelos criadores do projeto
- pessoas codam de maneiras diferentes
- Condigura ES Lint para determinar o padrão da equipe. E não se preoucupa de esquecer isso

- npx eslint .

-@Standard8 --ext doesn't work with flat config at all. You should specify the file patterns you want in your eslint.config.js file.
So if you did --ext .jsx before, you'd need to have a config that looks like this:

export default [
  { files: ["**/*.jsx"] }
];

Then when you run something like npx eslint ., it will find the .jsx files.

I'll update the docs.


# Lidando com Várias rotas baseado no endereço que o usuário está acessando

# ThemePRovider BrowserRouter
- São necessários e precisam ficar por fora
- Context Providers
  - Não tem efeito nenhum visual
  - Mas fornecem contexto para os componentes dentro deles

  # Layout de Rotas
  - Coisas que se repetem visualmente independente da rota que a gente olha
  - Se copiarmos tudo isso vai ser recriado do 0
  - Criar algo que pode ser reaproveitado entre as telas é melhor assim

  # Melhor estrutura de pastas para o seu time

  # Outlet
  - um espaço para ser inserido um conteúdo

  # Texto alternativo pode ser deixado em branco
  - melhor do que escrever algo no qual não consegue descrever


  # Toda página podemos começar com uma Div, depois podemos selecionar uma tag melhor para preencher


  # A questão Table e o Mobile
  - Nâo há como fazer scroll em table no mboile
  - Por isso é interessante que coloque uma div em volta para poder permitir um scroll


  # Quando estamos usando STYLED COMPONENETS
  - Toda que a gente vai criar um componente novo porque é visualmente diferente
  - Podemos só criar um novo styled component que satisfaz nossa necessidade

  # Criar bons formulários no react
  - Validação(Alguma forma de validação em cima dos campos. Não faça submit sem preencher ou preenche com valores errados)
  - Botão só perde o valor de disabled se os campos foram preenchidos
  - 

  # Dois modelos de trabalho

  - Controlled

- Manter em tempo real o estado da variavel
- Toda vez que o usuario mudar o valor do input
- Eu atualizo o valor do estado
- Mantém em tempo real a informação do input do usuario guardada no estado da nossa aplicação
- Monitorar a cada digitação e salvar o no estado essa informação
- Quais beneficios? Como tenho valor em tempo real
- Facil acesso
- Refletir visualmente as alterações da minha interface
- Possiveis problemas de performance


- Uncontrolled
  - buscamos o valor do input sempre que precisarmos dela
  - Perde fluidez
  - Ganha em performance
-   Mais inputs tende a ir uncontrolled
- React hook form
- tandto controlled e uncontrolled, melhor dos dois mundos
performance
e fluidez


- Função register fala quais os campos eu vou ter no meu formulário


# React Hook Form
- utiliza outras bibliotecas feitas para validação
- yup
- joy
- zod(traz mais intelisense)

@hookform/resolvers


# Schema based
- Validar os nossos dados segundo determinado formato


# Criar uma tipagem a partir de outra referencia
- type(ao invés de interface)

# Typescript não entende váriaveis javascript
- Sempre converter em um tipagem
- type of


# vai fazendo um componente e depois vai separando ele em mais arquivos

# Toda vez que eu to alterando um estado e ele depende do valor anterior é legal que ele seja setado como função


# Hooks
-prefixo use
-Adicionar algum funcionamento há algum componente da nossa aplicação
-useState
-sempre que a variavel é alterada é renderizado novamente o componente


# Fique atento a quantidade de renderizações que seu app passa
- sempre que usamos uma variavel interna
precisamos incluir ela no use effect

- oq implica é
sempre que a variavel mudar
o useEffect vai ser executado dn


# NO REACT A GENTE NUNCA PODE ALTERAR UMA INFORMAÇÃO sem seguir os principios da imutabilidade

- arrays de objetos
- na hora de muda a informação de um objeto
- preciso percorrer todos os items do array 
- para poder fazer a alteração
- Map percorre cada um dos ciclos e vai retornar de dentro do map cada um dos ciclos 
alterados ou não


# O que é um componente
- quando algo é muito repetido
- há partes que podem funcionar sozinhas sem depender do restante

# Prop Drilling
- problema comum no react
- quando a gete tem Muitas propriedades apenas para comunicação entre componentes
- quando há muitas propriedades sendo repassadas. só para ficar fazendo a comunicação entre componentes
- pode ser bem trabalhoso e prejudicar nossa compreensão

- Propriedades é a principal forma de comunicação entre componentes

- muitas propriedades são um pé no saco para lidar

- Context API -> Permite compartilharmos informações entre Vários componentes ao mesmo tempo

Todos os componentes podem ter acesso
Todos os componentes podem modificar essas informações
E quando foram modificadas
todos wue dependiam vão ser atualizados

Podemos colocar o que quisermos dentro da context api

Sempre que temos variaveis que vão ser alteradas usamos estado


Porque na home criamos o estado?
Porque a home é a componente pai que precisam dessa informação

Sempre que querem que as informaçõessejam acessíveis por contexto
a informação precisa estar no componente mais fora possívea


Theme Provider é um provedor de contexto
  por isso que as aplicações tem acesso a questões de tema
Browser ROuter também é um


# Pior problema do contexto vazio



# Geralmente tenta se manter no contexto somente coisas que não vão mudar se a gente trocar uma biblioteca ou coisa assim


# React Hook Form oferece um contexto próprio que pode utilizatr
# Form Provider
  - Spread
  - {...newCycleForm}
  - esse Spread
    - Pega cada uma das propriedades desse objeto e passa como propriedade desse componente aq


    # Só tem as váriaveis e funções that the code itself uses. Nothing out of context


    # A forma principal de componentes se comunicarem entre React é através de propriedades
    # Usamos contexto quando temos muitas propriedades para enviar de um componente para outro


    # Camadas
    Imagine que
    em agum momento eu posso criar na minha aplicação
    algum ciclo
    sem ser pelo formulário
    ou eu remova totalmente react hook form e o zod
    e eu não quero que isso interfira no meu contexto
    o contexto tem que ser desacoplado das bibliotecas externas