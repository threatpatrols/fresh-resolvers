# Fresh Resolvers

Provides daily up-to-date lists of public DNS resolvers using source-data 
from [public-dns.info](https://public-dns.info) filtered for -
 * servers that have high (1.00) reported uptime according to public-dns.info.
 * servers that support DNSSEC.
 * servers that pass [DNS Validator](https://github.com/vortexau/dnsvalidator) for correctness.

The resolver lists are grouped by countries using their 2-letter country code
thus allowing users to choose resolvers that are proximate to their location 
(or not) for better latency outcomes.

Countries have been selected by observing locations where AWS has datacenter 
regions as an estimate for countries where internet infrastructure is probably 
good/strong.  This is not perfect but serves the purpose in this case.
```text
AE AU BH BR CA CH CN DE ES FR HK ID IE IL IN IT JP KR SE SG UK US ZA
```

Our lists are autogenerated once per day (using Threat Patrols) and are made 
available in the `resolvers` path here -
 * https://github.com/threatpatrols/fresh-resolvers/tree/main/resolvers

### BonJarber/fresh-resolvers
This `fresh-resolvers` project is not an original idea on our behalf, it was 
forked from the excellent [BonJarber/fresh-resolvers](https://github.com/BonJarber/fresh-resolvers) repo and adapted 
here, the kudos belongs to BonJarber!

### Git History
We've chosen to throw away the git history by flattening the repo at each
commit because the repo becomes very large over time as the daily updates
keep coming.  If you have feedback on this let us know we'd be interested.
