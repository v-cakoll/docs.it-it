---
title: 'Procedura: aggiungere un endpoint ASP.NET AJAX senza usare la configurazione'
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 9aab53d6457aa7848fd4acea6317a30da352cc98
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579631"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>Procedura: aggiungere un endpoint ASP.NET AJAX senza usare la configurazione
Windows Communication Foundation (WCF) consente di creare un servizio che espone un endpoint abilitato per AJAX ASP.NET che può essere chiamato da JavaScript su un sito Web client. Per creare tale endpoint è possibile utilizzare un file di configurazione, come con tutti gli altri endpoint WCF, o un metodo che non richiede elementi di configurazione. In questo argomento viene illustrato il secondo approccio.  
  
 Per creare servizi con endpoint ASP.NET AJAX senza configurazione, i servizi devono essere ospitati da Internet Information Services (IIS). Per attivare un endpoint ASP.NET AJAX usando questo approccio, specificare <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> come parametro Factory nella direttiva [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) nel file con estensione svc. Questa factory personalizzata è il componente che configura automaticamente un endpoint ASP.NET AJAX, in modo che possa essere chiamato da JavaScript su un sito Web client.  
  
 Per un esempio funzionante, vedere il [servizio AJAX senza configurazione](../samples/ajax-service-without-configuration.md).  
  
 Per una descrizione di come configurare un endpoint ASP.NET AJAX usando gli elementi di configurazione, vedere [procedura: usare la configurazione per aggiungere un endpoint ASP.NET AJAX](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Per creare un servizio WFC di base  
  
1. Definire un contratto di servizio WCF di base con un'interfaccia contrassegnata con l' <xref:System.ServiceModel.ServiceContractAttribute> attributo. Contrassegnare ogni operazione con <xref:System.ServiceModel.OperationContractAttribute>. Assicurarsi di impostare la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
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
  
1. Creare un nuovo file denominato "file del servizio" con estensione svc nell'applicazione. Modificare questo file aggiungendo le informazioni della direttiva [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) appropriate per il servizio. Consente di specificare che deve <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> essere utilizzato nella direttiva [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) per configurare automaticamente un endpoint ASP.NET AJAX.  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. Generare il servizio e chiamarlo dal client. Internet Information Services (IIS) attiva il servizio quando viene chiamato. Per ulteriori informazioni sull'hosting in IIS, vedere [procedura: ospitare un servizio WCF in IIS](how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>Per chiamare il servizio  
  
1. L'endpoint è configurato in un indirizzo vuoto relativo al file con estensione svc, quindi il servizio è ora disponibile e può essere richiamato inviando richieste a Service. svc/ \<operation> -ad esempio, Service. svc/Add per l' `Add` operazione. È possibile utilizzarlo immettendo l'URL del servizio nella raccolta degli script del controllo Script Manager ASP.NET AJAX. Per un esempio, vedere [servizio AJAX senza configurazione](../samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Esempio  
  
 L'endpoint configurato automaticamente viene creato in un indirizzo vuoto relativo all'URL di base. Può essere aggiunto e utilizzato con questo approccio anche un file di configurazione. Se il file di configurazione contiene definizioni di endpoint, questi endpoint vengono aggiunti all'endpoint configurato automaticamente.  
  
 Ad esempio, service.svc utilizza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> e la directory del servizio contiene un file Web.config che definisce un endpoint per lo stesso servizio utilizzando <xref:System.ServiceModel.BasicHttpBinding> nell'indirizzo relativo "soap". In questo caso, il servizio contiene due endpoint: uno in service.svc, che risponde alle richieste ASP.NET AJAX, e un altro in service.svc/soap, che risponde alle richieste SOAP.  
  
 Se il file di configurazione definisce un endpoint in un indirizzo relativo vuoto e viene utilizzata la classe <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, viene generata un'eccezione e il servizio non viene avviato.  
  
 Non è possibile utilizzare la configurazione per modificare impostazioni sull'endpoint configurato automaticamente. Se è necessario modificare un'impostazione, quale la quota del lettore, non si deve utilizzare l'approccio senza configurazione rimuovendo <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> dal file con estensione svc e creando una voce di configurazione per l'endpoint.  
  
 Se il servizio richiede la modalità di compatibilità ASP.NET, se ad esempio utilizza la classe <xref:System.Web.HttpContext> o meccanismi di autorizzazione ASP.NET, è comunque necessario un file di configurazione per attivare questa modalità. L'elemento di configurazione richiesto è l' [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) elemento, che deve essere aggiunto come indicato di seguito.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 Per ulteriori informazioni, vedere l'argomento relativo ai [servizi WCF e a ASP.NET](wcf-services-and-aspnet.md) .  
  
 La classe <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> è una classe derivata di <xref:System.ServiceModel.Activation.ServiceHostFactory>. Per una spiegazione dettagliata del meccanismo factory dell'host del servizio, vedere l'argomento [Extending hosting using ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md) .  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di servizi WCF per ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md)
- [Procedura: eseguire la migrazione di servizi Web ASP.NET compatibili AJAX a WCF](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
