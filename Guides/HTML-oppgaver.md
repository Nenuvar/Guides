### HTML-oppgaver
Test oppgavene i [Replit](https://replit.com/@Nenuvar/DandD-Character)
#### Tags, paragrahps and attributes
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

##### Answers
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

#### Formatting Elements
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

##### Answers
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

#### Project_ D&D Character Website
Build this website following the instructions in the comments
```html
<!DOCTYPE html>
<html>
<body>
D&D Characters <!---h3 heading, red text--->
Nenuvar <!---bold--->

<!---The paragrahp below should have each sentence on their own line--->
Nenuvar is a gentle Firbolg druid who lives in a deep, green canyon hidden in the forests of Anoria. <!---`Anoria` in italic --->
<!---Format `Firbolg` to be an external link to this page: https://www.dndbeyond.com/posts/287-putting-the-fur-in-firbolg-the-evolution-of-a --->
They spend their days studying bugs — especially the yellow ones that glow like drops of sunlight. <!---`yellow` in yellow, bold --->
<!---Add a line here --->
<!---display the image in the link in this format: height: 400px, width: 350px --->
https://i.pinimg.com/736x/85/32/1d/85321d0fd65ed2358d608306faf73d89.jpg

<!---display this text smaller than the rest of the text and have it beneath the image--->
Nenuvar makes their home in a verdant, water-veined canyon hidden deep within the ancient forests of Anoria. 
</body>
</html>
```
##### Answers
###### Project_ D&D Character Website
Build this website following the instructions in the comments