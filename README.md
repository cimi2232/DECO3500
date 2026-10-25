# On The Beat

DECO3500 Social & Mobile Computing, Semester 2 2026. Team 27, "Friday".

Get talking to a stranger at a live gig, then get out of the way.

On The Beat is a phone app for one night at one venue. You arm one of four
cards (SAY HI, FIRST SONG?, LET'S DANCE!, LET'S GUESS!), and when two people
both say yes, and only then, each learns the other's first name and a quiet
spot to meet. Until then nobody sees your name, your photo or where you are.
An optional wristband (an M5StickC Plus on a strap) lets you do the same from
your wrist without taking your phone out in the crowd.

https://github.com/user-attachments/assets/4881ab35-b553-4f08-b1fe-21d7e0aba578

Our A2 poster, with the research, both testing rounds and the theory behind
the design, is [Documentation/a2-poster.png](Documentation/a2-poster.png).

## Try the prototype

**https://on-the-beat.fly.dev** is always on. Open it on two phones, ideally
on two different people.

1. Read the four promises, type a first name and tap I'M IN.
2. Pick a venue and tap THAT'S THE ONE. Both phones need the same one:
   *ZARA LARSSON, ON THE BEAT test night* is listed every night.
3. Skip the wristband (*no wristband — use my phone*) unless you have one.
4. Tap SAY HI to arm it. The screen turns blue, which means hello, and WHO'S
   NEAR lists the other phone as "Someone in this room", with no name.
5. Tap WAVE. When the other person waves back, both phones show the same
   two-digit number and a spot to meet. Tap ON MY WAY, send a short note if you
   cannot see each other, and tap WE FOUND EACH OTHER once you have.

No account and no password are needed for the app. The staff page
(`/staff`) asks for a venue passcode; it is not published in this public
repository, so ask the team for one. The venue poster, a screen for the
venue's wall with a code to scan, is at
`https://on-the-beat.fly.dev/poster/test-night-zara-larsson`.

To run it on your own computer (Node 22 or 24, the versions CI tests on):

```
cd Prototype
npm install
npm start      # the app and its relay on http://localhost:8790/
npm test       # build, then every test
```

Real phones need https, so use `npm run tunnel` or the address above. Every
other command, the wristband firmware and deploying are in
[Prototype/docs/running.md](Prototype/docs/running.md).

## What is in this repository

| Where | What |
|---|---|
| [Prototype/](Prototype/) | the working prototype: phone app, relay server, wristband firmware and tests ([its README](Prototype/README.md)) |
| [Prototype/docs/](Prototype/docs/) | how it works, the four promises, abuse resistance, the wristband guide, known limits |
| [Documentation/](Documentation/) | our A2 poster, the design proposal, the user interviews and their analysis, [how the design changed](Documentation/Design/), [our two testing rounds](Documentation/Evaluation/) and [where we managed tasks](Documentation/Task-management.md) |
| [Wiki](../../wiki) | Design Process Overview, Ethical Considerations and our stand-up records |

`Prototype/` carries the prototype's whole development history: 26 commits,
about one for each day it changed, from 24 Sep to 24 Oct 2026.

## Key documentation

- [Design Process Overview](../../wiki/Design-Process-Overview): how the prototype came to be and what testing changed
- [Ethical Considerations](../../wiki/Ethical-Considerations): the risks we found and what the design does about them
- [How it works](Prototype/docs/how-it-works.md): the four promises and where in the code each one is kept
- [Abuse resistance](Prototype/docs/abuse-resistance.md): every guard against misuse, each with its test
- [What is not done](Prototype/docs/not-done.md): known limits and how many people one machine holds

## License

The prototype is MIT licensed; see [Prototype/LICENSE](Prototype/LICENSE).
