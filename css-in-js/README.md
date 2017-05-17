
CSS-in-JS Workshop with Sunil Pai (author of Glamor - https://github.com/threepointone/glamor)

CSS-in-JS is a powerful technique to help you make your react components portable and manage your css code more easily, it has been popularized by the react team and has been taking over the frontend world ever since. We will cover:

  -what problems does css-in-js solve?
    1. Global Namespace Conflicts
    2. Dependencies
    3. Dead Code Elimination
    4. Minification
    5. Sharing Constants
    6. Non-deterministic Resolution
    7. Isolation
    8. Allows your css to respond to runtime events
    9. We can achieve post-processed SASS/LESS type magic with plain javascript - https://github.com/styled-components/polished

  -comparison of different css-in-js libraries
    1. require('styled-components') - uses tagged template literals to support writing plain css instead of object syntax in javascript - one drawback is yow are now using this 3rd party library as a wrapper around React.createClass
    2. styled-jsx/babel - allows you to write css via a jsx style tag
    render(<div className='reddish'>
      <style jsx>{`
        .reddish {
          color: red;
        }
      `}</style>
          omg what is this
    </div>)
    3. Glam - it's cool because it polyfills support for css variables, and can be an easy stepping stone from css files to css-in-js (although this comes with it's own tradeoffs - https://gist.github.com/threepointone/0ef30b196682a69327c407124f33d69a)
    4. there are many more options depeneding your needs & preferences (performance, server-side rendering, what trends you prefer to follow, etc, each has it's own virtues and flaws...) https://github.com/MicheleBertoli/css-in-js


  -a deepdive into glamor
    Supports inline selectors, shorthand rest spread operator,
    adding labels to assist debugging, takes care of prefixing, eliminating identical duplicate classes (some additional libraries can also elimitate identical rules across multiple classes - thus further reducing duplication & file sizes)

  -server side / static side rendering
  -composition strategies - theming, modularity, lazy loading, etc.
  -write your own plugins
  -autocomplete for styles with typescript/flow
  -build your own css-in-js lib!

  ADVANTAGES:
    -We are better equipped to avoid sending CSS over the wire unless it's essential to the component to be rendered. Less KBs sent to the browser improves bandwidth optimization.
    -Since it's plain javascript we can extend functionaly by making use of plugins (like Glamour plugins) or writing plain javascript.
    -Reducing preprcessing/build dependencies.

  DRAWBACKS:
    -We are no longer using W3C spec'd CSS and instead are binding our UI styles to plain javascript objects (the javascript could be in the same component file or imported from it's own javascript). Thus, you must be even more diligent with the organization of javascript styles to make them reusable across multiple components.


Slides form the original talk that inspired Glamour & this workshop: https://speakerdeck.com/vjeux/react-css-in-js
