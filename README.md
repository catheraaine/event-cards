# Sparkbox Event Card Project
These HTML/CSS exercises are an attempt to write complete, semantic markup and accompanying styles.

To reenforce the semantic aspect, I will break down [single-card.html](https://github.com/catheraaine/event-cards/blob/master/single-card.html) and explain my choices:

```
<article >
  <div class="vcard">
    <h2 class="url fn"><a href="http://www.lindseystirling.com/">Lindsey Stirling</a></h2>
    <ul>
      <li datetime="2016-07-22">
        July 22-24, 2016
      </li>
      <li>
        <span class="url org"><a href="http://wayhome.com/" title="WayHome Website">WayHome Music & Arts</a></span>
        <span class="adr">
          <span class="locality">Oro-Medonte</span>,
          <span class="region">On</span>,
          <span class="country-name">Canada</span>
        </span>
      </li>
    </ul>

    <img src="https://www.dropbox.com/s/g5qwby9vmoeswuk/lindsey.png?raw=1" alt="Lindsey and her violin." class="photo" />

  </div>
</article>
```

### `<article>`
I encase the entire card with an `<article>` tag. I could have gone with `<section>`, however, I believe that a single event card makes sense outside of the multi-card page setting, and it may be useful within the context of an RSS feed. So `<article>` works.

### `<div class="vcard">`
Speaking with [Ben](https://twitter.com/bencallahan), and later [Philip](https://twitter.com/zastrow), it seems that hCard/vCard is a good choice for this type of document. The vCard standards allow devices like Gmail and iOS to identify specific types of data on a website.

Philip also pointed out that adding the `vCard` class to my article tag may not be a good semantic choice (since there are set style guides), so I have elected to use a separate `<div>` as a container.

### `<h2 class="url fn">`
Here I have chosen an `<h2>` element, as I will likely have at least an `<h1>` on my full page, in the header. The `<h2>` will contain the names of performing artists, and is likely the second most important bit of information on the page, both for accessibility and SEO.

(Stylistically, my multi-card page will likely include a number of artists, as opposed to a single specific artist. If I choose a single artist, it would make more sense to put the artist name in the `<h1>` and something like 'event schedule' or the specific location in the `<h2>`.)

The class `fn` is used by vCard to describe someone's `Full Name`, and `url` tells vCard this link is a link that relates to the identified `fn`.

This specific `<h2>` does contain a link to the artist's website.

### `<ul>`
Each event card needs two pieces of information: a date and a location.

I have chosen to organize these items in an unordered list. A *list*, because the two items are more related than separate headings or paragraphs, but not so related to be in the same heading or paragraph. An *unordered* list, because the items make sense no mater how they are displayed on the page.

### `<li datetime="2016-07-22">`
The first `<li>` on my event card is the date of the event. As I said above, technically this could be before or after the venue. I chose above only because it looks nicer.

I have included the `datetime` attribute, because the content of this `<li>` is just a date. Thanks [Nate](https://twitter.com/nathanAlan) for showing me this attribute!

### `<li> <span class="url org">`
I have decided to make the second `<li>` include both the venue name and venue location. It may make sense to split these into two separate `<li>`s. I am not sure there is a wrong answer in this place. I made the choice to keep them together as, to me, the name of the venue is just a piece of the event location.

The name of the venue fits nicely within a vCard `org` class, once again with a `url` class to identify that the included link takes you to the venue website.


### `<span class="adr">`
Another vCard convention is to wrap addresses in an `adr` container class. Inside this class, you can identify specific pieces of an address with classes such as `locality`, `region`, and `country-name`. I have used these accordingly.

I could improve the usability of this section of my event card by adding in the full address of the venue and/or map data.

### <img>
This image is another feature Ben helped me to improve. Originally, I had the `<img>` located at the top of the card. However, the image itself is not that important to the content of the page. It is mostly a style image, though it would help a visual person quickly find the event on the page, if he or she recognized the artist. So the image is still content.

For that reason, I chose to keep this image in the markup, but move it to the very end of the card.



**And that's all! Look for my styles and multi-card layout, which should be up soon!**  
