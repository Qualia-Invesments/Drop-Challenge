# Qualia Engineering Challenge - "The Drop"

We appreciate your interest in working at Qualia Investments! You are invited to complete this coding challenge as an important step in our mutual assessment of fit. 

## Introduction

A ticket's life starts when a primary exchange (like Ticketmaster) releases an initial supply at a fixed price. That supply then might trickle to secondary exchange (like Stubhub) in hands of brokers. Brokers are betting that consumers will pay a premium after the event sells out.

Later on, primaries tend to "drop" extra tickets long after they were supposedly sold out. Drops are are an opportunity for brokers to invest in events that already have guaranteed demand -- well it is if they're actually fast enough to snatch up those new tickets before they sell out again in probably minutes.

Automated drop detection is one pillar of Qualia's software platform for brokers. You will build a fully-functional MVP of a drop checker for this assessment.

## Product Requirements

Your submission should poll an arbitrary set of Ticketmaster events for drops. When a drop happens it should send out an email notification.

Ticketmaster displays availability information on their event pages, but not through a documented API. You're going to need to figure out how to scrape availability. **HINT:** Poke around in your browser's dev tools on their website. You should be able to find a useful network request.

Our definition of a drop is when an event transitions from sold out to having supply. So even if new tickets are released, it's not a drop unless the event had been sold out before that point. A drop is a stateful event; you can't detect a drop from an isolated invocation of your system because our definition depends on ticket availability over time. **HINT:** That means your solution will require some form of persistence layer.

Design your system to check for drops on only ~50 events. Prioritize low-latency over throughput here. A late drop notification is useless because the event would probably already be sold out again.

Minimum requirements:
- Check a list of Ticketmaster event IDs for drops
- When a drop happens send details (event, section, seats) to a list of emails
- Write a readme including
    - Architecture overview
    - Justification for the design decisions you made
    - Installation / configuration / deployment instructions

## Implementation Details

- You can hard-code a list of Ticketmaster event IDs to check in a text file called `events.txt`. You can identify events by the ID at the end of their event page url (https://www1.ticketmaster.com/event/310056478FE21D8F). 
- We will share with you some sample events to use
- Hard-code emails to notify in `emails.txt`
- Use Python

## Rubric

The goal is to test your:
- resourcefulness
- knowledge of the Python language
- clarity of your code
- clarity of your readme (I love working with people who are articulate about technical topics)

Bonus points for:
- dockerizing
 - using Mongo or Postgres (our stack)
- writing tests

## Submission Instructions

- Email the link to a public repo with your work to augustus@investqualia.com and kyle@investqualia.com. Remember to include a readme.

_Feel free to reach out to me at augustus@investqualia.com with questions. I'm pumped to see what you come up with._



