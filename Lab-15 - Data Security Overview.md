![Banner](./assets/banner.png)

# Lab 15: Data Security Overview

## Task 1: Discuss Data Security Solutions

> Microsoft Purview

**⏰ Duration:** XX minutes

**🎯 Outcome:** At the end of this task, you will have a overview of the Purview Data Security solutions and objectives.

**🫂 Team Activity:** [XX minutes] Together as a group, revisit the questions posed at the start of Lab 15, adding a little detail around each answer to guide you in the following exercises.

- Have you got the respective Microsoft 365 Enterprise license to test out the Data Security capabilities?
- How familiar are you with the information protection framework: Know your data, Protect your data, Prevent Data Loss?
- Have you already use Data Classification tecniques like Sensitive Info Types or Trainable Classifiers? How are they different?
- Do you have M365 - E3/E5 Data Security policies in place already (Information Protection, Data Loss Prevention, Insider Risk Management, Information Barriers, etc)?
- Are there any other workloads that need to be considered/evaluated as part of the Purview Data Security initative? (On-Premises, SaaS apps, Fabric)
- Have you mapped the desired data protection motivations and outcomes?
- Have you planned your path to end user adoption?

If you were unable to answer many of these questions, lets aim to get clarity at the end of the session/workshop - once capabilities become clearer to you.

