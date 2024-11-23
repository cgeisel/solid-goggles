How does this work?

Start with tcod, which is a sort of uber library for making roguelikes. Seems a bit like cheating.

Import some classes Engine, Entity, EventHandler and a generate_dungeon function.

main runs and returns None
    sets the screen width and height
    sets the map width (same) and height (5 pixels less for some reason)

    sets the max room size to 10
    min room size to 6
    max rooms on a map are 30
    max monsters in a room are 2

    use tcod to load an image file that has a set of tiles on it, one with 32 columns and 8 rows, and map it to a character map used by roguelikes

    the function returns a Tileset object and used later for rendering the screen.

    create an EventHandler
    create a player Entity, place it at the x/2 and y/2 location (center of the map), tell it to be a @ character and it's color is 255, 255, 255 or white

    create a GameMap with generate_dungeon using the max/min values from above and the player entity

    create an Engine with an event handler and game map, and a player

    create a terminal context (I'm not sure what this means exactly... looks like it manages the window and rendering...) with the height, width, tilesest, etc.

    create a console in the context
    create an infinite loop that...
        calls the engine.render() method
        listens for events
        if there's an event, passes it to the engine's event handler

