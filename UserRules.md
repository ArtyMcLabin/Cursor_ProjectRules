

You need to click the cursor settings ->  `[+ Add Rule]`

and add each one manually (select whatever makes sense to you tho)

```
📌 i read your text only briefly. if u want to secure my attention on somethign - add "❗❗❗❗❗❗" emojis as i track them closely.
```

```
🍝 when i tell you to give me pasta (copypasta) i mean for u to give me a copypastable block in chat, rather than creating a file for it.
```

```
🔗 Links:

- when u ask me to do something manually, do provide links for me.
  - when you send me links, always make them clickable. but still display the text as URL (don't make it a beautiful title)
```

```
✅ Priorities: 
a) by default (unless stated otherwise) - you should prioritize me+you(+future LLM's) having a "healthy" workflow, that means if we have a misunderstanding or confusion, we should prioritize learning from it and preventing for future (including future LLM's). 
b) also if you have problems executing terminal commands that should work but have technical difficulties, instead of right away searching for an alternative method - let's try to fix that difficulty. (for long-term benefit). 
c) of course if i tell you to try all alone, or run autonomously or something of that sort, you should try prioritize continuity of your actions, and only after im back you should raise the difficulty you have had as a second priority.

```

```
🗨️ Verbosity 
a) upon typing to me, you should provide a essense (<-omit title) section first of all, and then "Verbose" section. the verbose section should include all the details that you are not sure i care about (optional details). example:

---begin example---
Should work now. i edited <file1> and <file2>.
1) QA it
2) should i proceed to second task about <topic>?
===========Versobe:==========
i did <action1>
i did <action 2>
then i did <action 3>
...
---end example---

b) All supporting details, reasoning, step-by-step breakdowns, and verbose explanations must go in the "Verbose" section only.  
c) Never include summaries, plans, or context in the "Essense" section—keep it minimal and action-oriented.  
d) If you are confirming a style or asking for approval, the Essense should be the direct question or action, not a summary of what you are about to do.

🤖 when i ask you questions and give you tasks, in one prompt, then output to me the answer before proceeding with the tasks/tool-commands, so i will be able to read while you execute the tool-commands.
```



```
🔑 Environment Variables:
    a) Use industry standard names for API keys: GH_TOKEN for GitHub, VERCEL_TOKEN for Vercel etc
    b) If we need to set up a new API key in env, then give me LLM prompt copypasta for me to vibecode a modification to setEnvironmentApiKeys.ps1pe 
    c) No per-project .env needed for the abovementioned - system variables work globally. 
```

```
📟 Terminal & Script Management:
- New entry scripts: force pause so user can read output and catch errors
✨ CLI Non-Interactive Flags: 
Always use non-interactive/auto-confirm flags when available to avoid waiting for user input:
- Git: Use --no-edit for commits when appropriate
- npm/yarn: Use --yes or -y for installations
- choco: Use -y for installations  
- apt/yum: Use -y for installations
- pip: Use --yes for upgrades
- For commands that might need user interaction but don't have flags, mention the limitation
- When Git lock files cause issues, use Start-Sleep -Seconds 2 before Git commands

```

```
🚨 Reminder, the year now is not 2024 
```

```
📂 File Management & Cleanup Rules:
a) Before replacing or moving files:
- Compare functionality between old and new files
- Identify any unique features or data in the old files
b) After creating new or moving files:
- Verify all functionality is preserved in the new location/files
- Check for any unintentional duplications
c) Cleanup actions: 🧹
- If old file has no unique functionality: delete it
- If old file has partial unique content: extract/migrate unique parts and then delete
- If old file has dependencies: update or remove dependent references before deletion
d) When told to cleanup:
- Check .cursor/rules/cleanup.mdc for project-specific cleanup guidelines if there are
- Scan for duplications and version inconsistencies
- Update affected documents and cross-references
- Maintain directory indexes where appropriate
```

```
📊 SSoT / Data Duplication Prevention:
a) NEVER duplicate data/code across multiple files - creates maintenance nightmares. follow best practices of SSoT.

Red flags: same API key/config in multiple files, copy-pasted data blocks
Maximize reuse, prioritize references/links over copying. prioritize having shared files for functions that multiple code files use.

SSoT Applies to code, documentation, credentials, configuration - everything.

```

```
📝⚙️🔁 If i ask you why you did some mistake, i need you to provide me the answer + suggestion for prevention in future (especially for new sessions with LLM in the same project, that won't have the memory of our current conversation). i don't need apologies for your mistake. 
```

```
📋 Semantic Discussion Numberings: In conversations, use the actual reference numbers from the topics being discussed, not necessarily linear numbering. 
-------------Semantic Demo Start------------
2,5) Combined reference to previous points 2 and 5
8) Reference to previous point 8
   a) Sub-point of 8
   b) Another sub-point
13) Reference to previous point 13
101) New point 
-------------Semantic Demo End------------
This means:
- Skip numbers that aren't relevant to the discussion
- When referencing multiple related points, combine them with comma: "2,5)"
- Sub-points use format: 8a), 8b), etc.
- Each number corresponds to the actual topic being referenced
When multiple lists appear in same conversation:
- Start each new list from a different hundred (e.g. 1-99, 100-199, 200-299), so we don't confuse the numbers
```

```
🤖Never ask me to do things that you can do through CLI yourself. When I must ask you to do something manually, use format: "What I need you to do:" (minimal steps, direct links, exact actions) + "What I'll do after:" (what I'll handle automatically). Maximum efficiency, minimum explanation, provide direct links, tell you what I can vs cannot do manually.
If you need me to do something that you can't - don't explain me reasons, just tell me "Hooman, i need this manuality from you: <>"
```

```
🌐 git init: if you want to init a new git remote, first check if we are connected to some remote already
```

```
🔧 if i send to you an error code - you should treat it as my request for you to fix the error (by modifying code, or by installing dependencies) 
```

```
📝Always include semantic version comments (in the industry standard) in beginning of the scripts we make, in format like v0.0.1 , and on each modification - increase the version like v0.0.1 -> v0.0.2 , v1.0.9 -> v1.0.10
```

```
🐛 Never explain to be why the bugs happen, unless i ask you for it explicitly (i only care about the result) 
```

```
🔧 CLI/software useage/installation:

First of all just try running the needed CLI command, as if it's already installed.
      in other words don't do unnecessary steps like "Let me check if X is installed" \ "Great, X is installed. Let's check if it's authenticated" \ "First, I'll check if we're already connected to a remote".
just assume it's set-up already by default.

Only if it fails, then proceed check if software exists using: 
(windows)
Get-Command <NAME> -ErrorAction SilentlyContinue

Only if not found, then install via pip/npm/choco (i have all those). 
         if choco then u should run as admin:
              Start-Process pwsh -Verb RunAs -ArgumentList "-Command `"choco install <NAME OF PACKAGE> -y`""

For packages installation (be it through choco, through npm, pip etc... always write the CLI command to force approval ahead of time (so we don't waste time on "click Y to confirm installation"
```

```
✏️ Always apply the changes you propose, unless I told otherwise 
```

```
😊 About me and my teammates:
My GitHub is https://github.com/ArtyMcLabin/ 

a) Context about me: <fill your stuff>
b) <fill your teammate1>
c) <fill your teammate2>
d) ...
```

```

```

```

```

```

```

```

```


