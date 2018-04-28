---
title: Integrazione di System.Web.Routing
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c3a5b9965f63a9fc501025493b3a323013ea2a4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="9b91e-102">Integrazione di System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="9b91e-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="9b91e-103">Quando si ospita un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in Internet Information Service (IIS), si inserisce un file con estensione svc nella directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="9b91e-103">When hosting a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="9b91e-104">Questo file con estensione svc specifica la factory di host del servizio da utilizzare e la classe che implementa il servizio.</span><span class="sxs-lookup"><span data-stu-id="9b91e-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="9b91e-105">Quando si effettua richieste al servizio specificare il file con estensione svc nell'URI, ad esempio: http://contoso.com/EmployeeServce.svc.</span><span class="sxs-lookup"><span data-stu-id="9b91e-105">When making requests to the service you specify the .svc file in the URI, for example: http://contoso.com/EmployeeServce.svc.</span></span> <span data-ttu-id="9b91e-106">Per i programmatori che scrivono servizi REST, questo tipo di URI non è ottimale.</span><span class="sxs-lookup"><span data-stu-id="9b91e-106">For programmers writing REST services this type of URI is not optimal.</span></span> <span data-ttu-id="9b91e-107">Gli URI per i servizi REST indicano una risorsa specifica e in genere non presentano estensioni.</span><span class="sxs-lookup"><span data-stu-id="9b91e-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="9b91e-108">La funzionalità di integrazione <xref:System.Web.Routing> consente di ospitare un servizio REST di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che risponde a URI sprovvisti di estensione.</span><span class="sxs-lookup"><span data-stu-id="9b91e-108">The <xref:System.Web.Routing> integration feature allows you to host a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST service that responds to URIs without an extension.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9b91e-109"> vedere routing [Routing ASP.NET](http://go.microsoft.com/fwlink/?LinkId=184660) e il [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="9b91e-109"> routing see [ASP.NET Routing](http://go.microsoft.com/fwlink/?LinkId=184660) and the [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) sample.</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="9b91e-110">Utilizzo dell'integrazione System.Web.Routing</span><span class="sxs-lookup"><span data-stu-id="9b91e-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="9b91e-111">Per utilizzare la funzionalità di integrazione <xref:System.Web.Routing>, viene utilizzata la classe <xref:System.ServiceModel.Activation.ServiceRoute> per creare una o più route e aggiungerle a <xref:System.Web.Routing.RouteTable> in un file Global.asax.</span><span class="sxs-lookup"><span data-stu-id="9b91e-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="9b91e-112">Queste route specificano i relativi URI a cui risponde il servizio.</span><span class="sxs-lookup"><span data-stu-id="9b91e-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="9b91e-113">Nell'esempio seguente viene illustrato come effettuare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="9b91e-113">The following example shows how to do this.</span></span>  
  
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
  
 <span data-ttu-id="9b91e-114">Tutte le richieste vengono indirizzato con un URI relativo che inizia con Customers al servizio `Service`.</span><span class="sxs-lookup"><span data-stu-id="9b91e-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="9b91e-115">Nel file Web.config è necessario aggiungere il modulo `System.Web.Routing.UrlRoutingModule`, impostare l'attributo `runAllManagedModulesForAllRequests` su `true` e aggiungere il gestore `UrlRoutingHandler` all'elemento `<system.webServer>`, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9b91e-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="9b91e-116">Vengono caricati un modulo e il gestore necessario per il routing.</span><span class="sxs-lookup"><span data-stu-id="9b91e-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="9b91e-117">Per altre informazioni, vedere [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span><span class="sxs-lookup"><span data-stu-id="9b91e-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="9b91e-118">È inoltre necessario impostare l'attributo `aspNetCompatibilityEnabled` su `true` nell'elemento `<serviceHostingEnvironment>`, come indicato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9b91e-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="9b91e-119">La classe che implementa il servizio deve abilitare i requisiti di compatibilità ASP.NET, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9b91e-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b91e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b91e-120">See Also</span></span>  
 [<span data-ttu-id="9b91e-121">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="9b91e-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="9b91e-122">Routing di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9b91e-122">ASP.NET Routing</span></span>](http://go.microsoft.com/fwlink/?LinkId=184660)
