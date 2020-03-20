---
title: Integrazione di System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: a80b5c3b336b4fd18b347a25ceaf509baf6461b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184386"
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="bb0a5-102">Integrazione di System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="bb0a5-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="bb0a5-103">Quando si ospita un servizio Windows Communication Foundation (WCF) in Internet Information Service (IIS) si inserisce un file con estensione svc nella directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="bb0a5-104">Questo file con estensione svc specifica la factory di host del servizio da utilizzare e la classe che implementa il servizio.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="bb0a5-105">Quando si effettuano richieste al servizio si specifica il `http://contoso.com/EmployeeServce.svc`file con estensione svc nell'URI, ad esempio: .</span><span class="sxs-lookup"><span data-stu-id="bb0a5-105">When making requests to the service you specify the .svc file in the URI, for example: `http://contoso.com/EmployeeServce.svc`.</span></span> <span data-ttu-id="bb0a5-106">Per i programmatori che scrivono servizi REST, questo tipo di URI non è ottimale.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-106">For programmers writing REST services, this type of URI is not optimal.</span></span> <span data-ttu-id="bb0a5-107">Gli URI per i servizi REST indicano una risorsa specifica e in genere non presentano estensioni.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="bb0a5-108">La <xref:System.Web.Routing> funzionalità di integrazione consente di ospitare un servizio REST WCF che risponde agli URI senza un'estensione.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="bb0a5-109">Per ulteriori informazioni sul [routing,](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))vedere ASP.NET Routing .</span><span class="sxs-lookup"><span data-stu-id="bb0a5-109">For more information about routing see [ASP.NET Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100)).</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="bb0a5-110">Utilizzo dell'integrazione System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="bb0a5-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="bb0a5-111">Per utilizzare la funzionalità di integrazione <xref:System.Web.Routing>, viene utilizzata la classe <xref:System.ServiceModel.Activation.ServiceRoute> per creare una o più route e aggiungerle a <xref:System.Web.Routing.RouteTable> in un file Global.asax.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="bb0a5-112">Queste route specificano i relativi URI a cui risponde il servizio.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="bb0a5-113">L'esempio seguente illustra come farlo.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-113">The following example shows how to do this.</span></span>  
  
```aspx-csharp  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));
   }  
</script>  
```  
  
 <span data-ttu-id="bb0a5-114">Tutte le richieste vengono indirizzato con un URI relativo che inizia con Customers al servizio `Service`.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="bb0a5-115">Nel file Web.config è necessario aggiungere il modulo `System.Web.Routing.UrlRoutingModule`, impostare l'attributo `runAllManagedModulesForAllRequests` su `true` e aggiungere il gestore `UrlRoutingHandler` all'elemento `<system.webServer>`, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 <span data-ttu-id="bb0a5-116">Vengono caricati un modulo e il gestore necessario per il routing.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="bb0a5-117">Per altre informazioni, vedere [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span><span class="sxs-lookup"><span data-stu-id="bb0a5-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="bb0a5-118">È inoltre necessario impostare l'attributo `aspNetCompatibilityEnabled` su `true` nell'elemento `<serviceHostingEnvironment>`, come indicato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="bb0a5-119">La classe che implementa il servizio deve abilitare i requisiti di compatibilità ASP.NET, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bb0a5-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```csharp
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb0a5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb0a5-120">See also</span></span>

- [<span data-ttu-id="bb0a5-121">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="bb0a5-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- <span data-ttu-id="bb0a5-122">[Routing di ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bb0a5-122">[ASP.NET Routing](https://docs.microsoft.com/previous-versions/aspnet/cc668201(v=vs.100))</span></span>
