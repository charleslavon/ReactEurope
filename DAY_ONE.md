## Roadmap for React
Andrew Clark [@acdlite](http://twitter.com/acdlit)
###### Synchronous scheduling blocks
blocking js processes causing video jank, preventing video chunks from beings played smoothly

###### Cooperative multitasking
Write code a certain way such that it can be split into chunks and executed in a coordinated way. Do this by splitting work in component boundaries - this is hte basis of React Fiber, a ground up rewrite of React aimed to solve complex scheduling problems. Checkout the talks from F8 on React Fiber.

###### React v16
    * Uses Fiber. Supports Fragments (sibling components) which allows you to return arrays from Render. (Strings are also a new supported return type from Render)
    * Improved error handling - if a component throws an error in render of a lifecycle method, react will unmount the entire component and force the user to refresh the browser(?). Error boundaries are also new which give try/catch like abilities to add some parachute behavior to potential error boundaries.
    * Portals - allow you to render a child component into the dom element of your choosing, e.g. useful for popups or modal overlays.  People typically have done this using lifecycle methods, but that doesn't deal well with context.
    * Async rendering - you'll be able ot opt-in to async rendering/scheuling per component subtree.
    * You can test this out with `yarn add react@next`

###### Beyond React 16
    * Offscreen/Hidden Prioritization - e.g. give priority to the scheduling of blocking events. like an input event shoudl take priority over a network request. Similarly events triggered for events which are hidden or offscreen currently have the same priority as 'on-screen' elements/events and thus are able to steal processign resources. Offscreen/hidden prioirties attempst to address this.
    * Better code splitting - e.g. only load the code for the routes which you're currently viewing (makes the inital render much faster and thus makes additional requests more expensive) So you'll have to make considered decisions on how to split your code.
    * Commit based rendering: grouping multiple request/render processes into one operation that deplays rendering until all the individual pieces are retrieved, pre-rendered, and then can be rendered all at once.




## Benchmarking React
Dominic Gannaway  [@trueadm](http://twitter.com/trueadm) creator of Inferno

## Building HighQuality JS tools - Jest (test runner)
Christoph Pojer [@copjer](http://twitter.com/copjer) Engineering Mgr @ Facebook London

  `yarn create react-app`
  `yarn create react-native-app`

Jest supports running tests across multiple projects at once
Interactive CLI for running/searching tests
Integrated code coverage

checkout jest-snapshot

jest-validate can help you setup/validate a project

They have an editor support package - search for webstorm support

"jest project is approachabe and easy to contribute to open source"

codemodes with jest-codemods and codeshift



## La Nouvelle Vague - the new wave of frameworks (hint...they aren't really frameworks at all
Sunil Pal [@threepointone](http://twitter.com/threepointone)

  We send too much code to the browsers

  We can do better - compile-to-js langs, css-in-js, route aware bundles, etc
  * checkout svelte.js,
  * gatsby.js,
  * next.js (more php than meteor),
  * relay (declare your data requirements),
  * Prepack,
  * threepointone/rakt

He basically talks about adding more responsibilities into compilers, bundlers, etc
React taught us that
  `view = f(code)`
He proposes that
  `app = f(code), where f is the bundler`



## The upside of JS Fatigue
Kevin Lacker [@lacker](http://twitter.com/lacker)
tl;dr; JS fatigue is good, it leads to more contributors and better products

Suggests that we read Richard P. Gabriel's - "Worse Is Better" Strategy
  1. Launch somehing simple
  2. Make it Popular
  3. Fill in the holes

Priorities:
  1. Simplicity: the most important consideration
  2. Correctness: is's slightly better to be simple than correct
  3. Consistency: Correctness is a bit more important than consistency
  4. Completeness

JS Fatigue is what drives the success of our ecosystem
  but there is a solution...the solution to JS Fatigue.....is More JavaScript - write your own library!

If you're sick of trying to keep up, don't like what's out there, or it doens't fit your needs, then write your own adn incrementally make it better.



## What WebAssembly means for React

Lin Clark [@linclark](http://twitter.com/linclark) [@codecartoons](http://twitter.com/codecartoons)
  checkout her talk at JSconf EU on what is WebAssembly

"web assembly allows multple langues to run in the browser" This means we could have C/C++ in the browser that may run faster than JS. Right now it does not support DOM interaction.




## How I learned to Stop Worrying and Love the Typechecker
Adam Perry - [@dika10sune](http://twitter.com/dika10sune)

Checkout [flow/try](http://flow.org/try)
  * doesnt' product runtime code
  * focus on immersivenes, performance
  * aimed at typing idiomatic Javascript for some values of idomatic? -
  * Mix of structrural & nominal typing

They specify struture & behavior - the same way unit tests can reinforce this.
Good for constraining the state of your programs

###### On Incremental Adoption:
Not everything has to be typed, you can specify an 'Any' type which is attractive when you're trying to adopt this incrementally, but here's a type. Instead of 'Any' using something easily greppable like $FlowFixme
`
        [options]
        supress_type=$FlowFixMe
`

Flow-typed is a community repo of type definition for common npm libraries - if might have the types you need to get some safety on the libraries you're already using

Editor Integration - is sweet



## Reason & Imperfection
Cheng Lou [@_chenglou](http://twitter.com/_chenglou)
  http://github.com/facebook/reason
  http://github.com/reasonml/reason-react

Pareto Principle - 80/20 'Good bang for the buck' 'Sweet spot'

Plugged the movie 'Inside Out'  (because of it's theme of sadness/imperfection being an critical part of life and the human experience )

Be adaptable - give yourself wiggle room for potential organic growth we want to find that 80/20 sweet spot that gives us amazing returns on our effort with the precieved appearance of 100%, when in really it's 80%

However,
    * If this 80/20 approach is badly done it will be brittle
    * This is not great for foundation building - standard library, type system, language semantics
    * Accidental 80%, is brittle
    * Makes composition very hard - there are side effects, mutability

His plug is to try for a 100% approach, creating islands of 100% pristine type safety (for example). Although this option is of course much harder to adopt...Thus, it's all about tradeoffs. A tasteful balance of tradeoffs. "It's a real luxury to be able to use a 80% approach. This is your sloppiness budget. You can only have a budget for sloppiness if your foundation is 100% solid."

Check this out - http://lamport.azurewebsites.net/pubs/future-of-computing.pdf
