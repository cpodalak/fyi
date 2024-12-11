---
slug: time-for-new-autosar-file-format
title: Time for new AUTOSAR file format?
tags: [autosar-big-picture]
---
# Time for new AUTOSAR file format?

## What is ARXML?
We all know plain **XML** (eXtensible Markup Language) file is a text-based file format that stores data in form of tags and text. Whereas **ARXML is AUTOSAR XML file to store AUTOSAR parameters** with added AUTOSAR specific tags and constraints.

Instead of delving into AUTOSAR parameters or the various types of ARXML files, let’s focus on a broader question:

**Why was ARXML chosen initially, and what alternative might be selected if AUTOSAR was initiated in 2023?**

## Why ARXML?
The answer is relatively straightforward. ARXML is based on XML. Whereas XML’s significant rise to prominence in the late 1990s and its adoption as a W3C recommendation in 1998 made it an ideal choice for data interchange and storage. Due to its flexible, human-readable, machine-readable nature and its widespread use in enterprise applications, web services (SOAP), and configuration files cemented its reputation well before the emergence of modern formats.

Essentially, XML was at the peak of its popularity when AUTOSAR was established.

### ARXML’s Place in Today’s Landscape
Since the early 2000s, the landscape of data serialization and configuration management has evolved considerably with modern formats like **JSON** (JavaScript Object Notation), **YAML** (YAML Ain’t Markup Language), and **TOML** (Tom’s Obvious, Minimal Language) or Data Modeling languages like ASN.1 or Protobuf.

Now, let’s not dig into JSON format much as it’s already been replaced by YAML and TOML in many areas.

Also, TOML is not as widely adopted as XML or YAML but it is gaining popularity for its simplicity and ease of use, particularly in smaller-scale applications and open-source projects, especially in the Rust and Go communities.

## CAN YAML replace ARXML?
Probably yes in some areas. YAML (YAML Ain’t Markup Language) is a human-readable data serialization standard that can be used in conjunction with all programming languages.

**Structured Data Representation:** YAML excels at representing structured data with a focus on human readability. It supports scalars (strings, numbers, booleans), arrays, and maps (key-value pairs), allowing for deeply nested data structures.

**Namespace Support:** YAML itself does not natively support XML-style namespaces. However, it can represent namespaced keys in a map through naming conventions or application-specific designs.

**Schema Validation:** While YAML does not have a built-in schema validation feature like XML Schema Definition (XSD), it can be used with external tools like JSON Schema for validation purposes. There are also custom schema validators for YAML, such as Kwalify or StrictYAML.

**Widespread Tooling:** YAML is widely supported across various programming languages and platforms with numerous libraries available for parsing and generating YAML data. It is commonly used in DevOps tools like Docker, Kubernetes, and continuous integration systems.

**Industry Precedence:** YAML has become a standard for configuration files in software development, particularly due to its clarity and ease of use. While not as entrenched as XML in enterprise data interchange.

### Can ASN.1 or Protocol Buffers replace AUTOSAR data exchange format?
ARXML is a file format used within the automotive industry to describe the configuration and behavior of automotive systems and their interactions. It is specifically tailored to the requirements and standards of the automotive domain.

While ASN.1(Abstract Syntax Notation One) and Protocol Buffers (protobuf) are powerful data modeling languages commonly used for defining data structures and serialization formats for network communication and data interchange across various industries, they are not designed specifically for the same purpose as ARXML.

## Conclusion
In my opinion, should the AUTOSAR team be in the position to choose today, they might consider YAML and come up with **ARYAML** or build a new data modelling language and call it as **ARDML** (AUTOSAR Data Modelling Language) to support “code first” approach.

If the AUTOSAR team decides to redefine the file format, I suggest considering the **adoption of multiple data exchange formats** that are best suited for use-cases. It’s important not to restrict the industry by using a single data exchange format for everything.

However, replacing ARXML would not be a simple task, given that it has been **deeply entrenched in the industry for over two decades** with extensive tools, workflows, and processes built around it. Transitioning to a new format raises interesting questions but also presents significant challenges that would require considerable effort, retooling, and **retraining across the entire ecosystem**.

### Potential for Change in the AI Era

Nevertheless, in an era where artificial intelligence and rapid technological advancements are the norms, change is always on the horizon. The industry’s mindset is increasingly open to innovation, suggesting that a shift, while complex, is not beyond the realm of possibility.

As the automotive industry continues to evolve with smart vehicles and connected infrastructure, the **demands on software architecture will undoubtedly lead to new considerations for data interchange formats.**