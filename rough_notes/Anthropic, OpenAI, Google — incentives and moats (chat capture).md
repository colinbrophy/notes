---
tags: [draft, ai-written]
---

## Context / goal

Capture a discussion about why Anthropic can be “frontier” despite being smaller, how its business model works, and how incentives/legacy moats shape the “Big 3” market structure (Anthropic, OpenAI, Google).

## Key points

- Frontier status is driven more by compute access, capital, and expertise than by headcount.
- Anthropic’s business model is “model supplier”: API + partnerships (not a consumer platform first).
- Embedding models via hyperscalers (e.g. AWS) can substitute for owning data centres, but creates dependency trade-offs.
- Google’s core search/ads interface creates an “innovator’s dilemma”: a too-good assistant can cannibalise search.
- Meta, Microsoft, and Apple sit in different parts of the stack (open weights / platform leverage / devices), so they can benefit from AI without the same exposure as Google.
- The market is oligopolistic and niche-partitioned: different players optimise different objective functions, not pure “best chatbot wins”.

## Cleanup targets

- [[Anthropic]]
- [[OpenAI]]
- [[Google]]
- [[Business models]]
- [[Moats]]
- [[Search (as interface)]]

## Chat (verbatim)

Please summarise the selection using precise and concise language. Use headers and bullet-pointed lists in the summary, to make it scannable. Maintain the meaning and factual accuracy.

jump to content
my subreddits

    home-popular-all-mod-users

 | 

    MapPorn-ChatGPT-LocalLLaMA-OpenAI-unitedkingdom-languagelearning-math-ChatGPTPro-AskFrance-askphilosophy-artificial-Anki-ArtificialInteligence-announcements-ChatGPTCoding-ClaudeAI-IRstudies-machinelearningnews-Refold-bbc-internationallaw-Anthropic-scienceLucyLetby-scienceScienceLetby-LucyLetbyTrials

edit »
reddit.com ClaudeAI

    commentsother discussions (1)

Fun-Yellow334 (3,750)|messages34|notifications|chat messages|mod messages|

    preferences

|logout
this post was submitted on 09 Jan 2026
155 points (96% upvoted)
shortlink:
Submit a new link
Submit a new text post
ClaudeAI
leave
Show my flair on this subreddit. It looks like:
Fun-Yellow334(edit)
created by [deleted]a community for 2 years
MODERATORS

    sixbillionthsheepMod
    Kris_AntAmbassadorMod
    David_AntAmbassadorMod
    inventor_blackMod ClaudeLog.com
    ClaudeAI-mod-botMod
    AutoModerator
    manipulation-pi
    bot-bouncer
    evasion-guard
    automod-toggle
    ...and 8 more »

account activity

155

I feel like I've just had a breakthrough with how I handle large tasks in Claude CodeProductivity (self.ClaudeAI)

submitted 8 hours ago by wynwyn87

And it massively reduced my anxiety!

I wanted to share something that felt like a genuine breakthrough for me in case it helps others who are building large projects with Claude Code.

Over the last ~9 weeks, my Claude Code workflow has evolved a lot. I’m using skills to fill in the gaps where Claude needs a bit of assistance to write Golang code as per the needs of my project, I've made Grok and Gemini MCP servers to help me find optimal solutions when I don't know which direction to take or which option to choose when Claude asks me a difficult and very technical question, I deploy task agents more effectively, I now swear by TDD and won't implement any new features any other way, I created a suite of static analysis scripts to give me insight into what's actually happening in my codebase (and catch all the mistakes/drift Claude missed), and I’ve been generating fairly detailed reports saved to .md files for later review. On paper, everything looks “professional” and it's supposed to ease my anxiety of "I can't afford to miss anything".

The problem was this:

