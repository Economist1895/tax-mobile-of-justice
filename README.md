# Tax Mobile of Justice

A 60-second arcade chase game. Drive the Tax Mobile of Justice (GST 009) around the city, catch fleeing tax evaders and send them to Revenue House before the Time Bar runs out.

It is a single HTML file with no build step and no dependencies. It runs in any modern browser on desktop or mobile.

## Play

Open `index.html` in a browser. To play on a phone, host the folder anywhere static, for example with GitHub Pages.

To run it locally on a different port:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Controls

| | Keyboard | Touch |
|---|---|---|
| Drive | Arrow keys or WASD: press the way you want to go | Slide your thumb on the round pad towards the way you want to go |
| Throw a Notice | Space | Yellow ✉️ button |
| Skip a catch scene | Space | ✉️ button |

Press a turn just before a junction and the car takes it for you. Touch-screen laptops start with keyboard controls and switch to touch controls when you touch the screen.

## How to play

- **Find suspects.** Red arrows at the edge of the screen point to them. They also show as red dots on the minimap.
- **Fill the gold ring to catch them.** Staying close fills it slowly and ramming stuns them. When gold brackets lock on to a suspect, throw a Notice to fill most of the ring. Notices have to be served in person, so drive in close to finish the catch.
- **Pick up Notices.** Notices are limited. Drive over the ✉️ Notices on the road to get more. Stacks give you two and suspects drop single ones as they drive.
- **Watch the case timers.** Each case has its own timer. If it runs out, the case is time-barred and the suspect gets away.
- **Avoid the tunnelling works.** Works near Revenue House close a couple of roads each shift. They are marked orange on the minimap.
- **Extras.**
  - Chicken rice 🍗 gives a speed boost.
  - Catching suspects back to back builds a streak bonus.

At the end of the shift you get a performance appraisal and a PG grade. Your best shift for each officer is saved as a personal best and shown on the officer's card, with its PG grade. It is kept in your browser on that device only, so a private or incognito window forgets it when you close it.

### Officers

- **Ryan Li (Normal)** has slower suspects, more time per case and more Notices. Recommended for first-timers. A first shift starts with a short training case.
- **Kaspar Chen (Hard)** has faster suspects who swerve at junctions and fewer Notices. Suspects only drop Notices when you're on their tail. Cases are worth 50% more and the PG targets are higher.

### Suspects

| Suspect | Quirk |
|---|---|
| Offshore Oliver | Fastest, and the biggest case |
| Shell Company Pte Ltd | Splits into two subsidiaries when caught |
| Cash-Only Contractor | Drops Notices twice as often as the others |
| Crypto Bro | Bursts of speed |
| Undeclared Influencer | Stops now and then to film a story, which gives you a chance to catch up |

## Code notes

Everything is in `index.html`: the HTML overlays, the CSS and one script. The main tuning values are near the top of the script:

- `ROUND_TIME`, `CATCH_R` and the Notice settings, such as range, cooldown and how far a Notice can fill the ring.
- `MODES`, which sets per-officer suspect speed, case time, case load, junction swerving, Notice drops, case values and PG thresholds.
- `TYPES`, which defines each suspect's speed, value and lines.

## License

[MIT](LICENSE)
