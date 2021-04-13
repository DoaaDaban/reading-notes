### Article [What Google Learned From Its Quest to Build the Perfect Team](https://www.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.html)

#### I learned from this article

1. As commerce becomes increasingly global and complex, the bulk of modern work is more and more team-based.
1. the most productive employees tend to build larger networks by rotating dining companions
1. The right norms, in other words, could raise a group’s collective intelligence, whereas the wrong norms could hobble a team, even if, individually, all the members were exceptionally bright.
1. psychological safety and emotional conversations were related
1. As long as everyone got a chance to talk, the team did well. But if only one person or a small group spoke all the time, the collective intelligence declined
1. In the best teams, members listen to one another and show sensitivity to feelings and needs.

### Article [CSS Transforms](https://learn.shayhowe.com/advanced-html-css/css-transforms/)

#### I learned from this article

1. The transform property comes in two different settings, two-dimensional and three-dimensional.
1. The un-prefixed declaration comes last to overwrite the prefixed versions, should a browser fully support the transform property.
1. 2D Transforms
   - 2D Rotate:The rotate value provides the ability to rotate an element from 0 to 360 degrees.
   - 2D Scale: allows you to change the appeared size of an element.
   - 2D Translate: will change the position of an element
   - 2D Skew: used to distort elements on the horizontal axis, vertical axis, or both.
1. To combine transforms, list the transform values within the transform property one after the other without the use of commas.
1. Perspective
   - In order for three-dimensional transforms to work the elements need a perspective from which to transform.
   - The higher the value, the further away the perspective appears,
1. Perspective Origin
1. Using three-dimensional transforms we can change elements on the z axis, giving us control of depth as well as length and width.
1. To allow nested elements to transform in their own three-dimensional plane use the transform-style property with the preserve-3d value.
1. backface-visibility property to hidden, and you will hide the element whenever it is facing away from the screen.

### Article [Transitions & Animations](https://learn.shayhowe.com/advanced-html-css/transitions-animations/)

#### I learned from this article

1. a transition to take place, an element must have a change in state, and different styles must be identified for each state
1. There are four transition related properties in total
   - transition-property: only the properties identified within the transition-property value will be affected by any transitions.
   - transition-duration: The duration in which a transition takes place
   - transition-timing-function: is used to set the speed in which a transition will move.
     - ease-in: starts slowly and speeds up throughout the transition, while the
     - ease-out: starts quickly and slows down throughout the transition.
     - ease-in-out: starts slowly, speeds up in the middle, then slows down again before ending.
   - transition-delay
1. not all properties may be transitioned, only properties that have an identifiable halfway point.
1. Animations: when more control is required, transitions need to have multiple states. In return, this is where animations pick up where transitions leave off.

   - Animations Keyframes
   - Animation Name: the animation-name property is used with the animation name to assign it to the element
   - Animation Duration, Timing Function, & Delay
   - Animation Iteration: To have an animation repeat itself numerous times
   - Animation Direction: Values for the animation-direction property include normal, reverse, alternate, and alternate-reverse.
   - Animation Play State: allows an animation to be played or paused using the running and paused keyword values respectively.
   - Animation Fill Mode: identifies how an element should be styled either before, after, or before and after an animation is run

1. some example on an awesome transition effect from [8 SIMPLE CSS3 TRANSITIONS](https://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users)

1. 3 CSS styles on buttons and examples on animations
