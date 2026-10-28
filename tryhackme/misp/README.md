# MISP


# Task 1: Room Overview

### **MISP - MALWARE INFORMATION SHARING PLATFORM**

This room explores the MISP
 Malware & Threat Sharing Platform through its core objective to 
foster sharing of structured threat information among security analysts,
 malware researchers and IT professionals.

### **Room Objectives**

We will be covering the following areas within the room:

- Introduction to MISP and why it was developed.
- Use cases MISP can be applied to
- Core features and terminologies.
- Dashboard Navigation.
- Event Creation and Management.
- Feeds and Taxonomies.

### **Room Prerequisites**

General familiarity with security concepts is: check out the [Pre-Security](https://tryhackme.com/path-action/presecurity/join) path and the [Jr. Security Analyst](https://tryhackme.com/room/jrsecanalystintrouxo) room.

At the end of the room, we will have an exercise task to test your knowledge of using MISP.

![Screenshot 2025-07-22 at 3.02.05 PM.png](images/01-screenshot.png)

# Task 2: MISP Introduction: Features & Terminologies

### **What is MISP?**

[MISP (Malware Information Sharing Platform)](https://www.misp-project.org/) is
 an open-source threat information platform that facilitates the 
collection, storage and distribution of threat intelligence and 
Indicators of Compromise (IOCs) related to malware, cyber attacks, 
financial fraud or any intelligence within a community of trusted 
members.

Information sharing follows a distributed model, with 
supported closed, semi-private, and open communities (public). 
Additionally, the threat information can be distributed and consumed by 
Network Intrusion Detection Systems (NIDS), log analysis tools and Security Information and Event Management Systems (SIEM).

MISP is effectively useful for the following use cases:

- **Malware Reverse Engineering**: Sharing of malware indicators to understand how different malware families function.
- **Security Investigations:** Searching, validating and using indicators in investigating security breaches.
- **Intelligence Analysis:** Gathering information about adversary groups and their capabilities.
- **Law Enforcement:** Using Indicators to support forensic investigations.
- **Risk Analysis:** Researching new threats, their likelihood and occurrences.
- **Fraud Analysis:** Sharing of financial indicators to detect financial fraud.

### **What does MISP support?**

![Image showing the MISP flow of functionalities.](https://tryhackme-images.s3.amazonaws.com/user-uploads/5fc2847e1bbebc03aa89fbf2/room-content/f290aace2e452972d1a9492f62cf46d5.png)

MISP provides the following core functionalities:

- **IOC database:** This allows for the storage of technical and non-technical information about malware samples, incidents, attackers and intelligence.
- **Automatic Correlation:** Identification of relationships between attributes and indicators from malware, attack campaigns or analysis.
- **Data Sharing:** This allows for sharing of information using different models of distributions and among different MISP instances.
- **Import & Export Features:** This allows the import and export of events in different formats to integrate other systems such as NIDS, HIDS, and OpenIOC.
- **Event Graph:** Showcases the relationships between objects and attributes identified from events.
- **API support:** Supports integration with own systems to fetch and export events and intelligence.

The following terms are commonly used within MISP and are related to the functionalities described above and the general usage of the platform:

- **Events:** Collection of contextually linked information.
- **Attributes:** Individual data points associated with an event, such as network or system indicators.
- **Objects:** Custom attribute compositions.
- **Object References:** Relationships between different objects.
- **Sightings:** Time-specific occurrences of a given data point or attribute detected to provide more credibility.
- **Tags:** Labels attached to events/attributes.
- **Taxonomies:** Classification libraries are used to tag, classify and organise information.
- **Galaxies:** Knowledge base items used to label events/attributes.
- **Indicators:** Pieces of information that can detect suspicious or malicious cyber activity.