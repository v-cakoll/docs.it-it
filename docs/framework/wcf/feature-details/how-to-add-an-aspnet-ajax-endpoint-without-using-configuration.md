---
title: 'Procedura: Aggiungere un endpoint ASP.NET AJAX senza usare la configurazione'
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 078580b96ab911f65790e58338951532cd7ad704
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344689"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>Procedura: Aggiungere un endpoint ASP.NET AJAX senza usare la configurazione
Windows Communication Foundation (WCF) consente di creare un servizio che espone un endpoint ASP.NET compatibile con AJAX che può essere chiamato da JavaScript su un sito Web client. Per creare tale endpoint è possibile utilizzare un file di configurazione, come con tutti gli altri endpoint WCF, o un metodo che non richiede elementi di configurazione. In questo argomento viene illustrato il secondo approccio.  
  
 Per creare servizi con endpoint ASP.NET AJAX senza configurazione, i servizi devono essere ospitati da Internet Information Services (IIS). Per attivare un endpoint ASP.NET AJAX utilizzando questo approccio, specificare il <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> come parametro Factory nella [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva nel file con estensione svc. Questa factory personalizzata è il componente che configura automaticamente un endpoint ASP.NET AJAX, in modo che possa essere chiamato da JavaScript su un sito Web client.  
  
 Per un esempio funzionante, vedere la [AJAX senza configurazione del servizio](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
 Per una descrizione di come configurare un endpoint ASP.NET AJAX utilizzando elementi di configurazione, vedere [come: Utilizzare la configurazione per aggiungere un Endpoint ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Per creare un servizio WFC di base  
  
1. Definire un contratto di servizio WCF basic con un'interfaccia contrassegnata con il <xref:System.ServiceModel.ServiceContractAttribute> attributo. Contrassegnare ogni operazione con <xref:System.ServiceModel.OperationContractAttribute>. Assicurarsi di impostare la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. Implementare il contratto di servizio `ICalculator` con `CalculatorService`.  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. Definire uno spazio dei nomi per le implementazioni `ICalculator` e `CalculatorService` eseguendo il wrapping di queste ultime in un blocco dello spazio dei nomi.  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>Per ospitare il servizio in Internet Information Services senza configurazione  
  
1. Creare un nuovo file denominato "file del servizio" con estensione svc nell'applicazione. Modificare questo file aggiungendo le appropriate [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) informazioni della direttiva per il servizio. Specificare che il <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> deve essere usata nel [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) direttiva per configurare automaticamente un endpoint ASP.NET AJAX.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. Generare il servizio e chiamarlo dal client. Internet Information Services (IIS) attiva il servizio quando viene chiamato. Per altre informazioni sull'hosting in IIS, vedere [come: Ospitare un servizio WCF in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>Per chiamare il servizio  
  
1. L'endpoint viene configurato in un indirizzo vuoto relativo al file con estensione svc, in modo che il servizio è ora disponibile e può essere richiamato inviando richieste a Service. svc /\<operazione >, ad esempio service.svc/Add per il `Add` operazione. È possibile utilizzarlo immettendo l'URL del servizio nella raccolta degli script del controllo Script Manager ASP.NET AJAX. Per un esempio, vedere la [AJAX senza configurazione del servizio](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Esempio  
  
 L'endpoint configurato automaticamente viene creato in un indirizzo vuoto relativo all'URL di base. Può essere aggiunto e utilizzato con questo approccio anche un file di configurazione. Se il file di configurazione contiene definizioni di endpoint, questi endpoint vengono aggiunti all'endpoint configurato automaticamente.  
  
 Ad esempio, service.svc utilizza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> e la directory del servizio contiene un file Web.config che definisce un endpoint per lo stesso servizio utilizzando <xref:System.ServiceModel.BasicHttpBinding> nell'indirizzo relativo "soap". In questo caso, il servizio contiene due endpoint: uno in service.svc, che risponde alle richieste ASP.NET AJAX, e un altro in service.svc/soap, che risponde alle richieste SOAP.  
  
 Se il file di configurazione definisce un endpoint in un indirizzo relativo vuoto e viene utilizzata la classe <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, viene generata un'eccezione e il servizio non viene avviato.  
  
 Non è possibile utilizzare la configurazione per modificare impostazioni sull'endpoint configurato automaticamente. Se è necessario modificare un'impostazione, quale la quota del lettore, non si deve utilizzare l'approccio senza configurazione rimuovendo <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> dal file con estensione svc e creando una voce di configurazione per l'endpoint.  
  
 Se il servizio richiede la modalità di compatibilità ASP.NET, se ad esempio utilizza la classe <xref:System.Web.HttpContext> o meccanismi di autorizzazione ASP.NET, è comunque necessario un file di configurazione per attivare questa modalità. L'elemento di configurazione richiesto è il [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) elemento che deve essere aggiunto come indicato di seguito.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 Per altre informazioni, vedere la [servizi WCF e ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) argomento.  
  
 La classe <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> è una classe derivata di <xref:System.ServiceModel.Activation.ServiceHostFactory>. Per una spiegazione dettagliata del meccanismo factory di host del servizio, vedere la [estensione di Hosting tramite ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) argomento.  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di servizi WCF per ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Procedura: Eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