When I discover missing or incomplete implementations, the plans (whether I've used /superpowers:brainstorming, /superpowers:writing-plans, or the default Claude plan-mode) would often become too large in scope. Things would get skipped, partially implemented, or quietly forgotten. I tried to compensate by generating more reports and saving more analysis files… and that actually made things worse :( I ended up with a growing pile of documents I had to mentally reconcile with the actual codebase.

The result: constant background anxiety and a feeling that I was losing control of the codebase.

Today I tried something different — and it was like a weight lifted off my chest and I'm actually relaxing a bit.

Instead of saving reports or plans to .md files, I told Claude to insert TODO stubs directly into the relevant files wherever something was missing, incomplete, or intentionally deferred - not vague TODOs, but explicit, scoped ones.

Now:

- The codebase itself is the source of truth

- Missing work lives exactly where it belongs

- I can run a simple script to list all TODOs

- I can implement them one by one or group small ones logically

- I write small, focused plans instead of massive ones

I no longer have to “remember” what’s left to do, or cross-reference old/overlapping reports that may already be outdated. If something isn’t done, it’s visible in the code. If it’s done, the TODO disappears.

This had an immediate psychological effect:

- Less overwhelm

- No fear of missing things

- No guilt about unfinished analysis

- Much better alignment with how Claude actually performs (small scope, clear intent)

- Gives me a chance to "Pretend you're a senior dev doing a code review of _____. What would you criticize? Which ____ are missing from _____?" on smaller scopes of changes

In hindsight, this feels obvious — but I think many of us default to out-of-band documentation because it feels more rigorous. For me, it turned into cognitive debt.

Embedding intent directly into the code turned that debt into a clear, executable task list.

If you’re struggling with large Claude Code plans, skipped steps, or anxiety from too much analysis: try letting the codebase carry the truth. Let TODOs be first-class citizens.

I'm curious if others have landed on similar patterns, or if you’ve found better ways to keep large AI-assisted projects sane. For me, I'm continuously upskilling myself (currently reading: The Power of Go - Tests) because I'm not writing the code, but I want to ensure I make informed decisions when I guide Claude.

This subreddit has given me golden nuggets of information based on the experience/workflows of others, and I wanted to share what I've learnt with the rest of the community. Happy coding everyone! :)

    63 commentssharesavehidereportcrosspost

all 63 comments
sorted by: best
formatting help
content policy

[–]ClaudeAI-mod-botMod[M] [score hidden] 4 hours ago stickied comment 

TL;DR generated automatically after 50 comments.

Alright, settle in, latecomers. The consensus is a resounding 'hell yeah' to OP's breakthrough.

The big idea: Stop drowning in .md plan files. Instead, have Claude embed specific TODO comments directly into the code wherever work is needed. This makes your codebase the one true source of truth and kills the anxiety of tracking a million separate documents.

The reaction: * Most of the thread is people saying "this is genius" and "I'm stealing this immediately." * A few veterans are gently reminding everyone that TODO comments are a classic dev practice, but agree it's a perfect strategy for wrangling AI-generated code.

For the overachievers, the thread has some upgrades: * Create a slash command to have Claude automatically find and list all your TODOs. * One user went full galaxy-brain, explaining how they use Design by Contract (DbC) as a form of "executable TODOs" that force the code to fail if a spec isn't met. It's a very detailed, high-value comment worth a read.

There's also a healthy debate on alternative structured workflows like BMAD/SDD and GSD for those who want to go even deeper into process management.

And yes, someone pointed out the classic reverse-problem: Claude proudly announcing "Code Complete" while leaving a trail of // TODO comments in its wake. We've all been there.

    permalinkembedsavereportreply

[–]Robot_Apocalypse 33 points 7 hours ago 

To does directly in the code is a GREAT idea. Thanks!

    permalinkembedsavereportreply

[–]FBIFreezeNow 7 points 5 hours ago 

To does whom thy loathe

    permalinkembedsaveparentreportreply

[–]wynwyn87[S] 2 points 6 hours ago 

Thanks! Hope it helps you too!

    permalinkembedsaveparentreportreply

[–]dumeheyeintellectual 2 points 7 hours ago 

Couldn’t agree more, do toes directly in the code is a GREAT idea, indeed.

    permalinkembedsavereportreply

[–]mjsarfatti 4 points 6 hours ago 

You are absolutely right!

    permalinkembedsavereportreply

[–]VadimH 2 points 4 hours ago 

To do: add to do's

    permalinkembedsavereportreply

[–]M4CH86 10 points 7 hours ago 

Superpowers with TDD are awesome. I suggest you check out BMAD (or one of the other SDD frameworks) to try full SDD too - that could be the next leap for you; it was for me.

    permalinkembedsavereportreply

[–]wynwyn87[S] 3 points 6 hours ago 

I've not come across BMAD or SDD yet. Thanks for the tip, I'm not quite sure what these mean, but I'll look into it!

    permalinkembedsavereportreply

[–]M4CH86 5 points 6 hours ago 

Think of it as an entire framework that drives the process of creating important document artefacts (plans, design, architecture etc) in a structured, predictable way, with workflows that guide you on what to do next (create a sprint plan, then create a user story, then develop it, then code review it etc) and often execute that on your behalf, with moments for you to review and change course. It can be customised too - I’m tweaking the entire implementation workflow to have hard gates on moving on from UAT before all critical bugs are resolved, for example. It does more than all of this and I’ve probably described it badly, but hopefully it gives you an idea!

    permalinkembedsavereportreply

[–]wynwyn87[S] 2 points 5 hours ago 

That sounds great, thanks for explaining this to me :) Planning the sprint, user story, etc. sounds really helpful. I've recently created a skill to plan user stories and tasks for Jira and another skill + script to sync it with Jira (the MCP server uses too many tokens and is too wasteful compared to syncing with a script) so this would definitely be worth looking into for me :)

    permalinkembedsavereportreply

