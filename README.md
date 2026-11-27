# Unkey

Connects Cursor to Unkey's MCP server so agents can manage Unkey APIs, keys, rate limits and Unkey's compute platform deployments.

## Connect your client

Add the server URL with no headers. When Cursor connects, it opens Unkey in your browser so you can sign in.

This plugin adds that server for you. After you install it, open Customize in the sidebar and check that unkey is listed and turned on.

To add the server by hand, open `~/.cursor/mcp.json` to use Unkey in every project, or `.cursor/mcp.json` in a project to use it there only:

```json
{
  "mcpServers": {
    "unkey": {
      "url": "https://mcp.unkey.com/"
    }
  }
}
```

For Unkey's compute platform only, name the server `unkey-compute` and use `https://mcp.unkey.com/compute` as the URL.

Then ask Cursor's agent something like "List my Unkey keyspaces," or "List my Unkey projects" on the compute platform server.

If the server does not connect, open the Output panel, choose MCP Logs, and look for an authentication or connection error.

## Sign in with Unkey

1. Add the server to Cursor. Cursor opens the Unkey dashboard in your browser. Sign in to the dashboard if you are not already signed in.
2. Check that the page names the client you just connected, for example Authorize Cursor. Cursor reports its own name, so also check the host on the Access goes to line. Authorize only a connection you started.
3. If you belong to more than one workspace, pick the one the assistant should work in.
4. Choose the permissions the assistant gets. You can only grant permissions your own role has, and the Permissions dropdown only lists presets your role can grant. For Unkey's compute platform, Compute read only and Compute full control cover every permission its tools check.
5. Click Authorize. The browser returns you to Cursor, and the server's tools are ready to use.

Cursor keeps itself signed in. Each access token lasts 15 minutes, and Cursor renews it in the background. The session ends after 7 days without use, or 30 days after you signed in, whichever comes first. Cursor then asks you to sign in again.

To see or end a session, open Settings > Sessions in the dashboard. Sessions from MCP clients have an MCP badge and show the client's host and the server it connected to. Click Revoke to end that client's access right away.
