http://linkurio.us/

Data sources:
Crunchbase (there's an open data set for 2013 data, have to file request for full data set)
ITJuzi?
Tech in Asia's own database

What am I interested in?
- investments received and given by companies and individuals
- information about a company's investment interests (ex: how much money did Shunfeng Capital invest in startups in 2016? how many were repeat investments? how many were to IoT companies?)
- information about the scene in general (ex: who are the top investors in the whole scene? what kind of investment entities are dominating the tech scene? (ex: BAT? late-stage investment funds?) What kind of companies or individuals have received the most funding?
- connections
     - ex: X startup just raised $100 million from such and such investors. Do they share other connections (coworkers, classmates, friends?)?

Node attributes:
Required by Linkurious:
- id
- x, y coordinates (would have to calculate that)

Optional:
- size (I'd have to calculate that)
- color (maybe to differentiate companies vs. individuals vs. investments firms?)
- label (the actual name of the investor/investee)

Edge attributes (directed graph):
Required by Linkurious:
- id
- source (investee)
- target (investor)

Optional:
-size/thickness (I'd have to calculate that)
- color (the kind of relationship: investee, friends, coworkers, classmates?)
- label (the exact amount and year?) //though that might not make sense as a label (can't do any sensible operations on a string)
- hidden, visible (sometimes investors will sell off their stake - this should still be recorded but not be visible in the graph)

Make a mini example first with Jack Ma, Masayoshi Son, SoftBank, Alibaba

Nodes:
Jack Ma
Masayoshi Son
SoftBank
Alibaba

Edges:
(Jack Ma, Masayoshi Son) = friend edge
(Soft Bank, Alibaba) = investor - investee edge
(Jack Ma, Alibaba) = employee/professional association edge
(Masayoshi Son, SoftBank) = employee/professional association edge

In this case, would need to calculate routes from SoftBank to Alibaba in the whole graph. That would be: (SoftBank, Alibaba), (SoftBank, Masayoshi Son, Jack Ma, Alibaba), (Alibaba, Jack Ma, Masayoshi Son, SoftBank). The last two are the same actually - nodes are just in different order (would need to check for that to reduce redundancy in results). 


