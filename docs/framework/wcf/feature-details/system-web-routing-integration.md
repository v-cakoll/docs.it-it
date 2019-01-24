---
title: Integrazione di System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 0ace776b8be64f42c05918bc234d39cd96bf8782
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688185"
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="c1d3c-102">Integrazione di System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="c1d3c-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="c1d3c-103">Quando si ospita un servizio Windows Communication Foundation (WCF) in Internet Information Service (IIS) si inserisce un file con estensione svc nella directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="c1d3c-104">Questo file con estensione svc specifica la factory di host del servizio da utilizzare e la classe che implementa il servizio.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="c1d3c-105">Quando si effettuano richieste al servizio è specificare il file con estensione svc nell'URI, ad esempio: `http://contoso.com/EmployeeServce.svc`.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-105">When making requests to the service you specify the .svc file in the URI, for example: `http://contoso.com/EmployeeServce.svc`.</span></span> <span data-ttu-id="c1d3c-106">Per i programmatori che scrivono servizi REST, questo tipo di URI non è ottimale.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-106">For programmers writing REST services this type of URI is not optimal.</span></span> <span data-ttu-id="c1d3c-107">Gli URI per i servizi REST indicano una risorsa specifica e in genere non presentano estensioni.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="c1d3c-108">Il <xref:System.Web.Routing> caratteristica di integrazione consente di ospitare un servizio WCF REST che risponde a URI sprovvisti di estensione.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="c1d3c-109">Per altre informazioni, vedere routing [Routing ASP.NET](https://go.microsoft.com/fwlink/?LinkId=184660).</span><span class="sxs-lookup"><span data-stu-id="c1d3c-109">For more information about routing see [ASP.NET Routing](https://go.microsoft.com/fwlink/?LinkId=184660).</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="c1d3c-110">Utilizzo dell'integrazione System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="c1d3c-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="c1d3c-111">Per utilizzare la funzionalità di integrazione <xref:System.Web.Routing>, viene utilizzata la classe <xref:System.ServiceModel.Activation.ServiceRoute> per creare una o più route e aggiungerle a <xref:System.Web.Routing.RouteTable> in un file Global.asax.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="c1d3c-112">Queste route specificano i relativi URI a cui risponde il servizio.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="c1d3c-113">Nell'esempio seguente viene illustrato come effettuare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-113">The following example shows how to do this.</span></span>  
  
```  
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
  
 <span data-ttu-id="c1d3c-114">Tutte le richieste vengono indirizzato con un URI relativo che inizia con Customers al servizio `Service`.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="c1d3c-115">Nel file Web.config è necessario aggiungere il modulo `System.Web.Routing.UrlRoutingModule`, impostare l'attributo `runAllManagedModulesForAllRequests` su `true` e aggiungere il gestore `UrlRoutingHandler` all'elemento `<system.webServer>`, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="c1d3c-116">Vengono caricati un modulo e il gestore necessario per il routing.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="c1d3c-117">Per altre informazioni, vedere [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span><span class="sxs-lookup"><span data-stu-id="c1d3c-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="c1d3c-118">È inoltre necessario impostare l'attributo `aspNetCompatibilityEnabled` su `true` nell'elemento `<serviceHostingEnvironment>`, come indicato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="c1d3c-119">La classe che implementa il servizio deve abilitare i requisiti di compatibilità ASP.NET, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c1d3c-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1d3c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1d3c-120">See also</span></span>
- [<span data-ttu-id="c1d3c-121">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="c1d3c-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="c1d3c-122">ASP.NET Routing</span><span class="sxs-lookup"><span data-stu-id="c1d3c-122">ASP.NET Routing</span></span>](https://go.microsoft.com/fwlink/?LinkId=184660)