Source: [Data Security Solutions](https://learn.microsoft.com/en-us/purview/purview-security)

## Task 2: Discuss Adoption Approach

> Microsoft Information Protection Framework

**⏰ Duration:** 10 minutes

**🎯 Outcome:** At the end of this task, you will be able to understand the Information Protection Framework stages.

### Understanding the framework

> Source: [Microsoft Purview Information Protection Framework](https://learn.microsoft.com/en-us/purview/information-protection-solution)

Purview Data Security solutions are deeply integrated and work together to provide a solution for different use cases. Information Protection and Data Loss Prevention use a three-phased approach to rollout the solution: Know your data, Protect your data and Prevent data loss. Each stage uses a combination o features to achieve their goals.

![Alt text of the image](https://learn.microsoft.com/en-us/purview/media/mip-solution-overview-extended.png)

### Know your data

> Source: [Know your data](https://learn.microsoft.com/en-us/purview/information-protection-solution?tabs=phase-one#know-your-data)

Purview Information Protection data classification helps you to discover and classify data in the organizaion. There are three main There are different data classification technologies, however the most common are:

**Sensitive Information Types (SITs)**
- Pattern based classifiers: Detect sensitive information like bank account or credit card numbers.
- More than 300 out-of-the-box SITs ready to be used.
- Create new SITs using regular expressions, [keyword list/dictionary](https://learn.microsoft.com/en-us/purview/sit-create-a-keyword-dictionary) and [functions](https://learn.microsoft.com/en-us/purview/sit-functions).
- Combine these elements to create accurate detections with different [confidence levels](https://learn.microsoft.com/en-us/purview/sit-sensitive-information-type-learn-about#more-on-confidence-levels), which are key for automatic labeling and data loss prevention.
- SITs are used in
-   DLP Policies - Rule conditions
-   Sensitivity Labels - automatic-labeling
-   Retention Labels - automatic-labeling
-   Insider risk management - policies
-   Communication Compliance - rule conditions
-   Service-Side automatic-labeling
-   Microsoft Priva 

Remember, to manage collections, you need to be at least a Domain Admin or Collection Admin within the [Purview governance portal](https://learn.microsoft.com/purview/governance-roles-permissions#domain-and-collection-permissions).

### Exercise: Create Domains and Collections

**🫂 Team Activity:** [5 minutes] As a group, identify whether there is a need to create multiple platform domains in Purview (limit is 4)? These allow you to separate data sources into isolated domains or merge existing (classic) Azure Purview accounts into one.

- Is there a requirement to create a dev/prod type of setup (bearing in mind that a data source can only be registered in one place at a time)?
- Can you use one platform domain (prod) and rely on the ability to change the status of non-curated assets instead of doing so in multiple domains?
- Does your organization have parent/child company setups where you need to consider how to represent the child company under the same Purview Data Map?

> **Does your tenant fall into any of these categories?** Government, Health Department, Education? If so, you may need to be guided by your Microsoft contact or partner regarding the optimal setup, given only 4 custom domains can be created.

**✍️ Do in Purview:** [5 minutes] Navigate to the Data Map and create a new platform/technical domain if required. If not required, continue on. You will be working inside the default domain.

- [Assign](https://learn.microsoft.com/purview/governance-roles-permissions#add-role-assignments) the respective platform domain admin(s).

## Task 3: Create and Extend Sensitivity Labels

> Microsoft Purview Solution: Information Protection

**⏰ Duration:** 30 minutes

**🎯 Outcome:** At the end of this task, you will have created tenant-wide sensitivity labels in the Compliance solution. These can be added manually (or automatically if an E5 Risk & Compliance license is available) to data assets at the time of creation (or labelled later). You will also learn how to expand these labels to the Purview Data Map solution for labelling of structured data assets.

### Understanding Sensitivity Labels

Sensitivity Labels are a feature that help you classify and protect organizational data (usually at the time of creation, but can be applied or modified at any time). They help ensure that user productivity and collaboration capabilities remain uncompromised by 'stamping' the data (file, folder etc) with a consistent text and protective properties that follow the data no matter where it is stored.

![Sensitivity Label Recommendation](./assets/sensitivity-label-recommendation.png)

Sensitivity labels can be used to control access to content using encryption, add watermarks, and apply access policies automatically. This enables the consistent protection of content in Teams, SharePoint sites, chat and meeting data.

Sensitivity labels are created and maintained in Purview - Information Protection and extend to Power BI, the Purview Data Map, and even integrate with third-party applications. [Supported data sources](https://learn.microsoft.com/en-us/purview/microsoft-purview-connector-overview) (see 'labeling' column).

The label's scope determines the label's settings and its availability to other apps and services. The label's order in the list also sets its priority (with labels appearing lower on the list having a higher order number and thus, higher priority).

![Applying Sensitivity Labels](./assets/applying-sensitivity-labels.png)

Sub labels, or 'child' labels beneath a 'parent' label, present labels to users in logical groups. They do not inherit the protection settings of their parent label, but do inherit their colour.

Sensitivity labels are also recognized and used by Microsoft services like Microsoft Copilot for Microsoft 365 and Azure Information Protection, etc. These services check the usage rights for the individual user at runtime, enabling an extra layer of protection for labeled items.

### Exercise: Implement Sensitivity Labels

**🫂 Team Activity:** [5 minutes] Discuss whether your organization has an E3/E5 license today and whether sensitivity labels are set up in your business already.

- Are you using sensitivity labels today and do these get automatically or manually applied to unstructured data assets like Microsoft 365 apps to protect new business data at the time of creation?
- Are sensitivity labels enforced for all users in the business (the recommended approach) or targeted selectively?

**✍️ Do in Purview:** [5 minutes] Open the Information Protection solution:

- Create, review, and publish organization-wide sensitivity labels as required.
  ![Sensitivity Labels Overview in Microsoft Purview](./assets/sensitivity-labels-overview.png)
- Define Auto-labeling policies as required by your organization.
- Define Trainable Classifiers and Sensitive Information Types as applicable.
- Enable the option to 'Extend Sensitivity Labels to the Purview Data Map'.</br>
  - New scans and supported data sources can now be labelled (automatically) with the sensitivity label.

## Task 4: Adding Lineage Connections

> Microsoft Purview Solution: Data Map

**⏰ Duration:** 10 minutes

**🎯 Outcome:** At the end of this task, you will have connected an Azure Data Factory instance and a Azure Data Share account to the Data Map. This ensures that ETL processes (e.g. at the column level) performed by that component are accurately captured as lineage, once we registering and scan the data sources it is connected too.

### Understanding Data Lineage

Data Lineage represents the lifecycle of an organization's data, tracing its origin and movement across the data estate. This data could include raw data from various platforms, transformed and prepared data, and data utilized by visualization platforms.

Understanding the lineage of data assets is important for troubleshooting data pipelines, data quality analysis, compliance, and impact analysis. It illustrates how data moves from source to destination, including the transformations and business rules applied.

![Asset Lineage](./assets/asset-lineage.png)

**Types of Lineage:**

- **Entity (or asset) Lineage:** As the name suggested, this is lineage at the coarse grain of the entity or object level. Lineage is typically represented as a graph showing source and target entities, linked by a process invoked by a compute system, assisting in making the lineage human-readable.
- **Column-level (or attribute) lineage:** This is lineage at a finer grain, i.e. columns within that entity. It identifies columns of a source entity that are used to create or derive columns in the target entity, assisting in tracking column-level changes from the source to the target.

### Exercise: Adding Lineage Connections (optional)

**✍️ Do in Purview:** [5 minutes] Navigate to the Data Map solution's 'Source Management', and enter the 'Lineage connections' tab. Add one or more Azure Data Factory resources.

![Adding Data Factory Lineage Connections](./assets/data-factory-lineage-connection.png)

After registration, the Status should appear as: `Connected`

![Data Factory Lineage Overview](./assets/data-factory-lineage-overview.png)

**✍️ Do in Purview:** [5 minutes] Navigate to the Data Map solution's Source Management, and enter the 'Lineage connections' tab. Add one or more Azure Data Share resources.

**✨ Pro Tip:** Each Data Factory or Azure Data Share instance can only be connected to one Purview account. A single instance cant be shared across accounts.

---

**⏸️ Reflection:** At this point you have understood the need for multiple platform domains and the collection hierarchy within each. You also learned about the types of roles a Purview administrator may assign at the top-most levels of the Data Map. You experimented with Sensitivity Labels and extended them to the Purview Data Map for automatic labeling in the next lab.

Lastly, you learned about the benefit of data lineage, how ETL tools like Azure Data Factory and data sharing services like Azure Data Share. can be connected to Purview to provide lineage information.

👉 [Continue: Lab 3](./Lab-03%20-%20Managing%20Data%20Sources.md)
