# CSS

How make sure your [[HTML]] looks good when viewed in a webpage

- [[adding CSS to HTML]]
- [[CSS Selector Syntax]]
- [[CSS Properties]]


### The Cascade of CSS
What determines which rules actually get applied to your HTML

#### Specificity
A more specific CSS declaration takes presedence over ones that are less specific.

Specificity will only be taken into account when an element has multiple, conflicting declarations targeting it, like a tie-breaker

From more to less specificity:
1. ID
2. Class
3. Type
4. Universal and combinators

#### Inheritance
Inheritance refers to certain CSS properties that, when applied to an element, are inherited by that element’s descendants, even if we don’t explicitly write a rule for those descendants.

Typography based properties (color, font-size, font-family, etc.) are usually inherited, while most other properties aren’t.

Directly targeting an element beats inheritance

#### Rule Order
If all else is equal, then whatever rule is defined last wins.