[–]M4CH86 2 points 5 hours ago 

That sounds like a really cool workflow!

    permalinkembedsavereportreply

[–]srdev_ct 2 points 6 hours ago 

It's funny, I started on BMAD and went to Superpowers. While BMAD was instrumental in helping shape how I approach AI-driven development, it got TOO heavy handed and the process too long, it was near impossible to automate / accelerate.

Once I knew what to ask for, how to prompt for pauses when I need them, and got better at monitoring progress, Superpowers helped streamline and accelerate dev, letting me push the pace while still retaining post of the benefits of BMAD

    permalinkembedsavereportreply

[–]M4CH86 1 point 6 hours ago 

Oh! Fascinating to talk to someone going in the other direction! Did you try the more streamlined options included in the framework? (“Quick Flow”, aka agent Barry) I haven’t tried this yet, but it looks and sounds similar to superpowers. I like the idea of being able to flex between full SDD and more nimble work within the same framework. If you try it, please report back, curious to hear what you find!

    permalinkembedsavereportreply

[–]srdev_ct 3 points 6 hours ago 

I haven't, I know BMAD6 is publicly available in alpha/beta - I'm waiting for it to mature then going to get after it again and see if it's improved. I think it's GREAT to be honest, and I still recommend it to anyone looking to get into AI -assisted DEV. Its rigor and methodology really gets you thinking about detailed planning, testing, validation, and context management. I never recommend someone go straight to Superpowers.

    permalinkembedsavereportreply

[–]M4CH86 2 points 5 hours ago 

Totally fair to wait; personally I’m upgrading each time there’s a new alpha and getting the best out of each update as it comes. Hasn’t caused any issues in my workflow (yet), but I’ve committed the working directories to git anyway so I can rollback just in case. Interesting take on BMAD for structure then superpowers for speed, I like that approach.

    permalinkembedsavereportreply

[–]quantum_splicer 3 points 7 hours ago 

That is what I do also I find it useful, you could also possibly create an slash command which gets Claude code to find all todos not done and then create an task list and then go from their 

    permalinkembedsavereportreply

[–]wynwyn87[S] 2 points 6 hours ago 

I invoke my codebase analysis scripts with slash commands and added one to list all the TODOs 👍

    permalinkembedsavereportreply

[–]crunchy_code 2 points 2 hours ago 

i would think it’s easy enough with a standard script, so you save yourself a bunch of tokens just to list todos on a codebase.

    permalinkembedsavereportreply

[–]Hegemonikon138 2 points 34 minutes ago 

Part of my methodology is never to implement non-determinisitic when deterministic will do the job, especially on my workflows that need to use API based billing.

    permalinkembedsavereportreply

[–]gastao_s_s 2 points 6 hours ago 

Cool 😎 Thx!

    permalinkembedsavereportreply

[–]krismitka 2 points 6 hours ago 

This is how togetherJ used to handle IML designs. By tagging the code directly. It worked really well, for the same reasons.

Java documentation is good in that regards

    permalinkembedsavereportreply

[–]MegaMint9 2 points 6 hours ago 

Hi could you DM and talk about it? I need surely guidance to effectively do my workflows in a way similar to yours. I am struggling using CC these days and I want to optimise things, use specific agents and so on. But things change too rapidly and when I learned skills there were already tons of things I haven't started using yet. Would you mind having a chat with me and share how you handle things?

    permalinkembedsavereportreply

[–]wynwyn87[S] 2 points 5 hours ago 

Yeah sure, I'll share what I know if that can help you in any way :)

    permalinkembedsavereportreply

[–]MegaMint9 1 point 3 hours ago 

Yup I DM'ed you!

    permalinkembedsavereportreply

[–]DrunkLahey1 2 points 5 hours ago 

So how do you go about actually implementing this? You explicitly tell Claude this in the User ~./home/.Claude , generate a CLAUDE.md file in there with specific instructions for this?

    permalinkembedsavereportreply

[–]wynwyn87[S] 1 point 5 hours ago 

