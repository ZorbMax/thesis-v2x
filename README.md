# thesis-v2x
## Progress:
### Meeting 2:
#### Enrollment:

Papers:

J. Whitefield, L. Chen, T. Giannetsos, S. Schneider, and H. Treharne,“Privacy-enhanced capabilities for VANETs using direct anonymous attestation”

N. Desmoulins, A. Diop, Y. Raffle, J. Traoré, and J. Gratesac, “Practical anonymous attestation-based pseudonym schemes for vehicular networks”

#### Re-enrollment:

Can't keep track of long term credentials if we want to preserve privacy

revoked TC go in mode "revoked" and thus can't run JOIN (or can JOIN but telling Issuer that TC got revoked)

What to do with self revocation ? 

-> force TC to contact RA first if self revoked

RA keep history of revoked pseudo that didnt reply (so got self revoked) OR keep all pseudo in history

RA reply to TC by sending the list of pseudonyms revoked in the window where TC self revoked 

Need to explore pseudonyms generation (Can a TC recognise his own pseudo without the need to keep them in memory? Seems like it can by computing pk_ps' = w^s (??))

Also, what happens if I turn off the car ? How to keep crypto credentials in memory of TC ? Need to have long term memory

#### DAA implementations:

xaptum in c : https://github.com/xaptum/ecdaa

rust adaptation : https://github.com/akakou/ecdaa-rs

#### V2X implementations:

(Open source) Veins: https://github.com/sommer/veins C++

(Open source) Artery: https://github.com/riebl/artery C++ (extension of Veins first but can be independant)

(Open source) Vanetza: https://github.com/riebl/vanetza C

#### Next? 

Explore already existing implementations and combine + adapt them to implement enrollment (V2X + DAA)

Better understanding of pseudonyms generation and verifying

#### Research question :

How does a practical V2X Direct Anonymous Attestation scheme perform in terms of speed, computational requirements, scalability, network overhead, and memory needs?

How does the scalability, computational requirements, network overhead and memory needs of DAA revocation schemes compare to those of PKI (both passive and active), and what enhancements have been made in these aspects?


### Meeting 1:
What do I need to add to existing implementation ?

Relaying HB every Tv -> is the value of Tv is supposed to be public ? (attacker can find the value by dropping until he's revocked)

Other paper focus lots of things -> I focus on revocation ? No, implement most realistic scheme possible.

Pseudonyms management ? In the paper, DAA don't really use them to verify ? PKI do use them because they are the proof they are enrolled ?
(can't use symetric key as there is no TC to store it without the user seeing it)

Rust (great choice) / Go / C

Focus on self revocation, enrollement, re enrollment (big picture)

Search for already existing V2X implementation or DAA implementation (cryptographic side of it)

