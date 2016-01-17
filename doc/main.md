"If you're busy and someone hands you a lemon, hand it back and ask for lemonade."

This document presents *Zen Beer Garden*, a proven approach for defending systems against work-based [high-density attacks](##hd). 

Today’s applications, frameworks, languages, and servers crumble when subjected to high- density attacks.

Zen Beer Garden defends against these attacks using a [simple approach](##abstract-simple).

We have [experimentally verified](##zbg) that Zen Beer Garden can successfully defend web applications against high-density attacks.

[Index](##index).

~index
## Index

- [A note on terminology](##hd-terms)
- [Compared to high-density attacks, low-density attacks are less *powerful*](##hd-compare-power)
- [Compared to high-density attacks, low-density attacks are less *economical*](##hd-compare-econ)
- [Compared to high-density attacks, low-density attacks are less *stealthy*](##hd-compare-stealth)
- [Example work-based high-density attack](##hd-ex)
- [Every legitimate request eventually reaches the worker because the worker will eventually be free or bored at the same time that the legitimate request arrives in the Doorman's hands](##spec-eventually)
- [For our experiments, we installed ZBG over top of four different web applications](##abstract-apps).
- [High-density attacks](##hd)
- [High-density attacks allow small forces to defeat larger forces](##hd-asym)
- [High-density attacks compared to conventional low-density attacks](##hd-compare)
- [High-density vulnerabilities are everywhere](##hd-survey)
- [If the Bouncer hands it back, then the Doorman turns the tables on the requester](##spec-handback)
- [Lately attackers have been increasingly utilizing high-density attacks](##hd-lately)
- [Legitimate requests](##spec-legit)
- [The algorithm can be summed up as: "If you're busy and someone hands you a lemon, hand it back and ask for lemonade."](##spec)
- [The algorithm: Workers and Requests](##spec-wr)
- [The algorithm: Busy, Bored, and Free](##spec-bbf)
- [The algorithm: Overloads](##spec-overloads)
- [The algorithm: Introduction to Zen Beer Garden](##spec-intro)
- [The algorithm: Theoretical Security Guarantee](##spec-sec)
- [The algorithm: The Zen Beer Garden Defense](##spec-zbg)
- [The algorithm: The Bouncer](##spec-bouncer)
- [The algorithm: The Doorman](##spec-doorman)
- [The algorithm: Proof for Security Guarantee](##spec-proof)
- [The most conventional type of denial-of-service (DoS) attack is a flood resource-consumption attack](##low-density)
- [Thinking in terms of mass and volume leads to a useful metaphor: density](##density)
- [We have experimentally verified that Zen Beer Garden can successfully defend web applications against high-density attacks](##zbg)
- [ZBG succeeded for two of the web applications](##abstract-success).
- [Zen Beer Garden defends against these attacks using a simple approach](##abstract-simple)



~hd
## High-density attacks

A high-density attack is when a tiny bomb causes a huge explosion.

A *work-based* high-density attack is one where the tiny bomb causes the victim to perform an explosive amount of work. [Example](##hd-ex).

[A note on terminology](##hd-terms).

[Compared to conventional low-density attacks](##hd-compare), high density attacks are particularly dangerous because they are particularly powerful, economical, and stealthy.

With high-density attacks, you don’t need an entire army to attack your enemies. You just need tiny bombs.

High-density attacks allow [small forces to defeat larger forces](##hd-asym).

High-density [vulnerabilities](##hd-survey) are everywhere.

[Lately](##hd-lately), attackers have been increasingly utilizing high-density attacks since the defenses against conventional DoS attacks are becoming increasingly effective.

~hd-ex
## Example work-based high-density attack
Bob transmits a single HTTP request to Wikipedia, which causes Wikipedia to spin so much CPU there's a blackout for everyone.

The above Wikipedia attack is a hypothetical example.

TODO

~hd-terms
## A note on terminology
For the sake of brevity, throughout the rest of this document, unless specified otherwise, the term *high-density attack* refers to *work-based high-density cyber attack*.

Zen Beer Garden only defends against *work-based* attacks.

Our experimental implementation, [ZBG](##zbg), only defends against work-based *cyber* attacks.

~hd-asym
## Small forces defeat larger forces

For example, the Rebels used high-density attacks to destroy the Death Star, twice.

<img src="img/deathstar.jpg">

~hd-survey
## Vulnerabilities

TODO

~hd-compare
## Compared to conventional low-density attacks

The most conventional type of denial-of-service (DoS) attack is a [flood](##low-density) resource-consumption attack. 

Thinking in terms of mass and volume leads to a useful metaphor: [density](##density).

Conventional flood attacks are low-density attacks, since each malicious request only consumes a small amount of victim resources.

For a low-density attack to be effective, the attacker must generate a large volume of requests, which can be accomplished using an army of attack computers (such as a botnet).

Compared to high-density attacks, low-density attacks are:

- [Less powerful](##hd-compare-power)
- [Less economical](##hd-compare-econ)
- [Less stealthy](##hd-compare-stealth)

~hd-compare-power
## Power
Low-density attacks are less *powerful* than high-density attacks, because low-density attacks consume fewer resources, per request.

~hd-compare-stealth
## Stealth
Low-density attack are less *stealthy* than high-density attacks, because low-density attacks must submit more requests to have an equivalent effect (since they are [less powerful](##hd-compare-power)). Thus, low-density attacks produce more observables.

~hd-compare-econ
## Economics
Low-density attacks are less *economical* than high-density attacks, because they are [less powerful](##hd-compare-power). For a low-density attack to have the same effect as a high-density attack, the low-density attack must submit far more requests. To submit more requests, the attacker will need greater computational resources, such as an army of requesters, viz. a botnet.

High-density attacks require less computing power.

~low-density
## Flood

In a flood attack, the attacker consumes a *massive* amount of victim resources by flooding the victim with a large *volume* of resource requests.

~density
## Density

In the density metaphor, mass measures the victim's resource consumption.

Volume measures the number of malicious resource requests.

Density measures the amount of victim resources consumed per malicious request (which, equivalently, is the ratio of mass to volume).

~hd-lately
## Lately

See Akamai’s 2012 [The State of the Internet](https://www.akamai.com/us/en/about/news/press/2012-press/akamai-first-quarter-2012-state-of-the-internet-report.jsp) report, Section 1.4 "Observed Denial-of-Service (DoS) Attack Activity."

~abstract-simple
## Simple approach

Zen Beer Garden protects each worker with a *Doorman* and a *Bouncer*.

The Doorman charges admission fees, which limits the amount of requests the worker receives.

The Bouncer kicks out requests that overload the worker.

The [algorithm](##spec) can be summed up as: "If you're busy and someone hands you a lemon, hand it back and ask for lemonade."

~spec
## Algorithm

This section provides the algorithmic specification for Zen Beer Garden, it's security guarantee, and a simple proof.

- [Workers and Requests](##spec-wr)
- [Busy, Bored, and Free](##spec-bbf)
- [Overloads](##spec-overloads)
- [Introduction to Zen Beer Garden](##spec-intro)
- [Theoretical Security Guarantee](##spec-sec)
- [The Zen Beer Garden Defense](##spec-zbg)
- [The Bouncer](##spec-bouncer)
- [The Doorman](##spec-doorman)
- [Proof for Security Guarantee](##spec-proof)

~spec-wr
## Workers and Requests

A worker is a thing that attempts to complete requests.

Every worker can complete a certain percentage of [legitimate requests](##spec-legit) (*Y*%) within a certain amount of time (*Z* seconds).

For example: *Nancy can complete 95% of professional requests within 3 hours.*

~spec-legit
## Legitimate requests

A request is legitimate if it is *not* intended to overload the worker.

A request is illegitimate if it is intended to overload the worker.

~spec-bbf
## Busy, Bored, and Free

- A worker is busy if she has been working on her current request for less than *Z* seconds.
- A worker is bored if she has been working on her current request for *Z* seconds or more.
- A worker is free if she isn't doing any work at all.

~spec-overloads
## Overloads

A worker can become overloaded under a variety of circumstances.

Requests might be coming in too quickly.

Or, there might be a deluge of work-intensive requests.

Or, in the worst-case scenario, a worker might be subjected to an incessant stream of impossible-to-fulfill requests.

Workers should protect themselves from overloads by employing the Zen Beer Garden defense.

~spec-intro
## Introduction to Zen Beer Garden

You should protect workers from overloads by placing Doormen and Bouncers between workers and requesters.

Theoretically, the Zen Beer Garden defense is 100% effective, even against the most threatening deluges.

In practice, the Zen Beer Garden defense tends to be effective, although there are many reasons the defense might fail.

~spec-sec
## Theoretical Security Guarantee

Zen Beer Garden is 100% effective.&#42;

If you use the Zen Beer Garden defense, you will never&#42; become overloaded. No matter what,&#42; *Y%* of legitimate requests are guaranteed to eventually complete.

&#42; *As long Doormen and Bouncers don’t get overloaded, legitimate requesters are patient, legitimate requesters are willing to work, your boss is competent, etc.*

~spec-zbg
## The Zen Beer Garden Defense

Guard every worker with a Bouncer and a Doorman.

Every request for work must go through the Doorman, then the Bouncer, before finally reaching the worker.

For example: *If a pharmaceutical rep wants Nancy to read an advertisement, the rep must give the ad to the Doorman, who then passes it to the Bouncer, who then might pass it to Nancy.*

~spec-bouncer
## The Bouncer

If the worker is free, the Bouncer passes the request to the worker.

If the worker is bored, the Bouncer asks the worker to stop working on her current task and accept the new request. The Bouncer then informs the old requester that her request was bounced.

If the worker is busy, the Bouncer hands the request back to the Doorman.

~spec-doorman
## The Doorman

When the Doorman receives a request from a requester, the Doorman passes it to the Bouncer.

If the Bouncer [hands it back](##spec-handback), then the Doorman turns the tables on the requester. Specifically, the Doorman invents some work for the requester to do. The Doorman passes the request back to the requester, and asks the requester to do the work the Doorman just invented.

For example: *If a rep wants to show Nancy an ad, but Nancy is busy, the Doorman might ask the rep to write a one-page essay explaining why the ad is relevant to Nancy in particular.*

These requests are designed to delay the requester while at the same time possibly having the requester do useful work for the worker.

The Doorman will refuse to pass the original request until the requester completes the work request.

If the worker continues to be busy, the Doorman increases the amounts of work he asks of requesters.

*If Nancy is bombarded by reps, she might ask reps for 10-page essays. Of course, every essay must come with a one-page summary.*

As the worker becomes less busy, the Doorman decreases the amounts of work he asks of requesters.

~spec-handback
## Hands it back

Recall, if the worker is busy, the [Bouncer](##spec-bouncer) hands the request back to the Doorman.


~spec-proof
## Proof for Security Guarantee

At least *Y*% of legitimate requests that reach the worker complete. We know this because the Bouncer only bounces a request after the worker has been working on it for at least *Z* seconds.

Every legitimate request eventually reaches the worker because the worker will [eventually](##spec-eventually) be free or bored at the same time that the legitimate request arrives in the Doorman's hands. Of course, the requester might have performed quite a bit of work in order to convince the Doorman to accept the request.

~spec-eventually
## Eventually

Assume the worst case scenario. I.e., assume *N* requests arrive every moment for *M* moments, where *N* and *M* are arbitrarily large.

Assume there is a mix of legitimate requests and illegitimate requests, where the illegitimate requests cause an infinite amount of work.

Assume the Doorman uses an exponential back off and back on strategy on a per request basis.

**Theorem**: Every request eventually reaches the worker.

**Proof**: The exponential back off will cause the requests to fan out over time.

~zbg
## Experimentally verified

To test Zen Beer Garden, we built a software system called *ZBG*.

ZBG defends web applications against high-density cyber attacks.

For our experiments, we installed ZBG over top of [four different web applications](##abstract-apps).

We subjected the applications to a suite of 10 different attacks of varying sophistication.

ZBG succeeded for [two of the web applications](##abstract-success).

Our experiments show that Zen Beer Garden works.

~abstract-apps
## Four different web applications

TODO

PHP, Python, Java, and Ruby.

~abstract-success
## ZBG succeeded for two of the web applications
TODO

ZBG successfully protected the PHP and Python applications because they have low memory footprints and fast restart times.

A different software approach would be necessary for Zen Beer Garden to successfully defend web applications with high memory footprints or slow restart times.