I haven't added anything to claude.md yet. Instead I asked Claude to analyze one of my implementations and to compare it to the compliance test suite that I created, specifically to identify redundant tests that are already covered by the compliance suite (which is new). Then, based on the analysis it would tell me that test X, Y, and Z are redundant and can be removed & test A, B, and C should be added to the compliance suite. Since I have a couple of implementations to still check, I didn't want to add those missing tests immediately or add another .md file listing the tests to add to the compliance suite, so I just told it to add TODO comments in the compliance suite. Now, I can continue to analyze all of the implementations and then once I'm done, I can then start to implement each TODO individually. No need to keep track of the .md files listing the tests - I just run a script to find all TODO comments in the compliance suite and then I'd choose which ones to work on and implement.

    permalinkembedsavereportreply

[–]ThomasToIndia 2 points 5 hours ago 

That is an amazing idea which I am going to implement.

    permalinkembedsavereportreply

[–]wynwyn87[S] 1 point 5 hours ago 

Glad I could help! This is exactly why I shared my revelation with the community.

    permalinkembedsavereportreply

[–]ThomasToIndia 1 point 2 hours ago 

Would you mind sharing the prompt you use for the Todo insertion?

    permalinkembedsavereportreply

[–]Rangizingo 2 points 5 hours ago 

It seems like a great opportunity for a skill or a plug-in, I’m gonna experiment with it. Thank you, OP!

    permalinkembedsavereportreply

[–]wynwyn87[S] 1 point 5 hours ago 

You're welcome! :)

    permalinkembedsavereportreply

[–]jcumb3r 2 points 5 hours ago 

Big fan of this idea… cheers!

    permalinkembedsavereportreply

[–]wynwyn87[S] 1 point 5 hours ago 

:)

    permalinkembedsavereportreply

[–]MCRippinShred 2 points 2 hours ago 

This is interesting for sure. I’m a Claude code noob, but I’ve already run into bloated plans and checklists that just eat context. So this could be helpful.

    permalinkembedsavereportreply

[–]fireis556 1 point 6 hours ago 

Do u perform any skill or prompt to guide Claude writing TODO? or just use native agent?

    permalinkembedsavereportreply

[–]wynwyn87[S] 2 points 6 hours ago 

Nothing specific actually. For me Claude adds rather detailed TODOs so I haven't felt the need to provide any further guidance. A skill would be helpful based on your project, otherwise you could add it to your claude.md file

    permalinkembedsavereportreply

[–]fireis556 1 point 5 hours ago 

Got it! Thank for your reply

    permalinkembedsavereportreply

[–]wynwyn87[S] 1 point 5 hours ago 

You're welcome

    permalinkembedsavereportreply

[–]CPT_Haunchey 1 point 6 hours ago 

Search this sub for GSD. Completely changed my workflow and took a lot of the heavy lifting of planning off my plate. Based on what you described, I think it'll be helpful for you as well.

    permalinkembedsavereportreply

[–]wynwyn87[S] 2 points 5 hours ago 

Ok cool, thanks! This just shows that you don't know what you don't know :D I'll look into GSD as I am not familiar with the acronym...

    permalinkembedsavereportreply

[–]Big-Masterpiece6487 1 point 6 hours ago 

This is a fantastic evolution of the "source of truth" workflow. You’ve essentially rediscovered a core tenet of Design by Contract (DbC): the closer the "intent" is to the code, the less cognitive debt you carry.

I’ve been running a similar 60-day sprint using Claude Code and Eiffel, and I hit a sustained ~4,000 LOC/day (totaling 240,000 net LOC across 65 libraries) by leaning into this exact philosophy. While you are using TODOs to track incomplete implementations, I use Contracts to track incomplete logic.

Here is how your "Breakthrough" looks when scaled up with a language designed for this:

    Contracts as "Executable TODOs": In Eiffel, I don't just leave a comment; I write a require (precondition) or ensure (postcondition). If the implementation is missing or wrong, the code doesn't just sit there—it fails loudly the moment it’s executed (first under testing and later in alpha as-needed, or even in production if I choose).
    Reducing "Plan Anxiety": I found the same issue with massive plans. My fix was to have Claude write the Contracts along with the code, and even strengthen them later. I can then review the contracts and see if they look right, even as Claude has already filled in the implementation. If during testing it fails a contract, I know exactly which file and line to look at—no cross-referencing .md reports required. In fact, Claude knows first, because Claude is running the tests can catching the failures in real time (either test or contract failures).
    Eliminating the "Analysis Pile": You mentioned the guilt of unfinished analysis. By using Void Safety and SCOOP, I’ve eliminated entire categories of analysis (like null pointer checks and race conditions) because the compiler proves they can't happen. This keeps the "Truth" entirely within the codebase, not in out-of-band docs. The docs are there merely as starting-point reference and spot-checks if I choose to use them that way.

