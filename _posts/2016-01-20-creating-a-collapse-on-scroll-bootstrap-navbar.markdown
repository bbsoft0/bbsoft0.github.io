---
layout:     post
title:      "Creating a Collapse-On-Scroll Bootstrap Navbar"
subtitle:   "Using the Built In Bootstrap Affix Plugin"
date:       2016-01-20 13:00:00
author:     "Barbu Bujor"
---

<div class="row">

	<div class="col-lg-8 col-lg-offset-2 col-md-10 col-md-offset-1">

		<p>Collapsing navigation bars are a very popular design choice, and can add a nice dynamic touch to many types of websites. There are loads of plugins and code snippets out there to help you achieve the effect, but what makes this method unique is that it uses built-in Bootstrap components to create the animated collapse-on-scroll effect rather than using additional third party plugins. This means you wont have to import any extra JavaScript libraries into your project or add any other additional resources other than your core Bootstrap files and jQuery.</p>

		<p>In this short, beginner level code review, we won't be using anything more than the default Bootstrap navbar, a bit of jQuery to activate the Bootstrap Affix plugin, and a little bit of custom CSS. For the more advanced designers out there, feel free to use your CSS pre-processor of choice or any other tools, but for the purposes of this guide I wanted to keep things as simple as possible!</p>

		<p>That being said, here is the collapse-on-scroll Bootstrap navbar that we will be exploring in this post:</p>

	</div>

	<div class="col-lg-12">

		<p data-height="540" data-theme-id="0" data-slug-hash="yepJoX" data-default-tab="result" data-user="davidtmiller" class='codepen'>See the Pen <a href='http://codepen.io/davidtmiller/pen/yepJoX/'>Easy Bootstrap Collapsing Animated Navigation on Scroll</a> by David Miller (<a href='http://codepen.io/davidtmiller'>@davidtmiller</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
		<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

	</div>

	<div class="col-lg-8 col-lg-offset-2 col-md-10 col-md-offset-1">

		<h2 class="section-heading">HTML Markup</h2>

		<p>First we'll take a look at the HTML markup for this menu customization. It's not that far from the default Bootstrap menu.</p>

	</div>

	<div class="col-lg-12">

		<p data-height="540" data-theme-id="0" data-slug-hash="yepJoX" data-default-tab="html" data-user="davidtmiller" class='codepen'>See the Pen <a href='http://codepen.io/davidtmiller/pen/yepJoX/'>Easy Bootstrap Collapsing Animated Navigation on Scroll</a> by David Miller (<a href='http://codepen.io/davidtmiller'>@davidtmiller</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
		<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

	</div>

	<div class="col-lg-8 col-lg-offset-2 col-md-10 col-md-offset-1">

		<p>The first addition you'll see is that we're adding a new ID to the <code>nav</code> element. The new ID is added so we can target the navbar when we add the jQuery to activate the affix plugin. Other than the addition of a new ID, make sure you're using the <code>navbar-fixed-top</code> class when building your navbar so the positioning will be correct. The real magic happens when the CSS and JavaScript come into play.</p>

		<h2 class="section-heading">Activating the Affix Plugin using jQuery</h2>

		<p>The affix plugin is what makes this technique work. What it does, in effect, is changes a CSS class on the navbar when the page scrolls from a certain point. In this example, at 100px below the top of the page, the affix plugin will remove the <code>.affix-top</code> class from the navbar and replace it with the <code>.affix</code> class instead. This allows us to write custom CSS styles for each class that will change the look and feel of the menu bar when the page scrolls.</p>

	</div>

	<div class="col-lg-12">

		<p data-height="200" data-theme-id="0" data-slug-hash="yepJoX" data-default-tab="js" data-user="davidtmiller" class='codepen'>See the Pen <a href='http://codepen.io/davidtmiller/pen/yepJoX/'>Easy Bootstrap Collapsing Animated Navigation on Scroll</a> by David Miller (<a href='http://codepen.io/davidtmiller'>@davidtmiller</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
		<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

	</div>

	<div class="col-lg-8 col-lg-offset-2 col-md-10 col-md-offset-1">

		<p>The jQuery snippet in the CodePen above targets the new ID we gave to the navbar, and it tells Bootstrap to add the affix classes and change between the two classes when the page passes 100px down from the top of the page.</p>

		<h2 class="section-heading">Custom CSS Styles</h2>

		<p>Finally, the custom CSS styles bring the whole concept together. We're adding a few rules to the navbar itself, in this case the <code>.navbar-default</code> class, and we're adding a rule to the <code>.affix</code> class. You'll see a CSS transition and some vertical padding added to the <code>.navbar-default</code>, and you'll see the vertical padding being reduced to 0 in the <code>.affix</code> class.</p>

	</div>

	<div class="col-lg-12">

		<p data-height="380" data-theme-id="0" data-slug-hash="yepJoX" data-default-tab="css" data-user="davidtmiller" class='codepen'>See the Pen <a href='http://codepen.io/davidtmiller/pen/yepJoX/'>Easy Bootstrap Collapsing Animated Navigation on Scroll</a> by David Miller (<a href='http://codepen.io/davidtmiller'>@davidtmiller</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
		<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

	</div>

	<div class="col-lg-8 col-lg-offset-2 col-md-10 col-md-offset-1">

		<p>Notice that we're putting all of the custom styles for the navbar in a media query. The purpose of this is to keep the mobile functionality of the default Bootstrap navbar unaffected. We only want the navbar to collapse when scrolling down when the menu items are not collapsed, or in other words, when the screen width exceeds 768px. On mobile devices, the collapsing navbar is not necessary.</p>

		<h2 class="section-heading">Suggested Customization Options</h2>

		<p>With this navbar setup you can add more custom styles apart from the padding being reduced when the user scrolls down on the page. You can customize the font color, background color of the navbar, the transparency of the navbar, or even the font size when the user scrolls down. To see an example of this same technique in use with some more custom styles added, check out the <a href="http://startbootstrap.com/template-overviews/creative/">Creative theme on Start Bootstrap</a>.</p>

		<p>Thanks for checking out this short code review, and good luck!</p>

	</div>

</div>
