---
title: Integrazione di System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 3b95b3117941ce7d019b87b00181b2cbac652f43
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48843851"
---
# <a name="systemwebrouting-integration"></a>Integrazione di System.Web.Routing
Quando si ospita un servizio Windows Communication Foundation (WCF) in Internet Information Service (IIS) si inserisce un file con estensione svc nella directory virtuale. Questo file con estensione svc specifica la factory di host del servizio da utilizzare e la classe che implementa il servizio. Quando si effettuano richieste al servizio è specificare il file con estensione svc nell'URI, ad esempio: `http://contoso.com/EmployeeServce.svc`. Per i programmatori che scrivono servizi REST, questo tipo di URI non è ottimale. Gli URI per i servizi REST indicano una risorsa specifica e in genere non presentano estensioni. Il <xref:System.Web.Routing> caratteristica di integrazione consente di ospitare un servizio WCF REST che risponde a URI sprovvisti di estensione. Per altre informazioni, vedere routing [Routing ASP.NET](https://go.microsoft.com/fwlink/?LinkId=184660).  
  
## <a name="using-systemwebrouting-integration"></a>Utilizzo dell'integrazione System.Web.Routing  
 Per utilizzare la funzionalità di integrazione <xref:System.Web.Routing>, viene utilizzata la classe <xref:System.ServiceModel.Activation.ServiceRoute> per creare una o più route e aggiungerle a <xref:System.Web.Routing.RouteTable> in un file Global.asax. Queste route specificano i relativi URI a cui risponde il servizio. Nell'esempio seguente viene illustrato come effettuare questa operazione.  
  
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
  
 Tutte le richieste vengono indirizzato con un URI relativo che inizia con Customers al servizio `Service`.  
  
 Nel file Web.config è necessario aggiungere il modulo `System.Web.Routing.UrlRoutingModule`, impostare l'attributo `runAllManagedModulesForAllRequests` su `true` e aggiungere il gestore `UrlRoutingHandler` all'elemento `<system.webServer>`, come indicato nell'esempio seguente.  
  
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
  
 Vengono caricati un modulo e il gestore necessario per il routing. Per altre informazioni, vedere [Routing](../../../../docs/framework/wcf/feature-details/routing.md). È inoltre necessario impostare l'attributo `aspNetCompatibilityEnabled` su `true` nell'elemento `<serviceHostingEnvironment>`, come indicato nel codice seguente.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 La classe che implementa il servizio deve abilitare i requisiti di compatibilità ASP.NET, come indicato nell'esempio seguente.  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Modello di programmazione HTTP Web di WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Il Routing di ASP.NET](https://go.microsoft.com/fwlink/?LinkId=184660)
