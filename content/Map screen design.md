>[!info] Overview
> This doc describes the requirements for the map screen, which includes:
> 1. Basecamp
> 2. Level Map (aka World Map)
> 
> The upper bound of the map is the family dining room, which is at the top of Basecamp. The bottom bound of the map is the further game level that the player has unlocked. The bottom of the map will get progressively longer.

# Navigation

The player doesn't directly navigate the player avatar. Instead, they navigate by selecting where they intend to go. This maintains consistent player input because on the gameplay screen, the player does not directly move their avatar either.

There are two main ways to navigate on the map screen:
1. [[#Selecting a destination]] — for example, to go to the library, the player selects the library in basecamp.
2. Using the [[#Quick Nav]] menu

## Selecting a destination
**Mobile/touchscreen**
On mobile/touchscreen, the player taps to access places (library, forge, etc.) to go to those places. To see the rest of the map, the player taps and drags the map up and down.

>[!info] FTUE
> A small animation or something early on instructs the player that they can drag to scroll (if they don't already try it).

**Desktop**
On desktop, clicking on a location takes them to that place. Eventually, show animation of the player going to the place. There will be a scroll bar/buttons to show that the player can scroll the screen. They should also be able to click/drag, use scroll wheel, or up/down arrow keys?

>[!info] FTUE
> A small tooltip should show up early on to let the player know that they can use the keyboard or mouse wheel or click and drag to scroll as well.

## Quick Nav
The Quick Nav is a sticky menu that allows the player to access certain places without needing to scroll to find it in the map. Selecting a Quick Nav option will trigger the avatar movement animation and scroll the view to the destination on the map.

The Quick Nav options are:
- Current story point — This is a contextual button that takes the player to the current highest priority task. Most often, this will correspond to the next story beat, which will likely be denoted by an [[##Alerts]]. The icon for this button will change to reflect where it will take the player. Some examples:
	- The next level — The next narrative beat is for the player to tackle the next new level. The icon shows a rock.
	- Library — the next narrative beat involves speaking to Leila about a book. The icon shows the Library.
	- Donnie is back — No narrative alerts (or maybe FTUE). Donnie has returned from a mission. The icon shows Donnie.
	- Forge — if there is new equipment ready for the player. The icon shows the Forge.
	- Cauldron — if there are new potions for the player to brew. The icon shows the Cauldron.
- Cauldron
- Forge — not scoped for demo
- Next level — takes the player to the next new level in the world map, with the "level goals" modal open.

## Transitions
In either touchscreen/desktop situation, if the player avatar is suppose to move, there will be a short animation that brings the avatar to the appropriate location. If the location is on a different vertical level that its current location (most cases), the player avatar will run off screen either left or right, then enter on the destination level from the right or left side of the screen—implying some offscreen shortcut.

If the avatar is offscreen from the current view, only show the avatar running into the view.

**Entering locations**
If the player selects a location, such as the Library, the avatar movement animation should be very short, followed by transition into the appropriate destination screen.

**Entering a game level**
Tapping on a level in the map will open to [[Level start modal]]. When using the [[#Quick Nav]] to access the next level, it shows this modal right away.

# Other UI
## Alerts
Icons will appear around the Map to draw player attention when something is new, or to guide them to the next story point.
- Story point — tracks the next story point
- New — used as a notification in various locations:
	- New potions are unlocked
	- New equipment is available
	- New achievement is unlocked
## Settings button
Opens the [[Settings menu modal]]
## Backpack/inventory button
Shows a modal with:
1. Resources they've collected
2. Potion/item inventory and what potions/items are equipped for play
	1. Should this actually be shown in the Cauldron?
3. Runes unlocked and equipped
	1. Should this be shown at the Family Shrine?

## Other
- Donnie's here/away sign on the breakroom — shows if Donnie is at Basecamp or away on a mission
- Active/inactive states for locations — in the beginning, most places will be inactive at Basecamp because family members are not there. Once family members return, their corresponding spaces will become "active," reflected in the artwork/UI

# Interactions
NPCs hang out around basecamp. Tapping on an NPC will bring the player avatar to the NPC, and engage (or attempt to engage) in conversation.