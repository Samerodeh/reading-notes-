# CSS Transforms 

## Transforms 

***With CSS3 came new ways to position and alter elements. Now general layout techniques can be revisited with alternative ways to size, position, and change elements. All of these new techniques are made possible by the transform property.*** 

***The transform property comes in two different settings, two-dimensional and three-dimensional. Each of these come with their own individual properties and values.*** 

> Transform Syntax 

    div {
    -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
    }


### 2D Transforms

**Elements may be distorted, or transformed, on both a two-dimensional plane or a three-dimensional plane. Two-dimensional transforms work on the x and y axes, known as horizontal and vertical axes. Three-dimensional transforms work on both the x and y axes, as well as the z axis. These three-dimensional transforms help define not only the length and width of an element, but also the depth.** 

* 2D Rotate 

*The transform property accepts a handful of different values. The rotate value provides the ability to rotate an element from 0 to 360 degrees.* 

    .box-1 {
     transform: rotate(20deg);
    }
    .box-2 {
    transform: rotate(-55deg);
    }



* 2D Scale 

*Using the scale value within the transform property allows you to change the appeared size of an element.* 

    .box-1 {
    transform: scale(.75);
    }
    .box-2 {
    transform: scale(1.25);
    } 


* 2D Translate 

*The translate value works a bit like that of relative positioning, pushing and pulling an element in different directions without interrupting the normal flow of the document. Using the translateX value will change the position of an element on the horizontal axis while using the translateY value will change the position of an element on the vertical axis.* 

    .box-1 {
     transform: translateX(-10px);
     }
    .box-2 {
     transform: translateY(25%);
     }
    .box-3 {
    transform: translate(-10px, 25%);
    } 


* 2D Skew 

*is used to distort elements on the horizontal axis, vertical axis, or both. The syntax is very similar to that of the scale and translate values. Using the skewX value distorts an element on the horizontal axis while the skewY value distorts an element on the vertical axis*


    .box-1 {
    transform: skewX(5deg);
    }
    .box-2 {
    transform: skewY(-20deg);
    }
    .box-3 {
    transform: skew(5deg, -20deg);
    }


### Transform Origin  

**the default transform origin is the dead center of an element, both 50% horizontally and 50% vertically.**

**The transform-origin property can accept one or two values. When only one value is specified, that value is used for both the horizontal and vertical axes. If two values are specified, the first is used for the horizontal axis and the second is used for the vertical axis.**

    .box-1 {
    transform: rotate(15deg);
    transform-origin: 0 0;
    }
    .box-2 {
    transform: scale(.5);
    transform-origin: 100% 100%;
    }
    .box-3 {
    transform: skewX(20deg);
    transform-origin: top left;
    }
    .box-4 {
    transform: scale(.75) translate(-10px, -10px);
    transform-origin: 20px 50px;
    }

### Perspective 

**In order for three-dimensional transforms to work the elements need a perspective from which to transform. The perspective for each element can be thought of as a vanishing point, similar to that which can be seen in three-dimensional drawings.**

**The perspective of an element can be set in two different ways. One way includes using the perspective value within the transform property on individual elements, while the other includes using the perspective property on the parent element residing over child elements being transformed.**

**Using the perspective value within the transform property works great for transforming one element from a single, unique perspective.**

    .box {
    transform: perspective(200px) rotateX(45deg);
    }


* Perspective Depth Value 

*The perspective value can be set as none or a length measurement. The none value turns off any perspective, while the length value will set the depth of the perspective. The higher the value, the further away the perspective appears, thus creating a fairly low intensity perspective and a small three-dimensional change. The lower the value the closer the perspective appears, thus creating a high intensity perspective and a large three-dimensional change.* 

    .box-1 {
    transform: perspective(100px) rotateX(45deg);
    }
    .box-2 {
    transform: perspective(1000px) rotateX(45deg);
    }


* Perspective Origin   

*As with setting a transform-origin you can also set a perspective-origin. The same values used for the transform-origin property may also be used with the perspective-origin property, and maintain the same relationship to the element. The large difference between the two falls where the origin of a transform determines the coordinates used to calculate the change of a transform, while the origin of a perspective identifies the coordinates of the vanishing point of a transform.* 

    .original {
    perspective: 200px;
    }
    .box {
    transform: rotateX(45deg);
    }
    .original-1 {
    perspective-origin: 0 0;
    }
    .original-2 {
    perspective-origin: 75% 75%;
    }
    .original-3 {
    perspective-origin: 20px 40px;
    }


### 3D Transforms 

**Using three-dimensional transforms we can change elements on the z axis, giving us control of depth as well as length and width.**

* 3D Rotate 