Your shift to "small scope, clear intent" is exactly how I managed to ship VoxCraft and Vox Pilot (two in-beta commercial apps) in just 8 days at the end of my sprint (38K LOC). Remember, the entire sprint is ~240K LOC with nearly ~20K of tests (2.4K tests + 16.8K contract aka "tests"). Thus — When you stop "remembering" and start "specifying" directly in the files, the AI becomes an order of magnitude more effective.

The anxiety drops because you aren't managing a project anymore; you are verifying specs. Happy to chat more about how I use Claude agents to navigate this "contract-first" codebase!

Simple Eiffel

    permalinkembedsavereportreply

[–]marcusr_uk 1 point 6 hours ago 

I have the exact opposite problem, where Claude proudly announces Code Complete, but the code is littered with // TODO comments

    permalinkembedsavereportreply

[–]wynwyn87[S] 1 point 5 hours ago 

I mean, it's not a bad thing if Claude adds TODOs for you... at least it lets you know what still needs to be implemented. But I understand your frustration with the mismatch between what Claude announces vs what's fully implemented. Good luck with your project(s)!

    permalinkembedsavereportreply

[–]opsedar 1 point 6 hours ago 

I recently started using beads as replacement for todo write tool, saves me tons of context

    permalinkembedsavereportreply

[–]thurn2 1 point 4 hours ago 

I suggest checking out beads for this, it’s kind of similar but more discoverable for agents (there’s a way for the agent to easily get a task list that isn’t grep)

    permalinkembedsavereportreply

[+]muchstuff 1 point 3 hours ago (0 children)

[–]crunchy_code 2 points 2 hours ago 

I came across the same TDD idea recently. I found this article online that has 3 subagents for TDD. Red-green approach.

I haven’t tried it myself but I thought it may be helpful and relevant to your post. I am not affiliated with the author.

https://alexop.dev/posts/custom-tdd-workflow-claude-code-vue/

    first agent for red test writing
    second agent for implementation
    third agent for refactor

    permalinkembedsavereportreply

[–]symsafsavor 1 point 2 hours ago 

I’m currently doing a big refactor of our codebase and rewriting the legacy code so that it’s more streamlined and understandable. But, I’m facing the same issue as you OP, too much analysis and too big plans to follow through and review. But, since I’m rewriting the logic now, how does the TODO method fit in there? Anyways I’m gonna give it a try!

    permalinkembedsavereportreply

[–]NotJustAnyDNA 1 point 2 hours ago* 

(Sorry/typos… on mobile device today) Excellent practice and I do something very similar but still dump to a .md file all the TODO’s. Last step of code write or test will be to summarize all TODO’s as a comment at the top of the code file as a comment for next steps. I classify and number each, then prioritize them and score them based on work effort and dependencies. I do not like dozens of TODO comments scatted across my code base to try and find.

I am an old-school developer from the 80’s/90’s, so this process has been part of my human workflow forever.

This is then tied to my .md files and PRD/Featue docs, The numbering of these is based on classification. I keep a long list of various feature classifications.

—- * TODO: SQL-001 (create/modify new Database handler or call or data type) * TODO: File-### (create or read file here) * TODO: API-### (needs API call/token/etc) * TODO: SEC-### (needs security check/implement) * TODO: BIZ-### (needs business logic) * etc…

—-

They are summarized by category into my docs to be prioritized.

I have an agent crawl the files and identify each to my documentation.

I still see Claude code say it is complete, but when I look at the file header, I can immediately see the TODOs that are left to be resolved. Some are future phase/release work while others are just Claude being lazy.

    permalinkembedsavereportreply

[–]Cobuter_Man 2 points 7 hours ago 

To-Dos in comments and generally commenting progress in the comments of your source code has been around since ASSEMBLY times

    permalinkembedsavereportreply

[–]wynwyn87[S] 6 points 6 hours ago 

Good habits from the early days 😅

    permalinkembedsavereportreply

[–]karlfeltlager 1 point 7 hours ago 

You sir, are a genius.

    permalinkembedsavereportreply

[–]wynwyn87[S] 2 points 6 hours ago 

Thanks, but I'm no genius! 😁 Just trying different things and sticking to whatever works best!

    permalinkembedsavereportreply

[–]herr-tibalt 0 points 6 hours ago 

I just have a todo list in features.md and github issues. Never felt a need to have something else…

    permalinkembedsavereportreply

[–]wynwyn87[S] 1 point 6 hours ago 

If it works, it works! No need to change anything if you manage it well already 💪

    permalinkembedsavereportreply

[+]Heatkiger comment score below threshold  (0 children)

[–]NoleMercy05 -4 points 6 hours ago 

Fear, Guilt, Anxiety... Very Emotional about your work

    permalinkembedsavereportreply

