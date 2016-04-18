# Landgate API Test

## Abstract

## Acknowledgements

## Table of Contents

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Landgate API Test](#landgate-api-test)
	- [Abstract](#abstract)
	- [Acknowledgements](#acknowledgements)
	- [Table of Contents](#table-of-contents)
	- [List of Figures](#list-of-figures)
	- [List of Tables](#list-of-tables)
	- [Introduction](#introduction)
		- [Landgate](#landgate)
		- [Web Services](#web-services)
			- [Open Geospatial Consortium Web Map Service](#open-geospatial-consortium-web-map-service)
			- [Open Geospatial Consortium Web Feature Service](#open-geospatial-consortium-web-feature-service)
			- [Google Maps Engine](#google-maps-engine)
			- [Esri ArcGIS for Server and ArcGIS ReST API](#esri-arcgis-for-server-and-arcgis-rest-api)
	- [Literature Review](#literature-review)
		- [Similar Work](#similar-work)
		- [Web Service Quality and Discovery](#web-service-quality-and-discovery)
		- [Web Service Evaluation](#web-service-evaluation)
		- [Acceptance](#acceptance)
	- [Materials and Methods](#materials-and-methods)
		- [Generalised Workflow](#generalised-workflow)
		- [Data Model and Structures](#data-model-and-structures)
			- [TestMaster](#testmaster)
				- [TestEndpoint](#testendpoint)
				- [LocationTest](#locationtest)
				- [NetworkTest](#networktest)
				- [PingTest](#pingtest)
			- [ReferenceObject](#referenceobject)
			- [Vector](#vector)
		- [iOS Mobile Application](#ios-mobile-application)
			- [Mobile Application Design Principles](#mobile-application-design-principles)
			- [iOS Application Architecture](#ios-application-architecture)
			- [Swift Open Source Packages](#swift-open-source-packages)
				- [Realm Mobile Database](#realm-mobile-database)
				- [Transporter State Machine](#transporter-state-machine)
				- [Reachability](#reachability)
				- [KDCircularProgress](#kdcircularprogress)
			- [Hardware](#hardware)
		- [Google Apps Engine Web Service](#google-apps-engine-web-service)
			- [Web Service Design Principles](#web-service-design-principles)
			- [Python Application Architecture](#python-application-architecture)
			- [Python Open Source Packages](#python-open-source-packages)
				- [Matplotlib](#matplotlib)
		- [Other Applications Deployed](#other-applications-deployed)
	- [Results](#results)
	- [Discussion](#discussion)
	- [Recommendations](#recommendations)
	- [Future Work](#future-work)
	- [Conclusions](#conclusions)
	- [References](#references)
	- [Appendix A](#appendix-a)
		- [Web Service Requests](#web-service-requests)
	- [Appendix B](#appendix-b)

<!-- /TOC -->

## List of Figures

## List of Tables

## Introduction

>Anoverviewofthereport.
Acleardescriptionofyouraimsand objectives,andthecontextoftheproblem or situation.
Thescopeofyourinvestigationaswell asanylimitations.
Ifneeded,abriefhistoricalbackground (withsubheadings)ofsignificantevents leading up to the present investigation.
Iftheexplanationofthecontext istoolong,makeita separatesectionandcall it Background/Context/Definitions/Key Terms.
Ifyouneedtoprovideananalysisof existingresearch,makeaseparatesection titled Literature Review.
Usethepresenttensetooutlinethe problemandyouraims.
Usepasttensetodescribeevents thathaveoccurredwhengivingbackground information or context.>

### Landgate

Landgate is the trading name of the Western Australian Land Information Authority, the statutory authority given charge of maintaining the state's land and property information system {Anonymous:2004tv}. The organisation is the inheritor of the mandate of various incarnations of the Department of Lands and Surveys, dating back to the original Survey Office in the 19th Century.

Landgate's role incorporates managing property ownership and transfer records, as well as property valuations to government agencies {Anonymous:x1iQOCOB}. Vital to society in the connected age, Landgate is Western Australia's leading spatial data agency. Landgate has successfully commercialised spatial data creation and access. Their cumulative efforts considerably lessened their dependence on funding from the state government. The success of this strategy has lead to a projected 5% increase in the number of datasets served through the 2015/16 financial year {Anonymous:2015va}.

[ ] Diagram organisation of Landgate, WALIS etc.

The Western Australian Land Information System (WALIS) is a partnership between government agencies, the private sector and the community. Their aim is to improve access to location information for the betterment of the Western Australian community {LocationInformationStrategyProgramCoordinationTeam:2012te}. The Shared Location Information Platform (SLIP) is WALIS's spatial data portal, the Western Australian government's Spatial Data Infrastructure (SDI), managed by Landgate. The portal presents datasets owned and maintained by authoritative agencies, standardises data formats and simplifies access.
SLIP Future is WALIS's programme to revamp the original SLIP Enabler portal and infrastructure {Anonymous:2014ww}. The custom built and open-source based infrastructure was deemed incapable of handling projected usage and implementing new features. WALIS built a new platform around Google's Software as a Service (SaaS) Google Maps Engine (GME). The new environment offered significant advantages in reliability, scalability and feature set {Anonymous:2014ww}.

In January 2015, Google announced the deprecation of Google Maps Engine {SLIPFuture:2015uc}. Further, they planned to shutter the service entirely by the end of January 2016 {Anonymous:2015tg}. Landgate and WALIS were left in search of a new provider for the SLIP Future programme. ESRI aggressively sought the business of GME refugee organisations {Anonymous:7YAzB1Ym} offering free software replacements and membership to business partnership programs. In July 2015, Landgate selected Esri's ArcGIS Server and Portal as the replacement for GME {Anonymous:2015uc}. Web services offering datasets in Esri's ArcGIS REST APIs will replace GME's API through a transition period through the end of 2015 and beginning of 2016.

### Web Services

[ ] introduce more

The development of powerful and flexible web services was the foundation that allowed the mobile web to blossom. Web services enable interaction between computer systems over a network. One system may call on another to provide data or a service without requiring a human user to mediate the interaction {Anonymous:bRhwymPh}. Mobile devices have limited processing power and storage available, so off-device storage and processing empowers on-device applications.

Service Oriented Architectures (SOA) is a standard governing software design that aims to compose a software product from loosely coupled, and hence replaceable, components {Endo:2010wf}. Designers commonly employ this pattern as a method for distributed computing {Palacios:2011eo}. A set of descriptive XML documents, such as Web Services Description Language (WSDL), enable service builders to publish to service registries and then consumers to find and bind to services suited to their needs. Communication is carried out with XML-based messages based on the Simple Object Access Protocol (SOAP), another highly capable standard.

Representational State Transfer (ReST) services are much easier to develop and consume {Castillo:2011ve}. The adoption of ReSTful services has led to an explosion of data available on the web, particularly with mobile applications in mind as the end consumers.

### Spatial Web Services

[ ] Introduce spatial web services
> Deliver Spatial data over
> What is spatial data
> Who are the Geospatial Consortium

#### Open Geospatial Consortium Web Map Service

A Web Map Service (WMS) composes an image file from server stored vector and raster layers in response to a request in a URL. Despite their focus on returning an image file, WMS operations are still dependent upon XML, especially for GetCapabilities, GetFeatureInfo, error descriptions and layer style code.

The open source and standards driven approach meant that WMS was widely adopted and became a cornerstone web mapping technology. The standard is now quite old; it was last updated to version 1.3.0 in 2006 {delaBeaujardiere:2006vq}.

#### Open Geospatial Consortium Web Feature Service

A Web Feature Service (WFS) returns geographic vector data in GML (Geographic Markup Language, a derivative of XML) in response to a URL request. It is a more complex and capable service than WMS. If fully deployed, WFS allows external users full create, read, update and delete (CRUD) access to a geographic database {Vretanos:2005ut}.

The WFS standard is of a similar age to WMS. Version 1.1.0 is most commonly deployed, dating from 2005 {Vretanos:2005ut}. Version 2.0 from 2010 gained capability and complexity from GML3 and somewhat simpler use from stored queries but was not widely adopted in the years after its release.

#### Google Maps Engine

Google Inc.'s Google Maps Engine (GME) service enabled the creation of more sophisticated web mapping services on top of the Google Maps interface. Whereas the familiar Google Maps application only allowed one or two additional map layers to be displayed, Google Maps Engine could host many hundreds of datasets in the cloud and perform multi-layer geographic analysis {Anonymous:s3eShq99}. The full version was a true enterprise application and cloud service, with off-the-shelf or bespoke solutions created to suit a client's needs. The scalability and reliability of Google's service were a significant attractor to geospatial providers, such as Landgate.

From the 22nd of November 2014, Google redirected GME website bound traffic to their Google Maps for Work service {Anonymous:A\_DLJUOY}, a more streamlined approach to providing enterprise mapping solutions than the previous five separate products.

In a commercial decision, Google Inc. announced the deprecation of the GME API on the 29th of January 2015 {Anonymous:2015tg}. Google shuttered the service on the 29th of January 2016.

#### Esri ArcGIS for Server and ArcGIS ReST API

ArcGIS for Server is Esri's enterprise level product for intra/internet GIS and provisioning web services {Anonymous:BHtz-GD9}. ArcGIS for Server has a long development history and has been an established (or entrenched rather) product in geospatial enterprises for many years.

The ArcGIS REST API exposes ArcGIS for Server data and functions as web services. This modern API has been fully developed since 2010 {Anonymous:hoTu0aor}. ArcGIS for Server's age means it is also fully capable of supporting older web service standards such as SOAP.

## Literature Review

### Similar Work

Web services are widely studied. However, the scope of applications for web services is broad. There are, therefore, few studies that examine the intersection of geographic web service performance, mobile device context and an individual, state-level spatial data infrastructure. Following are a cross-section of papers with aims partially aligned to those of this work.

Hamas, Saad and Abed {\*Hamad:2010tr} compare the performance of SOAP and ReST APIs on mobile devices. The measured criteria are response time and transmission size which predictably favour ReST interfaces.
Their experiment design emulates a mobile device on a desktop computer; further they restrict the simulated mobile network speed. These are useful controls in an experiment designed with a very clear aim of finding which service is faster. But real world complications such as heavy network traffic or poor signal are not addressed as a factor in the outcome. As an example, SOAP's WS-ReliableMessaging protocol may reduce overall transfer time in areas with weak signal by minimising the number of failed message attempts.

Tian et al. {\*Tian:2004cb} design a server-client system that can optionally compress responses to save the client's download limit or skip compression when the server is under heavy load to minimise timed out requests.

Working in the pre-smartphone era the team simulated an iPAQ Pocket PC, emulating the device on a Pentium III laptop. The laptop emulating the client is connected to the server via WiFi, Bluetooth or a simulated mobile network. To simulate the increased latency and slower connection speed of a GPRS network, they introduce another server that throttles network speed by artificially delaying messages.

Davis, Kimo and Duarte-Figueiredo {\*Davis:2009hf} focus on OGC Web Map Service (WMS) optimisation for mobile devices. They elaborate a service that combines the multi-layer composition of WMS with the mobile device response speed of AJAX-based web maps such as Google Maps.

Their experiment implemented the proposed service and interacted with it from a custom application deployed on a Nokia N95. Given the focus on minimising data sent and received from the device, the results vindicated their hypothesis. Unfortunately, the team declined to study response time results due to "severe fluctuations" that they attributed to an overcrowded network. They conclude, by extension not experiment, that smaller volumes of transmitted data would result in faster map interaction overall.

Fowler and Peterson {\*Fowler:2012bn} built a custom iPhone application to test the performance of SOAP and ReST versions of a public transportation web service in Hamburg over a typical working day. They measured response time, data serialisation/deserialisation time and response size on the device itself and returned the results to their own web service. Simple and detailed messages of significantly different response size control whether response time is dependent upon message size. The results, as is common, are given as mean and standard deviation, descriptive statistics without discussion of error responses.

Fowler and Peterson's methodology called for the mobile user to remain "fixed" while requesting and receiving the response, which we interpret as stationary. This is contrary behaviour for mobile device use. There are countless situations in which a mobile user would be active and moving while concurrently requesting data from a web service.

Provisioning web services from a mobile device faces similar network and device limitations as consuming a service from a mobile device. Nguyen, Jørstad and van Thanh {\*Nguyen:2008jt} explored web service performance on an emulated mobile device. While investigating the influence of varied simulated mobile network speeds, they concluded that testing on an actual device would provide ideal settings for their network simulation. Indeed, the subsequent experiment showed considerable differences between emulated and real network speed influence on web service performance. Even after modifying their simulated network speed to approximate real world network speed the difference is significant.

Hussain, Wang and Toure {\*Hussain:2014ce} test the response time and throughput of a variety of real world web services over DSL, WiFi and LAN internet connections. Results are simplified to descriptive statistics, average, minimum and maximum response time.

Hussain, Wang and Toure discuss some tests with unusually long response times and speculate that it may be due to other web traffic. The specific time or other conditions of these particular tests are not elucidated. In fact, the methodology is not sufficiently detailed to provide all the parameters used in web service requests. Repeating their experiments will likely produce different results.

Yang, Cao and Evans {\*Yang:2013ff} demonstrate that WMS servers struggle with heavy loads of simultaneous requests. They recorded response times to 1, 5, 10. 30, 50 and 100 concurrent requests to six important WMS servers. They found that response times increased with the number of requests until many servers either blocked all incoming requests to handle the load or simply timed out. They make several recommendations, particularly regarding parallel requests and processing. Most helpfully to this study, a simple progress bar to indicate to a user that their request is still being processed.

The emergence of ReSTful web services engendered many studies comparing performance to entrenched SOAP services. Few experimental designs take advantage of SOAP's inherent advantages, i.e. a message layer and orchestrated distributed computing, such a design would allow SOAP APIs to be compared more favourably with ReST APIs.

Castillo et al. {\*Castillo:2011ve} compare ReST and SOAP service implementations as the intermediary messaging layer for a genetic algorithm and a fitness evaluator. They also present one of the few papers to elaborate the advantages of the older SOAP API standard against a ReST API, but their experiment doesn't build on this. Their proof of concept methodology introduces a useful control, requests via SOAP and ReST send strings of either 100 or 1,000 characters. The proportional time difference between large and small requests controls whether the response time depends upon the amount of data sent and received, illuminating how much response time overhead is due to the API employed.

Like other researchers, Castillo et al. relate the results of their performance tests as average response time with a margin of error. They discuss accuracy, but this is in terms of their genetic algorithm's accuracy, not the error rate of the web service API.

Kanagasundaram et al. {\*Kanagasundaram:2012wv} expose a student database as a resource and perform Create, Read, Update Delete operations over SOAP and ReST web services. The comparison of response time between different operations leads the team to propose a hybrid SOAP and ReST web service that incorporates the security and reliability aspects of SOAP with ReST APIs' ease of development.

The experiment design places the client and server processes on separate cores of a single processor. This works well as an experimental control but comes at the expense of measuring real world performance. Furthermore, the results obtained by Kanagasundaram et al. {\*Kanagasundaram:2012wv} are averaged response times from experiments repeated until they achieved a 95% confidence level. But not all are presented in the paper, only a select subset. Presumably messages resulting in errors were excluded from the averaged results.

Expedients such as simulated mobile networks or emulated mobile devices can be more easily understood when considered in the context of testing a production server. Stress testing and automated test case generation, for example, both benefit from a quantity of tests unachievable with a few handheld devices. Services such as Load Impact {Anonymous:0z5u-mT-} emulate thousands of mobile users on a variety of devices with a range of network connectivity.

Mobile application testing is a rapidly growing field. Gao et al. {\*Gao:2014fp} identified four classes of mobile application testing approaches. Emulation-based testing, as seen above, where a device simulator runs on a desktop computer, is commonplace as emulators ship with most app development environments. Device-based testing runs the application and its services on a range of real devices to find edge case failures. Cloud testing suits large-scale tests scaleable to requirements. Crowd-based testing employs volunteers or contractors to test apps and can reach reasonable scales, they note that tests may not be completely thorough.

Yan et al. {\*Yan:2012uf} built a cloud testing suite, an approach they called Web Service - Testing-as-a-Service (WS-TaaS). Their experiment showed that cloud tested web services were capable of responding to significantly more requests than one tested on a single desktop computer. Most likely due to the limited bandwidth and processing power of the single testing node.

### Web Service Quality and Discovery

[ ] Citation to support topic sentence

Automating web service discovery is a much more active field of research with the aim of supporting semantic web development. An application should be able to bind the web service without supervision from the end user. How then, though, should the application choose which web service to employ from the multitude available, also without requiring user intervention. The investigators below are proponents of systematically and automatically applied quality metrics as a basis for deciding which web services should be bound.

Palacios, Garcia-Banjul and Tuya {\*Palacios:2011eo} surveyed Service Oriented Architecture literature to find articles focussed on dynamic binding. 57% of the 33 articles detected faults in web services and thereby excluded non-responsive services.

Orion, Marco and French {\*Oriol:2014kq} reviewed the state of the art in quality of service models for web services, surveying 65 papers written between 2001 and 2012. They showed that most researchers were assessing web services quality in terms of availability (essentially the probability a request will receive a response) with 94% of surveyed papers defining the metric. Response time was second place at 83% coverage and accuracy third with 62%.

Wu et al. {\*Wu:2011kk} propose web service registries evaluate the quality of services they expose. Service downtime, mismatches between catalogued metadata and current capability or inconsistencies when registered in multiple catalogues can lead to the selection of a suboptimal web mapping service. The catalogue service periodically interrogates an OGC WMS testing all operations listed in its GetCapabilities document. Successful tests decrease the frequency of future tests while a lack of response increases the frequency.

Wu et al. model quality factors using a hierarchical tree, proposed by Hanwu Zhang, one of the authors in their Ph.D. dissertation from 2008 (reference not found in English translation). This is a helpful concept for automated quality analysis as branches in the hierarchy can be weighted differently, emphasising categories of metrics (the "leaves") over others. Unfortunately, Wu et al.'s automated analysis stops after comparing the most recent response time to a weighted average of previously recorded response times. They go on to assess map data quality through a survey method. A GUI program presents returned data to an expert user for assessment and scoring out of five on a series of quality metrics.

Miao, Shi and Cao {\*Miao:2011dh} build upon Wu et al.'s method of adaptable testing frequency by halving test intervals when the response time is greater than the average of earlier tests. They go further to parameterise the proportion of failed requests. Their process is explained well in a flow chart, omitted from many similar papers.

Miao, Shi and Cao developed a C based program to crawl 100 WMS servers to measure their performance and stability as per their procedure. The conference paper referenced here omitted a table listing the servers assessed. As with Wu et al., the team leaves data quality assessment to a survey of expert users.

### Web Service Evaluation

The OASIS Web Services Quality Factors {Kim:2012wm} defines six quality factors with 28 sub-categories.
	1.	Business Value Quality - the value arising from using a web service as compared to the cost.
	2.	Service Level Measurement Quality - the service responsiveness from a client's point of view, including time and success criteria.
	3.	Interoperability Quality - the degree to which a service conforms to appropriate standards.
	4.	Business Processing Quality - the service's reliability for business use considering transmission integrity and integration with other processes.
	5.	Manageability Quality - management processes to ensure web service quality.
	6.	Security Quality - the service's ability to prevent intrusion, interception or destruction of the service itself or its messages.
Taken all together these represent all factors that affect a client's decision to consume a web service.
The scope of this study is limited to those aspects of Landgate's service that affect their suitability for use on mobile devices. The business process and value, management, interoperability and security factors cannot be tested with a mobile device. These are more suited to desktop studies and surveys of existing clients. Only Service Level Measurement Quality is within the purview of this study.
The sub-categories include;
	1.	Response Time - the time interval between the transmission of a request and the receipt of a response. The total time is composed of the time taken for the client to compose the request and decompose the response plus the network transmission time to and from the server plus the time taken for the server to process the request and formulate a response.
	2.	Maximum Throughput - the maximum number of requests a service can reliably respond to in a unit of time.
	3.	Availability - the proportion of time the server is operational, the complement of service downtime per measured time.
	4.	Accessibility - the probability of the web service can be reached when the system is operational, quantified as the number of received acknowledgement messages divided by the total number of requests.
	5.	Successability - the probability of receiving a successful response to a web service request, the number of responses divided by the number of requests.
We propose to track these factors through a series of frequent but irregularly timed tests from a mobile device deployed in situations common to the mobile network milieu.

### Acceptance

Park and Ohm {\*Park:2014jp} used survey data to construct a technology acceptance model to investigate users' acceptance of mobile mapping applications. They found that acceptance and hence intention to use a mobile mapping service depended to a large degree upon two factors; perceived locational accuracy and processing speed. Park and Ohm defined perceived locational accuracy as how well users envision their location in the map, essentially the degree to which mapped features correspond with a user's mental model of the world and where they are in it.

## Materials and Methods



### Generalised Workflow

[ ] Flowchart (similar to Miao, Shi and Cao, 2011)

### Data Model and Structures

#### TestMaster

##### TestEndpoint

##### LocationTest

##### NetworkTest

##### PingTest

#### ReferenceObject

#### Vector

### iOS Mobile Application

#### Mobile Application Design Principles

#### iOS Application Architecture

#### Swift Open Source Packages

##### Realm Mobile Database

##### Transporter State Machine

##### Reachability

##### KDCircularProgress

#### Hardware

### Google Apps Engine Web Service

#### Web Service Design Principles

#### Python Application Architecture

#### Python Open Source Packages

##### Matplotlib

### Other Applications Deployed

## Results

## Discussion

>Thissectionislikeashortessay – itisaconnectedseriesofsentencesthat
explainandargueyourinterpretationoftheevidence.
Summarise the major problem/s
Identifyalternative solutions to this/these major problem/s (there is likely to be more than one
solution per problem)
Briefly outlineeach alternative solution and then evaluate it in terms of its advantages and
disadvantages
No need to refer to theory orcoursework here.>

## Recommendations

>• Choose which of the alternative solutions should be adopted
• Briefly justify your choice explaining how it will solve the major problem/s
• This should be written in a forceful style as this section is intended to be persuasive
• Here integration of theory and coursework is appropriate>

## Future Work

Android app

Other jurisdictions (NSW LPI for instance) allows the various data providers to learn from each other and improve.

Compare errors to Landgate’s server logs for more insight into error causes.

## Conclusions

Our study's contexts are in a state of nearly constant change. Web services have lost complexity due to the dominance of ReST APIs, but the number of services available has grown exponentially. Mobile devices have more processing power, larger batteries and faster connections to the internet. There are whole new categories of mobile devices, such as smartwatches, that change the mobile device landscape. Web service evaluation studies must be continually revisited just to keep pace with change.

Similarly, service providers must prepare for a changing landscape that may not even be partially realised yet. Landgate has evolved and changed direction since early in the decade to build the SLIP Future program. They must continue to adopt new technologies and processes so as to remain relevant to their customers.

In this work we contribute to three aspects of the body of web service evaluation literature.
Firstly, we test services from an actual mobile device in real-world mobile usage situations. Tests are therefore as close to the real mobile experience as possible. This contrasts with the bulk of academic literature that performs tests on desktop computers emulating mobile devices.

Secondly, we examine more aspects of the interaction between client and server than merely average response time. Examining error responses and the conditions that lead to them will give valuable insight into mobile-specific situations likely to result in errors.

Lastly, our examination of a single service provider, Landgate and WALIS's SLIP service, should produce practical and actionable recommendations to improve its suitability for mobile users.

## References

## Appendix A

### Web Service Requests

## Appendix B