*With three-dimensional transforms we can rotate an element around any axes. To do so, we use three new transform values, including rotateX, rotateY, and rotateZ.* 

    .box-1 {
     transform: perspective(200px) rotateX(45deg);
    }
    .box-2 {
    transform: perspective(200px) rotateY(45deg);
    }
    .box-3 {
    transform: perspective(200px) rotateZ(45deg);
    }


* 3D Scale 

*By using the scaleZ three-dimensional transform elements may be scaled on the z axis. This isn’t extremely exciting when no other three-dimensional transforms are in place, as there is nothing in particular to scale.* 

    .box-1 {
    transform: perspective(200px) scaleZ(1.75) rotateX(45deg);
    }
    .box-2 {
    transform: perspective(200px) scaleZ(.25) rotateX(45deg);
    } 


* 3D Translate 

*A negative value here will push an element further away on the z axis, resulting in a smaller element. Using a positive value will pull an element closer on the z axis, resulting in a larger element.* 

    .box-1 {
    transform: perspective(200px) translateZ(-50px);
    }
    .box-2 {
    transform: perspective(200px) translateZ(50px);
    } 


* 3D Skew 

*Skew is the one two-dimensional transform that cannot be transformed on a three-dimensional scale. Elements may be skewed on the x and y axis, then transformed three-dimensionally as wished, but they cannot be skewed on the z axis.* 

### Transform Style 

**To allow nested elements to transform in their own three-dimensional plane use the transform-style property with the preserve-3d value.**

    .rotate {
    transform: perspective(200px) rotateY(45deg);
    }
    .three-d {
    transform-style: preserve-3d;
    }
    .box {
    transform: rotateX(15deg) translateZ(20px);
    transform-origin: 0 0;
    } 


## Transitions & Animations 

### Transitions 

**The easiest way for determining styles for different states is by using the :hover, :focus, :active, and :target pseudo-classes.** 

**There are four transition related properties in total, including transition-property, transition-duration, transition-timing-function, and transition-delay.** 

    .box {
    background: #2db34a;
    transition-property: background;
    transition-duration: 1s;
    transition-timing-function: linear;
    }
    .box:hover {
    background: #ff7b29;
    }


* Transitional Property 

*The transition-property property determines exactly what properties will be altered in conjunction with the other transitional properties. By default, all of the properties within an element’s different states will be altered upon change. However, only the properties identified within the transition-property value will be affected by any transitions.* 

    .box {
    background: #2db34a;
    border-radius: 6px
    transition-property: background, border-radius;
    transition-duration: 1s;
    transition-timing-function: linear;
    }
    .box:hover {
    background: #ff7b29;
    border-radius: 50%;
    } 


* Transition Duration 

*The duration in which a transition takes place is set using the transition-duration property. The value of this property can be set using general timing values, including seconds (s) and milliseconds (ms).* 

     .box {
    background: #2db34a;
    border-radius: 6px;
    transition-property: background, border-radius;
    transition-duration: .2s, 1s;
    transition-timing-function: linear;
    }
    .box:hover {
    background: #ff7b29;
    border-radius: 50%;
    }


* Transition Timing 

*The transition-timing-function property is used to set the speed in which a transition will move.* 

      .box {
    background: #2db34a;
    border-radius: 6px;
    transition-property: background, border-radius;
    transition-duration: .2s, 1s;
    transition-timing-function: linear, ease-in;
    } 
    .box:hover {
    background: #ff7b29;
    border-radius: 50%;
    }


* Transition Delay 

*On top of declaring the transition property, duration, and timing function, you can also set a delay with the transition-delay property.*

     .box {
    background: #2db34a;
    border-radius: 6px
    transition-property: background, border-radius;
    transition-duration: .2s, 1s;
    transition-timing-function: linear, ease-in;
    transition-delay: 0s, 1s;
    }
    .box:hover {
    background: #ff7b29;
    border-radius: 50%;
    }


### Shorthand Transitions 

**Declaring every transition property individually can become quite intensive, especially with vendor prefixes** 

    .box {
    background: #2db34a;
    border-radius: 6px;
    transition: background .2s linear, border-radius 1s ease-in 1s;
    }
    .box:hover {
    color: #ff7b29;
    border-radius: 50%;
    }

### Animations 

**when more control is required, transitions need to have multiple states. In return, this is where animations pick up where transitions leave off.** 

* Animations Keyframes

*To set multiple points at which an element should undergo a transition, use the @keyframes rule. The @keyframes rule includes the animation name, any animation breakpoints, and the properties intended to be animated.*

    @keyframes slide {
    0% {
    left: 0;
    top: 0;
    }
    50% {
    left: 244px;
    top: 100px;
    }
    100% {
    left: 488px;
    top: 0;
      }
    } 


