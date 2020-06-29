
# Pseudo Selectors

## Basic nesting

notice the space! to show parent child relationship

    .parent .child  {}
    
    .parent {  .child {}  }
    
    .parent {  
    	& .child {} 
     }


## both classes applied to same element
Without space to indicate classes of the same element

    .some-class.another-class  {  }
    
    .some-class { 
     &.another-class {} 
      }

##  Using the  `&`  with pseudo classes

Without space to indicate classes of the same element

    .button { 
         &:visited {  } 
         &:hover {  }
         &:active {  }
      }

## Adjacent sibling

    .button {
      > span {  }
      + span {  }
      ~ span {  }  
      }

###  The adjacent sibling 
The adjacent sibling combinator in CSS isn't a selector on its own, but a way of combining two selectors.

    img + p  { font-style:italic;  }

The plus sign (+) is the adjacent sibling combinator, between two paragraph tag (element) selectors. What this means is "select any paragraph tag that is directly after an image tag (with nothing in between)".

This is used for example to style image captions within a text

###  The child combinator 

    ol > li  {  color: red;  }

It means "select elements that are **direct descendants** only". In this case: "select list items that are direct descendants of an ordered list"

for example, if there is an `<ul>` nested with other `li` they won't be affected, because they aren't direct children of `ol`. 
the normal `ol li` selector would take any li that is inside an ol.

### The general sibling

    .featured-image ~ p  {  font-size:  90%;  }

 you would be selecting **all** paragraphs in an article that come after the featured image. Both selectors have to be the children of the same parent!


## Selector for the parent

you can put & at the right to specify the context (specify the parent)
Meaning, select the `button` class only when a child of a `body` with a `page-about` class.

    .button {  
    	body.page-about & {}
    }
    // compiles into:
    body.page-about .button  {}

## Modifying the nam for BEM

    .btn {  
    &-primary {}  
    &-secondary {}  
    }
    // compiles into
    .btn-primary  {}
    .btn-secondary  {}



## Child selectors

### column combinator
```css
col.selected || td
```

:target
:disabled
:first-child
:last-child
:not()
:placeholder-shown

[https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors/Using_the_:target_pseudo-class_in_selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors/Using_the_:target_pseudo-class_in_selectors)


### Attention!

When you do:

```
tr:first-child ...
```

you're actually selecting  `<tr>`  elements that  _are_  first children. Also be aware that:

```
tr :first-child ...
```

is selecting the first children  _of_  table rows.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NjY5NDY3MzQsLTY4NjYxODk2MCwtOD
M2NzgwMzcwLC0yMTIwOTYzNjE2LC0xODg4MDQ4MjI4LC0xMjQz
NjMxODYxLDQ5NzgxODgxMF19
-->



## test



# Pseudo classes

### links
a:hover
a:visited

### children
li:first-child
li:last-child
li:nth-child(4)
li:nth-last-child(4)
em:only-child

### type
in questi esempi è type: em

em:first-of-type
em:last-of-type
em:nth-of-type(4)
em:nth-last-of-type(4)
em-only-of-type

### Negation