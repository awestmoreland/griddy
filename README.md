griddy
======

Mixin for Bourbon + Neat to reset margins and omega when changing media queries.


Mixin
======

```scss
@mixin griddy($cols) {
  > *{
    @if($cols > 1) {
      @for $i from 1 through $cols {
        &:nth-child(#{$i}n) {
          margin-right: flex-gutter();
          clear: none;
        }
      }
      @include span-columns($grid-columns / $cols);
      @include omega($cols*1n);
    }
    @else {
      @include fill-parent();
    }
  }
}
```

Example Usage
======

```scss
.columns {

  @include clearfix;
  @include griddy(1);
  @include media($led) {
    @include griddy(2);
  }

  &.six-wide {
    @include media($desklamp) {
      @include griddy(3);
    }
    @include media($chandelier) {
      @include griddy(6);
    }
  }

  &.four-wide {
    @include media($desklamp) {
      @include griddy(4);
    }
  }
  img {
    width: 100%;
  }

}
```

Example Markup
======

```html
<ul class="columns four-wide">
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
  <li>Content</li>
</ul>
````
