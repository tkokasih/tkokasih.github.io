# CSS

## Background

CSS is a language that I used not frequently.
This notes is to refresh when I have to deal with it again.

CSS basic function is to describe how to display **elements**.
Some concepts that it needs to perform the functions:

| Concept | Short explanation |
|-------|------|
| Selector | Select element to apply a ruleset |
| Position | Define positioning of the element, relative to the surrounding elements/page |
| Box Model | Define the sizing of element |
| Value and units | Unit of properties, e.g. pixel, viewport, percent |


## Selectors

* Selector type:

  | name | pattern | example | comment |
  |------|----------|-------|--|
  | id                 | `#some-id`   | `#doc-content` | |
  | class              | `.classname` | `.nav`         | |
  | type               | `type-id`    | `li`           | |
  | universal selector | `*`          | `*`            | select everything

* Combinators:

  | name | pattern | example | comment |
  |-----|----------|---------|---------|
  | descendant | `a b` | `.nav li` | all `li` under `.nav` |
  | child | `a > b` | `.nav > li`  | all `li` directly under `.nav` |
  | adjacent sibling | `a + b` | `.nav:active + .nav` | `.nav` element directly following `.nav:active` |
  | general siblings | `a ~ b` | `.nav:active ~ .nav` | all `.nav` elements **AFTER** `.nav:active` |
  | compoud | `ab` | `ul.nav` | all `ul` which also has `.nav` class |

* Specificity of selector, can be noted in 4 digits:
  * `origin, id, class, type`, e.g. `1,3,4,2`
  * more specific selector wins, example below from most specific to least specific:

    | order | specificity | comment |
    |-------|--------------|----|
    | 1     | `1,0,0,0`    | origin |
    | 2     | `0,2,0,0`    | two ids, e.g. `#doc #content` |
    | 3     | `0,0,3,1`    | 3 classes + 1 type, e.g. `ul.active.disabled.system` |
    | 4     | `0,0,0,2`    | 2 types, e.g. `ul li` |

* Other kind of selectors (see internet):
  * pseudo-class selectors, e.g. `:first-child`, `:hover`, `:focus`, `:not(<selector)>)`
  * pseudo-element selector, e.g. `::before`, `::after`, `::first-line`, `::selection`
  * attribute selectors, e.g. `[attr]`, `[attr="value]`, `[attr^="value"]`


## Properties
* Shorthard properties:

  | # properties | pattern | example | comment |
  |--------------|-|-|-|
  | 4 | `top, right, bottom, left` | `padding: 2em 2em 1em 1em;` | |
  | 2 | `vertical (top, bottom), horizontal (left, right)` | `padding: 2em 1em`; |  |
  | 2 | `x, y` | `box-shadow: 10px 2px;` | |

* Units
  * Absolute unit (not exhaustive)

    | unit | example | comment |
    |--|--|--|
    | px | `1px` | pixel |
    | mm | `1mm` | milimeters |
    | cm | `10cm` | centimeters |
    | in | `2in` | inch |
    | pt | `12pt` | point = 1/72 inch |
    | pc | `1pc` | pica = 12 pt |

  * Relative unit (not exhaustive)

    | unit | example | comment |
    |--|--|--|
    | em | `0.8em` | font-size of the current element, or inherited font-size if used on font-size property |
    | rem | `0.8rem` | font-size of `:root` element |
    | vh | `80vh` | 1/100th of viewport height |
    | vw | `60vw` | 1/100th of viewport width |
    | vmin | `50vmin` | 1/100th of min(viewport height, viewport width) |
    | vmax | `50vmax` | 1/100th of max(viewport height, viewport width) |

  * 

## Box Model

```
 ______________________________________________________________________
|                                                                      |
|        ||||||||||||||||||||||||||||||||||||||||||||||||||||||        |
|        ||||||||||||          _________           ||||||||||||        |
|        ||||||||||||         |         |          ||||||||||||        |
| margin || border || padding | content |  padding || border || margin |
|        ||||||||||||         |_________|          ||||||||||||        |
|        ||||||||||||                              ||||||||||||        |
|        ||||||||||||||||||||||||||||||||||||||||||||||||||||||        |
|______________________________________________________________________|
```

* padding --> inside margin
* size of element (e.g. `width` and `height` properties) according to WC3 is the size of the content.
  * Typical CSS3 prefix is to change this to border
    ```CSS
    :root {
        box-sizing: border-box;
    }

    *,
    ::before,
    ::after {
        box-sizing: inherit;
    }
    ```

* Basic: inline v.s. block element:
  * inline will be 'flowed' within content, like a text.
    It doesn't have its own `width`, nor `height` properties.
  * block will take up the whole width and will not be "flowed", like a paragraph.
    It has its own `width` and `height` properties.

* Basic type of `display`:

    | name | example element | comment |
    |------|----|-----|
    | `inline` | `span`, `a` | inline element without its own `width` and `height`. Will be "flowed". |
    | `block`  | `p`, `div`, `h1`, `header` | block element with its own `width` and `height`. It will take up the whole width. |
    | `none` | `link`, `script`, `style`, `title` | element will be hidden. NOTE: `visibility: hidden` will only hide "empty out" the element, but the placeholder for element is still there. `display: none` will totally remove the element from the layout. |
    | `inline-block` | `img` | inline element, but with `width` and `height` |
    | `initial` | * | initial `display` from given element |

* flex:

    | name | example element | comment |
    |------|----|-----|
    | `flex` | - | element will be flex container |

  > ... to be continued ...