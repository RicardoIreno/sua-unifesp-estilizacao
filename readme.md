# Projeto de identidade visual do SUA Unifesp (Wiki.js)

<p align="center">
  <img src="__readme_src/banner.svg" />
</p>



![](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![](https://img.shields.io/badge/Sass-CC6699?style=for-the-badge&logo=sass&logoColor=white)




Visite a SUA Unifesp: <https://sua.unifesp.br>  


A Serviços Unificados Acessíveis — SUA Unifesp, é uma wiki implementada em [Wiki.js](https://js.wiki) que reúne informaçõe sobre todos os serviços oferecidos à Unifesp para usuários internos e externos.

Meu papel neste projeto foi desenvolver um logo e uma identidade visual para a feramenta. A extratégia escolhida para a plicar a esilização, dado o curto prazo, foi por injeção de código.


## Injeção de código


**Injeções globais:**
A Sobreposição feita na sessão temas no modo administração.


- `body-injection.css`: Altera as cores do menu lateral e do header. Também altero a cor do título "comentários" porque o cabeçalho deste está atrelado ao mesmo esquema de cores que o menu.

- `css-injection.css`: CSS contendo as classes de estilos adicionais


**Injeções locais:**
Colocada em cada página pela janela `Propriedades da página`:

- `css-logo-effect`: CSS que estiliza o efeito no logo. 

- `randomize-script`: Script que randomiza o logo a cada *refresh*.

### Usando as classes do CSS injetado

**classes criadas:**

Utilizáveis para customização do conteúdo:
- `.cardWrapper`  — transforma os links do container em cards;
- `.carc-[cores]` — confere cores aos links em `.cardWrapper`
- `.logoWrapper`  — container para o logo


Específicas para a página inicial: 
- `.card`         — cards da página inicial
- `.cardSize-gb`  — define o tamanho de `.card` para _grande_
- `.cardSize-md`  — define o tamanho de `.card` para _médio_


#### `.cardWrapper` para a criação de Cards

`.cardWrapper` transforma os links do container em cards. Use ela em um container:

```html
<section class="cardWrapper"> 

[<i class="fa fa-edit"></i> Ofice 360º](/pt-br/sti/office365) {.cardc-green}
  
[<i class="fa fa-at"></i> Intranet](/pt-br/sti/intranet) {.cardc-green}

</section>

```

**Importante sobre `.cardWrapper`:**

- afeta todas as tags `<a>` e `<i>` que estiverem no container
- Os links precisam ter um espaço de uma linha em branco entre eles.


**Cores disponíveis da classe `.cardc-<cor>`**

  red, pink, purple, indigo, blue, cyan, teal, green, lime, yellow, amber, orange, brown, grey, white.


- afeta todas as tags `<a>` e `<i>` que estiverem no container



## Gerando classes de cores com SASS


```css
$palette: (
  red:          #f44336,
  pink:         #e91e63,
  purple:       #9c27b0,
  indigo:       #3f51b5,
  blue:         #2196f3,
  cyan:         #00bcd4,
  teal:         #009688,
  green:        #4caf50,
  lime:         #cddc39,
  amber:        #ffc107,
  orange:       #ff9800,
  brown:        #795548,
  grey:         #9e9e9e,
  white:        #fff,
  mono:         #48495C
);

@each $k, $color in $palette {
  .cardc-#{$k} {

    a {
      color: $color !important;
      background-color: lighten($color, 30%);
    }
    
    i {  
      color: lighten($color, 35%) !important;
      background-color: lighten($color, 20%);
    }
    
  }
}
```


Visite a SUA Unifesp: <https://sua.unifesp.br>  

*Obrigado!*

[Ricardo Ireno](https://github.com/RicardoIreno/)