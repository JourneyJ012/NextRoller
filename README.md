# NextRoller
This document is incomplete! You can help by giving well formed opinions in https://github.com/JourneyJ012/NextRoller/issues/1 so that I can learn how to do stuff better.

## Introduction
NextRoller will be a cross-platform application that intends to serve as a simple replacement for other Dungeons and Dragons apps.

### What Role This Software Serves
This will serve two major roles, one personal and one as a software.
Software-wise, I want to make an actually good, highly-extensible D&D software with a large amount of features, such as homebrew support, damage calculators and NPC management.
Personally, this is hopefully my first actually cross-platform app. It may be re-wrote several times before the 1.0.0 release.

### Software Path
This is being made to be a convenient piece of software. As such, it should work offline with an option for online support (such as by linking to a web-domain running server software). Therefore, this will be broken into 3 parts --- the dedicated server mode, the "serverless" mode, and the client. For the sake of clarity, "serverless" and "dedicated server mode" will be called "server".

Serverless will primarily focus on Cloudflare Workers' free tier, such as storing configs in Cloudflare R2 and quests in a D1 Database. 

Dedicated Servers will replicate this fragmented design, but with MySQL as the DB.

On the client, content will be cached so that the app is usable without a connection. The goal is that a player with no internet can still understand their character, even if they can't access quests. When a connection exists, the client will use last-write-wins to manage conflicts with the server, except in the case that the Dungeon Master has made an edit within 16 hours, where they will win instantly.

I don't have a lot of plans. Submit some PRs and help make this decent.
