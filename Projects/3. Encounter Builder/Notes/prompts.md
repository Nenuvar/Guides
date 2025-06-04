
```python
def generate_battlemap_prompt(environment):

# ...earlier code
    template = (

        "Fill in the following template for a D&D battlemap prompt, using the environment: {environment}.\n"

        "A top-down drone shot of a [main subject] located in/on/at a {environment}. "

        "[Key feature 1], [key feature 2], and [key feature 3] are present. "

        "[Atmospheric detail 1], and [atmospheric detail 2] enhance the mood. "

        "Battlemap style, hand-painted digital illustration, [lighting descriptor], no photorealism. "

        "Focused detail on the [focus area].\n"

        "Replace all bracketed sections with creative, setting-appropriate details. "

        "Do not include the bracket labels in your output. Maximum 480 characters including spaces."

    ).format(environment=environment)

# rest of the code...
```