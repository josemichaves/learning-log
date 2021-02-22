# Accesibility

The first important tthing about HTML accesibility is to write **semantic HTML**, that means to use the appropiate tags. Semantic HTML uses the tag that do what the tag means.

| Non semantic HTML | Semantic HTML |
| :--- | :--- |
| &lt;div&gt;Click me!&lt;/div&gt; | &lt;button&gt;Click me!&lt;/button&gt; |
| &lt;div&gt;I'm an article&lt;/div&gt; | &lt;article&gt;I'm an article&lt;/article&gt; |

This is important because there's people that need the use of screen readers, and can be more easy to the screen reader to read, and the person to interpret what the screen reader says if the HTML is semantic and have meaning.

Another important part of tthe accesibility and even the SEO is the proper use of the **headings**, they can diferentiate parts of the document or the article, and the search engines can index the webs via the headings. And also the users at first glance they only see the headings, so it's important to proper use it.

| Heading | Use |
| :--- | :--- |
| &lt;h1&gt;Heading 1&lt;/h1&gt; | Main headings |
| &lt;h2&gt;Heading 2&lt;/h2&gt; | Secondary headings |
| &lt;h3&gt;Heading 3 &lt;/h3 - &lt;h6&gt;Heading 6&lt;/h6&gt; | Different highlits of the document |

The **alternantive text** \(`alt`\), is a short description of what is in the image, the people who uses a screen reader, cannot see the image, so we need to best describe this image in a short description. That can be also used if the image fails or the browser cannot render, it will show the `alt`.

```markup
<img src="images/skiingInNorway.jpg"
 alt="A person skiing" />
```

![Here we can see, first is the image, but when we have a failure, the alt text shows up.](../../.gitbook/assets/peek-2021-02-22-23-10.gif)

We can also specify the language on what the webpage is written, this will help with SEO and with screen readers. With the tag `<html lang="{languageUsed}">` to specify in what language we wrote the webpage we need to use the [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) or [ISO 639-2](https://en.wikipedia.org/wiki/List_of_ISO_639-2_codes) code list of languages.

We also need to write clearly, that means to not use abbreviatures when possible \(February instead of Feb\), not use dashes \(1 to 3 instead of 1-3\), that will keep the reading easy for screen readers.

And the need of the use well writen links. A link need to tell exactly to the reader what this link will go or will do.

| Bad | Good |
| :--- | :--- |
| **Click here** | **Find out more about HTML** |
| **Read more...** | Read more about **how to eat healthy** |
| Buy tickets to Mars **here** | **Buy tickets to Mars here** |