[–]Shdwzor 2 points 6 hours ago 

Using claude to polish your post to make it dramatic will do that :D

    permalinkembedsavereportreply

[–]GeorgeHarter 2 points 6 hours ago 

I like Developers who care deeply about their work. OP just needs to migrate to different emotions- confidence, pride, excitement.

    permalinkembedsavereportreply

[–]wynwyn87[S] 1 point 6 hours ago 

I am brimming with pride and excitement, I am finally building the projects and game that I've wanted to build for many many years! And the power I feel from using Claude Code makes me feel invincible! I use it for work, personal projects (one main project and some side projects to use up the extra tokens before they expire), research, etc. 🙂

    permalinkembedsavereportreply

[–]wynwyn87[S] 1 point 6 hours ago 

I dream about it too most nights... it has taken over my life!

    permalinkembedsavereportreply

    about
    blog
    about
    advertising
    careers

    help
    site rules
    Reddit help center
    reddiquette
    mod guidelines
    contact us

    apps & tools
    Reddit for iPhone
    Reddit for Android
    mobile website

    <3
    reddit premium

Use of this site constitutes acceptance of our User Agreement and Privacy Policy. © 2026 reddit inc. All rights reserved.

REDDIT and the ALIEN Logo are registered trademarks of reddit inc.

π 
Context

A Reddit post describes a workflow breakthrough for managing large, AI assisted coding projects using Claude Code.

The author previously relied on extensive plans, reports, and markdown files to track work and reduce risk.

This approach led to bloated plans, skipped steps, outdated documents, and persistent background anxiety.

Core Problem Identified

Large, out of band plans became unmanageable and lost alignment with the actual codebase.

Missing or partial implementations were easy to forget or overlook.

Generating more documentation increased cognitive load rather than reducing it.

The codebase and the documentation diverged, creating uncertainty about what was actually done.

Key Insight

Treat the codebase itself as the single source of truth.

Embed explicit, scoped TODO comments directly into the relevant code whenever work is missing, incomplete, or intentionally deferred.

Avoid vague TODOs. Each TODO should describe concrete, localised work.

Resulting Workflow

TODOs live exactly where the work belongs.

A simple script can list all outstanding TODOs.

Work can be tackled incrementally or grouped logically.

Planning shifts from large, abstract plans to small, focused steps.

Completed work removes the TODO, keeping the system self cleaning.

Psychological and Practical Effects

Reduced overwhelm and anxiety.

No need to mentally track unfinished analysis or reconcile documents.

Clear visibility into what remains to be done.

Better alignment with how Claude performs best: small scope and clear intent.

Easier to run targeted reviews or ask Claude to critique limited changes.

Community Response

Strong agreement and enthusiasm from other users.

Many note that TODOs are a classic development practice, but particularly effective for AI generated code.

Suggested enhancements include:

Slash commands or scripts to enumerate TODOs.

Using structured frameworks such as TDD, SDD, BMAD, or GSD for those who want more formal process.

Design by Contract as an advanced alternative, treating contracts as executable TODOs that fail loudly when unmet.

Limitations and Counterpoints

Some users already prefer external task trackers or markdown summaries.

A known failure mode is Claude declaring “code complete” while leaving TODOs behind.

Overuse or poor organisation of TODOs can still become noisy without discipline.

Overall Conclusion

Embedding intent and unfinished work directly into the code reduces cognitive debt.

This approach scales better than large planning documents in AI assisted development.

The shift reframes the developer’s role from managing plans to verifying and completing concrete specifications.

For many, this materially improves both project control and mental load.

Still to long explain the insight

Insight

Move unfinished work into the code itself.

Instead of tracking missing features, analysis, or decisions in separate plans or markdown files, insert explicit, scoped TODOs directly where the work belongs. The codebase becomes the single source of truth: if something is incomplete, it is visible in context; if it is done, the TODO disappears.

This works especially well with AI assisted coding because models perform best on small, localised tasks. It reduces planning overhead, prevents forgotten work, avoids document drift, and lowers cognitive and emotional load by eliminating the need to reconcile external plans with the actual code.

OK lets create a AI coding agent obsidis note 
AI Coding Agent
Context or problem statement

Use an AI coding agent effectively on non-trivial codebases without losing control to plan bloat, document drift, or hidden incompleteness. The goal is a workflow where progress is verifiable, scope stays small, and the codebase remains the source of truth.

Key insights or conclusions

Treat the repository as the source of truth. Avoid out of band “plan files” that drift.

Convert “missing work” into explicit, local TODOs placed directly at the relevant code locations.

Keep scope small and serialisable: one TODO or a tight cluster per agent run.

