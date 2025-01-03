## Module 1

What is a game?

A computer game is a software program in which one or more players make decisions through the control of game objects and resources.

- Organized form of play


Types of games

- First person game: is when the screen shows the same scene of what the a player sees.
- Third person game: is when the player sees his self and the opponent character or ship or object.

History of computer games:

- In 1972, Atari
- In 1978-1980, Nintendo
- In 1989, Nintendo released a Game Boy
- In 1990, Nintendo released Super Mario 3
- In 1991, Sony starts developing CD technology
- In 1992, PC gaming starts
- In 1995, Windows 95 released with Game SDK and Direct-X
- Microsoft released Xbox

---
## Module 2

Motivation factors for computer game:

- Many players enjoy playing games because they provide challenge.
- Players want to socialize.
- Player wants respect and proud.
- Players wants Emotional Experience.
- Player wants to Explore.
- Players wants to Fantasize

What do players expect?

- Player expects a consistent world.
- Player expects to understand the game world's bound.
- Player expect reasonable solution to work.
- Player expects direction.
- Player expects to accomplish a task incrementally.
- Player expects increase of hardness.

Genre of games:

- Adventure Game
	- Story-based
- Action Game
	- Real time game
- Real-Time Strategy (RTS)
	- Requires players to manage a limited set of resources to achieve a pre-determined goal.
- Turn-Based Strategy
	- Players take turns
- Role Playing Game (RPG)
	- Players expect to be able to micromanage their characters
- Massively Multiplayer Online Role-Playing Game (MMORPG)
	- RPG but with players over the Internet.

---
## Module 3

The following depends on the game content:
- Physics
- History
- Education
- Geography
- Sociology

#### Designer

Three types:

- Lead game designer
- Lead level designer
- Interface designer

Game designer:

- A visionary - overall view of the game
- Able to communicate and present ideas
- Creative and imaginative
- Technically savvy
- Artistically astute
- A good writer
- MUST HAVE PASSION FOR THE GAME!

Game designer responsibility:

- Give input on game design issues
- Propose game play ideas
- Build and test scenarios/missions

Level designer responsibility:

- Design detailed levels
- Designs and implements game content
- Evaluates levels of bugs, playability, fun

#### Producer

Producer who coordinate everyone's effort

- Manage a single game project.
- Ensures project is delivered on time.
- Ensures that the project is delivered within budget.
- Ensures quality.

#### Game Engine

It is a software designed for the creation and development of video games.

It provides a core functionalities including:
- Rendering
- Physical engine
- Sound engine
- Animation engine
- Artificial Intelligence
- Networking engine
- Memory management engine

Commercial engines like:
- Unreal Engine 3
- CryEngine 3
- Unity 3D

Open sauce engines:
- OGRE
- Panda3D
- Crystal Space

Advantages:
- Less development time required

Disadvantages:
- Dependent on other licensing scheme for release

**Graphics Engine**
It generates 2D or 3D animation graphics.

**Audio Engine**
Audio engine is the component which consists of algorithms related to sound.

**Physics Engine**
It emulates the laws of physics realistically. And it includes API for *collision detection*.

**Artificial Intelligence Engine**
Provides attack strategies.

## Module 4 | Phaser

What is the Phaser?

It is an HTML5 game framework which aims to help developers make powerful, cross-browser HTML5 games really quickly. *(open source)*

Phaser *scenes* are independent units or "worlds" within a game

```js
// Create a scence
class FirstScene extends Phaser.Scene {
	constructor() {
		super("FirstScene");
	}
}
```

```js
// Set scene image background

class FirstScene extends Phaser.Scene {
	constructor() {
		super("FirstScene");
	}
	preload() {
		this.load.image("bg", "assets,bg.jpg");
	}
	create() {
		this.add.image(300, 300, "bg");
	}
	update() {
	}
}
```

```js
const config = {
	width: 500,
	height: 500,
	backgroundColor: 0xff0000
}
const game = new Phase.game(config);
```
## Module 5 | Objects Manipulation

```js
// Add a text
this.add.text(150, 75, "Level 1", {
	font: "18px Arial",
	fill: "yellow"
})
```

```js
// Background positioning
create() {
	this.background = this.add.image(0,0, "bg");
	this.background.setOrigin(0,0);
}
```

```js
// Load objects
preload() {
	this.load.image("bg", "assets/bg.jpg");
	this.load.image("rocket", "assets/rocket.png");
}
create() {
	this.background = this.add.image(0,0, "bg");
}
```

```js
// Manipulate objects
/*
- Scaling
- Flipping
- Angel rotation
*/

this.rocket.setScale(1.5);
this.rocket.flipX = true; // flipY
```

```js
// Update function
// IMPORTANT
moveObject(obj, speed) {
	obj.x += speed;
	obj.angel += speed;
	if (obj.x > config.width)
		obj.x = 0
}

update() {
	this.moveObject(this.rocket, 2);
}
```

## Module 6 | Sprite Sheets

Sprite sheets is
- Fixed-size sheet
- Every frame in the sheet has exact same size
- Reference it using numbers
- Efficiently store and manage images frames of an animation

Benefits
- Reduced file size
- Improved performance
- Animation management
- Optimized memory usage

## Module 7 | Physics

```js
// Random position
rocket.setRandomPosition(0,0,config.width, config.height);
```

```js
// Environment bound
rocket.setCollideWorldBounds(true);
```

```js
// Prevent objects collisions
this.physics.add.collider(this.rocketSet, this.rocketSet);
```

## Module 8 | Cameras and Tile Sprites

Tile Sprite is a Sprite that has a repeating texture.

## Module 9 | Input

You can respond to input events from *keyboard*, *mouse*, and *gamepads*

## Module 10 | Output

Audio tag using HTML tag or Web Audio API.

Web Audio can do *positional audio*.

```js
this.sound.unlock();
this.sound.play("bg_audio", config);
```

```js
this.flying_audio = this.sound.add("flying_audio");

this.flying_audio.play();
this.flying_audio.pause();
this.flying_audio.resume();
this.flying_audio.stop();
```

## Module 11 | Extra

Overlap means no physics.
Collide has physics based response.