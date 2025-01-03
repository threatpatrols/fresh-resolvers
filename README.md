# Fresh Resolvers

Provides daily up-to-date lists of public DNS resolvers using source-data 
from [public-dns.info](https://public-dns.info) filtered for -
* servers that have high (1.00) reported uptime according to public-dns.info.
* servers that support DNSSEC.
* servers that pass [DNS Validator](https://github.com/vortexau/dnsvalidator) for 
  correctness.

The resolver lists are grouped by countries using their 2-letter country code thus
allowing you to choose resolvers that are proximate to your location (or not) for 
better latency outcomes.

The list of countries has been chosen by observing locations where AWS has regions,
then using this to estimate countries where internet infrastructure is probably
more-or-less good/strong; this is not perfect but serves the purpose of determining
probably-good internet infrastructure where the resolvers are probably more reliable.

```text
AE AU BH BR CA CH CN DE ES FR HK ID IE IL IN IT JP KR SE SG UK US ZA
```

Because the source list of resolvers from `public-dns.info` can be very large our
processing performs a random shuffle on the filtered country list then selects the 
top-200 ipv4 addresses before passing them through `dnsvalidator`. This is done 
because the dnsvalidator processing can take significant time to complete.  This also 
means the list of resolvers (and the order in which they appear) should change daily.

Previously we manually add the well-known `1.1.1.1`, `8.8.8.8` and `9.9.9.9` resolvers
into each country, this is no longer done (as at 2024-05-29)

Our lists are autogenerated every-second-day using a Github Action and are available in 
the `resolvers` path here -
* https://github.com/threatpatrols/fresh-resolvers/tree/main/resolvers

### BonJarber/fresh-resolvers
This `fresh-resolvers` project is not an original idea on our behalf, it was forked 
from the excellent [BonJarber/fresh-resolvers](https://github.com/BonJarber/fresh-resolvers) repo and adapted here, the kudos 
goes to BonJarber!
