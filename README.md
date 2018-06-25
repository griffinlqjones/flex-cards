# Griffin's Flex Cards Functional Mixin

> Flex cards is as flex cards do. They do for me what they'll do for you. - Me

This is a functional SCSS mixin to automatically produce uniformly sized and spaced flex items that will be flush with both the left and right sides of the container while avoiding javascript entirely.

If you have a flex container with rules like this:
```
.flex-container {
  display: flex;
  justify-content: flex-start; // or flex-end
}
```
and you have the very specific need to keep all of the contained flex items a uniform width while ALSO having them be perfectly flush with both sides of the flex container, then this is just the thing for you.

Here we have the default case as an example:
`@include flex-cards( 24%, "flex-start", 0, 1)`

This specifies that each flex card item will have a width of 24% (arg 1) and decide the placement and omission of margins based on being packed left towards the start line (arg 2). Further, the  `offset` value of `0` (arg 3) indicates that there are no preceding flex items such as headings that must be skipped. The `interval` value of `1` (arg 4) indicates that there no siblings between flex items that must be ignored at regular intervals.

And now here is an example of the above with context.
```
.flex-container {
  display: flex;
  justify-content: flex-start;
  
  .flex-item {
    @include flex-cards( 24%, "flex-start", 0, 1);
  }
}
```

It's great, in a very specific sort of way, for product pages and stuff so they don't look SLIGHTLY out of alignment thereby upsetting the delicate sensibilities of your visitors.
