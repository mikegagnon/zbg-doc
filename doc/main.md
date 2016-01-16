"If someone hands you a piece of lead, hand it back and ask for a piece of gold; the magic is inspiring the person to give you gold."

- [Abstract](##abstract)

~abstract
## Abstract
This technical report presents *Zen Beer Garden*, an approach for defending systems against work-based [high-density attacks](##hd). 

Today’s applications, frameworks, languages, and servers crumble when subjected to high- density attacks. Beer Garden defends against these attacks using a simple approach: it treats the server like a crowded beer garden and defends it using a “doorman” and a “bouncer.” The Doorman limits the attack rate by charging each request an admission fee, while the Bouncer evicts old requests to make room for new requests. Beer Garden also uses a Signature Service to develop signatures for high-density requests, which helps the Doorman charge greater admission fees for suspicious requests.

We tested Beer Garden’s ability to defend four web applications, each implemented in a different language (PHP, Python, Java, and Ruby). We subjected the applications to a suite of 10 different attacks of varying sophistication.

Our experimental results show that Beer Garden effectively defends web applications that have low memory footprints and fast restart times, such as those implemented in PHP and Python.

In addition to describing the Beer Garden defense and its experimental results, this technical report also presents a survey of high-density vulnerabilities and a comparative analysis of high- density attacks, as compared to conventional DoS attacks.

~hd
## High-density attacks

A high-density attack is when a tiny bomb causes a huge explosion.

A *work-based* high-density attack is one where the tiny bomb causes the victim to perform an explosive amount of work. [Example](##hd-ex).

[A note on terminology](##hd-terms).

High density attacks are particularly dangerous because they are particularly powerful, and economical, and stealthy.

With high-density attacks, you don’t need an entire army to attack your enemies. You just need tiny bombs.

High-density attacks allow [small forces to defeat larger forces](##hd-asym).

Lately, attackers have been increasingly utilizing high-density attacks since the defenses against conventional DoS attacks are becoming increasingly effective.

~hd-ex
## Example work-based high-density attack
Bob transmits a single HTTP request to Wikipedia, which causes Wikipedia to spin so much CPU there's a blackout for everyone.

~hd-terms
## A note on terminology
For the sake of brevity, throughout the rest of this document the term *high-density attack* refers to *work-based high-density attack*, since Zen Beer Garden only defends against work-based high-density attacks.

~hd-asym
## Small forces defeat larger forces

For example, the Rebels used high-density attacks to destroy the Death Star twice.

<img src="img/deathstar.jpg">
