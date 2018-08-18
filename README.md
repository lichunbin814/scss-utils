# scss-utils

## animation

### keyframe-gen

> @import '_animation.scss';

#### normal

``` scss
@include keyframe-gen(
  $name : "fadeIn" ,  
   $value : (
      0: (
            transform: scale(1),
            opacity: 1
      ),
      100: (
            transform: scale(0),
            opacity: 0
      ),
   )
);

// output css
@keyframes fadeIn {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  100% {
    transform: scale(0);
    opacity: 0;
  }
}
```
---

#### with reverse version

##### Purpose:
  - Reuse written keyframe to achieve reverse animation

``` scss
@include keyframe-gen(
  $name : "fadeIn" ,  
   $value : (
      0: (
            transform: scale(1),
            opacity: 1
      ),
      100: (
            transform: scale(0),
            opacity: 0
      ),
   ) , 
   $genReverse : true 
);

// output css
@keyframes fadeIn {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  100% {
    transform: scale(0);
    opacity: 0;
  }
}

@keyframes fadeIn-rev {
  100% {
    transform: scale(1);
    opacity: 1;
  }
  0% {
    transform: scale(0);
    opacity: 0;
  }
}
```

##### Use Case
  - [CSS CHALLENGE 100 - Day 2 - Menu Icon Animation](https://codepen.io/lichunbin814/pen/oMKwLZ)

![keyframe-reverse.gif](keyframe-reverse.gif)

``` scss
.menu {
  animation: fadeIn-rev 0.7s $cubic-bezier-in forwards;

  &.active {
     animation-name: fadeIn;
  }
}
```
---
