---
title: "Majority voting with Boyer-Moore"
description: "A playful walkthrough of the Boyer-Moore majority vote algorithm using Hogwarts professors."
pubDate: 2026-10-01
heroImage: "../../assets/Boyer-Moore.png"
---

Came across this interesting algorithm. Used for knowing the contestant with the majority in a voting.

Say professors <span style="color: #7c3aed;">McGonagall</span>, <span style="color: #ef4444;">Snape</span>, <span style="color: #0ea5e9;">Flitwick</span> and <span style="color: #22c55e;">Sprout</span> are all contesting to be the next headmaster/headmistress at Hogwarts, after Dumbledore.

All the students are given a choice to vote for their favourite professor.

The common approach is segregating the votes based on the contestant, counting each group and finally deciding the leader.

But in majority voting, the contestant has to get more than half the number of votes. That’s what this algorithm is for.

So let’s say we like to do majority voting i.e. any of the 4 professors needs to have more than half the number of students voting for them.

Here’s how the voting goes:

Initially count is 0. leader is None. Students are casting their votes as follows:

Dean Thomas’s vote: <span style="color: #7c3aed;">McGonagall</span> => count becomes 1 (increment, since leader is None yet), leader becomes <span style="color: #7c3aed;">McGonagall</span>.

Seamus Finnigan’s vote: <span style="color: #7c3aed;">McGonagall</span> => count becomes 2. (increment, since it’s the same contestant again)

Draco Malfoy’s vote: <span style="color: #ef4444;">Snape</span> (obviously 😉 ) => count becomes 1 (decrement, since it’s a different contestant)

Neville Longbottom’s vote: <span style="color: #22c55e;">Sprout</span> => count becomes 0 (decrement, since it’s a different contestant again)

Hermione Granger’s vote: <span style="color: #0ea5e9;">Flitwick</span> => leader becomes <span style="color: #0ea5e9;">Flitwick</span> (since count is 0).count becomes 1 (since current vote is the same as for leader).

Ron Weasley’s vote: <span style="color: #0ea5e9;">Flitwick</span> => count becomes 2 (increment, since it’s the same contestant again)

Harry Potter’s vote: <span style="color: #7c3aed;">McGonagall</span> => count becomes 1 (decrement, since it’s a different contestant)

….

….

….

Thus, all the students cast their votes. Not imagining all their votes here 😛

Get the idea?

Initially, count is set to 0 and leader is set to no one.
The contestant who got the first vote is set to leader and count is incremented.
count keeps incrementing as long as the current vote is for the same contestant.
If it’s for a different contestant, count decrements.
At any point of time, if count becomes 0, leader is reset to current vote’s contestant and the algorithm continues.
At the end, whichever contestant leader is set to, they’re declared the winner of the majority voting contest.
This algorithm is based on the clever idea of cancellation of votes, if a diffent contestant comes up for the next vote.
Very ingenius of <a href="https://en.wikipedia.org/wiki/Robert_S._Boyer" target="_blank" rel="noopener noreferrer">Mr Boyer</a> and <a href="https://en.wikipedia.org/wiki/J_Strother_Moore" target="_blank" rel="noopener noreferrer">Mr Moore</a>!

P.S. Who do you think became the next headmaster/headmistress of Hogwarts? My bet is on <span style="color: #7c3aed;">McGonagall</span> 😉

