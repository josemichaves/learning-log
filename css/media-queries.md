# Media Queries

Media queries are a way to target browser by certain characteristics, features, and user preferences, then apply styles or run other code based on those things. Perhaps the most common media queries in the world are those that target particular viewport ranges and apply custom styles, which birthed the whole idea of responsive design.

![Syntax of a media query](../.gitbook/assets/image%20%2866%29.png)

* Media: The first ingredient in a media query recipe is the @media rule itself, which is one of many CSS at-rules.
* Media types: What type of media are we trying to target? In many \(if not most\) cases, you’ll see a `screen` value used here, which makes sense since many of the media types we’re trying to match are devices with screens attached to them.

  But screens aren’t the only type of media we can target, of course. We have a few, including:

  * `all`: Matches all devices
  * `print`: Matches documents that are viewed in a print preview or any media that breaks the content up into pages intended to print.
  * `screen`: Matches devices with a screen
  * `speech`: Matches devices that read the content audibly, such as a screen reader. 

* Media feature: Once we define the type of media we’re trying to match, we can start defining what features we are trying to match it to. We’ve looked at a lot of examples that match screens to width, where `screen` is the _type_ and both __`min-width` and `max-width` are _features_ with specific values. There are a lot of media features available such as `width, height, resolution, display-mode, video-resolution, device-width, etc.`
* Operator: Media queries support logical operators like many programming languages so that we can match media types based on certain conditions. The `@media` rule is itself a logical operator that is basically stating that “if” the following types and features are matches, then do some stuff. We have `and`, `or`\(we can separate with a comma also\) and `not`.

```css
body {
  --bg-color: white; 
  --text-color: black;

  background-color: var(--bg-color);
  color: var(--text-color);
}

@media screen and (prefers-color-scheme: light) {
  body {
    --bg-color: black;
    --text-color:white;
  }
}
```

Here we can see a media query that will change the color schema depending what the user prefers.

