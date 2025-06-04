Features
- [x] Filter on environment
- [x] Dynamic CR calc based on party's level
- [x] Randomly select monsters
- [ ] Randomly insert short story beats
	Scene description
	Hero's motivation
	Monster's motivation
	Twist
```python
def generate_story(encounter, environment):
    """
    Generate a short story or flavor text for the encounter.
    :param encounter: List of monsters in the encounter.
    :param environment: The environment of the encounter.
    :return: A short story as a string.
    """
    main_monster = encounter[0].get("name", "a mysterious creature")
    story = f"In the {environment}, the adventurers stumble upon {main_monster}. "
    if len(encounter) > 1:
        story += "It is accompanied by its minions, ready to defend its lair."
    else:
        story += "It stands alone, guarding its territory fiercely."
    return story
```

- [x] Config file
	save folder path
	save party level
	save party size

- [ ] Add random treasure
```python
def generate_treasure(difficulty):
    """
    Generate random treasure based on the difficulty of the encounter.
    :param difficulty: The difficulty of the encounter (easy, medium, hard, deadly).
    :return: A list of treasure items.
    """
    treasure_table = {
        "easy": ["10 gold coins", "a healing potion"],
        "medium": ["50 gold coins", "a +1 weapon", "a scroll of fireball"],
        "hard": ["100 gold coins", "a +2 weapon", "a rare magic item"],
        "deadly": ["500 gold coins", "a legendary magic item", "a bag of holding"]
    }
    return random.sample(treasure_table[difficulty], k=2)
```
---

### **Dynamic Encounter Objectives**
- **Feature**: Generate objectives for the encounter, such as "Defend the village," "Retrieve the artifact," or "Survive the ambush."
- **Why**: Objectives add depth to encounters and make them more than just combat.
- **How**: Create a list of objectives and randomly select one based on the environment or monsters.

**Example**:
```python
def generate_objective(environment, main_monster):
    """
    Generate a random objective for the encounter.
    :param environment: The environment of the encounter.
    :param main_monster: The main monster in the encounter.
    :return: A string describing the objective.
    """
    objectives = [
        f"Defend the villagers from the {main_monster.get('name', 'enemy')} in the {environment}.",
        f"Retrieve the stolen artifact guarded by the {main_monster.get('name', 'enemy')} in the {environment}.",
        f"Survive the ambush set by the {main_monster.get('name', 'enemy')} in the {environment}.",
        f"Escort the caravan safely through the {environment}, avoiding the {main_monster.get('name', 'enemy')}.",
        f"Destroy the {main_monster.get('name', 'enemy')}'s lair in the {environment}."
    ]
    return random.choice(objectives)
```

---

### **Monster Synergy Suggestions**
- **Feature**: Suggest monsters that work well together (e.g., goblins with a hobgoblin leader, or wolves with a druid).
- **Why**: Synergistic encounters are more challenging and fun for players.
- **How**: Create a dictionary of monster synergies and use it to suggest minions for the main monster.

**Example**:
```python
MONSTER_SYNERGIES = {
    "Goblin": ["Hobgoblin", "Worg"],
    "Orc": ["Ogre", "Orc Shaman"],
    "Dragon": ["Kobold", "Dragonborn"],
    "Lich": ["Skeleton", "Zombie"],
    "Druid": ["Wolf", "Bear"]
}

def suggest_synergies(main_monster):
    """
    Suggest synergistic monsters to pair with the main monster.
    :param main_monster: The main monster in the encounter.
    :return: A list of suggested monsters.
    """
    name = main_monster.get("name", "Unknown")
    return MONSTER_SYNERGIES.get(name, [])
```

---

### **Environmental Effects**
- **Feature**: Add environmental effects like "thick fog," "lava flows," or "blinding sandstorm" to make encounters more dynamic.
- **Why**: Environmental effects can change the tactics and make encounters more memorable.
- **How**: Create a list of effects for each environment and randomly select one.

