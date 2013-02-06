
# Symbolset Sass

[Symbolset](http://symbolset.com/) is a beautiful collection of semantic symbol fonts. **Symbolset Sass** is a library of Sass [placeholder selectors](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html#placeholder_selectors_)</a> that allow you to use Symbolset without having to follow the markup conventions it comes with. This is useful when:

- You're working with HTML that is inconsistent or difficult to modify.
- You prefer not to add `.ss-icon` and `.ss-$icon` class attributes to your code.
- You'll only use a select number of icons and/or multiple sets, and prefer not to include the code for the entire library.

*Caution:* Examine your use case. If you plan to use a lot of icons, with a bunch of different selectors, the code this library generates can become quite large. In that case, it would more sense to modify your HTML and use the CSS that comes with the font.

## Supported Sets

- [SS Social](http://symbolset.com/#social)
- [SS Standard](http://symbolset.com/#standard)

## Usage

1. Purchase the font sets you want to use from [https://symbolset.com](https://symbolset.com/) and place them in your project directory.
2. Download <a href="https://github.com/jacine/Symbolset">Symbolset Sass</a> and place the partial in your <code>sass</code> or <code>scss</code> directory.
3. Modify the `@font-face` paths at the top of each set to match your project's setup.
4. Use `@import` to include the Symbolset partial in your stylesheet:
    ```scss
    @import "symbolset/symbolset";
    ```
5. Add icons to your CSS using `@extend`:
    ```scss

    // Use it with the selectors you have available, such as:
    .twitter:before { @extend %ss-twitter; }
    .twitter-circle:after { @extend %ss-twitter-circle; }
    .heart:before { @extend %ss-heart; }

    // Or, if you have the unicode characters in code:
    .ss-icon {
      @extend &ss-standard;
    }
    ```

## Questions

- **What about [SS Pika](http://symbolset.com/#pika) and [SS Symbolicons]((http://symbolset.com/#symbolicons))?** I plan to add these in the near future.
- **Why didn't you use mixins?** It was written using Sass placeholders because they are one of the best things about Sass. When used properly, they can help reduce the CSS output, whereas using mixins liberally will have the opposite effect.
- **Why didn't you use the @font-face Compass mixin?** I don't like it. It's not really intuitive, or foolproof in this situation because every project is structured differently. Either way, the person using this will need to modify the paths to the font files, so why add a dependency?
- **Can you make a real gem?** If I could cleanly work out the font path issue (see above), I would consider it, but I'm not sure if that's possible.
