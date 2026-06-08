# The Invisible Bug

A browser-based detective game about silent Next.js 16 bugs.

Built for the [DEV June Solstice Game Jam 2026](https://dev.to/devteam/join-the-june-solstice-game-jam-1000-in-prizes-3jla).

## Play It Live

[shubhrapokhariya.github.io/the-invisible-bug](https://shubhrapokhariya.github.io/the-invisible-bug/)

## What This Is

You are a developer. The build is green. CI passed. TypeScript is happy.

And something is completely broken in production.

Three real bugs are hiding in your codebase. The sun is setting. You have until the solstice to find them.

This game is based on actual Next.js 16 caching bugs I hit in production. The kind that compile clean, deploy fine, and break silently at 3am. Every level comes from a real incident.

## The Turing Angle

In 1950, Alan Turing asked: can a machine think?

This game asks something harder: can a human spot the bug that looks like correct code?

The build passes. The type checker passes. Every automated system says everything is fine. And something is still wrong.

That gap, between "valid" and "correct", is where this game lives.

## How to Play

1. Open the game in your browser
2. Click to begin, read the intro terminal
3. Browse files, CI logs, and production metrics
4. Click the line you think is buggy
5. Find it before the sun sets, or watch production collapse

Wrong clicks give feedback. Right clicks save the deploy.

## The Bugs (Spoilers)

&lt;details&gt;
&lt;summary&gt;Click to reveal&lt;/summary&gt;

**Level 1:** Tag mismatch between `cacheTag()` and `revalidateTag()` — different strings, zero TypeScript errors, cache never invalidates.

**Level 2:** Single-argument `revalidateTag()` deprecated in Next.js 16 — compiles clean with `strict: false`, silently falls back to legacy cache behavior.

**Level 3:** `middleware.ts` deprecated for Node.js runtime logic — file compiles, build says "middleware detected", but it does not run. Auth bypassed in production.

&lt;/details&gt;

## Tech Stack

One HTML file. About 1040 lines of vanilla JavaScript.

- No framework
- No build step
- No dependencies
- Web Audio API for all sounds (synthesized, zero external files)
- SVG for the sun arc timer

## Related Reading

This game is part of my Next.js 16 caching series on DEV:

1. [I built a free debugger because Next.js 16 'use cache' was completely invisible during development](https://dev.to/shubhradev/i-built-a-free-debugger-because-nextjs-16-use-cache-was-completely-invisible-during-development-4a8)
2. [7 Next.js 16 Caching Bugs That Compile Fine and Break Silently in Production](https://dev.to/shubhradev/7-nextjs-16-caching-bugs-that-compile-fine-and-break-silently-in-production-1cap)
3. [Next.js 16 Broke My App in 4 Places and None of Them Threw an Error](https://dev.to/shubhradev/nextjs-16-broke-my-app-in-4-places-and-none-of-them-threw-an-error-51mn)
4. [After 7 Next.js 16 Caching Bugs, I Stopped Guessing and Built a System](after-7-nextjs-16-caching-bugs-i-stopped-guessing-and-built-a-system-4ijp)

## License

MIT
