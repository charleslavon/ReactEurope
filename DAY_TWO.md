## Next Gen State Management
###### Michael Weststrate [@mweststrate](http://twitter.com/mweststrate)

This guys gives lots of talks so should be easy to find some of them online

###### Promoting 'mobx-state-tree'
    * Tries to combines the best ideas of Redux and Mobx into one model
    * Protection against uncoordinated modifications
    * Snapshots - what if we could get snapshots for free after each mutation? That's the idea behind mobx-state-tree
    * There's type information, compile & runtime type checks, etc
    * It's replayable and supports middleware


## Composition: A Superpower Explained
###### Nik Graf [@nikgraf](http://twitter.com/nikgraf)
  checkout this medium post [Why Using Chain is a Mistake](https://medium.com/making-internets/why-using-chain-is-a-mistake-9bc1f80d51ba) - de acuerdo

### RamdaJS - awwww yea!
### lodash/fp - meh ok, but I'll put it here because he promoted it

Also talked about 'polished' his toolset for writing css in javasript that has a set of SASS-like composable functions

Then got into the benefits of using Curring and functional composition to reduce code duplication and simplify the creation and use of higher order components.

react-vr for React Native. Gave some examples of applying composition techniques to React VR apps.


## Twitter Lite & The Future of Progressive Web Apps
###### Nicolas Gallagher [@necolas](http://twitter.com/necolas)
  http://mobile.twitter.com

###### Why PWA?
  Because they want to reach every person on the planet. Over 1 Billion people can only connect at 2G speeds. Also 1.8 Billion people cannot afford 500MB data per month.

###### React Native for the Web
  He's working on a web implementation of ReactNative but targeting the web. They are using some of this on TwitterLite. His reasoning is that React Native provides good building blocks for creative PWAs.



#### Lightning Talk
###### Glenn Reyes 'Leverage Code Splitting in React'
  [@glnnrys](http://twitter.com/glnnrys)


## Runtimes of React VR & use at Oculus
######  Mike ArmStrong [@m1k3](https://twitter.com/m1k3)
  The React motto is Learn Once and Write Everywhere - now they are bringing this to another dimension

  He's working on tooling and framework to make VR development accessible such that it foster a developer community.

  https://ocul.us/webvr
  `npm install -g react-vr-cli`
  `react-vr init WelcomeToVR`

## Functional && Reactive UI
###### Preethi Kasireddy [@iam_preethi](https://twitter.com/iam_preethi)
Her lifechanging post from 2 years ago - [why I'm leaving the web job in the world to be a software engineer](https://medium.com/swlh/why-i-left-the-best-job-in-the-world-3689a5a4649a)
She also has a [follow up post](https://medium.com/swlh/what-happened-after-i-left-the-best-job-in-the-world-to-become-an-engineer-ee06caca7db2)

As programmers we're so used ot describing how things work, isntead of the what - too many low level details. Instead what we are moving to in the Front End is: What ot be instead of How to do.

  * JQuery -> Imperative UI
  * React -> Declarative & Composable UI elements
  * Redux -> Purity & Composable State management
  * RxJS -> Streams of UI behaviors (think lodash for UI events)
    basically a data pipelines of publishers and subscribers where you can apply
  MobX -> Reactive UI - Reactivity for any Construct (which more fine grained controls)
    Adds observable cabalilities to existing structures like arrays, etc

###### Functional Reactive Programming
combines the principles of functional & reactive in a powerful way. Not saying it's teh answer for everything, but it has many applications.

###### FRP models data types that represent a value over time.
It's all about describimg a system in terms of  time-varying funcitons instead of mutable state.

Specify the dynamic behaivor of a system completely at the time of declaration.

Sodium.js - using this for her demo, not a produciton ready product

  Stream
    * mouse click
    * UI event
    * Component behavior

  Cell
    * continuous value over time
    * position ofa mouse
    * text input value,e tc

  Operations
    map, filter, merge, etc


With FRP you stay at the level or relationships between things and not the details of the mechanics that implements that relationship

The goal of FP is ot get referntial transparency with values that are mutable over time. So you need a blackbox to safely contain the mutable areas. That's what she's showing with her example of MobX + RxJS (e.g. stream.js)

###### Why referential transparency?
Because it yeilds associativity and thus we get compositionality which is the most powerful way to deal with complexity. With compostionality we get to live in a world of small composable funcitons instead of a large complex systems which cannot be extended nor broken down into smaller components.

Your primkary goal as a developer is to manage complexity, that's why this is super powerful.



## Exploring Relay Modern (the new version of Relay)
Lee Bryon [@leeb](https://twitter.com/leeb)
Talking about the history & future of Relay (the library that faciliates client-side GraphQL stuff)

## Animating the Virtual DOM
Sarah Drasner [@sarah_edo](https://twitter.com/sarah_edo)
  She showed an svg animated burning candle and smoke - minds blown
  -insert a couple fotos here -


## React as a Platform: A path towards a truly cross-platform UI
Leland Richardson [@intelligibabble](https://twitter.com/intelligibabble)
They write AirBnb 3 times in 3 different formats, for Android, iOS and Javascript for the Web
'Cross Platform' React - talking about this ideal and the realities of trying to get there.
Share code, without friction, wherever appropriate. Great presentation.


## A Novel Approach to Declarative Animations in React Native
Joel Arvidsson [@trastknast](https://twitter.com/trastknast)
I don't care where you go with this presentation. You started with a rainbow creating sharkTart. You win @trastknast

He chats about the nuances of using transitions and animations to make easily discoverable the structure & navigation patterns of an app.

Recommended APIs
  * Animated by Vjeux (react) - requires your components be state aware :(
  * CSS Animations (web, duh)
  * Animatable (react-native) - pure, stateless

  Recap: You gotta use motion if you want a sweet UX


## Putting the fun in functional with Elm
Tereza Sokol [@terezk_a](https://twitter.com/terezk_a)
Sharing her realworld experience of coverting her team's "react jungle of regrest" app to Elm, and the how to deal with the ridigity of real as an imperfect human.

