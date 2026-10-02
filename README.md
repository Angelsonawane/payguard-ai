# PayGuard Agent

A safety check for AI shopping agents. Before an agent can pay, PayGuard compares the purchase with the shopper's usual pattern, on the device, and decides to approve, ask for confirmation, or block. Approved purchases go through a real PayPal checkout (sandbox, test money).

## Live demo

Open the GitHub Pages link for this repo, or open `index.html` in a browser. Pick one of the three purchases:
- Groceries: approved, then pay with PayPal sandbox.
- Headphones: paused until you confirm, then pay.
- Gift cards: blocked, PayPal is never called.

## How it works

1. Each behavior (request speed, pasted card, new device, amount, time of day, failed attempts) becomes a node.
2. Each node is compared with the shopper's usual pattern.
3. The differences are combined into a 0 to 100 risk score: under 30 approve, 30 to 59 confirm, 60 or more block.

The check runs in the browser and the page shows how long it took. Payments use the PayPal JavaScript SDK in sandbox mode.

## Limits

The shopping agent is simulated and the weights are set by hand. It is a prototype and uses test money only.

## Next steps

Connect a real AI agent, add server-side PayPal order checks, and tune the weights on real data.

## AI disclosure

Built by Angel Sonawane, who designed the concept and directed AI tools (Claude) to build and test the prototype.

## License

MIT. See `LICENSE`.
