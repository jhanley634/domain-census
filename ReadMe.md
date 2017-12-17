
# Domain Census

How many nameservers are there?

More specifically, how many authoritative nameservers respond to (most) internet clients?

One can only identify server S as a nameserver w.r.t. some domain D that S answers for.
So our task is to spider the interweb for (D, S) pairs that prove responsive.
We begin with a set of seed domains, e.g. {"google.com"}, and progressively grow the set.

For each domain in the set, we consider domain plus ancestors, e.g. "google.com", "com", ".",
and issue 4 queries. They are for A, AAAA, MX, and NS. 

Each NS-set and MX-set answer implies names to add to our active set.
Additionally, A and AAAA address rev-maps imply additonal domain names.
