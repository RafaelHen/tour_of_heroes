### **Estrutura de um código angular:**

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/954e919b-5e14-4f41-8e0f-1ea48e8fcde3)

# Passagem de parametro do TS para HTML

Dentro do arquivo AppComponent.ts do componente principal da minha aplicação , tem uma propriedade String chamada title com o seguinte valor:

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/e5c1f7f8-d6b5-4e90-b58a-a40c47c4503d)

Para passar esta propriedade para o **app.component.html** , usa-se {}. As chaves duplas são a sintaxe *de ligação de interpolação* do Angular . Esta ligação de interpolação mostra o valor da propriedade “Title” do componente dentro da tag de cabeçalho HTML.

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/609c6e0e-ac5d-4be5-88bc-06ff2817cf31)

A imagem acima representa o HTML do componente ***principal*** da minha aplicação, dentro dele está sendo chamado um outro componente chamado de <app-heroes> através da sua propriedade de metadado **Selector** 

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/76c687a8-4ce7-4b35-92bb-38db5c3f75d1)


# Criando ediçao de heroi atráves do ngModel

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/59ef57b6-cda4-4d20-b8cd-8f524f9942d7)

`[([ngModel](https://angular.io/api/forms/NgModel))]`é a sintaxe de ligação de dados bidirecional do Angular.

Aqui ele vincula a `hero.name`propriedade à caixa de texto HTML para que os dados possam fluir *em ambas as direções* . Os dados podem fluir da `hero.name`propriedade para a caixa de texto e da caixa de texto de volta para o arquivo `hero.name`.

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/7583b615-2ad8-4da7-974b-9c74d935ae6b)

O ngModel é importado na classe **`AppModule,** é nessa classe que são importados os`**me*tadados***

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/71593019-5231-4bad-9934-0eea336fa979)

# Criando Mocks e Listando com nfFor*

Use a `[NgFor](https://angular.io/api/common/NgFor)`diretiva para apresentar uma lista de itens.

1. Defina um bloco de HTML que determine como o Angular renderiza um único item.
2. Para listar seus itens, atribua a abreviatura `let hero of heroes`

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/e1c30e6c-9c69-4373-b7b7-9268d4b7a400)

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/5ec23188-196a-45b9-93a8-49173deefc2e)

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/f50dd00b-2437-4858-a3c0-056792066e3e)

# Fazendo vinculações de eventos - **Event binding**

Para vincular a um evento, você usa a sintaxe de ligação de evento Angular. Essa sintaxe consiste em um nome de evento de destino entre parênteses à esquerda de um sinal de igual e uma instrução de modelo entre aspas à direita.

No html

## No Html

Exemplo: 

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/db624d94-0f97-444b-a8e6-9adcc7054753)

## No Ts

Exemplo:

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/8d287f89-2a3b-4e14-9bbb-24ddb3e1925e)

## Removendo componentes através de eventos CSS

Para criar uma associação de classe única, digite o seguinte:

`[class.sale]="onSale"`

Angular adiciona a classe quando a expressão vinculada `onSale`é verdadeira e remove a classe quando a expressão é falsa - com exceção de `undefined`. Consulte [delegação de estilo](https://angular.io/guide/style-precedence#styling-delegation) para obter mais informações.

Exemplo:

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/5794ead7-6207-4849-8fc5-160ee2d768f3)

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/d23324b2-1ca7-427f-855c-baedca024374)

Quando o herói da linha atual é igual ao `selectedHero`, Angular adiciona a classe CSS `selected`. Quando os dois heróis são diferentes, Angular remove a classe.

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/d347e71f-549b-4e0e-990b-12eb37dd2408)

# **Compartilhando dados entre diretivas e componentes filho e pai link**

https://angular.io/guide/inputs-outputs

Um padrão comum em Angular é o compartilhamento de dados entre um componente pai e um ou mais componentes filhos. Implemente esse padrão com os decoradores e .`@[Input](https://angular.io/api/core/Input)() @[Output](https://angular.io/api/core/Output)()`

Primeiramente foi criado um novo componente para ser a classe filho da **heroes.component,** foi criado o **heroes-datail.**

Primeiramente foi feito para o *ngIf receber uma propriedade chamada **hero** do tipo **Hero**

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/99219246-576b-4c80-8f3a-506826e98bc5)

No arquivo do TS, foi importado os seguintes metadados `import { [Component](https://angular.io/api/core/Component), [Input](https://angular.io/api/core/Input) } from '@angular/core';` 

Logo abaixo mostra que a declaração da propriedade hero logo após o decorator **@Input** que pode ser do tipo Hero ou Undefined.

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/22bb71e7-e185-4bf7-95a2-814a2101a2b0)

Dentro da heroes.component que é a nossa classe PAI, iremos declara a classe filha, a hero-detail. Nela está sendo feito a troca de dados entre a classe pai e filha, onde [hero] é a propriedade que declaramos após o **@Input** que irá receber os dados da classe pai através da propriedade **SelectedHero** 

<app-hero-detail *[propriedade-classe-filha]*="propriedade-classe-pai"></app-hero-detail>

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/e8770019-54d2-4e84-9a66-227e4589c1a2)

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/f504201a-b3ac-4c48-85ca-0b5acbf80c43)

# Criando um serviço para o compartilhamento de dados