* Animation Name

*Once the keyframes for an animation have been declared they need to be assigned to an element. To do so, the animation-name property is used with the animation name, identified from the @keyframes rule, as the property value. The animation-name declaration is applied to the element in which the animation is to be applied to.*

    .stage:hover .ball {
    animation-name: slide;
    }


* Animation Duration, Timing Function, & Delay 

*To start, animations need a duration declared using the animation-duration property* 

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    }


*A timing function and delay can be declared using the animation-timing-function and animation-delay properties respectively. The values for these properties mimic and behave just as they do with transitions.* 

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    }


### Customizing Animations 

**Animations also provide the ability to further customize an element’s behavior, including the ability to declare the number of times an animation runs, as well as the direction in which an animation completes.** 

* Animation Iteration 

*To have an animation repeat itself numerous times the animation-iteration-count property may be used. Values for the animation-iteration-count property include either an integer or the infinite keyword.* 

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    animation-iteration-count: infinite;
    }


* Animation Direction 

*you may also declare the direction an animation completes using the animation-direction property.*

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    } 


* Animation Play State 

*The animation-play-state property allows an animation to be played or paused using the running and paused keyword values respectively.* 

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    }
    .stage:active .ball {
    animation-play-state: paused;
    }


* Animation Fill Mode 

*The animation-fill-mode property identifies how an element should be styled either before, after, or before and after an animation is run.* 

    .stage:hover .ball {
    animation-name: slide;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: .5s;
    animation-fill-mode: forwards;
    }
    .stage:active .ball {
    animation-play-state: paused;
    }


### Shorthand Animations 

**Fortunately animations, just like transitions, can be written out in a shorthand format. This is accomplished with one animation property, rather than multiple declarations. The order of values within the animation property should be animation-name, animation-duration, animation-timing-function, animation-delay, animation-iteration-count, animation-direction, animation-fill-mode, and lastly animation-play-state.** 

    .stage:hover .ball {
    animation: slide 2s ease-in-out .5s infinite alternate;
    }
    .stage:active .ball {
    animation-play-state: paused;
    } 



 ## 8 simple CSS3 transitions that will wow your users 

 * Fade in 

 *Fade in effects are coded in two steps: first, you set the initial state; next, you set the change, for example on hover:* 

     .fade
    {
        opacity:0.5;
    }
    .fade:hover
    {
        opacity:1;
    } 


* Change color 

*we just set the div’s class to “color” and specify the color we want in our CSS*

      .color:hover
    {
        background:#53a7ea;
    }


* Grow & Shrink 

*use CSS3’s transform to enlarge.* 

    .grow:hover
    {
        -webkit-transform: scale(1.3);
        -ms-transform: scale(1.3);
        transform: scale(1.3);
    } 


* Rotate elements 

*one of the best is transforming the rotation of an element.*

    .rotate:hover
    {
        -webkit-transform: rotateZ(-30deg);
        -ms-transform: rotateZ(-30deg);
        transform: rotateZ(-30deg);
    } 


* Square to circle 

*simple effect to achieve, we just transition the border-radius property.* 

    .circle:hover
    {
        border-radius:50%;
    }


*  3D shadow 

*This effect is achieved by adding a box shadow, and then moving the element on the x axis using the transform and translate properties so that it appears to grow out of the screen.*

    .threed:hover
    {
        box-shadow:
                1px 1px #53a7ea,
                2px 2px #53a7ea,
                3px 3px #53a7ea;
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
    } 


* Swing 

*We can also create highly complex animations using @keyframes, animation and animation-iteration.* 

    @-webkit-keyframes swing
    {
    15%
    {
        -webkit-transform: translateX(5px);
        transform: translateX(5px);
    }
    30%
    {
        -webkit-transform: translateX(-5px);
       transform: translateX(-5px);
    } 
    50%
    {
        -webkit-transform: translateX(3px);
        transform: translateX(3px);
    }
    65%
    {
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
    }
    80%
    {
        -webkit-transform: translateX(2px);
        transform: translateX(2px);
    }
    100%
    {
        -webkit-transform: translateX(0);
        transform: translateX(0);
    }
    } 

    .swing:hover
    {
        -webkit-animation: swing 1s ease;
        animation: swing 1s ease;
        -webkit-animation-iteration-count: 1;
        animation-iteration-count: 1;
    }


* Inset border 

*One of the hottest button styles right now is the ghost button; a button with no background and a heavy border.* 

    .border:hover
    {
        box-shadow: inset 0 0 0 25px #53a7ea;
    }


