# scss-utils

## animation

### keyframe-gen

> @import _animation.scss

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

#### with reverse version

use case : [CSS CHALLENGE 100 - Day 2 - Menu Icon Animation](https://codepen.io/lichunbin814/pen/oMKwLZ)

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
