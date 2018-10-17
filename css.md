## Positioning Elements
- `position: absolute` should be avoided at all costs. Exhaust ALL other options first.

## Spacing
- Spacing should be coptured as variables to maintain consistency across the project
- Spacing between stacking elements should always, and only, be applied as a `margin-bottom`
- Layout spacing (e.g. vertical spacing between top-level elements) should be contained as a mixin and included in each pattern to maintain consistent spacing between page-level elements.
  - Overrides of that spacing is acceptable only between two elements that have a "full-width" color background, and would look weird if they were not flush with eachother

## Fonts
- Font styles should be contained as mixins that allow only the color to be changed on implementation.
  - If there's a variation of weight, size, etc. it's a new mixin (hint: push back, and see whether the 2px difference in font-size is actually necessary)

## Important
- `!important` should be avoided at all costs. Exhaust ALL other options first.

## Styles for a component that only apply when inside another
- These should ONLY include layout styles relative to the wrapping container
  - e.g. Wrapped in an `@include breakpoint($break-<wrapper>-<size>)` statement

## Wrapping breakpoint styles
- In components, Add breakpoint statments inside the bem selectors because you are affecting how that element responds. (You will have multiple breakpoint statements. One for each block/element/modifier as necessary)
- In wrapping components, combine all styles inside a single breakpoint selector because you are affecting the **layout** of the wrapper, not the styles of the element.
