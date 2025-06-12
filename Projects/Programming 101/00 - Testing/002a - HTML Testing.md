---
Uke: 1
Dag: "1"
Emne: HTML
tags:
  - codetest
  - HTML
---
## HTML-oppgaver
Test oppgavene i [Replit](https://replit.com/@Nenuvar/DandD-Character)
### Tags, paragrahps and attributes
1. Lag en nettside med en overskrift og et paragraf
```html
<!DOCTYPE html>

<html>
<body> 
	<h3>My D&D Character</h3>
	<p>Nenuvar is their name. They are a huge Firbolg druid.</p>
</body>
</html>
```
2. Lag en nettside med en utgående lenke
```html
<!DOCTYPE html>
<html>
<body>
	<h3>My D&D Character</h3>
	<p>Nenuvar is their name. They are a huge Firbolg druid.</p>
	<a>This is a link to a Pinterest illustration of were Nenuvar lives.</a>
</body>
</html>
```
3. Display an image on your website. H: 400px, W: 350px
```html
<img src="https://i.pinimg.com/736x/85/32/1d/85321d0fd65ed2358d608306faf73d89.jpg" height="400" width="350">
```
- an image tag does not need to be closed `</img>` because it doesn't display any text. It only uses the `src` attribute (src=source) to display the image link on the website. 
- Remember that the image link needs to be a direct link to the image itself `.jpg`
4. Add a paragraph with three new lines. Use two different methods to add the separated paragrahps. Add a line between two of the paragraphs
```html
<h2>Method 1</h2>
Line 1
Line 2
Line 3
<h2>Method 2</h2>
Line 1
Line 2
Line 3
```

#### Answers
1. Lag en nettside med en overskrift og et paragraf
```html
<!DOCTYPE html>

<html>
<body> 
	<h3>My D&D Character</h3>
	<p>Nenuvar is their name. They are a huge Firbolg druid.</p>
</body>
</html>
```
2. Lag en nettside med en utgående lenke
```html
<!DOCTYPE html>
<html>
<body>
	<h3>My D&D Character</h3>
	<p>Nenuvar is their name. They are a huge Firbolg druid.</p>
	<a>This is a link to a Pinterest illustration of were Nenuvar lives.</a>
</body>
</html>
```
3. Display an image on your website. H: 400px, W: 350px
```html
<img src="https://i.pinimg.com/736x/85/32/1d/85321d0fd65ed2358d608306faf73d89.jpg" height="400" width="350">
```
- an image tag does not need to be closed `</img>` because it doesn't display any text. It only uses the `src` attribute (src=source) to display the image link on the website. 
- Remember that the image link needs to be a direct link to the image itself `.jpg`
4. Add a paragraph with three new lines. Use two different methods to add the separated paragrahps. Add a line between two of the paragraphs
```html
<h2>Method 1</h2>
Line 1
Line 2
Line 3
<h2>Method 2</h2>
Line 1
Line 2
Line 3
```

### Formatting Elements
1. Follow the instructions for formatting each line
	Bonus for doing it in different ways
	Bonus: Why are we using the `<pre>` tag?

```html
<pre>
This is a bold text

This is an italic text

This line is emphasized

This line is italic

Highlight this line

Strikethrough this line

Underline this text

This line is smaller than the rest

This line looks inserted

This should be subscripted 0 2

This should be supascripted 0 2
</pre>
```

2. Colors: Follow the instructions for formatting each line
```html
<h2>This heading should be green with a background color of yellow</h2>
```

3. Comments. Comment out the marked lines
```html
This is a text
Comment out this line
```

#### Answers
1. Follow the instructions for formatting each line
	Bonus for doing it in different ways
	Bonus: Why are we using the `<pre>` tag?
		`Answer:` Because then the text will appear exactly as formatted in the source code. If not, every line would need the `<p>` tag. 
```html
<pre>
    <b>This is a bold text</b>
    <!--- bonus---> <strong>This is a bold text</strong>

    <i>This is an italic text</i>

    <em>This line is emphasized</em>

    <mark>Highlight this line</mark>

    <del>Strikethrough this line</del>

    <u>Underline this text</u>

    <small>This line is smaller than the rest</small>

    <ins>This line looks inserted</ins>

    This should be sub scripted 0<sub>2</sub>

    This should be super scripted 0<sup>2</sup>
</pre>
```

2. Colors: Follow the instructions for formatting each line
```html
<h2 style="color:green; background-color:yellow">This heading should be green with a background color of yellow</h2>
```

3. Comments. Comment out the marked lines
```html
This is a text
<!---Comment out this line--->
```

### Project_ D&D Character Website
#### Difficulty: Intro
Copy the code below into the editor at [Replit](https://replit.com/@Nenuvar/DandD-Character) and build the website following the instructions in the comments
```html
<!DOCTYPE html>
<html>
<!---Format the title to be: Nenuvar - D&D Characters --->
<!---Format the favicon to be this image: https://i.pinimg.com/736x/08/35/df/0835dfa95938ea0cc49c276781f82030.jpg  --->

D&D Characters <!---h3 heading, red text--->
Nenuvar <!---bold--->

<!---The paragrahp below should have each sentence on their own line--->
Nenuvar is a gentle Firbolg druid who lives in a deep, green canyon hidden in the forests of Anoria. <!---`Anoria` in italic --->
<!---Format `Firbolg` to be an external link that opens in a new tab: https://www.dndbeyond.com/posts/287-putting-the-fur-in-firbolg-the-evolution-of-a --->
They spend their days studying bugs — especially the yellow ones that glow like drops of sunlight. <!---`yellow` in yellow, bold --->
<!---Add a line here --->
<!---display the image in the link in this format: height: 400px, width: 350px --->
https://i.pinimg.com/736x/85/32/1d/85321d0fd65ed2358d608306faf73d89.jpg

<!---display this text smaller than the rest of the text and have it beneath the image--->
Nenuvar makes their home in a verdant, water-veined canyon hidden deep within the ancient forests of Anoria. 

<!---display these elements as a list of Nenuvar's goals in life--->
Nenuvar's Life Goals <!---h4 heading, green text--->
Find a bug no one’s ever seen
Build a cozy bug hotel in the canyon, especially for yellow bugs
Learn to speak Beetle
Ride a giant dragonfly into the sunset 
Make people love bugs (or at least not scream).


</html>
```
#### Difficulty: Medium
```html
<!DOCTYPE html>
  <!-- Title should be "HTML Practice Test - Aränòr Explorer" -->
  <!-- Add a favicon using this image: https://i.pinimg.com/736x/6e/49/52/6e49527e1977818e4dfac3f34f1cb519.jpg -->
  <!-- Use an h1 heading for "Welcome to Aränòr!" -->
  <!-- Style it to be green using inline CSS -->

  <!-- Add a horizontal line -->

  <!-- This paragraph describes Aränòr. Format the text this way
  Aränòr in bold
  Name of continents in italic
  Races. Add external link to DnD Beyond that opens in new tab: https://www.dndbeyond.com/classes/3-druid?srsltid=AfmBOor2eQjP8_LEFnr5nMWS3fBIKmVQnTksm2oT5XKm-_N4W_f2Sv2h
  Monsters or creatures. Add external link to DnD Beyond that opens in new tab:https://www.dndbeyond.com/spells/2619047-conjure-elemental?srsltid=AfmBOoqJwP6igqFgc_ta5HrTeZh4M803aELVWVvk61PTWftfegEzGyCT
   -->
  <!-- Aränòr is a realm where wild magic flows through the land, shaping the world in unpredictable ways. The continent of Arborìon rises from the earth as a colossal tree, home to druids, elemental guardians, and whispering winds. In this land, every leaf remembers, and every stone listens. --> 

  <!-- Add a link to https://www.dndbeyond.com/ in a new tab -->
  <!-- Use "Visit D&D Beyond" as the link text -->

  <!-- Add an image from this URL: https://i.pinimg.com/originals/8c/bc/d1/8cbcd1a20f73c68d8ec4c0e3549345ec.jpg -->
  <!-- Style the image to be 350px wide and 400px tall -->

  <!-- Add a caption under the image that is smaller than the rest of the text -->
  <!-- "A hidden glade within the heart of the Ancientspire, said to glow under moonlight." -->

  <!-- Add a break line and show the following text as-is:
    Ancientspire Log: 
    - Coordinates: X:112, Y:77
    - Status: Verdant and humming
  -->

  <!-- Create a table with 2 columns and 2 rows:
       - Column 1: Region
       - Column 2: Known For
       - Row 1: Stormharbour Reach | Shipwrights and stormbinding rituals
       - Row 2: Ithril Aeries | Ancient celestial observatories and sky-whales
  -->

  <!-- Add a list of 3 mythical creatures (ordered list) -->
  <!-- 1. Moonshadow Stag
       2. Emberwyrm
       3. Glass-Eyed Siren
  -->

  <!-- Add a description list of 2 terrain types and their descriptions -->
  <!-- Fogbarrow — A dense, haunted swamp veiled in luminous fog
       Sunfire Cliffs — Red-orange plateaus that pulse with solar energy
  -->

  <!-- Add a bold, italic, underlined, and strike-through version of the word "Adventure" -->

  <!-- Add two span elements inside a paragraph:
       One should be red text: "Beware the glowing thorns"
       The other green: "Trust the moss-covered stones"
  -->

  <!-- Add subscript (H2O) and superscript (CO2) text showing this example: 
       H2O is vital, but so is CO2
  -->

  <!-- Use symbols like copy, hearts, and dollar -->
  <!-- Text: "All content copy 2025 by the Aränòr Cartographic Guild. Support us with dollar and get a map pin shaped like a hearts!" -->

  <!-- Create an iframe showing https://www.openstreetmap.org -->

  <!-- Create a form with:
       - A label and input for name: "Name:"
       - A checkbox for "Are you a Dungeon Master?"
       - A submit button
       - Use POST as the method and "#" as the action for now
  -->
  <!-- Add this line underneath the form: -->
  <!-- This form collects user information for exploring the Aränòr Archives -->
</html>
```
#### Answers
##### Project_ D&D Character Website
###### Difficulty Intro
Build this website following the instructions in the comments
```html
<!DOCTYPE html>
<html>
  <head>
    <title>
      Nenuvar - D&D Characters
    </title>
    <link rel="icon" href="https://i.pinimg.com/736x/08/35/df/0835dfa95938ea0cc49c276781f82030.jpg"
  </head>
  <body>
  <pre>
<h3 style="color:red">D&D Characters</h3> 
<b>Nenuvar</b> 
Nenuvar is a gentle <a href="https://www.dndbeyond.com/posts/287-putting-the-fur-in-firbolg-the-evolution-of-a" target="_blank">Firbolg</a> druid who lives in a deep, green canyon hidden in the forests of <i>Anoria</i>. 
They spend their days studying bugs — especially the <b style="color:yellow">yellow</b> ones that glow like drops of sunlight. 
<!---Add a line here --->
<img src="https://i.pinimg.com/736x/85/32/1d/85321d0fd65ed2358d608306faf73d89.jpg" height="400" width="350"> 
<small>Nenuvar makes their home in a verdant, water-veined canyon hidden deep within the ancient forests of Anoria.</small>
<h4 style="color:green">Nenuvar's Life Goals</h4> 
Find a bug no one’s ever seen <!---display these elements as a list of Nenuvar's goals in life--->
Build a cozy bug hotel in the canyon, especially for yellow bugs
Learn to speak Beetle
Ride a giant dragonfly into the sunset 
Make people love bugs (or at least not scream)
  </pre>
  </body>
</html>
```

###### Difficulty Medium
```html
<!DOCTYPE html>
  <!-- Title should be "HTML Practice Test - Aränòr Explorer" -->
  <!-- Add a favicon using this image: https://i.pinimg.com/736x/6e/49/52/6e49527e1977818e4dfac3f34f1cb519.jpg -->
  <!-- Use an h1 heading for "Welcome to Aränòr!" -->
  <!-- Style it to be green using inline CSS -->

  <!-- Add a horizontal line -->

  <!-- This paragraph describes Aränòr. Format the text this way
  Aränòr in bold
  Name of continents in italic
  Races. Add external link to DnD Beyond that opens in new tab: https://www.dndbeyond.com/classes/3-druid?srsltid=AfmBOor2eQjP8_LEFnr5nMWS3fBIKmVQnTksm2oT5XKm-_N4W_f2Sv2h
  Monsters or creatures. Add external link to DnD Beyond that opens in new tab:https://www.dndbeyond.com/spells/2619047-conjure-elemental?srsltid=AfmBOoqJwP6igqFgc_ta5HrTeZh4M803aELVWVvk61PTWftfegEzGyCT
   -->
  <!-- Aränòr is a realm where wild magic flows through the land, shaping the world in unpredictable ways. The continent of Arborìon rises from the earth as a colossal tree, home to druids, elemental guardians, and whispering winds. In this land, every leaf remembers, and every stone listens. --> 

  <!-- Add a link to https://www.dndbeyond.com/ in a new tab -->
  <!-- Use "Visit D&D Beyond" as the link text -->

  <!-- Add an image from this URL: https://i.pinimg.com/originals/8c/bc/d1/8cbcd1a20f73c68d8ec4c0e3549345ec.jpg -->
  <!-- Style the image to be 350px wide and 400px tall -->

  <!-- add a caption under the image that is smaller than the rest of the text -->
  <!-- "A hidden glade within the heart of the Ancientspire, said to glow under moonlight." -->

  <!-- Add a break line and show the following text as-is:
    Ancientspire Log: 
    - Coordinates: X:112, Y:77
    - Status: Verdant and humming
  -->

  <!-- Create a table with 2 columns and 2 rows:
       - Column 1: Region
       - Column 2: Known For
       - Row 1: Stormharbour Reach | Shipwrights and stormbinding rituals
       - Row 2: Ithril Aeries | Ancient celestial observatories and sky-whales
  -->

  <!-- Add a list of 3 mythical creatures (ordered list) -->
  <!-- 1. Moonshadow Stag
       2. Emberwyrm
       3. Glass-Eyed Siren
  -->

  <!-- Add a description list of 2 terrain types and their descriptions -->
  <!-- Fogbarrow — A dense, haunted swamp veiled in luminous fog
       Sunfire Cliffs — Red-orange plateaus that pulse with solar energy
  -->

  <!-- Add a bold, italic, underlined, and strike-through version of the word "Adventure" -->

  <!-- Add two span elements inside a paragraph:
       One should be red text: "Beware the glowing thorns"
       The other green: "Trust the moss-covered stones"
  -->

  <!-- Add subscript (H2O) and superscript (CO2) text showing this example: 
       H2O is vital, but so is CO2
  -->

  <!-- Use symbols like copy, hearts, and dollar -->
  <!-- Text: "All content copy 2025 by the Aränòr Cartographic Guild. Support us with dollar and get a map pin shaped like a hearts!" -->

  <!-- Create an iframe showing https://www.openstreetmap.org -->

  <!-- Create a form with:
       - A label and input for name: "Name:"
       - A checkbox for "Are you a Dungeon Master?"
       - A submit button
       - Use POST as the method and "#" as the action for now
  -->
  <!-- Add this line underneath the form: -->
  <!-- This form collects user information for exploring the Aränòr Archives -->
</html>
```