O @Injectable() marca a classe como aquela que participará do *sistema de injeção de dependência.*

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/ce618607-9138-4c94-a190-bf880fc2d20e)

**`@Injectable()`** é usado principalmente para informar ao Angular que a classe pode ser injetada em outros componentes, serviços ou módulos, e o Angular se encarregará de gerenciar a criação da instância quando necessário.

usar o metadado **`providedIn: 'root'`** em um serviço no Angular, você estará configurando o Angular para criar uma única instância desse serviço em todo o aplicativo, garantindo assim que ele seja instanciado antes de qualquer componente, pois você está Injetando a classe de serviço na raiz do projeto.

Quando você usa **`providedIn: 'root'`**, o Angular cria uma instância do serviço quando o aplicativo é inicializado e a mantém em cache para uso posterior. Isso significa que a instância do serviço estará disponível assim que o aplicativo começar a ser executado, garantindo que outros componentes ou serviços que dependem dele possam acessá-lo imediatamente.

Um provedor é algo que pode criar ou entregar um serviço. Ele basicamente instancia uma classe no sistema para prestar serviço. O provider vem como metadadado do decorador @[Injectable](https://angular.io/api/core/Injectable)() 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/fef1f6ad-85fc-41f6-892e-a9dbc9ce4697/70c0eaf3-1fb1-4843-b62a-b30069918230/Untitled.png)

### **Ganchos de ciclo de vida - *[lifecycle hook](https://angular.io/guide/lifecycle-hooks) ngOnInit***

O **`ngOnInit`** no Angular é um método usado para realizar inicializações e configurações quando um componente é instanciado. É chamado automaticamente após a criação do componente e antes da exibição do mesmo. É comumente usado para buscar dados, configurar variáveis e realizar outras tarefas de inicialização.

Os ganchos oferecem a oportunidade de agir em uma instância de componente ou diretiva no momento apropriado, à medida que o Angular cria, atualiza ou destrói essa instância.

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/9c46698b-0e08-4e67-b152-7071ed5f9bf5)

 O ciclo de vida do componente `ngOnInit`chama o método do `HeroService`, e não o construtor.

# **`HeroService` - usando eventos assincronos com RxJS**

No meu exemplo acima estou trabalhando com o getHeroes de maneira sincrona, mas caso o`getHeroes()`não conseguisse retornar imediatamente com os dados principais, não poderia ser síncrono, pois isso bloquearia o navegador enquanto ele espera para retornar os dados.

O RxJS (Reactive Extensions for JavaScript) é uma biblioteca para programação reativa em JavaScript. Ela é usada para lidar com fluxos de dados assíncronos e eventos de uma maneira mais fácil e compreensível. O RxJS é usado para simplificar o tratamento de fluxos de dados assíncronos, tornando o código mais eficiente, conciso e legível em aplicações JavaScript, especialmente em cenários complexos que envolvem eventos, solicitações de rede e operações assíncronas.

# Observable - **RxJS**

RxJS introduz o conceito de "observables", que são sequências de eventos ou valores que podem ser observados. Isso facilita a captura e manipulação de fluxos de dados assíncronos.

Primeiramente iremos importar o `Observable, of` da biblioteca `rxjs` dentro do nosso hero.service

`import { Observable, of } from 'rxjs';`

Logo após iremos reformular nosso metodo getHeroes()

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/3808bbe5-2990-4d16-8ccb-cb1d4f64fb31)


`of(HEROES)`retorna um `Observable<Hero[]>`que emite *um único valor* , a matriz de heróis.

Agora iremos ter que alterar o metodo getHeroes() dentro da HeroesComponent

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/c0684c5b-feb9-41e8-9112-48b418b23ac0)

O `Observable` aguarda a emissão do conjunto de heróis, o que pode acontecer agora ou daqui a alguns minutos. O `subscribe()` permite que você registre funções de callback para lidar com os dados que fluem pelo observable, acima estamos passando o array de heroes e iremos aguardar o retorno do callback da chamada, o retorno do callback irá para a propriedade `heroes` do componente.

# **Adicionando navegação com roteamento**

ng generate module app-routing --flat --module=app

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/643e59f5-a719-4957-b211-f8fc051634d8)

O tipo Route tem duas propriedades:

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/7e59d427-19df-489e-802f-4d02008da7af)

Isso informa ao roteador para corresponder a esse URL `path: 'heroes'`e exibir `HeroesComponent`quando o URL for algo como `localhost:4200/heroes`.

**`@NgModule`** é um decorador em Angular que é usado para definir e configurar módulos na sua aplicação. Um módulo é uma coleção de componentes, diretivas, serviços e outros recursos que são agrupados logicamente para fornecer funcionalidade específica em uma aplicação Angular.

A linha a seguir adiciona o RouterModule à matriz de imports de AppRoutingModule e o configura as rotas em um único passo, chamando RouterModule.forRoot():

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/017d4957-9c38-40ab-87ea-71c8b0534102)

O método é chamado de forRoot() porque você configura o roteador no nível raiz da aplicação. O método forRoot() fornece os provedores de serviços e diretivas necessários para o roteamento e realiza a navegação inicial com base na URL atual do navegador.

Em seguida, AppRoutingModule exporta o RouterModule para que ele esteja disponível em toda a aplicação.

![image](https://github.com/RafaelHen/tour_of_heroes/assets/48704686/0eb422c6-7f8d-4796-8872-59e6bd006c2d)
