#How to make a new theme for CSG

##Introduction

So, you want to make your own theme? It's simple, really! Just follow this short guide!

##Keywords

CSG replaces keywords from the source with actual content during generation. For example, let's take the unprocessed HTML file for BluFade.

![Screenshot](http://i.imgur.com/6NBhBUk.png)

In the screenshot you can see the most vital keywords for the functionality of a website. These are

- `$WEBSITE_TITLE` is replaced with the title of the site.
- `$PAGE_TITLE` is the title of the page, decided from the filename of the Markdown file.
- `$PAGE_URL` (not shown) is the relative URL to the page.
- `$PAGE_CONTENT` is the generated HTML from processing the Markdown.
- `$WEBSITE_FOOTER` is replaced with the footer of the site.
- `$CSG_INFO` is a string of characters which tells the viewer what version was used to generate this page and when (in UTC).

##Navigational buttons

The interpreter requires there to be navigational buttons which are decided where to be placed based on the source-code. It looks for the presence of `$PAGE_TITLE` and `$PAGE_URL` at the same line and basically clones that line for every button.

For example, in BluFade it's specified as this:

    <table id="pageheader_links">
	    <tr>
            <a href="$PAGE_URL"><td class="tablebutton">$PAGE_TITLE</td></a>
        </tr>
    </table>

This means that after a processing it could look like this:

    <table id="pageheader_links">
	    <tr>
            <a href="home.html"><td class="tablebutton">Home</td></a>
            <a href="ourgreatproduct.html"><td class="tablebutton">Our Great Product</td></a>
            <a href="testimonials.html"><td class="tablebutton">Testimonials</td></a>
            <a href="aboutus.html"><td class="tablebutton">About Us</td></a>
        </tr>
    </table>

##Conclusion

This simple guide should set you off in no time! Have fun!