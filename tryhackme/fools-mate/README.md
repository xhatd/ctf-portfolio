# Fools Mate 

## Task 1: Bypassing the Chess Interface

While interacting with the web interface and playing chess, while making any winning move it triggered a warning:

> "I'll shut down your PC if you play that."

The application then prevented the move from being made.

I was a bit lost fter inspecting the website's JavaScript, I understood and found the following code:

```javascript
if (probe.isCheckmate()) {
    showSystemNotice("I'll shut down your PC if you play that.");
    return false;
}
```

The application checks whether a move results in checkmate and blocks it through client-side JavaScript.

I had to do some google search and lookup how to do client-side bypass in the terminal since thats my focus at the momement.

### Bypassing the Restriction

Instead of making the move through the web interface, let's use `curl` to send a POST request directly to the `/api/move` endpoint.

```bash
curl -X POST http://<TARGET_IP>/api/move \
  -H "Content-Type: application/json" \
  -d '{"from":"a1","to":"a8"}'
```

This sends the move directly to the server without triggering the browser's JavaScript check.

If the server accepts the move without independently validating it, we've successfully bypassed the client-side restriction.

![Curl](images\01-Curl.png)
