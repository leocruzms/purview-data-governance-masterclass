![Banner](./assets/banner.png)

# Lab 15: Data Security Introduction

## Task 1: Executive Overview

**⏰ Duration:** 20 minutes

**🎯 Outcome:** The facilitator will provide an executive overview of the Microsoft view of Data Security, the industry trends, and the Purview Data Security solutions.

Provide a overview of the [Identify and protect sensitive business data Framework](https://learn.microsoft.com/en-us/security/zero-trust/adopt/identify-protect-sensitive-business-data)

- Identitfy Purview Data Security solutions principles: [Know your data, Protect your data and Prevent Data loss](https://learn.microsoft.com/en-us/purview/information-protection)
- Discuss [Know your data](https://learn.microsoft.com/en-us/training/modules/m365-compliance-information-governance/know-your-data) process and Purview data classification technologies.
- Discuss how Sensitivity Labels are used to [Protect your data](https://learn.microsoft.com/en-us/training/modules/m365-compliance-information-governance/protect-your-data).
- Discuss typical [Data governance processes](https://learn.microsoft.com/azure/cloud-adoption-framework/scenarios/cloud-scale-analytics/govern-components).
- Briefly cover off the [Reference model for planning](https://learn.microsoft.com/purview/data-catalog-get-started?view=o365-worldwide#reference-model-for-planning) guidance.

Discuss the [recommendations for data classification](https://learn.microsoft.com/azure/well-architected/security/data-classification) from the Azure [Well-Architected Framework](https://learn.microsoft.com/azure/well-architected/), noting that many organisations will have defined data classification policies to work from, but are still on the journey to a fully formed taxonomy.

Next cover the Industry Challenges and an Introduction to Microsoft Purview.

At a summary level - Purview Data Governance contains two main components:

- The Data Map – technical metadata and lineage from source are ingested and structured via the logical constructs of Domains & Collections.
- The Unified Catalog - organizing, annotating, and publishing data, so that its accessible and understood by end-users, reflecting enterprise terminology and context. The abstraction of “data products” provide the linkage to the technical metadata and lineage from the data map.
- 

### Exercise: Create Data Products

**🫂 Team Activity:** [10 minutes] Identify a business unit (governance domain) and then on a whiteboard map out their data assets into groups that can easily be packaged together for a couple of specific use cases. It may be that transaction information and customer details that can be grouped into an Open Banking data product for example.

**✨ Pro Tip:** If lost, just use the 'Sales' example from above.

While its tempting to create a one-to-one mapping between data assets and Data products, it is important to note that a individual data asset can belong to zero-to-many Data products. i.e. the enterprise product hierarchy table, used across numerous reporting and downstream solutions. Carefully consider the trade-offs when deciding on the approach, especially across the entire data lifecycle, and when governance grows across the data estate.

**✨ Pro Tip:** Create a Key-Design-Decision (KDD) which articulates the rationale, considerations, and implications for whichever approach you decide. This will create transparency and an audit trail for this decision.

**✍️ Do in Purview:** [5 minutes]

- Define your Data products per Governance domain via the 'New data product' wizard. Provide a name and description, and list the use cases in the respective text area. Take advantage of rich text descriptions and bullet pointing for readability.
- In the Data product overview, note the status (draft/published).
- Now associate Data assets via the 'Add data assets' option as per the whiteboard exercise above. The Data assets added here should be relevant to the Data product and may belong to no, one, or more Data products.
- Associate any Terms via the 'Add term' option.
- Associate any OKRs via the 'Add OKR' option (more on this in the next lab).
- Review the data product owner contact, and ensure it correctly reflects the employee(s) directly responsible for its upkeep.

**✨ Pro Tip:** To speed up your curation experience, explore the option to let Copilot ([licence dependant](https://learn.microsoft.com/purview/copilot-in-purview-overview)) discover recommended data assets to associate with each Data product.

## Task 2: Defining Data Product Access

**⏰ Duration:** 15 minutes

**🎯 Outcome:** At the end of this task, you will have defined access controls for a Data product, enabling it for self-service consumption by end users.

### Understanding Data Product Access

[Access Policies](https://learn.microsoft.com/purview/how-to-manage-data-catalog-access-policies) are essential to ensure that data is used responsibly and in compliance with organizational policies. Data Access defines who can access the data product, what they can do with the data, and under what conditions they can access the data. Access policies are defined at the data product level and enforced across all data assets within it.

**🫂 Team Activity:** [15 minutes] Discuss access controls for a given data product you created in Task 1 of this lab.

- Outline the intended usage of that Data product, with a name and brief description. Does this required an access request workflow for end users?
- Define the access approval requirements for the Data product. Who are the people that need to approve and grant access to the physical data assets in the Data product?
  - Should employee manager approval be required?
- Is a privacy and compliance review required?
- Does the requestor need to accept any data use terms before proceeding with the request?
- Is there access duration requirement for that Data Product?

**✍️ Do in Purview:** [10 minutes] Now define the Data product access using the 'Manage access' option, adding in the relevant purpose and approval requirements based on the team activity. Repeat with other Data products.

---

**⏸️ Reflection:** You have now created Data products and defined access controls for each. How do you think this will help your organization in making data more discoverable and consumable? What are some of the challenges you foresee in maintaining these Data product - access controls as the business evolves?

**✨ Pro Tip:** Remember that you are aiming for a federated data governance model. The task of maintaining data products and access isn't all on you.

👉 [Continue: Lab 7](./Lab-07%20-%20OKRs.md)
