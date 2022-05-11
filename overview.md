<!-- Output copied to clipboard! -->

<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 0.853 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β33
* Wed May 11 2022 14:06:31 GMT-0700 (PDT)
* Source doc: A Formalization of Supply Chains for Security and Resilience_Git Version
----->


Formalizing and Implementing Supply Chains \
for Security and Resilience

V5 – Updated 7Apr2022

<p style="text-align: right">
Authors \
Edward Griffor \
James Butler</p>


<p style="text-align: right">
Sahra Abowitz</p>


<p style="text-align: right">
Benjamin Treuhaft</p>


<p style="text-align: right">
PatrickWilkie</p>


<p style="text-align: right">
Robert Read \
</p>


Table of Contents



* Background
* Natural Language Definitions and Descriptions
* Modeling Supply Chains
* Quantifying Supply Chain Resilience
* Implementing Supply Chains on and Information Technology-Based Platform

**Background**

Economies, and the businesses in the various sectors of those economies, struggle to manage capacity, struggled to balance supply with demand, especially in times where demand has surged. The causes of imbalance vary widely. However, recent surges in demand were for specific goods and services needed to respond to the COVID 19 pandemic. 

Today’s supply chains integrate physical and digital capabilities – including sensors, networks, data, and analytics – to improve efficiency and awareness. The sections below describe how the application of concepts from the field of cyber-physical systems (CPS) can enhance supply chain agility and resilience. The first section provides natural language definitions and descriptions of the relevant properties of supply chains. The second section sets out a formal approach to enable the application of powerful computational methods, including artificial intelligence, to the goals of supply chain security and resilience. 

**Natural Language Definitions and Descriptions**

The elements of a supply chain can comprise everything from the supply of raw materials to the end consumer, and include all intermediate steps, ranging from engineering, and manufacturing to logistics and distribution. 

The ‘glue’ that holds the elements of a supply chain together and provides trust or confidence is the set of agreements or contracts, which describe the requirements for associated transactions, specifying what is supplied, how much, its characteristics, payments, etc. This ‘glue’ represents the means by which a supply chain is composed.

Steps in a supply chain are ordered and consist of transactions between two or more elements in which completion of the responsibilities of a preceding element(s) is a prerequisite for the succeeding element(s) to execute their responsibilities.  The ordering of steps and associated dependencies create three critical characteristics of a supply chain.



* First, disruption of any one step influences the function of the entire chain. The resulting ‘brittleness’ (i.e. lack of resilience) is described in more detail below. 
* Second, steps in a supply chain may converge (where many elements are followed by one or a few), or branch (where one or a few elements are succeeded by many).  This creates both ‘bottlenecks,’ where flow throughout the chain depends on a small number of elements; and options, where multiple elements may be available for a required step.  The balance of bottlenecks and options influences the resilience and agility of a supply chain. 
* Third, individual elements typically have their own supply chains whose function is required for the element to fulfill its contractual responsibilities. As a result, assessing the functional status of a given supply chain requires assessing its hierarchical dependencies; assessing whether all of the elements of a chain are sufficiently supplied themselves to ensure their ability to meet their contractual obligations. 

A supply chain is compositional. That is, its characteristics are defined by the characteristics of its elements and the contracts governing its transactions. For example, the resilience of a supply chain is a function of both the resilience of its elements and the structure of contracts governing its transactions. A supply chain with a brittle element at a bottleneck is more brittle than another with the same element at an option point. Because of compositionality, managing a supply chain for resilience requires continuing awareness and management of the resilience of all of its elements and contracts.

Agility – a measure of the ease with which a supply chain can be restructured – is one means for enhancing resilience. For example, a supply chain disrupted by failure of one or more elements might be repaired by substituting equivalent functional elements. Mechanisms for agility (i.e., means for quick and easy repair) for a supply chain increase resilience to disruptions, including pandemics and disasters. 

