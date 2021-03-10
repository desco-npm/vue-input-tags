<div align="right">
  <a href="README.US.md">
    <img alt="Read in American English" src="https://img.shields.io/static/v1?label=&message=🇺🇸 Read in American English&color=red&style=for-the-badge" />
  </a>
</div>

<table>
  <tr>
    <td><img src="https://i.ibb.co/q987VGF/Design-sem-nome-3.png"></td>
    <td>  
      <h1>@desco/vue-input-tags</h1>
      Componente VueJS para entrada de Tags.
      <br /><br />
      <div align="center">
        <img alt="Licença MIT" src="https://img.shields.io/static/v1?label=Licença&message=MIT&color=green&style=for-the-badge">
        <img alt="Versão 1.0.3" src="https://img.shields.io/static/v1?label=Versão&message=1.0.3&color=blue&style=for-the-badge">
      </div>
      <h4 align="center"> 
        🚀 Pronto para uso 🚀
      </h4>
    </td>
  </tr>
</table>

> <a href="https://github.com/desco-npm" target="_blank">Veja outros projetos NPM aqui.</a>

> <a href="https://github.com/descoifica" target="_blank">Veja outros projetos aqui.</a>

---

## 📋 Tabela de conteúdos

* [🛠️ Tecnologias](#Tecnologias)
* [⚙️ Instalação](#Instalação)
* [📦 Importação](#Importação)
* [📚 Como Usar](#Como-Usar)

---

## 🛠️ Tecnologias

As seguintes tecnologias são utilizadas:

* [VueJs](https://vuejs.org/)
* [PUG/JADE](https://pugjs.org)
* [SCSS/SASS](https://sass-lang.com)
* [Element](https://element.eleme.io)

---

<a name="Instalação"></a>

## ⚙️ Instalação

```bash
npm install --save @desco/vue-input-tags
```

> Note que será necessário ter o **NPM** instalado para o comando funcionar.

---

<a name="Importação"></a>

## 📦 Importação

```js
import vueInputTags from '@desco/vue-input-tags'
```

---

<a name="Como-Usar"></a>

## 📚 Como Usar

## 📚 How to use

```html
<template>
  <vueInputTags
    :value="tags"
    new-tag-txt="+ Tag"
    separator-character=";"
    :max="10"
    :add-on-blur="false"
    :allow-repeat="false"
    :transitions="false"
  />
</template>
```

```js
<script>
  export default {
    components: { vueInputTags, },
    data () {
      return {
        tags: '',
      }
    }
</script>
```

### Parâmetros

| Nome | Tipo | Obrigatório | Padrão | Descrição |
|---|---|---|---|---|
| value | String | Sim | - | String que contém/conterá as tags |
| new-tag-txt | String | Não | + Tag | Texto a ser exibido para adicionar nova tag |
| separator-character | String | Não | ; | Caracter que será usado para separar as tags dentro da string|
| max | Number | Sim | - | Limite de tags permitidas |
add-on-blur | Boolean | Não | true | Se deve adicionar a tag digitada ao tirar o foco do campo |
alow-repeat | Boolean | Não | false | Se permite repetir tags |
transitions | Boolean | Não | true | Se deve ter animações |

---

## Autor

<table>
  <tr>
    <td width="150px">
      <img src="https://scontent.fsdu1-1.fna.fbcdn.net/v/t1.0-9/539886_235546170253505_5977326689811409130_n.jpg?_nc_cat=106&ccb=3&_nc_sid=174925&_nc_eui2=AeGgFWn_fWInwRkTo3mHSP993TbQ0TzG0Y3dNtDRPMbRjS-eZL1tr4I5maqz6O-jva9qWnIxKOsD3UtSm9CTeCys&_nc_ohc=Qw6NaDGrtIgAX9uFF2c&_nc_ht=scontent.fsdu1-1.fna&oh=5ebac9874d7a24e157c8c99fd965c2a4&oe=606539CE" width="100px;" alt=""/>
      <b>Rafael A. R. Dias</b>
    </td>
    <td>  
      <a href="mailto:eu@diasrafael.com.br" target="_blank" >
        <img alt="Email eu@diasrafael.com.br" src="https://img.shields.io/static/v1?label=Email&message=eu@diasrafael.com.br&color=red&logo=gmail&style=for-the-badge">
      </a>
      <a href="https://www.linkedin.com/in/diasrafael/" target="_blank">
        <img alt="Linkedin @diasrafael" src="https://img.shields.io/static/v1?label=Linkedin&message=@diasrafael&color=blue&logo=linkedin&style=for-the-badge">
      </a>
      <a href="https://www.facebook.com/eudiasrafael" target="_blank">
        <img alt="Facebook @eudiasrafael" src="https://img.shields.io/static/v1?label=Facebook&message=@eudiasrafael&color=blue&logo=facebook&style=for-the-badge">
      </a>
      <a href="https://github.com/descodifica" target="_blank">
        <img alt="GitHub Geral @descodifica" src="https://img.shields.io/static/v1?label=GitHub Geral&message=@descodifica&color=black&logo=github&style=for-the-badge">
      </a>
      <a href="https://github.com/desco-npm" target="_blank">
        <img alt="GitHub NPM @desco-npm" src="https://img.shields.io/static/v1?label=GitHub NPM&message=@desco-npm&color=black&logo=github&style=for-the-badge">
      </a>
      <a href="https://www.npmjs.com/org/desco" target="_blank">
        <img alt="NPM @desco" src="https://img.shields.io/static/v1?label=NPM&message=@desco&color=red&logo=npm&style=for-the-badge">
      </a>
    </td>
  </tr>
</table>