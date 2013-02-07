# Symbolset Sass

[Symbolset](http://symbolset.com/) is a beautiful collection of semantic symbol fonts. **Symbolset Sass** is a library of Sass [placeholder selectors](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#placeholder_selectors_)</a> that allow you to use Symbolset without having to follow the markup conventions it comes with. This is useful when:

- You're working with HTML that is inconsistent or difficult to modify.
- You prefer not to add `.ss-icon` and `.ss-$icon` class attributes to your code.
- You'll only use a select number of icons and/or multiple sets, and prefer not to include the code for the entire library.

*Caution:* Examine your use case. If you plan to use a lot of icons, with a bunch of different selectors, the code this library generates can become quite large. In that case, it would more sense to modify your HTML and use the CSS that comes with the font.

## Supported Sets

- [SS Social](http://symbolset.com/#social)
- [SS Standard](http://symbolset.com/#standard)
- [SS Pika](http://symbolset.com/#pika) (Coming Soon!)
- [SS Symbolicons](http://symbolset.com/#symbolicons) (Coming Soon!)

## Usage

First, you must purchase the font sets you want to use from [https://symbolset.com](https://symbolset.com/) and place them in your project directory.

1. Download <a href="https://github.com/jacine/symbolset">Symbolset Sass</a> and place the partial in your <code>sass</code> or <code>scss</code> directory.
2. In your project's scss/sass stylesheet, include the following:
    ```scss
    // Import the base file.
    @import "symbolset/symbolset";

    // Specify where the font files are located.
    $ss-standard-directory: '../fonts/ss-standard/webfonts/';
    $ss-social-directory: '../fonts/ss-social/webfonts/';

    // Import only the font sets you wish to use.
    @import "symbolset/ss-standard";
    @import "symbolset/ss-social";
    @import "symbolset/ss-social-circle";
    ```
3. Add icons to your CSS using `@extend`:
    ```scss
    // Use it with the selectors you have available, such as:
    .twitter:before { @extend %ss-twitter; }
    .twitter-circle:after { @extend %ss-twitter-circle; }
    .heart:before { @extend %ss-heart; }

    // Or, if you have the unicode characters in code:
    .ss-icon {
      @extend %ss-standard;
    }
    ```
