# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

Both solutions could support deployement of the CMS app.

Using VM:
- Given the low level of expected activity on the application, costs would be higher given the static size of the compute.
- Scalability and availability could be supported by multiplying the number of VMs and using scale-sets or laod balancers - This also incurs higher costs
- Using a VM involves managing the underlying OS and application runtime. this is labor intensive. deployment workflows are more complex, keeping the whole system up to date requires more effort and this all contributes to higher costs.

Using AppService
- the service limits the amount of RAM and vCPUs available but given the expected traffic, is applicable an results in lower compute costs
- Horizontal and vertical sacalability is natively managed, ensuring dynamic capacity and failover to closely match the workload, leading to optimized costs
- code deployment can seamlessly be driven by CI/CD which leads to automated, effortless deployments and maintenance, reinforced by the fact that the underlying OS/app runtime is managed by Microsoft

For this project I've opted for App Service given that the deployed application is a simple HTTP based solution which fits nicely App Service. We're using python which is one of the supported languages. Capacity is not an issue at this stage and there are no specific requirements on the underlying OS.


*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

### Assess app changes that would change your decision.

If the traffic on the application would increase significantly enough to reach the limits of App Service vCPU or a steady high traffic; using a VM could become more cost effective. 
Should the application require to stick to a particular runtime version that no longer is supported by Microsoft, this could necessitate a migration towards a VM based compute.
