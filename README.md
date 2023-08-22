This is the dbt project for EDA Enrichment. 
It manages the complete enrichment process for all DA3 data domains.

## Data domains

### Product domain

The product data domain contains the data assets built using product data. 
The consumption data is accessible on BigQuery via the `da3_product_data_domain` dataset. 

- [Product domain main Confluence page](https://zendesk.atlassian.net/wiki/spaces/EDATA/pages/5380112446/Product)
- [Product domain dbt enrichment](apps/da3_enrichment/models/domains/product/)

## Accessing sandboxes

Other than the consumption datasets, the developer-specific datasets are accessible on BigQuery (on `edw-dev` project) via a standardized naming pattern.

To access the sandbox for a dataset named `<consumption_dataset_name>`, the sandbox name would be the following: `sandbox_<username>_<consumption_dataset_name>`.

## Monitoring and alerting

We leverage the dbt package [re_data](https://docs.getre.io/latest/docs/introduction/whatis) to ensure monitoring and alerting for our different data assets.
re_data queries are executed via dedicated Airflow tasks to generate the metrics defined in our [dbt_project.yml](./dbt_project.yml) file.

The dedicated [monitoring dashboard](https://re-data.prod.edw.zende.sk/) is accessible via VPN while using an RFA gateway.

## Useful resources

- [How we use dbt within EDA](https://zendesk.atlassian.net/wiki/spaces/EDATA/pages/5416781685/). This page contains information about:
  - Our models layering strategy
  - dbt project structure
  - Our model materialization strategy
  - How we use documentation, macros, tests, and seeds
  - dbt-related external resources
- [Our dbt style guide](./dbt_style_guide.md)
- [EDA dbt onboarding](https://zendesk.atlassian.net/wiki/spaces/EDATA/pages/5435983731/EDA+dbt+Onboarding)
- [re_data documentation](https://docs.getre.io/latest/docs/introduction/whatis)
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
# eda_da3_enrichment
