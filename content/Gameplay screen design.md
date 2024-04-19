>[!info] Overview
> This doc describes the requirements for the main gameplay screen throughout Underminers Revolution. It will be able to accommodate the narrative gameplay and be styled to reflect the different worlds that the player traverses.

# Flow
If the player enters from [[Map screen design]], they will encounter: 
1. This screen
2. [[Level end modal]]

If the player enters from the last game screen, they will encounter:
1. [[Level start modal]]
2. This screen
3. [[Level end modal]]

# Requirements

Describes UI/UX requirements for this screen.
From left to right on screen:
## Info rail (left)
Mostly non-interactive elements:
- level #
- turn timer
- character/health
- info modals are aligned over the left side of the screen when they appear
- level goals
### Info modal
Info modals show details about various objects in the game. The modal is for info purposes only, so the only interaction is to open or close.
- tap and hold OR mouse right click(?) or long hover(?) on board items opens an info modal
	- modal is aligned on left side of screen
    - for monsters, shows their attack pattern, health, weakness(?)
    - for items, show description and/or how to use(?)
    - for rocks and other static elements, show flavor text
    - highlight the thing to make sure it's clear what the modal is referring to

## Game board
- "up next" rocks at top
- monsters in board show attack/health info — always on (with an option to turn off in menu. or option for minimal view?)
- Go bar with:
	- rotate clockwise/counterclockwise buttons
	- "go" button — executes the rotation so that any effects resolve OR executes mining action on the selected rock group
		- disabled by default

**Game board interactions**
- buttons for rotate clockwise/counterclockwise
	- shows the rotation preview, no gravity consequences are executed
	- need to visually show that it's just a preview:
		- Board border color changes
		- "Go button" becomes active state
		- Potion/rune action panel becomes disabled (lower saturation and opacity)
		- A pulsing opacity animation on the board might be good (kind of like a blinking cursor or other sort of wait animation)?
	- need a way to show that the board is rotated in "preview" mode
- tapping on a group of rocks highlights them in preparation for mining
	- for groups of <3, there is an error animation to show that you must select a group of 3 or more of the same rocks
	- once a valid group is selected:
		1. the go button is active
		2. the rotate buttons are disabled
		3. the potion/rune action panel is disabled

## Action rail (right)
The right rail shows interactive elements. Ideally, the left/right rails can be swapped for different handedness.
Contains:
- settings button (opens [[Settings menu modal]])
- attack range toggle (shows hints/monster hit range)
- potion belt:
    - shows up to 4(?) potions in inventory, each of which is selectable. May have more than one of a type of potion, in which case shows a # on the icon
    - selecting a potion shows its description and a "use" button in a modal
    - for potions that require a target:
	    1. Use button is disabled until target is selected
	    2. on desktop, show dotted line targeting reticules on hover. on click, show solid targeting reticules
	    3. on touch screen, tapping should select the target. More specifically, on touch down, show the dotted lines. if user drags, the reticules should also move. on touch up, show solid line reticules.
	    4. once target is selected, the use button is active
    - Use button activates the potion and uses it up
- rune bar — not scoped for demo

# Designs & Prototypes
https://www.figma.com/file/8cF3NfD5gMtko1Qm78B3rS/Demo-Design?type=design&node-id=401%3A604&mode=design&t=Iw1krlme8LSYFL8s-1


❓How do displays differ between phone/tablet? Can we set different images to display on each, similar to providing retina size and standard size images for browsers? (is that a thing anymore?)

**Technical considerations**

Design for landscape and portrait mode - esp for tablet, maybe Switch later