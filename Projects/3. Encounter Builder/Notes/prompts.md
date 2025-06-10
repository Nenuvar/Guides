### Prompts
Forest clearing
```
A battlemap for D&D, showing a top-down view of a ruined stone castle courtyard. Crumbled walls, broken statues, and overgrown ivy cover the area. Clear pathing and variety in cover. Fantasy medieval style, moody daylight with overcast sky. Designed for use with minis.
```
- Creates a true top-down view of a detailed battlemap as described 
```
Top-down view battlemap for Dungeons & Dragons, high-resolution, fantasy style. Environment: ancient forest with overgrown ruins and mossy stone pillars. Includes terrain features like fallen logs, dense underbrush, scattered stones, and a small stream. Designed for tabletop RPG use. No characters or monsters, only terrain. Lighting: dappled sunlight through the trees. Realistic textures
```
- all if the above, and more realistic textures
[DALLE3 and gpt-image-1 Prompt Tips and Tricks Thread - Prompting - OpenAI Developer Community|Prompt Discussion](https://community.openai.com/t/dalle3-and-gpt-image-1-prompt-tips-and-tricks-thread/498040/68)
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