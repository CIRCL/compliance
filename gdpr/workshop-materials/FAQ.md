# Frequently asked questions (FAQ)

## Disclaimer

This document is a “frequently asked questions” or FAQ including questions and discussions gathered during workshops and trainings organized by The Computer Incident Response Center Luxembourg ([CIRCL](https://www.circl.lu/)), specifically related to the General Data Protection Regulation (GDPR). The questions and answers given during the workshops are enriched with further insights and references.

It is important to note that CIRCL doesn't provide legal advice. CIRCL is sharing their practical experience (as a CSIRT and ISAC) about GDPR and privacy compliance at large. The present document contains general information about legal matters, specifically related to the General Data Protection Regulation (GDPR). The information is not advice, and should not be treated as such. Legal information in this document is provided “as is” without any representations or warranties.

## Q1. Can public OpenPGP key servers be considered transfers of personal data to third countries?

Another related question would be whether publicly available personal data on a website, such as contact emails can be considered as transfer of personal data to third countries.
The GDPR does not provide any definition of a “transfer of personal data”, especially in case of transfers of personal data to third countries or international organisations.

To find the answer to this question, official opinions or previous case law need to be investigated. Specifically, the Bodil Lindqvist landmark case (Case C101-01, 6 November 2003) provides interpretation related to transfers of personal data to third countries within the scope of data uploaded on a webpage. To be noted that the Bodil Lindqvist case is a decision by the Court of Justice of the European Communities (European Court of Justice) ruled on the scope of Directive 95/46/EC (Data Protection Directive). Therefore, the case may be interpreted differently once the GDPR comes into force.

The [judgement](http://curia.europa.eu/juris/document/document.jsf?docid=48382&doclang=en) states that:

> “The reply to the fifth question must therefore be that there is no transfer [of data] to a third country within the meaning of Article 25 of Directive 95/46 where an individual in a Member State loads personal data onto an internet page which is stored with his hosting provider which is established in that State or in another Member State, thereby making those data accessible to anyone who connects to the internet, including people in a third country.”

This statement supports the assumption that public information loaded on a web page should not be considered as transfers of personal data to third countries. However, personal data available on a public website are in the scope of GDPR principles, especially the purpose limitation.

OpenPGP key servers should therefore not be considered as transfer of personal data to a third country or an international organisation.

## Q2. Can “vital interest” be used as a legal ground by CSIRTs?

Vital interest in one of the legal grounds listed in 6(1) (d) of the GDPR: “processing is necessary in order to protect the vital interests of the data subject or of another natural person”

Recital 46 provides more insight on vital interest:

> “The processing of personal data should also be regarded as lawful where it is necessary to protect an interest which is essential for the life of the data subject or that of another natural person. Processing of personal data based on the vital interest of another natural person should in principle take place only where the processing cannot be manifestly based on another legal basis”

Based on those two paragraphs, vital interest can be understood as a legal ground directly related to the imminent life or death of a data subject. CSIRT are unlikely to process personal data to save the life of a data subject and therefore they are unlikely to use vital interest as a legal ground. Instead, CSIRTs are more likely to process personal data for the performance of a task carried out in the public interest. For more information, please refer to the [workshop GDPR introduction slides](https://github.com/CIRCL/compliance/blob/master/gdpr/workshop-materials/02_CIRCL_2016-LU-IA-0098_slide_workshop_2018.05_v0.98.pdf) or the [Information sharing and cooperation enabled by GDPR article](https://github.com/MISP/misp-compliance/blob/master/GDPR/information_sharing_and_cooperation_gdpr.md).

## Q3. How far should CSIRTs investigate during a personal data breach to determine to what extent personal data were stolen and who are the data subjects affected?

When a personal data breach occurs, it is the responsibility of the data controller to notify the breach to the responsible data protection authority (DPA). Therefore, it is often not the responsibility of an external CSIRTs helping to resolve the incident to report the personal data breach and to determine how far the analysis needs to go to determine exactly to what extent personal data were stolen and who are the data subjects affected.

However, CSIRTs can also be data controllers, for example an internal CSIRT of a private organisation subject to a personal data breach. In that case, it is the responsibility of the organisation to which the CSIRT is part of to define and document criteria regarding incident notification to the DPA and depth of investigation to determine the extent of personal data stolen and the affected data subjects. For example, it may not be relevant to investigate each single anti-virus alert.

To be noted that in some sectors such as the banking sector, laws and regulations, for example PSD2 (Payment Services Directive (EU) 2015/2366), define clear thresholds for incident notification. Additionally, personal data breach notification can be amended by other laws or regulations. PSD2 provides the stakeholders with 24h period, instead of the 72h provided by the GDPR, to report a personal data breach. Threshold for reporting will also be clarified by the Directive on security of network and information systems (NISD).

As an additional highlight, to report data breach in Luxembourg, CIRCL chooses the approach of a public record named [TR-46](https://www.circl.lu/pub/tr-46/). This approach is also used by the State of California, releasing personal data breach notification as a public record. 


## Q4. How should the territorial scope need be interpreted, specifically, regarding Recital 2 of the GDPR? Are non-EU data subjects, for example, under the scope of the GDPR?

Recital 2 of the GDPR states that:

> “principles of, and rules on the protection of natural persons with regard to the processing of their personal data should, whatever their nationality or residence, respect their fundamental rights and freedoms, in particular their right to the protection of personal data.”

This recital can be understood as applying the GDPR to non-EU data subjects. Article 3 gives more details regarding the territorial scope:

> Article 3(1): “This Regulation applies to the processing of personal data in the context of the activities of an establishment of a controller or a processor in the Union, regardless of whether the processing takes place in the Union or not.”

> Article 3(2): “This Regulation applies to the processing of personal data of data subjects who are in the Union”

According to Article 3, the GDPR applies when the processing of personal data is located in the EU. Therefore, it can be understood that even personal data of data subjects not physically located in the EU are in the scope of the GDPR if the processing occurs in the EU. Such interpretation also seems to be in accordance with the EU Commission and [EU parliament](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A52014AP0212)’s statement that companies should respect the principles within the GDPR “whatever the nationality or residence” of a data subject.

## Q5. What are the reasonable expectations of the data subjects regarding honeypots, especially regarding transparency?

In this answer, honeypots need to be considered as software applications usually passively listening on an open port, used by CSIRTs or private organisations to detect attacks in a network or perform research on threat actor Techniques Tactics Procedures (TTPs). Examples of such honeypots are spamtrap, distributed denial of services detection devices, SSH honeypopts etc...

The types of honeypots which are not in scope of this question are honeypots involving social engineering or used in the process of catching and prosecuting criminals, for example by Law enforcement (e.g. setting up websites targeted at online child predators).

In other words, the scope of this answer includes only honeypots related to enticement mechanisms, not entrapment.

Honeypots can have different levels of interaction; from a low level (only capturing packets without responding, e.g. distributed denial of services detection devices) to honeypot having a high level of interaction, (e.g. honeypot provided the threat actor with an interactive shell).

When operating honeypots, [two general categories of data are collected](https://jis-eurasipjournals.springeropen.com/track/pdf/10.1186/s13635-017-0057-4):

* The contents of communications (e.g. payload, command executed in a shell etc.)
* Information to establish communication (also called metadata or traffic data e.g. IP addresses of the source)

Moreover, honeypots are more likely to be operated under one of the two following legal grounds:

* Article 6(1) (a) – ‘processing is necessary for the performance of a task carried out in the public interest’. For example, if the honeypot is operated by national, governmental or sectorial CSIRTs to increase the level of security of their constituency. 
* Article 6(1) (f) – ‘processing is necessary for the purposes of the legitimate interests pursued by the controller’. For example, if a private organisation operates a honeypot on its network to detect potential attack.

Honeypots are not actively collecting data but usually passively listen on an open port, which should not be contacted in normal circumstances. Two types of traffic usually go to a honeypot:

* Traffic from threat agents trying to compromise the system
* Traffic from misconfigured equipment. This kind of traffic can include personal data, but is unlikely to have a significant impact on the data subject if those personal data were to be disclosed.

Identifying the data subject owning the personal data collected in a honeypot can represent a certain burden for the entity operating an honeypot. For low-level honeypot, usually one can only rely on an IP addresses, and even if it is possible to find a data subject behind an IP address, e.g. ask Internet Service Providers (ISPs), it requires a significant amount of time and effort (e.g. from hours to days). Indeed, there is no public records of IP addresses owner like [whois database](https://www.whois.com/) for domain names. Moreover, although it is possible to find domains linked to IP addresses, and therefore may be possible to find usable whois information for IP addresses, far from all IP addresses are linked to a domain name. Considering the fact that with honeypots, potentially millions of IP addresses can be gathered in a short time period, it requires a disproportionate effort to identify data subject from personal data collected with commonly used honeypots.

Additionally, ensuring transparency and rights of the data subject for personal data collected with honeypots would seriously impair the achievement of the objectives, especially when the honeypot is used to detect attacks from threat actors.
 
Therefore, implementing transparency and data subject rights would in most cases (1) require a disproportionate effort and (2) render impossible or seriously impair the achievement of the objectives of that processing.

Having this in mind, the data controller needs to find restrictions or derogations to the GDPR to justify the fact that transparency and the data subject rights cannot be implemented. The data controller may rely for that, depending on its legal grounds and purpose, on several articles:

* Article 14 (5) (b) – can be used if the personal data from the honeypot can be considered as not being obtained from the data subject.
* Article 23 (1) (e) – When the controller is processing personal data in the public interest, it may use this article to restrict the scope of the obligations and rights to the data subject.
* Article 23 (1) (i) ‘[..] the protection of the data subject or the rights and freedoms of others; [..]’ – This paragraph may also be used by the data controller in some cases.

To be noted that the limitations laid down in Article 23 (1)(e) and (1)(i) can apply if Union or Member State laws can restrict the scope of the exercise of data protection rights. This limitation, in the case of CSIRTs  processing activities strictly limited to the activities provided/prescribed by their mandate is subject to the principle of proportionality, limitation and may comply in specific situations with the criteria provided in Art. 52 of the EU Charter (e.g. necessary and genuinely meet objectives of general interest recognised by the Union).

## Q5. Is there any case law existing concerning Honeypot?

No case law involving honeypot has been found yet.

## Q6. Should CSIRTs keep an OpenPGP key server?

OpenPGP key server and protocol have not been developed with privacy-by-design in mind. Indeed, applying the data subject rights to an OpenPGP key server would usually involve disproportionate effort. For example, due to the distributed and resilient nature of the PGP network and to the security concern of PGP key deletion, it would involve a disproportionate technical effort to delete or modify PGP keys on the server.

However, CIRCL or any organisation operating an OpenPGP key server cannot change the way the protocol was designed, and it is therefore not their responsibility to implement privacy-by-design for the OpenPGP key server. If the organisation has a legal ground and a legitimate purpose to operate an OpenPGP key server, they should be allowed to continue operating this server, especially given the fact that OpenPGP key server is a privacy enabler tool, as it promotes and enables confidentiality, integrity, authentication and non-repudiation.

To be noted that additional preventive controls can be put in place to mitigate the risk of a data subject wanted to delete his/her PGP key from the server, for example by displaying and transparency notice next to the [OpenPGP upload form](https://pgp.circl.lu/). 

## Q7. Is there any model or new architecture to implement privacy-by-design OpenPGP key server?

There are several emerging models for a privacy-by-design enabled OpenPGP key server and protocol.

However, these emerging solutions tackle many challenges such as:

* It is difficult to prove the identity of the OpenPGP key owner if the register of the keys is not public
* Emerging solution, even if there are proven effective, will most likely take a long time to be broadly used and implemented

To tackle privacy-by-design for OpenPGP ley servers, CIRCL suggests a new approach involving a “privacy list” of OpenPGP keys. This approach will not only be useful for data protection issues but as well for OpenPGP key abuses. For more information, please refer to [CIRCL GitHub](https://github.com/CIRCL/openpgp-keys-filterlists).   


## Q8. How can the new GDPR related taxonomies be used by organisations operating a MISP instance?

Two data protection related taxonomies (["gdpr"](https://github.com/MISP/misp-taxonomies/tree/master/gdpr) and ["fpf"](https://github.com/MISP/misp-taxonomies/tree/master/fpf)) were recently added by CIRCL in the MISP GitHub repository. Those taxonomies are a first step into categorizing attributes as personal data in MISP.

Organisations are encouraged to define a set of standard taxonomies to be systematically used to classify MISP events and/or attributes. For example, CSIRTs are encouraged to use the TLP taxonomy for every events. Those GDPR related taxonomies could be used by organisation to classified their personal data in MISP, and the degree of identifiability of those personal data. Additionally, organisation can choose not to send or receive events or attributes tagged with specific taxonomies. For more information on the MISP filtering capabilities, please refer to the MISP documentation.

One use case is for organisations whose processing activities’ purposes do not allow them to share special categories of data to prevent sharing those data to another MISP instance. It also allows organisation whose processing activities’ purposes do not allow them to receive and process special categories of data, to filter out all those taxonomies when receiving data from other MISP instances.