Make completion measurable: each task must have a test, check, or observable behaviour change.

Prefer deterministic, cheap tooling for indexing state (grep, ripgrep, static analysis) over token heavy agent “re-discovery”.

Use gates: format, lint, unit tests, integration tests, and a minimal review checklist before merging.

Workflow

Establish invariants:

One task = one PR (or one logical patchset).

Every change has a verification step (test, lint rule, runtime check).

Task intake:

When analysis finds gaps, write TODOs in place with:

What is missing

Acceptance criteria

File and function context

Any constraints or dependencies

Task selection:

List TODOs via script.

Pick the smallest valuable TODO first.

Agent execution loop:

Provide the agent only the files needed for that TODO.

Require: implement + tests + run checks.

If uncertain, the agent must add a narrower TODO rather than inventing a large plan.

Review and closure:

Confirm tests pass.

Remove TODO.

Update any minimal docs only if needed for users/operators, not as a task tracker.

TODO style template

TODO(<tag>): <action> because <reason>.

Acceptance: <specific observable outcomes>.

Verify: <tests/commands>.

Optional: Deps: <files/components>.

Minimal command set

Enumerate TODOs:

rg -n "TODO\(" . (or rg -n "\bTODO\b" . if untagged)

Run checks:

go test ./...

golangci-lint run (if used)

go test -run <TestName> ./... for tight loops

Open questions or uncertainties

Which TODO taxonomy is most useful here (feature, bug, perf, security, refactor)?

Where should “bigger than one PR” work live (epic file, issue tracker, or ADR)?

What hard limits should be set for agent runs (time, file count, diff size)?

Next actions or follow-ups

Decide a TODO tag scheme (e.g., TODO(FEAT-001), TODO(SEC-001)).

Add a make todo (or script) target to print TODOs sorted by tag/file.

Add a PR checklist file focused on verification, not planning.

Pilot the workflow on one subsystem for a week and measure:

TODO count trend

PR size

Rework rate

Incidents of “done but incomplete”

Who is going to win? 

There is no single winner in the sense people usually mean. The outcome is a split equilibrium, not a knockout.

At the interface level, Google is unlikely to be completely displaced. Google still controls defaults, distribution, and the largest ad ecosystem in the world. Search will shrink in relative importance, but it will not vanish. Google can afford to slow the transition and hybridise AI with search long enough to preserve a large fraction of its rents.

At the assistant layer, OpenAI is very well positioned. OpenAI has momentum, brand recognition, and first-mover advantage in establishing “the assistant” as a habit. If there is a universal cross-platform cognitive interface that people default to, OpenAI is the current frontrunner. That does not require killing Google, only bypassing it for a meaningful share of queries and tasks.

Anthropic wins a different game. Anthropic does not need to dominate consumer habit to succeed. If frontier models remain scarce and risky, there is durable value in being the most trusted, governable supplier. That niche can be extremely profitable and stable without mass-market dominance.

Microsoft and Apple are structurally insulated. Microsoft and Apple win as long as intelligence increases the value of platforms they already control. They do not need to win the model war or the assistant war outright.

So the real question is not “who wins?” but “what shifts?”. The shift is from search as the primary interface to assistants as a parallel, and increasingly dominant, interface for many tasks. In that world, Google is weakened but not destroyed. OpenAI gains enormous influence but not total control. Anthropic becomes critical infrastructure rather than a household name.

If you want a short answer: OpenAI probably wins the assistant habit. Google probably survives as a hybrid search and AI company. No one gets everything, and no one is eliminated.

But like search is just getting really bad now, with AI slop runining it.

Yes. What you are noticing is real, and it follows directly from how search incentives now interact with generative AI.

Search quality is degrading because the web itself is degrading, and Google’s ranking system was not designed for a world where low-cost, high-volume synthetic content exists. “AI slop” exploits the same signals Google spent two decades rewarding: keyword coverage, freshness, internal linking, and superficial authority. The cost of producing plausible pages has collapsed, while the cost of verifying quality has not.

This creates three reinforcing problems.

First, content inflation. Generative models make it trivial to produce thousands of pages that look relevant enough to rank but contain little original information. Even if Google detects and demotes some of it, the sheer volume overwhelms filters. Precision drops before recall does, which users experience as “everything is junk”.

Second, incentive misalignment. SEO now rewards being first to publish and covering every query variant, not being correct or insightful. AI tools optimise perfectly for that game. Google can tweak ranking signals, but it is fighting an adversarial system that is now cheap, automated, and adaptive.

