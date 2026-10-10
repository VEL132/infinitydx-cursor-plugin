# infinitydx-cursor-plugin
Plugin package for Cursor MarketPlace ∞Dx
# ∞Dx

**Physical-world context for AI agents and applications.**

**∞Dx**, by **Artificial Infinity**, turns street-level observations into structured, queryable intelligence, enabling AI systems and applications to understand and interact with the physical world.

∞Dx helps AI agents understand what is physically present at a location, where it is, when it was observed, and how recent the available information is.

Rather than relying exclusively on static maps, web pages, or historical geographic information, AI systems can access observed physical-world context to support everyday questions, business decisions, operational workflows, and specialized infrastructure analysis.

The platform combines recurring street-level visual observations, geospatial processing, physical asset detection, coverage and inspection information, historical observations, and supporting visual evidence into a machine-readable interface.

Through **Model Context Protocol (MCP)** and API interfaces, ∞Dx makes physical-world observations accessible to compatible AI systems.

## What ∞Dx can be used for

∞Dx supports both general physical-world context queries and specialized infrastructure or asset-level questions.

### General physical-world context

- **Location and neighborhood intelligence**  
  Understand the observed physical characteristics of streets, neighborhoods, commercial areas, public spaces, and geographic locations, including visible infrastructure, street conditions, environmental features, and other relevant physical context.

- **Context for AI agents and applications**  
  Enable AI systems to incorporate geographically grounded physical observations into their reasoning, recommendations, and workflows.

- **Property and insurance assessment**  
  Add observed physical surroundings, nearby infrastructure, road conditions, vegetation, and other relevant street-level context to property assessments, insurance underwriting, or claims investigations.

- **Commercial location and retail site selection**  
  Evaluate the observed physical surroundings of potential business locations, including street accessibility, surrounding infrastructure, visible environmental characteristics, and other location-related considerations.

- **Mobility, routing, and logistics**  
  Provide physical-world context for delivery operations, fleet planning, route assessment, and mobility decisions using available street and road observations.

- **Nighttime and environmental context**  
  Understand available nighttime observations, streetlight illumination, streetscape characteristics, and other physical conditions relevant to activities occurring after dark.

- **Historical physical-world context**  
  Compare observations collected at different times to identify observable changes in streets, infrastructure, and surrounding physical environments.

### Infrastructure and operational intelligence

- **Infrastructure intelligence**  
  Query utility poles, telecommunications infrastructure, traffic signs, road assets, street furniture, sanitation assets, vegetation, and other supported physical infrastructure.

- **Road and mobility context**  
  Query observed road conditions, mapped and unmapped road extent, inspection status, and DAY/NIGHT coverage where available.

- **Asset condition and maintenance context**  
  Retrieve supported condition observations and identify assets or locations that may require inspection, maintenance, or follow-up.

- **Physical-world evidence**  
  Retrieve short-lived visual evidence associated with supported observations when available.

- **Operational and analytical workflows**  
  Support infrastructure audits, maintenance planning, field operations, site assessments, and other workflows that benefit from observed physical-world context.

## Example interactions

The following examples illustrate how AI agents and applications can incorporate ∞Dx physical-world context into practical questions and workflows.

### General location and neighborhood context

**Understand an unfamiliar neighborhood**

> I'm visiting Quinta Camacho in Bogotá for the first time. What physical street context would be useful for me to know before I arrive?

**Understand the physical environment of a location**

> Using ∞Dx, describe the physical environment around Parque de la 93 in Bogotá. What characterizes the surrounding streets, public spaces, infrastructure, and visible urban environment?

**Compare physical environments**

> Using ∞Dx, compare the observed physical environments of Quinta Camacho and Parque de la 93 in Bogotá. What are the most relevant differences in their streetscape and surrounding infrastructure?

### Business, property, and insurance

**Commercial property risk assessment**

> I'm reviewing an insurance application for a commercial property near Avenida Carrera 68 and Calle 72 in Bogotá. What should I be concerned about around the property that could affect the risk profile?

**Retail site selection**

> I'm considering opening a convenience store near Plaza de las Américas in Bogotá. What should I know about the location before deciding whether it's a good site?

**Motor insurance claims**

> A customer says their car was damaged after hitting a pothole near Calle 80 and Avenida Boyacá in Bogotá. Can you help me assess whether the claim is plausible and what evidence might support it?

### Mobility, logistics, and nighttime context

**Delivery operations**

> I have a delivery van going through Quinta Camacho. Based on what has been observed, are there any street conditions the driver should know about?

**Compare road conditions along alternative routes**

> For driving north through this part of Bogotá, which appears to have fewer observed road-surface problems: Carrera 7 between Calle 70 and Calle 74, or Carrera 11 over the same north-south span?

