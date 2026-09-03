git add .
git commit -m "test nexus webhook"
git push -u origin test-nexus-webhook
app.post("/webhook", (req, res) => {
    const event = req.headers["x-github-event"];

    if (event === "pull_request") {
        const { action, pull_request } = req.body;

        console.log("🔥 PR Webhook received!");
        console.log("Action:", action);
        console.log("PR Number:", pull_request.number);
        console.log("PR Title:", pull_request.title);
    }

    res.status(200).send("Webhook received");
});
app.post("/webhook", (req, res) => {

    if (!verifyGitHubSignature(req)) {
        console.log("❌ Invalid GitHub signature");
        return res.status(401).send("Invalid signature");
    }

    console.log("✅ GitHub signature verified!");

    const event = req.headers["x-github-event"];

    if (event === "pull_request") {
        const { action, pull_request } = req.body;

        console.log("🔥 PR Webhook received!");
        console.log("Action:", action);
        console.log("PR Number:", pull_request.number);
        console.log("PR Title:", pull_request.title);
    }

    res.status(200).send("Webhook received");
});