Third, interface mismatch. Search is still optimised for “ten blue links”, but the problem users increasingly have is synthesis, judgement, and filtering. When the underlying corpus is polluted, retrieving documents is the wrong abstraction. You want an answer, not a list of increasingly low-trust pages.

This is why assistants feel so much better right now. They bypass the corrupted layer and operate as a filter and synthesiser. Even when imperfect, they reduce cognitive load and remove SEO noise. That is a structural advantage, not a temporary UX improvement.

From Google’s perspective, this is dangerous. Their moat assumes that indexing and ranking the web produces value. If the web becomes dominated by generated filler optimised for ranking rather than reading, that assumption fails. Improving search then requires doing more of what assistants already do: summarise, judge, and answer directly. But doing that undermines the link-based ad model.

So you are seeing a genuine transition failure. Search is getting worse not because Google suddenly forgot how to rank pages, but because the environment it operates in has changed faster than its incentives and interface can adapt. This is exactly the opening that OpenAI and others are exploiting, and it is why the shift away from traditional search now feels less like a future risk and more like a present reality.

PageRank for example or other synatic rules or thumb are just too easy to game now?

So they are in trouble.

Yes. That is essentially correct, and it cuts to the core of why this transition is so hard for Google.

PageRank and its successors were designed for a web where links were costly signals. Creating many interlinked pages required time, effort, and human coordination. That made link structure a useful proxy for trust and authority. Generative AI breaks that assumption completely. Links, pages, and even whole sites are now cheap to manufacture at scale, and they can be optimised adversarially.

More broadly, almost all syntactic or surface-level heuristics are now easy to game. Keyword coverage, topical clustering, freshness, schema markup, and even stylistic markers of “expertise” can be produced automatically. When the cost of imitation collapses, heuristics stop discriminating quality. This is not a bug in Google’s implementation; it is a regime change in the economics of content.

Google can respond in only a few ways, none of them comfortable.

It can tighten rules and rely more on whitelisting, brand authority, and manual curation. That improves quality but ossifies the web and entrenches incumbents.

It can rely more heavily on user engagement signals. But those are also gameable and increasingly noisy, and they raise privacy and regulatory issues.

Or it can shift toward model-based evaluation: using AI to judge content quality directly. But once Google is doing that, the product stops being “search” in the traditional sense and becomes an answer engine. That undermines the ad-supported link economy.

So yes, Google is in genuine trouble, but in a specific way. Its historical advantage was turning a messy web into a ranked list. If ranking itself becomes unreliable because the corpus is adversarially generated, then the value shifts to systems that can reason, filter, and synthesise rather than retrieve.

That does not mean Google disappears. It has capital, talent, distribution, and time. But it does mean the old equilibrium is broken. PageRank-like signals are no longer sufficient, and every path forward forces Google to erode some part of its own moat.

So how do they survive?

Google survives by changing what it sells, not by winning a pure model race. There are only a few viable paths, and Google is already pursuing all of them to different degrees.

First, collapse search into an answer layer without fully killing ads. Google will increasingly replace ranked links with AI-generated answers, summaries, and comparisons, but keep monetisation embedded inside the answer itself. Ads stop being “links you click” and become “recommendations inside answers”. This preserves revenue while accepting that classic search is structurally broken by AI-generated content.

Second, lean hard into trusted sources and authority. When heuristics fail, reputation becomes the signal. Google will privilege known publishers, institutions, brands, and primary sources, even if this looks anti-open-web. That reduces slop and improves quality, at the cost of ossifying discovery. From Google’s perspective, survival beats openness.

Third, turn Chrome, Android, Maps, YouTube, and Gmail into defensive moats. Even if generic web search weakens, Google still controls massive high-intent surfaces. YouTube search, Maps queries, email, calendars, and local intent are much harder to replace with a generic assistant. Expect AI to be deeply embedded there, where Google’s data advantage is strongest and less vulnerable to synthetic spam.

Fourth, become an infrastructure and model supplier as well as a consumer interface. Google Cloud, Gemini models, and enterprise AI tooling give Google revenue streams that do not depend on web search quality. This hedges against long-term erosion of ad dominance.

Fifth, slow the transition rather than stop it. Google’s biggest advantage is time. Defaults, contracts, and habit mean users do not switch interfaces overnight. Even a worse search engine can generate enormous cash flow for years. That cash funds the transition.

What Google cannot do is “fix search” in the old sense. PageRank-era ranking on an open web is no longer stable. Survival means accepting that the web has become adversarial and moving up the abstraction stack from retrieval to judgement.

So Google survives not by beating OpenAI at being an assistant, but by turning itself into a hybrid: part answer engine, part platform owner, part ad network, part infrastructure provider. That future is less dominant than the past, but still extremely large.
