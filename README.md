---
services: Application
platforms: .Net
author: selvasingh
---

# Getting Started with Application - Manage Application Gateway - in .Net #

          Azure network sample for managing application gateways.
           - CREATE an application gateway for load balancing
             HTTP/HTTPS requests to backend server pools of virtual machines
             This application gateway serves traffic for multiple
             domain names
             Routing Rule 1
             Hostname 1 = None
             Backend server pool 1 = 4 virtual machines with IP addresses
             Backend server pool 1 settings = HTTP:8080
             Front end port 1 = HTTP:80
             Listener 1 = HTTP
             Routing rule 1 = HTTP listener 1 => backend server pool 1
             (round-robin load distribution)
             Routing Rule 2
             Hostname 2 = None
             Backend server pool 2 = 4 virtual machines with IP addresses
             Backend server pool 2 settings = HTTP:8080
             Front end port 2 = HTTPS:443
             Listener 2 = HTTPS
             Routing rule 2 = HTTPS listener 2 => backend server pool 2
             (round-robin load distribution)
           - MODIFY the application gateway - re-configure the Routing Rule 1 for SSL offload &
             add a host name, www.Contoso.Com
             Change listener 1 from HTTP to HTTPS
             Add SSL certificate to the listener
             Update front end port 1 to HTTPS:1443
             Add a host name, www.Contoso.Com
             Enable cookie-based affinity
             Modified Routing Rule 1
             Hostname 1 = www.Contoso.Com
             Backend server pool 1 = 4 virtual machines with IP addresses
             Backend server pool 1 settings = HTTP:8080
             Front end port 1 = HTTPS:1443
             Listener 1 = HTTPS
             Routing rule 1 = HTTPS listener 1 => backend server pool 1
             (round-robin load distribution)


## Running this Sample ##

To run this sample:

Set the environment variable `AZURE_AUTH_LOCATION` with the full path for an auth file. See [how to create an auth file](https://github.com/Azure/azure-sdk-for-net/blob/Fluent/AUTH.md).

    git clone https://github.com/Azure-Samples/application-gateway-dotnet-manage-application-gateways.git

    cd application-gateway-dotnet-manage-application-gateways

    dotnet restore

    dotnet run

## More information ##

[Azure Management Libraries for C#](https://github.com/Azure/azure-sdk-for-net/tree/Fluent)
[Azure .Net Developer Center](https://azure.microsoft.com/en-us/develop/net/)
If you don't have a Microsoft Azure subscription you can get a FREE trial account [here](http://go.microsoft.com/fwlink/?LinkId=330212)

---

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.