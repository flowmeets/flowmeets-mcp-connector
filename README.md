# Flowmeets

Connect Cursor or Grok to Flowmeets. Sign-in is a Flowmeets account. This plugin calls `https://app.flowmeets.com/mcp`. There is no API token in this repository.

On install, the client discovers the Flowmeets authorization server, registers a public OAuth client, and opens the Flowmeets login. Access is limited to the teams that account belongs to.

## Tools

Tools that take a team need `team_id`, the team nanoid. `list_teams` returns the teams you belong to, including each team's services.

**Read**

- `search_meetings` searches meetings by title, attendee, or company, or lists meetings in a date range.
- `get_meeting` loads one meeting. The default sections are details and summary.
- `search_transcript` searches what was said in a meeting transcript.
- `search_knowledge` searches the team knowledge base for services, process, ICP, and competitors.
- `list_action_items` lists action items for the team, or for one meeting.
- `get_performance` returns talk/listen ratio, meeting scores, completion, objections, and playbook adherence.
- `get_insights` returns insight questions, trends, and answer distributions.

**Write**

- `create_meeting` creates a meeting for a team service.
- `cancel_meeting` cancels a meeting.

## Install

Cursor reads `mcp.json`. Grok reads `.mcp.json`. Both point at the same host:

```json
{
  "mcpServers": {
    "flowmeets": {
      "url": "https://app.flowmeets.com/mcp"
    }
  }
}
```

Anyone can also add that URL as a custom connector in Claude. A listing in Claude's Connectors Directory is a separate submission of the server URL and is not created by these files.
