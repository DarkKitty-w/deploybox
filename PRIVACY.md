# LockAutopsy — Privacy Policy

Last updated: 30 October 2026
Applies to: the LockAutopsy Firefox add-on (`lock-autopsy@lockautopsy.org`), the LockAutopsy
userscript, and the LockAutopsy service at `https://lock-autopsy.smither.workers.dev`.

## What the add-on sends

When you press the check button on a supported page (DexScreener, GeckoTerminal, GMGN), the add-on
reads **the token contract address from that page** and sends it, with the chain name, in **one HTTPS
request** to the LockAutopsy service.

## What the service does with it

It builds a report about that token's locked supply and returns it to your browser. Nothing about the
request is linked to a person.

- No account exists, and none is required.
- Your IP address is **not written to our database**. It is used, in memory only, to stop abuse:
  the rate limiter stores a one-way hash, not the address.
- Reports are counted as anonymous totals — how many checks per hour and per day — with no IP, no
  address and no identifier attached.

## What it never does

- No browsing history, no other page content, no cookies, no analytics or tracking scripts.
- No wallet connection, no signature requests, no access to keys or seed phrases.
- The add-on is read-only: it cannot move funds.
- Nothing is sold, rented, or shared with third parties.

## Optional Pro key

If you paste a Pro licence key into the add-on's settings, it is stored in your browser's extension
storage and sent only to the same LockAutopsy service to unlock the paid report. It is not sent
anywhere else, and it is never placed in a URL.

## Data retention

The database keeps aggregate counts (per hour and per day) and, for a paid report, the payment
record needed to prove the purchase. It does not keep a history of which addresses you looked at.

## Contact

alex.ryder0201@gmail.com
