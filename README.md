
        const { action, pull_request } = req.body;

        console.log("🔥 PR Webhook received!");
        console.log("Action:", action);
        console.log("PR Number:", pull_request.number);
        console.log("PR Title:", pull_request.title);
    }
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

app.post("/webhook", (req, res) => 

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


    res.status(200).send("Webhook received");
});

import { fetchPullRequestDiff } from "./github/github";
import { parseDiff } from "./diff-parser";

async function main() {
  const diffUrl =
    "https://github.com/ShubhamTiwari007xx/webhook/pull/64.diff";

  console.log("📥 Fetching real GitHub diff...");

  const diff = `
diff --git a/auth.js b/auth.js
--- a/auth.js
+++ b/auth.js
@@ -10,2 +10,3 @@
 const user = getUser();
+const password = user.password;
+console.log(password);

@@ -30,2 +31,3 @@
 const token = getToken();
+validateToken(token);
+return token;
`;
  console.log("✅ Diff fetched!");
  console.log("📏 Diff length:", diff.length);

  const result = parseDiff(diff);


}

main();


