# LoadMask jQuery plugin

[See in English.](README.md)

O comportamento desse plugin é bastante baseado no conveniente método  ```Element.mask()``` do [ExtJS Framework](https://sencha.com/products/extjs/) e esse fork em específico adaptado para trabalhar em conjunto com outro plugin, o [jQuery Mask Plugin](http://igorescobar.github.io/jQuery-Mask-Plugin/).

O LoadMask jQuery plugin pode colocar uma máscara em um elmento DOM enquanto o seu conteúdo está sendo carregado ou modificando evitando interações e informar que a tarefa em segundo plano ainda está rodando. É bem leve (~2Kb) e fácil de usar.

[~~Você pode ver uma demonstração online aqui.~~](http://jquery-loadmask.googlecode.com/svn/trunk/demo/index.html)

#### Uso
> **Versão do jQuery necessária:** 1.2.3 ou superior.

_Observe que somente os elementos que aceitam nós filhos podem receber a mascara._

Para começar a usar o plugin você precisa incluir os arquivos ```jquery.loadmask.css``` e ```jquery.loadmask.js``` (ou sua versão minificada ```jquery.loadmask.min.js```) na sua página html:
```html
<link href="jquery.loadmask.css" rel="stylesheet" type="text/css" />
<script type="text/javascript" src="jquery.loadmask.min.js"></script>
```

#### Colocando a Máscara
Para colocar uma máscara sobre um elemento (ou vários elementos) simplesmente chame o método ```loadmask(label, delay)``` com dois parâmetros ```label``` e ```delay``` opcionais:

```javascript
$("#mydiv").loadmask("Carregando...");
$(".grids").loadmask("Carregando...", 500);
```

Se o parâmetro ```label``` for informado, uma caixinha com esse label e um ícone girando ao lado será mostrada, caso contrário será somente uma máscara cinza transparente.

O parâmetro ```delay``` configura um atraso em milisegundos antes que o(s) elemento(s) tenha a máscara. Se o método ```unloadmask()``` for chamado antes do tempo de atraso estabelecido, nenhuma máscara será mostrada. Isso pode ser utilizado para processos rápidos em que exibir uma máscara não é necessário.

#### Retirando a Mascara
Para remover uma máscara anteriormente colocada em um elmento (ou vários elementos) chame ```unloadmask()``` sem nenhum parâmetro:

```javascript
$("#mydiv").unloadmask();
```

Chamando ```unloadmask()``` em uma máscara com atraso evita que ela seja mostrada.

#### Verificando se um elemento já está com a máscara
Você pode usar o método ```isMasked()``` em um elemento para verificar se ele já está com a máscara. Observe que o método irá retornar ```false``` enquanto a máscara estiver esperando o tempo de atraso.

```javascript
if($("#mydiv").isMasked()) { ... }
```

#### Integração com jQuery UI
Veja esse [código](https://code.google.com/p/jquery-loadmask/issues/detail?id=4&can=1)

#### Contribuições do projeto original
* `wpaap` - provided snapshot for integration with ASP.net UpdatePanel
* `Artur` - Alexandre Moreira (artur.alexandre@gmail.com) - implemented delayed mask
* `theonlylawislove` - provided Jquery UI integration solution

Obrigado!
