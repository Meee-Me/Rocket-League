# Nitro Kickoff

A 1v1 rocket-car soccer game that runs in the browser. Drive, jump, dodge and boost your car into a giant ball, and outscore the bot before the clock runs out. A tie goes to golden-goal overtime.

Open `index.html` in any modern browser to play. It is a single file and needs no build step; Three.js loads from cdnjs.

## Deluxe account

Nitro Kickoff is a Deluxe Games website and signs in with Deluxe Main (the button on the start screen).
Signed in, your match record (wins, losses and goals) is saved to your Deluxe account. Guests keep it in
the browser, and it moves into the account when they sign in.

Deluxe Main lets it sign in only from **https://nitro-kickoff.vercel.app**. Deploy this repository on
Vercel as a project named `nitro-kickoff` (no build step). If Vercel gives it a different address, change
it in Deluxe Main's `worker/apps.js` and `public/deluxe.js`.

## Controls

| Action | Keyboard | Gamepad |
| --- | --- | --- |
| Drive / reverse | W / S (or arrows) | RT / LT |
| Steer | A / D | Left stick |
| Jump, double jump | Space | A |
| Dodge | Space in the air while holding a direction | A + stick |
| Boost | Shift | B |
| Tilt nose in the air | W / S | Left stick |
| Ball cam | C | Y |
| Pause | P or Esc | Start |
| Sound on/off | M | |

Touch controls appear on phones and tablets.

## Stadiums

Pick one on the start screen; the game remembers your choice.

| Stadium | What's different |
| --- | --- |
| **Neon Dome** | Night arena under the stars, glass walls with neon trim |
| **Spud Bowl** | A sunny farm ground. The fans are potatoes in team caps, four giant potato mascots stand in the corners, and the ball is a giant potato. Grass slows the ball and makes it bounce less |
| **Frost Rink** | Ice under falling snow. Cars slide when they turn, and the ball keeps rolling |

Every stadium has stepped stands full of fans in team colours, floodlight towers and a big screen behind
each goal showing the score and clock. The crowd stands up for shots on goal and jumps when someone
scores, and you can hear it get louder. On slow devices the game lowers its resolution and then hides
the crowd automatically to stay smooth.

## Features

- Three bot difficulties (Rookie, Pro, Ace) and 2, 3 or 5 minute matches
- Boost pads: big ones refill to 100, small ones add 12
- Aerials, double jumps and dodges that hit harder
- Goal explosions, a kickoff countdown and overtime