**Nighttime pickup context**

> I have a late-night pickup near Parque de la 93 in Bogotá. What can your observations tell me about how well-lit the street appears around there?

### Historical physical-world context

**Understand changes over time**

> Here is a pin in Bogotá: 4.5952, -74.1445. Has this location looked materially different over time, or have the observed street conditions stayed broadly similar?

**Compare historical observations**

> Using ∞Dx, show me the current and earlier observations of this location, keeping daytime and nighttime histories separate, with supporting images where available.

### Infrastructure and asset intelligence

**Utility and telecommunications infrastructure**

> Using ∞Dx, show me ten utility or telecom poles observed in Bogotá, with their category, location, observation date, and supporting images for three examples.

**Road conditions**

> Using ∞Dx, show me five pothole or road-crack observations in Quinta Camacho, Bogotá, with location, observation date, and an image for each.

**Vegetation and physical surroundings**

> Using ∞Dx, show me areas in Chicó, Bogotá where medium or high vegetation density was observed, including locations, observation dates, and available images.

**Broad physical-context assessment**

> Using ∞Dx, give me an operational snapshot of the physical street context around Quinta Camacho, Bogotá. Include available observations for road conditions, traffic signs, utility infrastructure, streetlights, road markings, vegetation, and road coverage.

### Visual evidence

**Retrieve supporting imagery**

> Can you show me the images that support the most important points you just mentioned?

The examples illustrate potential workflows. Available responses depend on supported tools, geographic coverage, observation history, account permissions, and available visual evidence.

## MCP connection

∞Dx exposes its physical-world context capabilities through a **Model Context Protocol (MCP)** server.

**Production MCP endpoint:**

```text
https://mcp.artinfinitydx.com/mcp
```

MCP enables compatible AI clients, including Cursor, to discover and invoke available ∞Dx tools through a standardized interface.

### Connection architecture

```text
Cursor / MCP-compatible AI client
          |
          | HTTPS + OAuth authorization
          v
     ∞Dx MCP Server
          |
          v
     ∞Dx API Services
          |
          v
 Physical-world observations
 Coverage, assets and evidence
          |
          v
    Structured MCP responses
```

The MCP integration supports tool discovery, authenticated access, access control, and requests to the underlying ∞Dx physical-context services.

Once connected, an AI client can invoke available tools, receive structured physical-world observations, and incorporate that context into responses or application workflows.

## Authentication

∞Dx uses OAuth-based authentication for MCP access.

For clients supporting the required OAuth flow:

1. The client discovers the ∞Dx MCP server and its authorization metadata.
2. The user is redirected to the ∞Dx authorization flow.
3. Following successful authentication and authorization, the client obtains the credentials required to access the MCP server.
4. Subsequent MCP tool calls are authorized according to the user's account, permissions, and available ∞Dx capabilities.

OAuth compatibility and the authentication experience may vary between MCP clients.

**Security:** Access tokens, API credentials, and other secrets must never be embedded in prompts or committed to public repositories.

## Data availability and interpretation

∞Dx provides access to physical-world observations collected and processed within supported geographic areas.

Data availability depends on location, observation category, capture history, processing status, and account permissions.

Important considerations include:

- **Observation recency:** Observations describe physical conditions at the time they were collected and do not necessarily represent current conditions.
- **Geographic coverage:** Not every road, neighborhood, city, or geographic area has available observations.
- **Refresh frequency:** Observation frequency can vary by road segment, geographic area, and collection activity.
- **Observed versus inferred information:** AI agents should distinguish directly observed physical facts from interpretations or conclusions.
- **Detection limitations:** AI-assisted observations may contain uncertainty or classification errors.
- **Missing observations:** The absence of an observation does not prove that a feature or physical condition is absent.
- **Visual evidence:** Supporting imagery may be available through temporary, access-controlled links.
- **Contextual use:** ∞Dx observations can contribute to broader decisions and analysis alongside other relevant information.

## Privacy and security

The public Cursor plugin repository contains integration configuration and documentation only.

It does not contain proprietary processing infrastructure, private databases, customer observations, authentication credentials, or API secrets.

Access to ∞Dx services is subject to authentication, authorization, and applicable account permissions.

## About Artificial Infinity

**Artificial Infinity** is building a vision-first system of record for the physical world—continuously observing streets and infrastructure to create a living, machine-readable representation of reality.

∞Dx makes this evolving physical context accessible through MCP and API interfaces, enabling AI agents, developers, and organizations to incorporate grounded physical-world observations into their applications, decisions, and workflows.

**MCP endpoint:** https://mcp.artinfinitydx.com/mcp

**Cursor plugin repository:** https://github.com/VEL132/infinitydx-cursor-plugin

---

© Artificial Infinity / VirtualEL. All rights reserved.
