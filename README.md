# Nitro Kickoff

A 1v1 rocket-car soccer game that runs in the browser. Drive, jump, dodge and boost your car into a giant ball, and outscore the bot before the clock runs out. A tie goes to golden-goal overtime.

Open `index.html` in any modern browser to play. It is a single file and needs no build step; Three.js loads from cdnjs.

## Deluxe account

Nitro Kickoff is a Deluxe Games website and signs in with Deluxe Main (the button on the start screen).
Signed in, your match record (wins, losses and goals) is saved to your Deluxe account. Guests keep it in
the browser, and it moves into the account when they sign in.

It lives at **https://rocket-league-blond.vercel.app** (Vercel deploys the `main` branch), and Deluxe Main
lets it sign in only from that address. If the address changes, change it in Deluxe Main's
`worker/apps.js` and `public/deluxe.js`.

## Online play

**Play online** on the start screen opens a lobby for people signed in with Deluxe Main.

- **Create room** gives a 5-letter code and an invite link. Friends tap the link, or type the code under *Join*.
- Pick blue or orange, and the host chooses the stadium, match length and the bots that fill empty spots (up to 3 per team, 6 people).
- The host starts the match. Everyone is named by their Deluxe account. When it ends, everyone goes back to the lobby.

How it works: the host's browser runs the match and sends 30 snapshots a second through a room on the Deluxe server
(`wss://deluxe-drive.deluxelordd.workers.dev/arena/CODE`, a Durable Object in the deluxe-drive repository). Everyone else sends their
controls. Each player's own car is driven on their own screen, so it answers at once, and the host's version corrects it
gently if the two drift apart. Other cars and the ball are smoothed between snapshots.

Good to know: the host must keep the game tab open and in front, and a host on a slow connection is slow for everyone.
Matches cannot be paused. If the host leaves the match ends. Your own car does not bump into other cars until the host's
next update arrives, so contact looks a moment late for guests.

## Controls

| Action | Keyboard | Gamepad |
| --- | --- | --- |
| Drive / reverse | W / S (or arrows) | RT / LT |
| Steer | A / D | Left stick |
| Jump, double jump | Space | A |
| Dodge | Space in the air while holding a direction | A + stick |
| Boost | Shift | B |
| Tilt nose in the air | W / S | Left stick |
| Powerslide | E | X or LB |
| Ball cam | C | Y |
| Pause | P or Esc | Start |
| Sound on/off | M | |

Touch controls appear on phones and tablets. The round boost gauge is the boost button: hold it to boost. It glows while you boost and turns red when it's empty.

## Stadiums

Pick one on the start screen; the game remembers your choice.

| Stadium | What's different |
| --- | --- |
| **Grasslands** | The standard stadium and the default: a striped grass pitch on a sunny day, with green hills beyond the stands |
| **Neon Dome** | Night arena under the stars, glass walls with neon trim |
| **Spud Bowl** | A sunny farm ground. The fans are potatoes in team caps, four giant potato mascots stand in the corners, and the ball is a giant potato. Grass slows the ball and makes it bounce less |
| **Frost Rink** | Ice under falling snow. Cars slide when they turn, and the ball keeps rolling |

Every stadium has stepped stands full of fans in team colours, floodlight towers and a big screen behind
each goal showing the score and clock. The crowd stands up for shots on goal and jumps when someone
scores, and you can hear it get louder. On slow devices the game lowers its resolution and then hides
the crowd automatically to stay smooth.

## Features

- Blue vs orange teams, chevron markings on the pitch, a glass-roofed stadium with floodlight rows, name tags over the other cars, and a feed with goal messages and bot quick chat

- 1v1, 2v2 and 3v3. Bot teammates take turns: the closest one attacks, the others cover the goal
- Powerslide (E, gamepad X or LB, DRIFT on phones) for tight turns
- Demolitions: hit an opponent at near top speed and they explode, then respawn at their goal after 3 seconds

- Drive up the walls and across the ceiling (fall off if you slow down)
- Aerials: hold jump to jump higher, and hold jump + boost in the air to fly upward
- Big goals: 26 wide and 12 high

- Three bot difficulties (Rookie, Pro, Ace) and 2, 3 or 5 minute matches
- Boost pads: big ones refill to 100, small ones add 12
- Aerials, double jumps and dodges that hit harder
- Goal explosions, a kickoff countdown and overtime
