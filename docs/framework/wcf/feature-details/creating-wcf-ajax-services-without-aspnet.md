---
title: Creazione di servizi WCF AJAX senza ASP.NET
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: 77a850408c3d952dbd4f682ea704d3248ae17c3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490357"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>Creazione di servizi WCF AJAX senza ASP.NET
Servizi AJAX Windows Communication Foundation (WCF) sono accessibili da qualsiasi pagina Web compatibile con JavaScript, senza necessità di ASP.NET AJAX. In questo argomento viene descritto come creare un servizio WCF.  
  
 Per istruzioni sull'uso di WCF con ASP.NET AJAX, vedere [creazione di servizi WCF per ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).  
  
 Esistono tre parti per la creazione di un servizio AJAX WCF:  
  
-   Creazione di un endpoint AJAX a cui sia possibile accedere dal browser.  
  
-   Creazione di un contratto di servizio compatibile con AJAX.  
  
-   Accesso ai servizi WCF AJAX.  
  
## <a name="creating-an-ajax-endpoint"></a>Creazione di un endpoint AJAX  
 Il modo più semplice per abilitare il supporto AJAX in un servizio WCF consiste nell'utilizzare il <xref:System.ServiceModel.Activation.WebServiceHostFactory> nel file con estensione svc associato al servizio, come nell'esempio seguente.  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 In alternativa, è anche possibile usare la configurazione per aggiungere un endpoint AJAX. Usare <xref:System.ServiceModel.WebHttpBinding> sull'endpoint del servizio e configurare tale endpoint con <xref:System.ServiceModel.Description.WebHttpBehavior>, come illustrato nel frammento di codice seguente.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint   
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 Per un esempio funzionante, vedere il [servizio AJAX con JSON e XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>Creazione di un contratto di servizio compatibile con AJAX  
 Per impostazione predefinita, i contratti di servizio esposti su un endpoint AJAX restituiscono dati in formato XML. Inoltre, le operazioni del servizio sono accessibili, per impostazione predefinita, tramite richieste HTTP POST agli URL che includono l'indirizzo endpoint seguito dal nome dell'operazione, come illustrato nell'esempio seguente.  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 Questa operazione è accessibile tramite una richiesta POST HTTP a `http://serviceaddress/endpointaddress/GetCities` e restituire un messaggio XML.  
  
 È possibile usare il Modello di programmazione Web completo per personalizzare questi aspetti di base. Ad esempio, è possibile usare gli attributi <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> per controllare il verbo HTTP al quale risponde l'operazione o usare la proprietà `UriTemplate` di questi rispettivi attributi per specificare gli URI personalizzati. Per altre informazioni, vedere la [modello di programmazione HTTP Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) argomento.  
  
 Nei servizi AJAX viene spesso usato il formato dati JSON. Per creare un'operazione che restituisce JSON invece di XML, impostare la proprietà <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (o <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) su <xref:System.ServiceModel.Web.WebMessageFormat.Json>. Il [della serializzazione JSON autonoma](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) argomento viene illustrato come predefinito .NET dati e i tipi di contratto mapping dei tipi in JSON.  
  
 In genere, le richieste e le risposte JSON sono costituite da un solo elemento. Nell'operazione `GetCities` precedente, la richiesta assomiglia all'istruzione seguente.  
  
```  
"na"  
```  
  
 La risposta a questa richiesta è simile all'istruzione seguente.  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 Se l'operazione accetta un parametro aggiuntivo, lo stile della richiesta deve essere "incapsulato", per eseguire il wrapping di entrambi parametri in un solo oggetto JSON. Un esempio di questo stile di messaggio JSON è riportato nell'esempio seguente.  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 Il contratto seguente accetta questo messaggio.  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a>Accesso ai servizi AJAX.  
 Gli endpoint AJAX WCF accettano sempre richieste JSON e XML.  
  
 Le richieste HTTP POST con un tipo di contenuto di "application/json" vengono trattate come JSON e quelle con tipo di contenuto che indica XML (ad esempio, "text/xml") vengono trattati come XML.  
  
 Le richieste HTTP GET contengono tutti i parametri di richiesta presenti nell'URL stesso.  
  
 Spetta all'utente decidere come creare la richiesta HTTP per l'endpoint. Inoltre, l'utente ha il pieno controllo sulla costruzione del codice JSON che forma il corpo della richiesta. Per un esempio di creazione di una richiesta da JavaScript, vedere il [servizio AJAX con JSON e XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).
