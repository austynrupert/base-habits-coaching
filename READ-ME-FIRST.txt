# Deploy folder — Base Habits Coaching

Upload the **contents** of this folder to your site root. That's it.

```
index.html                                   home page (has the password box)
about-me.html
headshot.jpg / before-200lbs.png / after-158lbs.png
clients/index.html                           encrypted
clients/phase-1/base-habits/index.html       encrypted
clients/phase-1/calories/index.html          encrypted
```

Password: **getstrong26**

## How it behaves

A client clicks "Current Client Access" on the home page, types the password, and lands
on the client home. Every client page then opens with no further prompting for 30 days.
If someone goes straight to a client page URL, they get the StatiCrypt password screen
there instead — same password, same result.

The client pages are genuinely encrypted. Without the password there is nothing to read
in the page source.

## Changing the password later

Open `tools/client-password.html` (keep that file OFF the server) and follow the three
steps it prints. It gives you the re-encrypt command and the one line to change in
`index.html`.

Two things must stay true or the single sign-in breaks:

- All client pages are encrypted in **one run** with `--salt 01c8cfd2929a928a2e2c895f2d8b3fd2`.
- The VERIFIER line in `index.html` matches that same password.

## Do not upload

- `clients/` at the project root — that's the unencrypted source. Keep it; it's what you
  edit and re-encrypt from.
- `tools/client-password.html`.
