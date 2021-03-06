"If you're busy and someone hands you a lemon, hand it back and ask for lemonade."

This document presents *Zen Beer Garden*, a proven approach for defending systems against work-based [high-density attacks](##hd). 

Today’s applications, frameworks, languages, and servers crumble when subjected to high-density attacks.

High-density vulnerabilities are prevalent. We found 71 high-density vulnerabilities in [our survey](##hd-survey) of high-density vulnerabilities..

Zen Beer Garden defends against these attacks using a [simple approach](##abstract-simple).

We have [experimentally verified](##zbg) that Zen Beer Garden can successfully defend web applications against high-density attacks.


***

[How to read this document](##howto).

[Bibliography](##bib)

~index
## Index


- [2012 Beer Garden Technical Report](##bg-tech)
- [A note on terminology](##hd-terms)
- [Every legitimate request eventually reaches the worker because the worker will eventually be free or bored at the same time that the legitimate request arrives in the Doorman's hands](##spec-eventually)
- [Example work-based high-density attack](##hd-ex)
- [For our experiments, we installed ZBG over top of four different web applications](##abstract-apps).
- [HashDoS](##hashdos)
- [High-density attacks allow small forces to defeat larger forces](##hd-asym)
- [High-density attacks are *economical*](##hd-compare-econ)
- [High-density attacks are *less recyclable*](##recycle)
- [High-density attacks are *powerful*](##hd-compare-power)
- [High-density attacks are *specialized*](##specialized)
- [High-density attacks are *stealthy*](##hd-compare-stealth)
- [High-density attacks compared to conventional low-density attacks](##hd-compare)
- [High-density attacks vary in *sophisticated*](##sophisticated)
- [High-density attacks](##hd)
- [High-density vulnerabilities are everywhere](##hd-survey)
- [How columns work](##columns)
- [How do web applications handle high-density attacks? Caching / memoization](##handle-cache)
- [How do web applications handle high-density attacks? Over-provisioning resources](##handle-over)
- [How do web applications handle high-density attacks? Overloaded server behavior](##handle-overloaded)
- [How do web applications handle high-density attacks? Rate limiting](##handle-rate)
- [How do web applications handle high-density attacks? Switch to lightweight software](##handle-switch)
- [How do web applications handle high-density attacks? The "bouncer" defense](##handle-bouncer)
- [How do web applications handle high-density attacks? The "doorman" defense](##handle-doorman)
- [How do web applications handle high-density attacks? The "signature" defense](##handle-sig)
- [How do web applications handle high-density attacks? Timeouts and resource limits](##handle-timeouts)
- [How do web applications handle high-density attacks? Vulnerability patching](##handle-patch)
- [How do web applications handle high-density attacks?](##handle)
- [How to enlarge an image](##enlarge)
- [How to read this document](##howto)
- [If the Bouncer hands it back, then the Doorman turns the tables on the requester](##spec-handback)
- [Implementation and design errors](##surv-imp-design)
- [Internet services are generally vulnerable to low-density attacks](##gen-vuln)
- [Issue SOLR-3652](##solr-3652)
- [Java infinite-loop high-density vulnerability](##CVE-2010-4476)
- [Lately attackers have been increasingly utilizing high-density attacks](##hd-lately)
- [Legitimate requests](##spec-legit)
- [Low-density attacks are conventional floods](##low-density)
- [Low-density attacks require little-to-no specialization](##ld-specialize)
- [Low-density vulnerabilities are more prevalent than high-density vulnerabilities](##prevalent)
- [Mass, volume, and density metaphor](##density)
- [Note to hackers](##enlarge-req)
- [Note: content-delivery networks offer a form of economical over-provisioning](##cdn)
- [Note: not all network protocols are inherently vulnerable to low-density attacks](##atm)
- [Note: we couldn't find vulnerabilities for some systems](##surv-note-na)
- [PHP infinite-loop high-density vulnerability](##CVE-2010-4645)
- [Survey Django](##django)
- [Survey Drupal](##drupal)
- [Survey Java](##java)
- [Survey MediaWiki](##mediawiki)
- [Survey PHP](##php)
- [Survey Python](##python)
- [Survey Redmine](##redmine)
- [Survey Ruby on Rails](##ror)
- [Survey Ruby](##ruby)
- [Survey Solr](##solr)
- [Survey Tomcat](##tomcat)
- [Survey WordPress](##wordpress)
- [The algorithm can be summed up as: "If you're busy and someone hands you a lemon, hand it back and ask for lemonade."](##spec)
- [The algorithm: Busy, Bored, and Free](##spec-bbf)
- [The algorithm: Introduction to Zen Beer Garden](##spec-intro)
- [The algorithm: Overloads](##spec-overloads)
- [The algorithm: Proof for Security Guarantee](##spec-proof)
- [The algorithm: The Bouncer](##spec-bouncer)
- [The algorithm: The Doorman](##spec-doorman)
- [The algorithm: The Zen Beer Garden Defense](##spec-zbg)
- [The algorithm: Theoretical Security Guarantee](##spec-sec)
- [The algorithm: Workers and Requests](##spec-wr)
- [The result of errors in string parsing](##surv-string)
- [This survey is not intended to be exhaustive](##surv-exhaustive)
- [This survey only includes publicly documented vulnerabilities](##surv-pub)
- [Triggered by manipulating the input in common ways](##surv-manip)
- [Vulnerability survey methodology](##surv-method)
- [We also rate our confidence that the issue is an exploitable high-density vulnerability](##surv-confidence)
- [We have experimentally verified that Zen Beer Garden can successfully defend web applications against high-density attacks](##zbg)
- [We surveyed 16 software software projects](##surv-soft)
- [ZBG succeeded for two of the web applications](##abstract-success).
- [Zen Beer Garden defends against these attacks using a simple approach](##abstract-simple)


~bib
## Bibligraphy

1. [Bug #60082](##Bug-60082)
1. [Bug #61240](##Bug-61240)
1. [Bug 18489](##Bug-18489)
1. [Bug 44818](##Bug-44818)
1. [Bug 7601](##Bug-7601)
1. [CVE-2004-0983](##CVE-2004-0983)
1. [CVE-2005-3510](##CVE-2005-3510)
1. [CVE-2006-0322](##CVE-2006-0322)
1. [CVE-2006-5467](##CVE-2006-5467)
1. [CVE-2007-3698](##CVE-2007-3698)
1. [CVE-2007-5712](##CVE-2007-5712)
1. [CVE-2008-3656](##CVE-2008-3656)
1. [CVE-2008-3790](##CVE-2008-3790)
1. [CVE-2008-4310](##CVE-2008-4310)
1. [CVE-2008-5349](##CVE-2008-5349)
1. [CVE-2009-1100](##CVE-2009-1100)
1. [CVE-2009-1190](##CVE-2009-1190)
1. [CVE-2009-2625](##CVE-2009-2625)
1. [CVE-2009-3695](##CVE-2009-3695)
1. [CVE-2009-3876](##CVE-2009-3876)
1. [CVE-2009-3877](##CVE-2009-3877)
1. [CVE-2009-4017](##CVE-2009-4017)
1. [CVE-2009-4418](##CVE-2009-4418)
1. [CVE-2010-4476](##CVE-2010-4476)
1. [CVE-2010-4476](##CVE-2010-4476)
1. [CVE-2010-4535](##CVE-2010-4535)
1. [CVE-2010-4645](##CVE-2010-4645)
1. [CVE-2011-0534](##CVE-2011-0534)
1. [CVE-2011-1471](##CVE-2011-1471)
1. [CVE-2011-2526](##CVE-2011-2526)
1. [CVE-2011-4137](##CVE-2011-4137)
1. [CVE-2011-4815](##CVE-2011-4815)
1. [CVE-2011-4838](##CVE-2011-4838)
1. [CVE-2011-4858](##CVE-2011-4858)
1. [CVE-2011-4885](##CVE-2011-4885)
1. [CVE-2012-0022](##CVE-2012-0022)
1. [CVE-2012-0845](##CVE-2012-0845)
1. [CVE-2012-0876](##CVE-2012-0876)
1. [CVE-2012-1150](##CVE-2012-1150)
1. [CVE-2012-1588](##CVE-2012-1588)
1. [CVE-2012-2336](##CVE-2012-2336)
1. [CVE-2012-2921](##CVE-2012-2921)
1. [CVE-2012-3443](##CVE-2012-3443)
1. [CVE-2012-3444](##CVE-2012-3444)
1. [CVE-2012-4885](##CVE-2012-4885)
1. [Client Puzzles: A Cryptographic Countermeasure Against Connection Depletion Attacks](##handle-cycles)
1. [DDoS Defense by Offense](##handle-net)
1. [Defect #11106](##Defect-11106)
1. [Defect #11275](##Defect-11275)
1. [Defect #3449](##Defect-3449)
1. [Defect #5942](##Defect-5942)
1. [Defect #633](##Defect-633)
1. [Defect #6796](##Defect-6796)
1. [Defect #7699](##Defect-7699)
1. [Defect #9796](##Defect-9796)
1. [Drupd0s.sh exploit](##Drupd0ssh-exploit)
1. [Efficient Denial of Service Attacks on Web Application Platforms](##klink)
1. [Issue #1525](##Issue-1525)
1. [Issue #2619](##Issue-2619)
1. [Issue #3672](##Issue-3672)
1. [Issue 13891](##Issue-13891)
1. [Issue SOLR-138](##Issue-SOLR-138)
1. [Issue SOLR-2631](##Issue-SOLR-2631)
1. [Issue SOLR-2855](##Issue-SOLR-2855)
1. [Issue SOLR-3243](##Issue-SOLR-3243)
1. [Issue SOLR-3606](##Issue-SOLR-3606)
1. [Issue SOLR-3652](##Issue-SOLR-3652)
1. [Low Orbit Ion Cannon](##cannon)
1. [National Vulnerability Database](##nist)
1. [Patch #9484](##Patch-9484)
1. [SA-CONTRIB-2012-126](##SA-CONTRIB-2012-126)
1. [Selective early request termination for busy internet services](##zhou)
1. [The State of the Internet](##akamai)
1. [Ticket #11685](##Ticket-11685)
1. [Ticket #19973](##Ticket-19973)
1. [Ticket 1265946](##Ticket-1265946)
1. [Ticket 13275](##Ticket-13275)
1. [Ticket 7336](##Ticket-7336)
1. [Ticket 9479](##Ticket-9479)
1. [Web content adaptation to improve server overload behavior](##bib-handle-switch)
1. [WebSOS: An Overlay-based System For Protecting Web Servers From Denial of Service Attacks](##handle-human)


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

High-density [vulnerabilities](##hd-survey) are prevalent.

[Lately](##hd-lately), attackers have been increasingly utilizing high-density attacks since the defenses against conventional DoS attacks are becoming increasingly effective.

How do web applications [handle](##handle) high-density attacks?

~handle
## How do web applications handle high-density attacks?

- [Overloaded server behavior](##handle-overloaded)
- [Timeouts and resource limits](##handle-timeouts)
- [Vulnerability patching](##handle-patch)
- [The "bouncer" defense](##handle-bouncer)
- [Rate limiting](##handle-rate)
- [The "doorman" defense](##handle-doorman)
- [The "signature" defense](##handle-sig)
- [Over-provisioning resources](##handle-over)
- [Caching / memoization](##handle-cache)
- [Switch to lightweight software](##handle-switch)

~handle-switch
## Switch to lightweight software

During overloads web applications can [switch](##bib-handle-switch) to using more efficient software components, even if it means sacrificing the user experience somewhat. For example, if an overloaded web application replaced an attacked O(N<sup>2</sup>) algorithm for a less desirable O(N) algorithm, the application would defeat the attack.

~bib-handle-switch
## Web content adaptation to improve server overload behavior

T. F. Abdelzaher and N. Bhatti, "[Web content adaptation to improve server overload behavior](http://www8.org/w8-papers/4c-server/web/web.pdf)," in World Wide Web Conference, 1999.

~handle-cache
## Caching / memoization

Caching the results of requests can turn duplicate high-density requests into low-density requests. However clever adversaries can often evade caching by making each high-density request distinct, or by causing the cache to flush. Also, the semantics of applications do not always permit caching.

~handle-over
## Over-provisioning resources

As a generic defense against DoS attacks, administrators may over-provision servers, allocating significantly more resources than are needed for legitimate traffic. Content-delivery networks, such as Akamai, provide such over provisioning as a service.

Such systems are still vulnerable to high-density attacks, because "infinite-density" attacks can consume even the largest resource pools.

~handle-sig
## The "signature" defense

Firewalls and signature-based intrusion-detection systems are generally ineffective against 0-day high-density attacks because it is difficult to know, a priori, how high-density requests will appear different from low-density requests. Such knowledge is necessary to develop signatures ahead of time.

[ZBG](##zbg) uses a form of signature-based detection by dynamically learning signatures, in real time while an attack happens.

~handle-doorman
## The "doorman" defense

The "[doorman](##spec)" defense rate limits attackers by charging visitors "admission fees." For example a doorman can require visitors pay admission by spending their own [CPU cycles](##handle-cycles), [network bandwidth](##handle-net), and even [human labor](##handle-human).

[ZBG](##zbg) uses the Doorman defense to rate limit attackers according to their CPU resources.

~handle-cycles
## Client Puzzles

Ari Jules and John Brainard, "[Client Puzzles: A Cryptographic Countermeasure Against Connection Depletion Attacks](http://www.internetsociety.org/sites/default/files/juels.pdf)," in Proceedings of NDSS '99 (Networks and Distributed Security Systems), 1999.

~handle-net
## DDoS Defense by Offense

Michael Walfish, Mythili Vutukuru, Hari Balakrishnan, David Karger, and Scott Shenker, "[DDoS Defense by Offense](http://nms.csail.mit.edu/papers/speakup-tocs10.pdf)," in ACM SIGCOMM, 2006

~handle-human
## WebSOS

Angelos Stavrou et al., "[WebSOS: An Overlay-based System For Protecting Web Servers From Denial of Service Attacks](https://www.cs.columbia.edu/~angelos/Papers/2005/websos-jcn.pdf)," in Computer Networks: The International Journal of Computer and Telecommunications Networking - Web security, vol. 48, 2005.

~handle-rate
## Rate limiting
A common approach to DoS defense is rate limiting. If you can sufficiently limit the attacker's rate of admission, it is possible to defend against high-density attacks. However, most off-the-shelf admission controls have a limited ability to rate limit attackers. For example, a rate limiter based on IP addresses won't work against an adversary with many IP addresses. Similarly, a rate limiter based on username won't work against logged out users.

~handle-bouncer
## The "bouncer" defense

Similar to Beer Garden's [Bouncer](##spec) component, some overloaded web servers will [selectively terminate greedy requests](##zhou). These systems are designed to handle occasional bursts of unintentional high-density requests and cannot handle high volumes of high-density requests unless they also rate limit the attacker.

~zhou
## Selective early request termination for busy internet services

Jingyu Zhou and Tao Yang, "[Selective early request termination for busy internet services](http://www2006.wwwconference.org/programme/files/pdf/2011.pdf)," in WWW '06 Proceedings of the 15th international conference on World Wide Web, vol. 2006.

~handle-patch
## Vulnerability patching

Perhaps the most common way developers defend against high-density attacks is identifying and patching specific high-density vulnerabilities. This approach only provides a limited defense since prevention and identification is laborious and error prone. Further, patching cannot defend against 0-day attacks (unlike Zen Beer Garden).

~handle-timeouts
## Timeouts and resource limits

Web servers typically enforce timeouts and resource limits on requests. These limits are liberal so that occasional, legitimate high-density requests can be serviced.

Zen Beer Garden differs by only using liberal limits during normal operation, and switching to tight limits during overloads. Some servers, such as Jetty, also tighten up their timeouts in response to overloads.

TODO: Link Jetty

~handle-overloaded
## Overloaded server behavior

During overloads, typical web servers reject incoming requests.

In contrast, Zen Beer Garden evicts over-budget tasks in favor of new requests. Since over-budget tasks tend to be malicious, Zen Beer Garden's behavior favors legitimate requests.

~hd-ex
## Example work-based high-density attacks
*Hypothetical example*: Bob transmits a single HTTP request to Wikipedia, which causes Wikipedia to spin so much CPU there's a blackout for everyone.

*Real examples*:

- Bob triggers logic errors that lead to [infinite loops](##ex-infinite) on the server.
- Bob causes an SQL database to execute [exorbitantly expensive database operations](##ex-sql).
- Bob triggers [excessive regular-expression backtracking](##ex-re).

See also our [survey of 71 high-density vulnerabilities](##hd-survey).

~ex-infinite
## Infinite loops

See for example the [PHP](##CVE-2010-4645) and [Java](##CVE-2010-4476) floating-point vulnerabilities.

~CVE-2010-4476
## CVE-2010-4476

"The Double.parseDouble method in Java Runtime Environment (JRE) in Oracle Java SE and Java for Business 6 Update 23 and earlier, 5.0 Update 27 and earlier, and 1.4.2_29 and earlier, as used in OpenJDK, Apache, JBossweb, and other products, allows remote attackers to cause a **denial of service via a crafted string that triggers an infinite loop** of estimations during conversion to a double-precision binary floating-point number, as demonstrated using 2.2250738585072012e-308." -- [https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-4476](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-4476)

~ex-sql
## Exorbitantly expensive database operations

See for example Django Ticket 9479 in our survey as well as our SQL-overload experiment in Section 6.2.8

TODO: Full report

~ex-re
## Excessive regular-expression backtracking

See for example the Django vulnerability [CVE-2009-3695](##CVE-2009-3695) as well as our regex-overload experiment in Section 6.3.5

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

We [surveyed 16 software software projects](##surv-soft), and found 71 high-density vulnerabilities.

We performed our survey by [searching public databases](##surv-method).

Our survey reveals that high-density vulnerabilities are often:

- [Implementation and design errors](##surv-imp-design)
- [Triggered by manipulating the input in common ways](##surv-manip)
- [The result of errors in string parsing](##surv-string)

~surv-imp-design
## Implementation and design errors

We were able to classify 57% of the vulnerabilities as either implementation errors (24%) or design errors (33%). [Note](##imp-design-note). 

- [Example implementation errors](##imp-design-imp)
- [Example design errors](##imp-design-design)

<img src="img/imp-design.png">



~imp-design-note
## Note
For the remaining 43% of vulnerabilities we had insufficient information to determine whether they were implementation or design errors.

~surv-manip
## Triggered by manipulating the input in common ways

37% of vulnerabilities are triggered with "large" inputs. [Examples](##surv-manip-large).

21% of vulnerabilities are triggered with "corner-case" input. [Examples](##surv-manip-corner).

11% of vulnerabilities are triggered with malformed input -- input that is either syntactically or
semantically invalid. [Examples](##surv-manip-mal).

<img src="img/invalid.png">








~imp-design-imp
## Example implementation errors

- PHP [CVE-2011-1471](##CVE-2011-1471)
- PHP [CVE-2012-2336](##CVE-2012-2336)
- PHP [CVE-2010-4645](##CVE-2010-4645)
- Ruby [CVE-2006-5467](##CVE-2006-5467)
- Java [CVE-2010-4476](##CVE-2010-4476)
- Java [CVE-2009-2625](##CVE-2009-2625)
- Django [CVE-2010-4535](##CVE-2010-4535)

~imp-design-design
## Example design errors

- PHP [CVE-2011-4885](##CVE-2011-4885)
- PHP [CVE-2009-4418](##CVE-2009-4418)
- PHP [CVE-2009-4017](##CVE-2009-4017)
- Python [CVE-2012-0876](##CVE-2012-0876)
- Python [CVE-2012-1150](##CVE-2012-1150)
- Ruby [CVE-2011-4815](##CVE-2011-4815)
- Ruby [CVE-2011-4838](##CVE-2011-4838)
- Ruby [CVE-2008-3656](##CVE-2008-3656)
- Ruby [CVE-2008-3790](##CVE-2008-3790)
- Java [CVE-2009-1190](##CVE-2009-1190)
- Django [CVE-2012-3444](##CVE-2012-3444)
- Django [CVE-2012-3443](##CVE-2012-3443)
- Django [CVE-2011-4137](##CVE-2011-4137)
- Django [Ticket 13275](##Ticket-13275)
- Django [CVE-2009-3695](##CVE-2009-3695)

~surv-manip-large
## Examples of "large" input vulnerabilities

- PHP [CVE-2009-4418](##CVE-2009-4418)
- PHP [CVE-2009-4017](##CVE-2009-4017)
- Python [CVE-2012-0876](##CVE-2012-0876)
- Python [CVE-2012-1150](##CVE-2012-1150)
- Ruby [CVE-2011-4815](##CVE-2011-4815)
- Ruby [CVE-2011-4838](##CVE-2011-4838)
- Java [CVE-2009-1190](##CVE-2009-1190)
- Django [CVE-2012-3444](##CVE-2012-3444)
- Django [CVE-2012-3443](##CVE-2012-3443)
- Django [CVE-2010-4535](##CVE-2010-4535)


~surv-manip-corner
## Examples of "corner-case" vulnerabilities

- PHP [CVE-2011-4885](##CVE-2011-4885)
- PHP [CVE-2010-4645](##CVE-2010-4645)
- Python [CVE-2012-0876](##CVE-2012-0876)
- Python [CVE-2012-1150](##CVE-2012-1150)
- Ruby [CVE-2011-4815](##CVE-2011-4815)
- Ruby [CVE-2011-4838](##CVE-2011-4838)
- Ruby [CVE-2008-3656](##CVE-2008-3656)
- Java [CVE-2010-4476](##CVE-2010-4476)
- Java [CVE-2009-1190](##CVE-2009-1190)
- Django [Ticket 13275](##Ticket-13275)
- Django [CVE-2009-3695](##CVE-2009-3695)

~surv-manip-mal
## Examples of malformed-input vulnerabilities

- PHP [CVE-2011-1471](##CVE-2011-1471)
- PHP [CVE-2012-2336](##CVE-2012-2336)
- Python [Issue 13891](##Issue-13891)
- Ruby [CVE-2006-5467](##CVE-2006-5467)
- Java [CVE-2009-2625](##CVE-2009-2625)
- Django [CVE-2010-4535](##CVE-2010-4535)

~surv-string-ex
## Examples of string-parsing vulnerabilities

- PHP [CVE-2012-2336](##CVE-2012-2336)
- Python [CVE-2012-0876](##CVE-2012-0876)
- Python [CVE-2012-2921](##CVE-2012-2921)
- Ruby [CVE-2008-3790](##CVE-2008-3790)
- Ruby [CVE-2006-5467](##CVE-2006-5467)
- Java [CVE-2010-4476](##CVE-2010-4476)
- Java [CVE-2009-3877](##CVE-2009-3877)
- Java [CVE-2009-3876](##CVE-2009-3876)
- Java [CVE-2009-2625](##CVE-2009-2625)
- Java [CVE-2009-1190](##CVE-2009-1190)
- Django [CVE-2010-4535](##CVE-2010-4535)






~surv-string
## The result of errors in string parsing

When looking at the tasks the vulnerable code performs, we noticed that many vulnerabilities occurred while parsing strings. [Examples](##surv-string-ex).

<img src="img/parsing.png">




~surv-soft
## Survey of 16 software software projects

- Languages
    - [PHP](##php)
    - [Python](##python)
    - [Ruby](##ruby)
    - [Java](##java)
- Web-application frameworks
    - [Django](##django)
    - [Drupal](##drupal)
    - [WordPress](##wordpress)
    - [Ruby on Rails](##ror)
- Web applications
    - [MediaWiki](##mediawiki)
    - OSQA[*](##surv-note-na)
    - [Redmine](##redmine)
    - [Solr](##solr)
- Servers:
    - [Tomcat](##tomcat)
    - Nginx[*](##surv-note-na)
    - Jetty[*](##surv-note-na)
    - Mongrel[*](##surv-note-na)

~surv-note-na
## Note: we couldn't find vulnerabilities for some systems

While we found several CPU consumption issues in OSQA, Nginx, Jetty, and Mongrel, none of them seemed intentionally exploitable by a remote attacker. We therefore don’t include any OSQA, Nginx, Jetty, or Mongrel vulnerabilities in this survey.

~php
## PHP

1. [Bug #60082](##Bug-60082)
1. [Bug #61240](##Bug-61240)
1. [CVE-2009-4017](##CVE-2009-4017)
1. [CVE-2009-4418](##CVE-2009-4418)
1. [CVE-2010-4645](##CVE-2010-4645)
1. [CVE-2011-1471](##CVE-2011-1471)
1. [CVE-2011-4885](##CVE-2011-4885)
1. [CVE-2012-2336](##CVE-2012-2336)

~python
## Python

1. [CVE-2012-0845](##CVE-2012-0845)
1. [CVE-2012-0876](##CVE-2012-0876)
1. [CVE-2012-1150](##CVE-2012-1150)
1. [CVE-2012-2921](##CVE-2012-2921)
1. [Issue 13891](##Issue-13891)

~ruby
## Ruby

1. [CVE-2004-0983](##CVE-2004-0983)
1. [CVE-2006-5467](##CVE-2006-5467)
1. [CVE-2008-3656](##CVE-2008-3656)
1. [CVE-2008-3790](##CVE-2008-3790)
1. [CVE-2008-4310](##CVE-2008-4310)
1. [CVE-2011-4815](##CVE-2011-4815)
1. [CVE-2011-4838](##CVE-2011-4838)

~java
## Java

1. [CVE-2007-3698](##CVE-2007-3698)
1. [CVE-2008-5349](##CVE-2008-5349)
1. [CVE-2009-1100](##CVE-2009-1100)
1. [CVE-2009-1190](##CVE-2009-1190)
1. [CVE-2009-2625](##CVE-2009-2625)
1. [CVE-2009-3876](##CVE-2009-3876)
1. [CVE-2009-3877](##CVE-2009-3877)
1. [CVE-2010-4476](##CVE-2010-4476)

~django
## Django

1. [CVE-2007-5712](##CVE-2007-5712)
1. [CVE-2009-3695](##CVE-2009-3695)
1. [CVE-2010-4535](##CVE-2010-4535)
1. [CVE-2011-4137](##CVE-2011-4137)
1. [CVE-2012-3443](##CVE-2012-3443)
1. [CVE-2012-3444](##CVE-2012-3444)
1. [Ticket 7336](##Ticket-7336)
1. [Ticket 9479](##Ticket-9479)
1. [Ticket 13275](##Ticket-13275)

~drupal
## Drupal

1. [CVE-2012-1588](##CVE-2012-1588)
1. [Drupd0s.sh exploit](##Drupd0ssh-exploit)
1. [SA-CONTRIB-2012-126](##SA-CONTRIB-2012-126)
1. [Ticket 1265946](##Ticket-1265946)

~wordpress
## Wordpress

1. [Ticket #11685](##Ticket-11685)
1. [Ticket #19973](##Ticket-19973)

~ror
## Ruby on Rails

1. [Issue #1525](##Issue-1525)
1. [Issue #2619](##Issue-2619)
1. [Issue #3672](##Issue-3672)

~mediawiki
## Mediawiki

1. [Bug 7601](##Bug-7601)
1. [Bug 18489](##Bug-18489)
1. [CVE-2006-0322](##CVE-2006-0322)
1. [CVE-2012-4885](##CVE-2012-4885)

~redmine
## Redmine

1. [Defect #633](##Defect-633)
1. [Defect #3449](##Defect-3449)
1. [Defect #5942](##Defect-5942)
1. [Defect #6796](##Defect-6796)
1. [Defect #7699](##Defect-7699)
1. [Defect #9796](##Defect-9796)
1. [Defect #11106](##Defect-11106)
1. [Defect #11275](##Defect-11275)
1. [Patch #9484](##Patch-9484)

~solr
## Solr

1. [Issue SOLR-138](##Issue-SOLR-138)
1. [Issue SOLR-2631](##Issue-SOLR-2631)
1. [Issue SOLR-2855](##Issue-SOLR-2855)
1. [Issue SOLR-3243](##Issue-SOLR-3243)
1. [Issue SOLR-3606](##Issue-SOLR-3606)
1. [Issue SOLR-3652](##Issue-SOLR-3652)

~tomcat
## Tomcat

1. [Bug 44818](##Bug-44818)
1. [CVE-2005-3510](##CVE-2005-3510)
1. [CVE-2011-0534](##CVE-2011-0534)
1. [CVE-2011-2526](##CVE-2011-2526)
1. [CVE-2011-4858](##CVE-2011-4858)
1. [CVE-2012-0022](##CVE-2012-0022)


~conf
## Note on confidence

Confidence marks how confident we are that the issue is actually exploitable.

~Bug-60082
## Bug #60082

**Software project**: PHP

**Year**: 2011

**Confidence**: medium[*](##conf)

**Summary**: "100% CPU / when using references with ArrayObject(&$ref)." 

**Characteristics**: unknown

[bugs.php.net](https://bugs.php.net/bug.php?id=60082)

~Bug-61240
## Bug #61240

**Software project**: PHP

**Year**: 2012

**Confidence**: medium[*](##conf)

**Summary**: "In the document of curl_multi_exec, has a example in the document. it can run in php 5.2, but php 5.3 and php 5.4 cause cpu load 100%. Note: it seems that high CPU consumption only occurs if the developer misuses the libcurl library."

**Characteristics**: unknown

[bugs.php.net](https://bugs.php.net/bug.php?id=61240)

~CVE-2009-4017
## CVE-2009-4017

**Software project**: PHP

**Year**: 2009

**Confidence**: high[*](##conf)

**Summary**: PHP "does not restrict the number of temporary files created when handling a multipart/form- data POST request, which allows remote attackers to cause a denial of service (resource exhaustion)"

**Characteristics**: design error, large input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-4017)



~CVE-2009-4418
## CVE-2009-4418

**Software project**: PHP

**Year**: 2009

**Confidence**: high[*](##conf)

**Summary**: "attackers [can] cause a denial of service (resource consumption) via a deeply nested serialized variable"

**Characteristics**: design error, large input 

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-4418)


~CVE-2010-4645
## CVE-2010-4645

**Software project**: PHP

**Year**: 2010

**Confidence**: high[*](##conf)

**Summary**: "attackers [can] cause a denial of service (infinite loop) via a certain floating-point value in scientific notation, which is not properly handled in x87 FPU registers"

**Characteristics**: implementation error, corner-case input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-4645)


~CVE-2011-1471
## CVE-2011-1471

**Software project**: PHP

**Year**: 2011

**Confidence**: high[*](##conf)

**Summary**: "Integer signedness error in zip_stream.c in the Zip extension in PHP before 5.3.6 allows context-dependent attackers to cause a denial of service (CPU consumption) via a malformed archive file that triggers errors in zip_fread function calls." 

**Characteristics**: implementation error, malformed input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-1471)


~CVE-2011-4885
## CVE-2011-4885

**Software project**: PHP

**Year**: 2011

**Confidence**: high[*](##conf)

**Summary**: PHP "computes hash values for form parameters without restricting the ability to trigger hash collisions predictably, which allows remote attackers to cause a denial of service (CPU consumption) by sending many crafted parameters."

**Characteristics**: design error, corner-case input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-4885)


~CVE-2012-2336
## CVE-2012-2336

**Software project**: PHP

**Year**: 2012

**Confidence**: high[*](##conf)

**Summary**: PHP-CGI "does not properly handle query strings that lack an = (equals sign) character, which allows remote attackers to cause a denial of service (resource consumption) by placing command-line options in the query string"

**Characteristics**: implementation error, malformed input, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-2336)

~CVE-2012-0845
## CVE-2012-0845

**Software project**: Python

**Year**: 2012

**Confidence**: high[*](##conf)

**Summary**: "A denial of service flaw was found in the way Simple XML-RPC Server module of Python processed client connections, that were closed prior the complete request body has been received. A remote attacker could use this flaw to cause Python Simple XML-RPC based server process to consume excessive amount of CPU."

**Characteristics**: unknown

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=/CVE-2012-0845)

[bugs.python.org](http://bugs.python.org/issue14001)


~CVE-2012-0876
## CVE-2012-0876

**Software project**: Python

**Year**: 2012

**Confidence**: high[*](##conf)

**Summary**: "The XML parser (xmlparse.c) in expat before 2.1.0 computes hash values without restricting the ability to trigger hash collisions predictably, which allows context-dependent attackers to cause a denial of service (CPU consumption) via an XML file with many identifiers with the same value."

**Characteristics**: design error, large input, corner-case input, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-0876)

[bugs.python.org](http://bugs.python.org/issue14234)

~CVE-2012-1150
## CVE-2012-1150

**Software project**: Python

**Year**: 2012

**Confidence**: high[*](##conf)

**Summary**: "An attacker can cause hash collisions in hash tables used to implement the dict data structure, leading to worst-case algorithmic performance"

**Characteristics**: design error, large input, corner-case input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-1150)

[bugs.python.org](http://bugs.python.org/issue13703)

[www.ocert.org](http://www.ocert.org/advisories/ocert-2011-003.html)

[Efficient Denial of Service Attacks on Web Application Platforms](##klink)

~CVE-2012-2921
## CVE-2012-2921

**Software project**: Python

**Year**: 2012

**Confidence**: high[*](##conf)

**Summary**: "Universal Feed Parser (aka feedparser or python-feedparser) before 5.1.2 allows remote attackers to cause a denial of service (memory consumption) via a crafted XML ENTITY declaration in a non-ASCII encoded document."

**Characteristics**: Memory consumption, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-2921)


~Issue-13891
## Issue 13891

**Software project**: Python

**Year**: 2012

**Confidence**: high[*](##conf)

**Summary**: "UDP listening programs written in python on this version are susceptible to malformed-UDP-packet based DoS attacks which cause severe CPU spikes in the python process."

**Characteristics**: Malformed input

[bugs.python.org](http://bugs.python.org/issue13891)






~CVE-2004-0983
## CVE-2004-0983

**Software project**: Ruby

**Year**: 2004

**Confidence**: high[*](##conf)

**Summary**: "The CGI module in Ruby 1.6 before 1.6.8, and 1.8 before 1.8.2, allows remote attackers to cause a denial of service (infinite loop and CPU consumption) via a certain HTTP request."

**Characteristics**: unknown

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2004-0983)


~CVE-2006-5467
## CVE-2006-5467

**Software project**: Ruby

**Year**: 2006

**Confidence**: high[*](##conf)

**Summary**: "The cgi.rb CGI library for Ruby 1.8 allows remote attackers to cause a denial of service (infinite loop and CPU consumption) via an HTTP request with a multipart MIME body that contains an invalid boundary specifier, as demonstrated using a specifier that begins with a "-" instead of "&ndash;&ndash;" and contains an inconsistent ID."

**Characteristics**: implementation error, malformed input, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2006-5467)

[rubyforge.org](http://rubyforge.org/pipermail/mongrel-users/2006-October/001946.html)

[blog.evanweaver.com](http://blog.evanweaver.com/2006/10/25/mongrel-denial-of-service-vulnerability/)

~CVE-2008-3656
## CVE-2008-3656

**Software project**: Ruby

**Year**: 2008

**Confidence**: high[*](##conf)

**Summary**: "Algorithmic complexity vulnerability in the WEBrick::HTTPUtils.split_header_value function in WEBrick::HTTP::DefaultFileHandler in WEBrick in Ruby 1.8.5 and earlier, 1.8.6 through 1.8.6-p286, 1.8.7 through 1.8.7-p71, and 1.9 through r18423 allows context-dependent attackers to cause a denial of service (CPU consumption) via a crafted HTTP request that is processed by a backtracking regular expression."

**Characteristics**: design error, corner-case input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=2008-3656)

[www.ruby-lang.org](http://www.ruby-lang.org/en/news/2008/08/08/multiple-vulnerabilities-in-ruby/)


~CVE-2008-3790
## CVE-2008-3790

**Software project**: Ruby

**Year**: 2008

**Confidence**: high[*](##conf)

**Summary**: "The REXML module in Ruby 1.8.6 through 1.8.6-p287, 1.8.7 through 1.8.7-p72, and 1.9 allows context-dependent attackers to cause a denial of service (CPU consumption) via an XML document with recursively nested entities, aka an ".""

**Characteristics**: design error, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-3790)

[www.ruby-lang.org](http://www.ruby-lang.org/en/news/2008/08/23/dos-vulnerability-in-rexml/)

~CVE-2008-4310
## CVE-2008-4310

**Software project**: Ruby

**Year**: 2008

**Confidence**: high[*](##conf)

**Summary**: "httputils.rb in WEBrick in Ruby 1.8.1 and 1.8.5, as used in Red Hat Enterprise Linux 4 and 5, allows remote attackers to cause a denial of service (CPU consumption) via a crafted HTTP request. NOTE: this issue exists because of an incomplete fix for CVE-2008-3656."

**Characteristics**: unknown

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-4310)


~CVE-2011-4815
## CVE-2011-4815

**Software project**: Ruby

**Year**: 2011

**Confidence**: high[*](##conf)

**Summary**: An attacker can cause hash collisions in hash tables used to implement the dict data structure, leading to worst-case algorithmic performance.

Note: this vulnerability is for the CRuby implementation of the Ruby runtime.

**Characteristics**: design error, large input, corner-case input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-4815)

[www.ocert.org](http://www.ocert.org/advisories/ocert-2011-003.html)

[Efficient Denial of Service Attacks on Web Application Platforms](##klink)

~CVE-2011-4838
## CVE-2011-4838

**Software project**: Ruby

**Year**: 2011

**Confidence**: high[*](##conf)

**Summary**: An attacker can cause hash collisions in hash tables used to implement the dict data structure,
leading to worst-case algorithmic performance.

Note: this vulnerability is for the JRuby implementation of the Ruby runtime.

**Characteristics**: design error, large input, corner-case input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-4838)

[www.ocert.org](http://www.ocert.org/advisories/ocert-2011-003.html)

[Efficient Denial of Service Attacks on Web Application Platforms](##klink)



~CVE-2007-3698
## CVE-2007-3698

**Software project**: Java

**Year**: 2007

**Confidence**: high[*](##conf)

**Summary**: "The Java Secure Socket Extension (JSSE) in Sun JDK and JRE 6 Update 1 and earlier, JDK and JRE 5.0 Updates 7 through 11, and SDK and JRE 1.4.2_11 through 1.4.2_14, when using JSSE for SSL/TLS support, allows remote attackers to cause a denial of service (CPU consumption) via certain SSL/TLS handshake requests."

**Characteristics**: unknown

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-3698)


~CVE-2008-5349
## CVE-2008-5349

**Software project**: Java

**Year**: 2008

**Confidence**: high[*](##conf)

**Summary**: "Unspecified vulnerability in Java Runtime Environment (JRE) for Sun JDK and JRE 6 Update 10 and earlier, and JDK and JRE 5.0 Update 16 and earlier, allows remote attackers to cause a denial of service (CPU consumption) via a crafted RSA public key."

**Characteristics**: unknown

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2008-5349)


~CVE-2009-1100
## CVE-2009-1100

**Software project**: Java

**Year**: 2009

**Confidence**: high[*](##conf)

**Summary**: "Multiple unspecified vulnerabilities in Java SE Development Kit (JDK) and Java Runtime Environment (JRE) 5.0 Update 17 and earlier, and 6 Update 12 and earlier, allow remote attackers to cause a denial of service (disk consumption) via vectors related to temporary font files and (1) ""limits on Font creation,"" aka CR 6522586, and (2) another unspecified vector, aka CR 6632886."

**Characteristics**: Disk consumption

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-1100)


~CVE-2009-1190
## CVE-2009-1190

**Software project**: Java

**Year**: 2009

**Confidence**: high[*](##conf)

**Summary**: "Algorithmic complexity vulnerability in the java.util.regex.Pattern.compile method in Sun Java Development Kit (JDK) before 1.6, when used with spring.jar in SpringSource Spring Framework 1.1.0 through 2.5.6 and 3.0.0.M1 through 3.0.0.M2 and dm Server 1.0.0 through 1.0.2, allows remote attackers to cause a denial of service (CPU consumption) via serializable data with a long regex string containing multiple optional groups, a related issue to CVE-2004-2540."

**Characteristics**: design error, large input, corner-case input, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-1190)


~CVE-2009-2625
## CVE-2009-2625

**Software project**: Java

**Year**: 2009

**Confidence**: high[*](##conf)

**Summary**: "MLScanner.java in Apache Xerces2 Java, as used in Sun Java Runtime Environment (JRE) in JDK and JRE 6 before Update 15 and JDK and JRE 5.0 before Update 20, and in other products, allows remote attackers to cause a denial of service (infinite loop and application hang) via malformed XML input, as demonstrated by the Codenomicon XML
fuzzing framework."

**Characteristics**: implementation error, malformed input, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-2625)


~CVE-2009-3876
## CVE-2009-3876

**Software project**: Java

**Year**: 2009

**Confidence**: high[*](##conf)

**Summary**: "Unspecified vulnerability in Sun Java SE in JDK and JRE 5.0 before Update 22, JDK and JRE 6 before Update 17, SDK and JRE 1.3.x before 1.3.1_27, and SDK and JRE 1.4.x before 1.4.2_24 allows remote attackers to cause a denial of service (memory consumption) via crafted DER encoded data, which is not properly decoded by the ASN.1 DER input stream parser, aka Bug Id 6864911."

**Characteristics**: memory consumption, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-3876)


~CVE-2009-3877
## CVE-2009-3877

**Software project**: Java

**Year**: 2009

**Confidence**: high[*](##conf)

**Summary**: "Unspecified vulnerability in Sun Java SE in JDK and JRE 5.0 before Update 22, JDK and JRE 6 before Update 17, SDK and JRE 1.3.x before 1.3.1_27, and SDK and JRE 1.4.x before 1.4.2_24 allows remote attackers to cause a denial of service (memory consumption) via crafted HTTP headers, which are not properly parsed by the ASN.1 DER input stream parser, aka Bug Id 6864911."

**Characteristics**: memory consumption, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-3877)


~CVE-2010-4476
## CVE-2010-4476

**Software project**: Java

**Year**: 2010

**Confidence**: high[*](##conf)

**Summary**: "The Double.parseDouble method in Java Runtime Environment (JRE) in Oracle Java SE and Java for Business 6 Update 23 and earlier, 5.0 Update 27 and earlier, and 1.4.2_29 and earlier, as used in OpenJDK, Apache, JBossweb, and other products, allows remote attackers to cause a denial of service via a crafted string that triggers an infinite loop of estimations during conversion to a double-precision binary floating-point number, as demonstrated using 2.2250738585072012e-308"

**Characteristics**: implementation error, corner-case input, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-4476)





~CVE-2007-5712
## CVE-2007-5712

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~CVE-2009-3695
## CVE-2009-3695

**Software project**: Django

**Year**: 2009 

**Confidence**: high[*](##conf)

**Summary**: "Algorithmic complexity vulnerability in the forms library in Django 1.0 before 1.0.4 and 1.1 before 1.1.1 allows remote attackers to cause a denial of service (CPU consumption) via a crafted (1) EmailField (email address) or (2) URLField (URL) that triggers a large amount of backtracking in a regular expression."

**Characteristics**: design error, corner-case input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-3695/)

[www.djangoproject.com](https://www.djangoproject.com/weblog/2009/oct/09/security/)


~CVE-2010-4535
## CVE-2010-4535

**Software project**: Django

**Year**: 2010

**Confidence**: high[*](##conf)

**Summary**: "The password reset functionality in django.contrib.auth in Django before 1.1.3, 1.2.x before 1.2.4, and 1.3.x before 1.3 beta 1 does not validate the length of a string representing a base36 timestamp, which allows remote attackers to cause a denial of service (resource consumption) via a URL that specifies a large base36 integer."

**Characteristics**: Implementation error, large input, malformed input, string parsing

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2010-4535)

[www.djangoproject.com](https://www.djangoproject.com/weblog/2010/dec/22/security/)

~CVE-2011-4137
## CVE-2011-4137

**Software project**: Django

**Year**: 2011

**Confidence**: high[*](##conf)

**Summary**: "The verify_exists functionality in the URLField implementation in Django before 1.2.7 and 1.3.x before 1.3.1 relies on Python libraries that attempt access to an arbitrary URL with no timeout, which allows remote attackers to cause a denial of service (resource consumption) via a URL associated with (1) a slow response, (2) a completed TCP connection with no application data sent, or (3) a large amount of application data, a related issue to CVE-2011-1521."

**Characteristics**: design error

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-4137)

[www.djangoproject.com](https://www.djangoproject.com/weblog/2011/sep/09/security-releases-issued/)

~CVE-2012-3443
## CVE-2012-3443

**Software project**: Django

**Year**: 2012

**Confidence**: high[*](##conf)

**Summary**: "The django.forms.ImageField class in the form system in Django before 1.3.2 and 1.4.x before 1.4.1 completely decompresses image data during image validation, which allows remote attackers to cause a denial of service (memory consumption) by uploading an image file."

**Characteristics**: memory consumption, design error, large input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-3443)


~CVE-2012-3444
## CVE-2012-3444

**Software project**: Django

**Year**: 2012

**Confidence**: high[*](##conf)

**Summary**: "The get_image_dimensions function in the image-handling functionality in Django before 1.3.2 and 1.4.x before 1.4.1 uses a constant chunk size in all attempts to determine dimensions, which allows remote attackers to cause a denial of service (process or thread consumption) via a large TIFF image."

**Characteristics**: design error, large input

[cve.mitre.org](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-3444)

[www.djangoproject.com](https://www.djangoproject.com/weblog/2012/jul/30/security-releases-issued/)


~Ticket-7336
## Ticket 7336

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Ticket-9479
## Ticket 9479

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Ticket-13275
## Ticket 13275

**Software project**: Django

**Year**: 2010

**Confidence**: medium[*](##conf)

**Summary**: "url_backwards_re appears to hang in some circumstances. When we've seen this before it has been due to catastrophic backtracking, so I'm guessing that's the cause here, though I can't say with complete certainty that that is the the issue."

**Characteristics**: design error, corner-case input

[code.djangoproject.com](https://code.djangoproject.com/ticket/13275)





~CVE-2012-1588
##CVE-2012-1588

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Drupd0ssh-exploit
## Drupd0s.sh exploit

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~SA-CONTRIB-2012-126
## SA-CONTRIB-2012-126

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Ticket-1265946
## Ticket 1265946

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()





~Ticket-11685
## Ticket #11685

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Ticket-19973
## Ticket #19973

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()





~Issue-1525
## Issue #1525

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Issue-2619
## Issue #2619

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Issue-3672
## Issue #3672

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()






~Bug-7601
## Bug 7601

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Bug-18489
## Bug 18489

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~CVE-2006-0322
## CVE-2006-0322

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~CVE-2012-4885
## CVE-2012-4885

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()





~Defect-633
## Defect #633

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Defect-3449
## Defect #3449

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Defect-5942
## Defect #5942

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Defect-6796
## Defect #6796

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Defect-7699
## Defect #7699

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Defect-9796
## Defect #9796

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Defect-11106
## Defect #11106

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Defect-11275
## Defect #11275

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Patch-9484
## Patch #9484

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()





~Issue-SOLR-138
## Issue SOLR-138

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Issue-SOLR-2631
## Issue SOLR-2631

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Issue-SOLR-2855
## Issue SOLR-2855

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Issue-SOLR-3243
## Issue SOLR-3243

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Issue-SOLR-3606
## Issue SOLR-3606

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~Issue-SOLR-3652
## Issue SOLR-3652

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()





~Bug-44818
## Bug 44818

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~CVE-2005-3510
## CVE-2005-3510

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~CVE-2011-0534
## CVE-2011-0534

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~CVE-2011-2526
## CVE-2011-2526

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~CVE-2011-4858
## CVE-2011-4858

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()


~CVE-2012-0022
## CVE-2012-0022

**Software project**: 

**Year**: 

**Confidence**: [*](##conf)

**Summary**: 

**Characteristics**: 

[Link]()








~surv-method
## Methodology

We searched NIST’s [National Vulnerability Database](##nist) as well as the public issue trackers for the projects.

This survey is [not intended to be exhaustive](##surv-exhaustive). 

It is also worth mentioning that this survey [only includes publicly documented vulnerabilities](##surv-pub).

For each potential vulnerability we found, we record its identifier, the year it was reported, a summary, and one or more links.

We also rate our [confidence](##surv-confidence) that the issue is an exploitable high-density vulnerability. 

~surv-confidence
## Confidence

Sometimes, it is not possible to be sure that the issue is exploitable from the published problem description alone.

~surv-pub
## Only includes publicly documented vulnerabilities

We have found that applications often have trivial, undocumented vulnerabilities. For example, if an application request accepts N items, then a request containing an extreme number of items might consume significant resources. We discovered and exploited several such trivial attacks in our experiments. We also note that the accuracy of our survey is limited; it is not always possible to know from descriptions and discussions alone if a bug is truly an exploitable vulnerability.

~surv-exhaustive
## Not intended to be exhaustive

We primarily focused our search on the vulnerability history in the years leading up to, and including, 2012. We also specifically searched for work-based high-density vulnerabilities, though we also report other types of high-density vulnerabilities we came across.

~nist
## NIST

National Institute of Standards and Technology. [National Vulnerability Database](http://nvd.nist.gov/).

~hd-compare
## Compared to conventional low-density attacks

[Mass, volume, and density metaphor](##density)

Low-density attacks are [conventional floods](##low-density).

Low-density vulnerabilities are [more prevalent](##prevalent) than high-density vulnerabilities.

High-density attacks are [powerful](##hd-compare-power), [economical](##hd-compare-econ), [stealthy](##hd-compare-stealth), [specialized](##specialized), [less recyclable](##recycle), and they vary in [sophistication](##sophisticated).

<img src="img/compare.png">

~recycle
## Less recyclable

Low-density attacks are generally recyclable, in the sense that the same attack can be recycled and used again. They are recyclable since low-density vulnerabilities are inherent to the design of the Internet; defenders have a limited ability to defend themselves from high- volume, low-density attacks.

In contrast, high-density attacks are not generally recyclable since they target specific implementation level vulnerabilities. In most cases, once the defender is subjected to an attack it is straightforward to fix the implementation -- making it invulnerable to that specific attack.

~sophisticated
## Sophisticated

High-density attacks vary in the sophistication required to conduct the attack. [Unsophisticated example](##simple-hd). 

Many high-density vulnerabilities require sophisticated attacks. [Sophisticated example](##complex-hd).

~complex-hd
## Example of a sophisticated high-density attack

Consider the [HashDoS](##hashdos) vulnerabilities discovered in 2011. The attacks exploit weaknesses in hash algorithms to trigger hash collisions, which leads to N<sup>2</sup> algorithmic performance and a subsequent denial of service.

~simple-hd
## Example of an unsophisticated high-density attack

Consider a web application that uses an inefficient Ω(N<sup>2</sup>) algorithm to process web requests, where N represents the number of HTTP headers. An unsophisticated high-density attack could simply send a request with 10<sup>4</sup> headers, leading to 10<sup>8</sup> computations.


~specialized
## Specialization

Low-density attacks require [little-to-no specialization](##ld-specialize) in order to attack a particular target.

High-density attacks on the other hand require attacks tailored to application-specific vulnerabilities. For example, an attack might need to exploit an underflow to cause excessive looping, as exemplified by [Issue SOLR-3652](##solr-3652).

~solr-3652
## Issue SOLR-3652

TODO. See section 3.12

~ld-specialize
## Little-to-no specialization

All that is needed is the ability to generate a large volume of traffic towards the victim. There exist a variety of generic, off-the-shelf tools that can be used to launch effective low-density attacks. For example, the [Low Orbit Ion Cannon](##cannon) can target any web service on the Internet.

~cannon
## Low Orbit Ion Cannon
[Low Orbit Ion Cannon](https://en.wikipedia.org/wiki/Low_Orbit_Ion_Cannon), Wikipedia.

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

See [Efficient Denial of Service Attacks on Web Application Platforms](##klink).

~klink
## Efficient Denial of Service Attacks on Web Application Platforms

Alexander Klink and Julian Walde, "[Efficient Denial of Service Attacks on Web Application Platforms](https://events.ccc.de/congress/2011/Fahrplan/attachments/2007_28C3_Effective_DoS_on_web_application_platforms.pdf)," in The 28th Chaos Communication Congress, 2011.

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

For a low-density attack to be effective, the attacker must generate a large volume of requests, which can be accomplished using an army of attack computers (such as a botnet).

~density
## Density

In the density metaphor, mass measures the victim's resource consumption.

Volume measures the number of malicious resource requests.

Density measures the amount of victim resources consumed per malicious request (which, equivalently, is the ratio of mass to volume).

~hd-lately
## Note: Lately

See Akamai’s 2012 [The State of the Internet](##akamai) report, Section 1.4 "Observed Denial-of-Service (DoS) Attack Activity."

~akamai
## Akamai

Akamai’s 2012 [The State of the Internet](https://www.akamai.com/us/en/about/news/press/2012-press/akamai-first-quarter-2012-state-of-the-internet-report.jsp) report.

~abstract-simple
## Simple approach

Zen Beer Garden protects each worker with a *Doorman* and a *Bouncer*.

During overloads, the Doorman makes requesters do work, which slows the rate of malicious requests.

The Bouncer kicks out requests that overload the worker.

The [algorithm](##spec) can be summed up as: "If you're busy and someone hands you a lemon, hand it back and ask for lemonade."

[Why does this approach work?](##why-work)

~why-work
## Why does this approach work?

Imagine you're Wikipedia.

You've got many legitimate users cruising your site.

There's a small number of attackers, each with their own laptop, who bombard your site with high-density bombs as fast as they can.

Because the Doorman makes requesters do work, the attackers are slowed down. The Doorman increases the amount of work until the system recovers, then the Doorman decreases the amount of work.

Now, each attacker can only drop one bombs slowly.

Then, the Bouncer kicks out the bombs that do get admitted into the system.

Consequently, the attackers can't enter your site fast enough to cause a blackout.

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

A request is malicious if it is intended to overload the worker.

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
