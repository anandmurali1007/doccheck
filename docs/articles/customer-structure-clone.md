# Customer article structure clone

Structural clone of the reported article. Prose is neutral; every Markdown
construct, attribute-quoting style and indentation quirk matches the customer
file exactly, including the inconsistent callout indentation and the trailing
hard-break spaces.

[Product One](https://example.com/products/platform){target=`_blank`} is a platform that helps organizations:

* Identify and prioritize real risks
* Detect, investigate, and respond to real-time threats
* Get unified visibility and eliminate siloes

Integrating with Product One enables you to **receive vulnerability, compliance, and identity findings via the Platform.**

## Prerequisites
To integrate your Product One setup, you will need to provide your **API Server URL** and **Access Token**. You can review the official documentation site [here](https://example.com/en/docs/product-one/){target=`_blank`}.

:::(Warning) (your title goes here)
To access the Vulnerability Engine in Product One, you must be credentialed as a user with at least [Advanced User](https://example.com/en/docs/administration/manage-teams-and-roles/#:~:text=team%20member%20permissions.-,Advanced%20User%3A,-In%20Product%20One) permissions.
:::

* To obtain your **API Server URL**, review the SaaS Regions and IP Ranges [topic](https://example.com/en/administration/saas-regions/#platform-regions){target=`_blank`}.
* To obtain your **API (Access) Token**, review the official documentation [here](https://example.com/en/administration/retrieve-the-api-token/){target=`_blank`}.
* **Copy and save** these data points for setup in the platform.
   
## Add an Instance

1. Go to **Settings** > **Integrations - Data Sources** >  **Product One** > **Integrate**.
2. In the **Name** field, enter a descriptive name for this instance.
3. In the **API Server URL** and **Access Token** fields, paste the values you saved.
4. For each type of finding that you want to collect, select its **respective checkbox**. You can select **Collect Host Vulnerabilities**, **Collect Container Vulnerabilities**, **Collect Container Image Vulnerabilities**, and/or **Collect CSPM Findings**.
    :::(Info) (Collect CSPM Findings)
    This single checkbox collects all three posture families: cloud posture (CSPM), Kubernetes posture (KSPM), and host configuration benchmarks. They arrive as three separate finding types.
    :::
5. In the Collection Settings,
    1. Select the **enabled toggle**.
    3. Select **when to collect data** (daily or weekly) and **time**.
6. In the Automatic Resolution Settings, enter values (in number of days) for **Last Reported Time** and **Last Collected Time.**  
     :::(Warning) (Important)
     Last Collected Time and Last Reported Time relate to when data is collected from data sources and when the third party records a finding. Set your Last Collected Time value to a number that is **equal or less than** the Last Reported Time.
     :::
7. When finished, select **Save**.
