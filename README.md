# Azure Resource Graph Queries

# How to use

1. Log in to Azure Portal
2. Navigate to Azure Resource Graph Explorer
3. Use queries to retrieve Azure Cost Advisor Recommendations

# Notes

- Recommendations where the type refers to Reserved Instances/Capacity will include an annual savings value
  - Check the "properties.extendedProperties.term" field to understand which Reservation period the saving applies to
  - When querying by RecommendationType be aware of the number of resources that the recommendation is applied to.  This can be found in "properties.extendedProperties.targetResourceCount"
- Recommendations where the type refers to Right Size or Shut down will not have an annual savings value.  Instead refer to "properties.extendedProperties.targetSku".
  - To calculate targetSku costs a separate call will need to be made against the Pricing API: https://docs.microsoft.com/en-us/rest/api/cost-management/retail-prices/azure-retail-prices

## All the above is achievable by viewing Azure Advisor Cost Optimisation blade in the Azure Portal.  However, to present in a different "finance friendly" format, you will need to export this data and re-present with something like PowerBI.