The ability to substitute equivalent elements is dependent on composability; a measure of the ease or difficulty in creating or restructuring a supply chain from sets of elements. One factor in composability is modularity; the degree to which supply chain elements of a given class (e.g. logistics) can be substituted for one another while retaining both the essential functions of the class and the required interactions with adjacent elements. For example, two transport companies with equivalent bills of lading, rate and route structures, cargo capabilities, payment mechanisms, etc. would be modular with respect to the logistics function even if one included rail and the other only truck transport. In this particular example, supply chain resilience to rail disruption is enhanced by modularity for composability. 

Another factor in composability is interoperability, which includes both the ability of engineered systems to interact physically and of digital systems to exchange and act on information. For example, standardized shipping containers can be interoperable with respect to different ship, rail, and trucking systems. Information systems using standardized data and metadata formats can exchange data for distinct monitoring and control functions.  Interoperability among and between elements can facilitate composability and increase supply chain resilience. 

These complex concepts of interactions and dependencies, compositionality, agility, composability, modularity, and interoperability are at the heart of CPS measurement science.  The following section describes application of formalisms from the CPS field to supply chain resilience and security.

To achieve a supply chain that is resilient to disruptions, requires a deeper understanding of the supply chain itself, its elements and the role that contracts play. These elements need to be composable, the elements and their composition need to be accompanied by evidence for their validity, e.g., that a composition of materials needed and their use to manufacture a product is such that the materials meet the requirements of the manufacturer and its processes and that the capacity is there to fulfill the order with the quality and timing stated by the customer.

This is a complex structure that to date has not been apparent to participants in the market and, for just this reason, disruptions occur and shortages result or the products fail to meet the need of the customer. Hence this complexity needs to be illuminated by having a precise and measurable description of supply chain, orders and their dynamics.

**The Structure of Supply Chains**

In this essay we will introduce formal definitions of ‘supply chain’ and ‘order,’ drawn from existing standards or a published taxonomy (e.g. GS1 taxonomy). Further we will define a _dynamic supply chain_ as one that can be created, assessed, modified, or restructured in real-time using an implementation of this formalization.

A _dynamic_ supply chain comprises _elements_ that are composed to fulfill a single order or a set of orders. An element is _complete_ when there is verifiable evidence,<sup><a href="applewebdata://0005969A-DC57-40DA-AC85-59B68BA313B6#_ftn1">[1]</a></sup> sufficient for the specified risk level, that the respective contractor(s) can meet the relevant requirements of the specified order(s).

A fulfillmentsupply chain is _complete_ (with respect to a class of orders) when there is verifiable evidence that a dynamic supply chain can fulfill all contractual requirements for any specified order (in that class). A chain is _at risk_ when one or more of its elements exceed the specified risk level<sup><a href="applewebdata://0005969A-DC57-40DA-AC85-59B68BA313B6#_ftn2">[2]</a></sup>. A chain is _disrupted_ when one or more of its elements becomes _incomplete<sup><a href="applewebdata://0005969A-DC57-40DA-AC85-59B68BA313B6#_ftn3">[3]</a>,<a href="applewebdata://0005969A-DC57-40DA-AC85-59B68BA313B6#_ftn4">[4]</a></sup>_ (is not complete). 

An order is _valid_ when all relevant customer requirements are fully specified and there is verifiable evidence<sup>1</sup> that contracts are in place for all required elements in the supply chain. An order is _fulfilled_ when there is verifiable evidence<sup>1</sup> that all contractual requirements for all steps in a chain are completed.

<sup>[1]</sup> Evidence includes automated and recorded human assertions.

<sup>2</sup> Risk factors and associated risk levels are specified via implementing contracts.

<sup>3</sup> An element is incomplete when its associated verifiable evidence is incomplete. 

<sup>4</sup> One purpose of the platform, in addition to creating new supply chains, is to manage risk and repair disruptions to active chains.
