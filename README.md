# Symbolset Sass

[Symbolset](http://symbolset.com/) is a beautiful collection of semantic symbol fonts. **Symbolset Sass** is a library of Sass [placeholder selectors](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#placeholder_selectors_)</a> that allow you to use Symbolset without having to follow the markup conventions it comes with. This is useful when:

- You're working with HTML that is inconsistent or difficult to modify.
- You prefer not to add `.ss-icon` and `.ss-$icon` class attributes to your code.
- You'll only use a select number of icons and/or multiple sets, and prefer not to include the code for the entire library.

## Supported Sets

- [SS Social](http://symbolset.com/#social) (regular and circle)
- [SS Standard](http://symbolset.com/#standard)
- [SS Pika](http://symbolset.com/#pika)
- [SS Symbolicons](http://symbolset.com/#symbolicons) (block and line)

## Usage

First, you must purchase the font sets you want to use from [https://symbolset.com](https://symbolset.com/) and place them in your project directory.

1. Download <a href="https://github.com/jacine/symbolset">Symbolset Sass</a> and place the partial in your <code>sass</code> or <code>scss</code> directory.
2. In your project's scss/sass stylesheet, include the following:
    ```scss
    // Specify where the font files are located.
    $ss-pika-dir: '../fonts/ss-pika/webfonts/';
    $ss-social-regular-dir: '../fonts/ss-social/webfonts/';
    $ss-social-circle-dir: $ss-social-regular-dir;
    $ss-standard-dir: '../fonts/ss-standard/webfonts/';
    $ss-symbolicons-block-dir: '../fonts/ss-symbolicons-block/webfonts/';
    $ss-symbolicons-line-dir: '../fonts/ss-symbolicons-line/webfonts/';

    // Import the base file.
    @import "symbolset/symbolset";

    // Import only the font sets you wish to use (Do NOT use all of them at once).
    @import "symbolset/ss-pika";
    @import "symbolset/ss-social-circle";
    @import "symbolset/ss-social-regular";
    @import "symbolset/ss-standard";
    @import "symbolset/ss-symbolicons-block";
    @import "symbolset/ss-symbolicons-line";
    ```
3. Add icons to your CSS using `@extend`:
    ```scss
    // Use it with the selectors you have available, such as:
    .twitter:before { @extend %ss-twitter; }
    .twitter-circle:after { @extend %ss-twitter-circle; }
    .heart:before { @extend %ss-heart; }

    // Or, if you have the unicode characters in code:
    .icon {
      @extend %ss-standard;
    }
    ```

## Caution

- These sets were not designed to be used all at once, except for the social sets. They can be used alongside each other and one of the other font sets. For example, attemping to use Pika and Standard at the same time will cause conflicts because the sets share many of the same icon names and characters. If you do this, last set imported will win specificity-wise. This would be a terrible idea anyway, but it's worth mentioning.
- Examine your use case. If you plan to use a lot of icons, with a bunch of different selectors, the code this library generates can become quite large. In that case, it would more sense to modify your HTML and use the CSS that comes with the font.
