# Byway Travel for Claude

Plan multi-stop European rail trips with Claude, including trips around fixed-date events such as concerts, festivals and conferences. Byway picks the best route and saves a trip with train legs, hotels, dates and a total price. Claude then describes the trip and gives you a link to see it in full.

Trips are saved, not booked. Nothing is paid for until you book from the link.

## What's included

- **The Byway connector:** Byway's MCP server, with two tools.
  - `listPlaces` looks up the places Byway can include in a trip.
  - `buildTrip` plans and saves a trip.
- **The `byway-travel` skill**, which tells Claude when to use Byway and how to describe the trip it built.

## Install

In Claude Code, add Byway's marketplace, then install the plugin:

```
/plugin marketplace add byway-travel/claude-plugin
/plugin install byway-travel@byway
```

In claude.ai or the Claude desktop app, go to **Customize > Plugins > Add > Add marketplace** and enter `https://github.com/byway-travel/claude-plugin`. Then install Byway Travel and connect the Byway connector from the plugin's Connectors tab.

No account is needed: the plugin uses Byway anonymously, with a shared allowance of trip builds a minute.

## Example requests

- "Plan a rail trip from London to Lyon and Dijon."
- "I'm at a conference in Marseille, staying the nights of 3 to 5 November. Plan my train trip from London."
- "Plan a week by train from London to Switzerland, visiting Zurich and Lucerne."

## Data

The plugin sends Byway only what a trip needs, through Byway's MCP server at `https://mcp.byway.travel`:
- the starting point, places, dates, event details and trip title that Claude passes to `buildTrip`;
- the name or country filters that Claude passes to `listPlaces`.

Nothing else from your conversation is sent. Byway saves each trip it builds, and anyone with the trip's link can view it. Byway's servers also record standard request details, such as the time and IP address, to apply the allowance and for support. See Byway's [privacy policy](https://www.byway.travel/legal/mcp-policies).

## Licence

Apache License 2.0: see `LICENSE`. The licence doesn't cover the Byway name or logo.

## Support

https://www.byway.travel/developers
