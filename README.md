# traplogger
a utility for logging activity on your Linksys router

Dug from the bottom of the trunk to see if I could remember anything about
Perl. I created this in 2001.

I was pleased with this script's initial popularity - it was a treat to see
a Unix blogger whose work I admired recommend it - but I had no particular
interest in updating it to include more interesting features like automatic
dynamic DNS update, status emails, and so on. After contacting me with a few
questions Mike Wohlgemuth created linksysmon and included those and some other
features.

There are some things I really don't like about this script when reading it
after all this time. Invoking snmptrapd the way we're doing is very goofy,
there is no conception of reducing the daemon's privileges once it has been
started, and I remember deciding that Net-SNMP did not look particularly
secure when I studied it at the time. It might have improved enormously but
there are a lot of other options out there today. 

A reasonable way to reimplement this in 2015 would probably involve writing
a real daemon the old fashioned way with Go or C, or perhaps by including a
simple regex in one of the newer snmpd imlementations. This script of mine
never made it past version 1.0 but it is very short and easy to tweak. I have
not tested it with a modern version of Net-SNMP and I do not know how Linksys
hardware's use of SNMP has evolved over time. I will leave this as-is for now
and, as Mike's site is no longer up, create a repo for linksysmon. traplogger
and linksysmon, between the two of them, might provide a useful reference for
anyone who needs to use SNMP with a Linksys home router.
