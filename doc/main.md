"If you're busy and someone hands you a lemon, hand it back and ask for lemonade."

This document presents *Zen Beer Garden*, a proven approach for defending systems against work-based [high-density attacks](##hd). 

Today’s applications, frameworks, languages, and servers crumble when subjected to high- density attacks.

Zen Beer Garden defends against these attacks using a [simple approach](##abstract-simple).

We have [experimentally verified](##zbg) that Zen Beer Garden can successfully defend web applications against high-density attacks.

***

[How to read this document](##howto).

[Index](##index)

~index
## Index

- [2012 Beer Garden Technical Report](##bg-tech)
- [A note on terminology](##hd-terms)
- [Example work-based high-density attack](##hd-ex)
- [Every legitimate request eventually reaches the worker because the worker will eventually be free or bored at the same time that the legitimate request arrives in the Doorman's hands](##spec-eventually)
- [For our experiments, we installed ZBG over top of four different web applications](##abstract-apps).
- [High-density attacks](##hd)
- [High-density attacks allow small forces to defeat larger forces](##hd-asym)
- [High-density attacks are more *powerful*](##hd-compare-power)
- [High-density attacks are more *economical*](##hd-compare-econ)
- [High-density attacks are more *stealthy*](##hd-compare-stealth)
- [High-density attacks are specialized](##specialized)
- [High-density attacks compared to conventional low-density attacks](##hd-compare)
- [High-density vulnerabilities are everywhere](##hd-survey)
- [How columns work](##columns)
- [How to enlarge an image](##enlarge)
- [How to read this document](##howto)
- [If the Bouncer hands it back, then the Doorman turns the tables on the requester](##spec-handback)
- [Issue SOLR-3652](##solr-3652)
- [Internet services are generally vulnerable to low-density attacks](##gen-vuln)
- [Java infinite-loop high-density vulnerability](##CVE-2010-4476)
- [Lately attackers have been increasingly utilizing high-density attacks](##hd-lately)
- [Legitimate requests](##spec-legit)
- [Low-density attacks require little-to-no specialization](##ld-specialize)
- [Low-density vulnerabilities are more prevalent than high-density vulnerabilities](##prevalent)
- [Note to hackers](##enlarge-req)
- [Note: content-delivery networks offer a form of economical over-provisioning](##cdn)
- [Note: not all network protocols are inherently vulnerable to low-density attacks](##atm)
- [PHP infinite-loop high-density vulnerability](##CVE-2010-4645)
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

~howto
## How to read this document

This document is presented in [Sidenote](https://github.com/mikegagnon/sidenote) format.

- Click the links you're interested ins
- [How to enlarge an image](##enlarge)
- [How columns work](##columns)

~columns
## How columns work

To increase or decrease the number of columns, click "**more columns**" or "**fewer columns**" in the upper right corner of the page

If a column is moved off screen, and you want to see that column again, just click the "**back**" or "**forward**" blue arrows.

<img src="img/arrows.png">

~enlarge
## How to enlarge an image

Decrease the number of columns by clicking "**fewer columns**" in the upper right-hand corner. The fewer the columns, the larger the image.

When you're done, click "**more columns**" until you're happy with the number of columns.

Try it out.

<img src="img/deathstar.jpg">

[Note to hackers](##enlarge-req).

~enlarge-req
## Note to hackers

I would love a Github pull request on [Sidenote](https://github.com/mikegagnon/sidenote)  so that we can enlarge images with an overlay, on click. :-)

~hd
## High-density attacks

A high-density attack is when a tiny bomb causes a huge explosion.

A *work-based* high-density attack is one where the tiny bomb causes the victim to perform an explosive amount of work. [Examples](##hd-ex).

[A note on terminology](##hd-terms).

[Compared to conventional low-density attacks](##hd-compare), high density attacks are particularly dangerous because they are particularly powerful, economical, and stealthy.

With high-density attacks, you don’t need an entire army to attack your enemies. You just need tiny bombs.

High-density attacks allow [small forces to defeat larger forces](##hd-asym).

High-density [vulnerabilities](##hd-survey) are everywhere.

[Lately](##hd-lately), attackers have been increasingly utilizing high-density attacks since the defenses against conventional DoS attacks are becoming increasingly effective.

~hd-ex
## Example work-based high-density attacks
*Hypothetical example*: Bob transmits a single HTTP request to Wikipedia, which causes Wikipedia to spin so much CPU there's a blackout for everyone.

*Real examples*:

- Bob triggers logic errors that lead to [infinite loops](##ex-infinite) on the server.
- Bob causes an SQL database to execute [exorbitantly expensive database operations](##ex-sql).
- Bob triggers [excessive regular-expression backtracking](##ex-re).

TODO: Link to vulns and attacks used in experiments

~ex-infinite
## Infinite loops

See for example the [PHP](##CVE-2010-4645) and [Java](##CVE-2010-4476) floating-point vulnerabilities.

~CVE-2010-4645
## CVE-2010-4645

"strtod.c, as used in the zend_strtod function in PHP 5.2 before 5.2.17 and 5.3 before 5.3.5, and other products, allows context-dependent attackers to cause a **denial of service (infinite loop)** via a certain floating-point value in scientific notation, which is not properly handled in x87 FPU registers, as demonstrated using 2.2250738585072011e-308." -- [https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-4645](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-4645)

~CVE-2010-4476
## CVE-2010-4476

"The Double.parseDouble method in Java Runtime Environment (JRE) in Oracle Java SE and Java for Business 6 Update 23 and earlier, 5.0 Update 27 and earlier, and 1.4.2_29 and earlier, as used in OpenJDK, Apache, JBossweb, and other products, allows remote attackers to cause a **denial of service via a crafted string that triggers an infinite loop** of estimations during conversion to a double-precision binary floating-point number, as demonstrated using 2.2250738585072012e-308." -- [https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-4476](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-4476)

~ex-sql
## Exorbitantly expensive database operations

See for example Django Ticket 9479 in our survey as well as our SQL-overload experiment in Section 6.2.8

TODO: Full report

~ex-re
## Excessive regular-expression backtracking

See for example the Django vulnerability CVE-2009-3695 as well as our regex-overload experiment in Section 6.3.5

TODO: Full report

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

Compared to low-density attacks, high-density attacks are:

- [More powerful](##hd-compare-power)
- [More economical](##hd-compare-econ)
- [More stealthy](##hd-compare-stealth)

Low-density vulnerabilities are [more prevalent](##prevalent) than high-density vulnerabilities.

High-density attacks are [specialized](##specialized).

~specialized
## Specialization

Low-density attacks require [little-to-no specialization](##ld-specialize) in order to attack a particular target.

High-density attacks on the other hand require attacks tailored to application-specific vulnerabilities. For example, an attack might need to exploit an underflow to cause excessive looping, as exemplified by [Issue SOLR-3652](##solr-3652).

~solr-3652
## Issue SOLR-3652

TODO. See section 3.12

~ld-specialize
## Little-to-no specialization

All that is needed is the ability to generate a large volume of traffic towards the victim. There exist a variety of generic, off-the-shelf tools that can be used to launch effective low-density attacks. For example, the [Low Orbit Ion Cannon](https://en.wikipedia.org/wiki/Low_Orbit_Ion_Cannon) can target any web service on the Internet.


~prevalent
## Prevalence

Internet services are [generally vulnerable](##gen-vuln) to low-density attacks.

While not ubiquitous like low-density vulnerabilities, high-density vulnerabilities are prevalent. In our [2012 survey](##bg-tech) of 16 web systems we found 71 publicly known high-density vulnerabilities.

~bg-tech
## 2012 Beer Garden Technical Report

TODO

~gen-vuln
## General vulnerability

First the design of the TCP/IP protocol suite is inherently vulnerable to low-density attacks since it does not enforce any quality of service (QoS); i.e. the network itself makes no attempt to ensure that misbehaving users can't infringe on the quality of service for other users. [Note](##atm).

Second, typical server software does not limit resource usage per user.

Lastly, most Internet servers are under provisioned because straightforward over-provisioning is not cost effective. [Note](##cdn).

These deficiencies make it possible for attackers to consume large amounts of resources simply by submitting large volumes of requests.

~atm
## Note

Not all network protocols are inherently vulnerable to low-density attacks. For example, the ATM protocol has quality-of-service (QoS) policing built into the network.

~cdn
## Note

Content-delivery networks offer a form of economical over-provisioning.

~hd-compare-power
## Power
High-density attacks are more *powerful* than low-density attacks, because high-density attacks create more work, per request.

For example, the [HashDoS](##hashdos) high-density attack can consume 100% CPU using an attack with an attack rate less than 1 kilobit-per-second.

In contrast, low-density attacks are less potent and necessitate a large volume of malicious requests in order to succeed.

~hashdos
## HashDoS

The HashDoS attack against CRuby 1.8 can keep one i7 core 100% busy with an attack rate of 720 bits/s.

See Alexander Klink and Julian Walde, "[Efficient Denial of Service Attacks on Web Application Platforms](https://events.ccc.de/congress/2011/Fahrplan/attachments/2007_28C3_Effective_DoS_on_web_application_platforms.pdf)," in The 28th Chaos Communication Congress, 2011.

~hd-compare-stealth
## Stealth

Low-density attacks are easily detectable since the flood of requests produces many loud observables throughout the network. Monitoring the network -- at any point in the path -- clearly reveals the telltale signs of a DoS flood.

On the other hand, high-density attacks produce fewer observables. In practice, when a system experiences a high-density attack the operator observes the service outage then must troubleshoot to identify the cause. The effects of high-density attacks are often similar to the effects caused by accidental faults in the system.

~hd-compare-econ
## Economics

High-density attacks are more economical since they are more [more powerful](##hd-compare-power).

It is often possible to launch a successful high-density attack using the resources of a single attacker machine.

In contrast, low-density attacks require more attacker resources since they are less potent.

To successfully execute a low-density attack against a well-resourced victim, attackers most often require an entire army of attacking machines (i.e. a botnet).

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
