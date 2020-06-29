# Vue

# Vue

  

## basics

  

### vue cli

  

### starting to serve:

  

first run npm install, then npm run serve

  

npm run serve

  

vue-cli-service serve

  

## commands

  

iterate from a list, repeats html content

bind to unique key for faster rendering

  

## LIST

  

v-if, v-show,

:key, v-for

  

### list  v-for

  

``` javascript

<ul class="list is-hoverable">

<li v-for="hero in heroes" :key="hero.id"

>

<a class="list-item" @click ="selectedHero = hero"

:class="{'is-active': selectedHero === hero}">

<span>{{hero.firstName}}</span>

</a>

</li>

</ul>`

```

### @click

you can attach a function

  

@click ="selectedHero = hero"

  

### :class="{'foo' :  true}"

puoi aggiungere classi che verranno attivate se il bool è true.

  

:class="{'is-active': selectedHero === hero}">

  

### v-if

display content based on an expression

content is added or removed from DOM

set the v-if directive to an expression that evaluates to truthy or falsey

  

  

<div v-if='selectedHero">

You Selected {{selectedHero.firstName}}

</div>

  

if it's falsey, it won't be added in the html!!

falsey = like false empty string and undefined

  

### show and hide content

it's not removed from the html

  

### v-show = "expression"

  

not ideal when inside there are things that have to be evaluated. like something that is also called inside.

  

better use an exterior flag

  

-declare that in the data

  

```javascript

<div class="field">

<label for="show" class="checkbox">

Show more

<input type="checkbox" class="is-primary" id="show" v-model="showMore">

</label>

</div>

```

prepare a div that will be shown if above is true

  

<div class="field"  v-show="showMore">

<label class="label" for="description">description</label>

<input

class="input"

id="description"

v-model="selectedHero.description"

/>

</div>

  

  

## V-model recap

  

  

## Interacting with a component

  

### Defining Data Models

#### The data function:

the Vue instance adds all properties in data to Vue's reactivity system.

  

when a value changes the component reacts and updates itself to match the new values.

Se usi visual code, puoi usare vdata as a snippet!

  

  

//component's data model

data() {

//function as best practice

return {

heroes:[],

selectedHero:undefined,

message:'',

};

},

  

  

### computed properties

fires when any dependency value changes

cached based on its reactive dependencies.

only re-evaluates when any of its reactive dependencies have changed

  

computed: {

fullName(){

return `${this.hero.firstName}${this.hero.lastName}`;

},

},

  

Another way is using get/set

  

use get to compute the value, and get to modify computed dependencies.

  

### Using component Lifecycle Hooks

  

these are methods();

that are similar to data();

  

you can link here methods and specify when you want them to be fired

  

**beforemounted, created** create (dom not available) best way to connect to api

templated not yet mounted.

  

created(){get...}

  

**mounted** to interact with third part components: jquery

  

**updated** data changed

  

**destroy** dom removed

  

  

### Watchers

  

to watch some properties change

react to data changes,

named same as reactive value

accepts new and old values

ideal for asynchronous operations

  

    watch: {
    
    //react when model changes
    
    hero(){},
    
    // react when objects.properties changes
    
    "selectedHero.capeCounter":{
    
    // launch immediately when true
    
    immediate:true,
    
    // for nested properties
    
    deep:true,
    
    handler(newValue,oldValue){execture logic}
    
    }
    
    }

  


### Filters

  

Local filters are defined in a component

| indica che arriva un filtro.

**{{firstName | capitalize}}**