**Example**:
```python
ENVIRONMENTAL_EFFECTS = {
    "forest": ["Thick fog reduces visibility", "Falling branches deal damage", "Wildfire spreads rapidly"],
    "mountain": ["Rockslides block paths", "Thin air causes exhaustion", "Echoes confuse sound-based spells"],
    "swamp": ["Sticky mud slows movement", "Poisonous gas lingers", "Swarming insects distract players"],
    "desert": ["Blinding sandstorm", "Scorching heat causes exhaustion", "Shifting dunes obscure tracks"]
}

def generate_environmental_effect(environment):
    """
    Generate a random environmental effect for the encounter.
    :param environment: The environment of the encounter.
    :return: A string describing the effect.
    """
    effects = ENVIRONMENTAL_EFFECTS.get(environment, ["No special effects"])
    return random.choice(effects)
```

### **Encounter Replayability**
- **Feature**: Save the seed used for random number generation to allow the Dungeon Master to replay the exact same encounter.
- **Why**: Replayability is useful for testing or reusing encounters.
- **How**: Save the random seed and use it to regenerate the encounter.

**Example**:
```python
def save_seed(seed, folder_path):
    """
    Save the random seed to a file for replayability.
    :param seed: The random seed.
    :param folder_path: Path to the folder where the file should be saved.
    """
    os.makedirs(folder_path, exist_ok=True)
    file_name = "encounter_seed.txt"
    file_path = os.path.join(folder_path, file_name)
    with open(file_path, "w") as file:
        file.write(str(seed))
    print(f"\nSeed saved to: {file_path}")
```

---

### **Encounter Triggers**

- **Feature**: Generate a reason or trigger for the encounter, such as "a loud noise," "a magical disturbance," or "a fleeing NPC."
- **Why**: Triggers add context and make encounters feel more organic.
- **How**: Create a list of triggers and randomly select one.

**Example**:
```python
def generate_trigger():

    """

    Generate a random trigger for the encounter.

    :return: A string describing the trigger.

    """

    triggers = [

        "A loud noise echoes through the area.",

        "A magical disturbance draws the adventurers' attention.",

        "An NPC runs toward the party, screaming for help.",

        "The ground shakes violently, and monsters emerge.",

        "A strange artifact begins to glow, summoning creatures."

    ]

    return random.choice(triggers)
 ```

### **NPC Allies**

- **Feature**: Add NPC allies to the encounter, such as a wandering ranger, a local guard, or a captured prisoner who joins the fight.
- **Why**: NPC allies can add tactical depth and role-playing opportunities.
- **How**: Create a list of NPCs and randomly select one to join the encounter.

**Example**:
```python
def add_npc_ally():

    """

    Add an NPC ally to the encounter.

    :return: A dictionary representing the NPC ally.

    """

    npcs = [

        {"name": "Wandering Ranger", "cr": "1", "hp": 30, "role": "Ranged Support"},

        {"name": "Local Guard", "cr": "1/2", "hp": 20, "role": "Tank"},

        {"name": "Captured Prisoner", "cr": "0", "hp": 10, "role": "Distraction"}

    ]

    return random.choice(npcs)
```

### **Monster Behavior Profiles**

- **Feature**: Assign behavior profiles to monsters, such as "aggressive," "defensive," or "cunning."
- **Why**: Behavior profiles make encounters more dynamic and challenging.
- **How**: Add a behavior field to each monster and use it to influence their tactics.

**Example**:
```python
def assign_behavior(monster):

    """

    Assign a behavior profile to a monster.

    :param monster: The monster to assign a behavior to.

    :return: The monster with an added behavior field.

    """

    behaviors = ["Aggressive", "Defensive", "Cunning", "Territorial"]

    monster["behavior"] = random.choice(behaviors)

    return monster
```

### **Weather Effects**

- **Feature**: Add weather effects to the encounter, such as "heavy rain," "blizzard," or "scorching heat."
- **Why**: Weather effects can influence combat and add immersion.
- **How**: Create a weather table for each environment and randomly select one.

**Example**:
```python
def generate_weather(environment):

    """

    Generate a random weather effect based on the environment.

    :param environment: The environment of the encounter.

    :return: A string describing the weather effect.

    """

    weather_table = {

        "forest": ["Heavy rain", "Thick fog", "Sunny and clear"],

        "mountain": ["Blizzard", "Strong winds", "Clear skies"],

        "swamp": ["Humid and sticky", "Light rain", "Dense mist"],

        "desert": ["Scorching heat", "Sandstorm", "Cool night breeze"]

    }

    return random.choice(weather_table.get(environment, ["No special weather"]))
```
