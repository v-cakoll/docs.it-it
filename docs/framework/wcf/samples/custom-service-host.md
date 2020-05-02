---
title: Host di servizi personalizzati
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 70d527599c310cba694624839f14a313f6000337
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728437"
---
# <a name="custom-service-host"></a>Host di servizi personalizzati
Questo esempio dimostra come usare un derivato personalizzato della classe <xref:System.ServiceModel.ServiceHost> per modificare il comportamento in fase di esecuzione di un servizio. Questo approccio fornisce un'alternativa riusabile alla configurazione tradizionale di un gran numero di servizi. In questo esempio viene inoltre illustrato come impiegare la classe <xref:System.ServiceModel.Activation.ServiceHostFactory> per usare un ServiceHost personalizzato nell'ambiente di hosting Internet Information Services (IIS) o nel servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a>Informazioni sullo scenario
 Per impedire la divulgazione accidentale di metadati del servizio potenzialmente sensibili, la configurazione predefinita per i servizi di Windows Communication Foundation (WCF) Disabilita la pubblicazione dei metadati. Questo comportamento è sicuro per impostazione predefinita, ma significa anche che non è possibile usare uno strumento di importazione di metadati (ad esempio Svcutil. exe) per generare il codice client necessario per chiamare il servizio, a meno che il comportamento di pubblicazione dei metadati del servizio non sia abilitato in modo esplicito nella configurazione.  
  
 L'abilitazione della pubblicazione dei metadati per un gran numero di servizi comporta l'aggiunta degli stessi elementi di configurazione a ciascun singolo servizio, che produce una quantità elevata di informazioni di configurazione sostanzialmente uguali. Come alternativa alla configurazione di ogni singolo servizio, è possibile scrivere il codice imperativo che consente la pubblicazione dei metadati una volta e riusare quindi tale codice su vari servizi diversi. Ciò viene ottenuto creando una nuova classe che viene derivata da <xref:System.ServiceModel.ServiceHost> ed esegue l'override del metodo `ApplyConfiguration`() per aggiungere imperativamente il comportamento di pubblicazione di metadati.  
  
> [!IMPORTANT]
> Per maggior chiarezza, questo esempio illustra come creare un endpoint non protetto per la configurazione di metadati. Tali endpoint sono potenzialmente disponibili per gli utenti anonimi non autenticati ed è necessario prestare attenzione prima di distribuire tali endpoint per assicurarsi che la divulgazione pubblica dei metadati di un servizio sia appropriata.  
  
## <a name="implementing-a-custom-servicehost"></a>Implementazione di un ServiceHost personalizzato
 La classe <xref:System.ServiceModel.ServiceHost> espone diversi metodi virtuali utili che possono essere sottoposti a override dagli eredi per modificare il comportamento di un servizio in fase di esecuzione. Ad esempio, il metodo `ApplyConfiguration`() legge informazioni di configurazione del servizio dall'archivio di configurazione e modifica di conseguenza <xref:System.ServiceModel.Description.ServiceDescription> dell'host. L'implementazione predefinita legge la configurazione dal file di configurazione dell'applicazione. Le implementazioni personalizzate possono eseguire l'override di `ApplyConfiguration`() per alterare ulteriormente la <xref:System.ServiceModel.Description.ServiceDescription> usando codice imperativo o anche sostituire completamente l'archivio di configurazione predefinito. Ad esempio, per leggere la configurazione dell'endpoint di un servizio da un database invece che dal file di configurazione dell'applicazione.  
  
 In questo esempio si vuole creare un ServiceHost personalizzato che aggiunge l'oggetto ServiceMetadataBehavior (che consente la pubblicazione dei metadati) anche se questo comportamento non viene aggiunto in modo esplicito nel file di configurazione del servizio. A tale scopo, creare una nuova classe che erediti da <xref:System.ServiceModel.ServiceHost> ed esegua l'override `ApplyConfiguration`di ().  
  
```csharp
class SelfDescribingServiceHost : ServiceHost  
{  
    public SelfDescribingServiceHost(Type serviceType, params Uri[] baseAddresses)  
        : base(serviceType, baseAddresses) { }  
  
    //Overriding ApplyConfiguration() allows us to
    //alter the ServiceDescription prior to opening  
    //the service host.
    protected override void ApplyConfiguration()  
    {  
        //First, we call base.ApplyConfiguration()  
        //to read any configuration that was provided for  
        //the service we're hosting. After this call,  
        //this.Description describes the service  
        //as it was configured.  
        base.ApplyConfiguration();
  
        //(rest of implementation elided for clarity)  
    }  
}  
```  
  
 Poiché non si vuole ignorare alcuna configurazione fornita nel file di configurazione dell'applicazione, la prima cosa che l'override di () è chiamare `ApplyConfiguration`l'implementazione di base. Dopo che questo metodo è stato completato, è possibile aggiungere in modo imperativo <xref:System.ServiceModel.Description.ServiceMetadataBehavior> alla descrizione usando il codice imperativo seguente.  
  
```csharp
ServiceMetadataBehavior mexBehavior = this.Description.Behaviors.Find<ServiceMetadataBehavior>();  
if (mexBehavior == null)  
{  
    mexBehavior = new ServiceMetadataBehavior();  
    this.Description.Behaviors.Add(mexBehavior);  
}  
else  
{  
    //Metadata behavior has already been configured,
    //so we do not have any work to do.  
    return;  
}  
```  
  
 L'ultima operazione dell'override di `ApplyConfiguration`() è aggiungere l'endpoint di metadati predefinito. Per convenzione, viene creato un endpoint di metadati per ogni URI nella raccolta BaseAddresses dell'host del servizio.  
  
```csharp
//Add a metadata endpoint at each base address  
//using the "/mex" addressing convention  
foreach (Uri baseAddress in this.BaseAddresses)  
{  
    if (baseAddress.Scheme == Uri.UriSchemeHttp)  
    {  
        mexBehavior.HttpGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeHttps)  
    {  
        mexBehavior.HttpsGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpsBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetPipe)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexNamedPipeBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetTcp)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexTcpBinding(),  
                                "mex");  
    }  
}  
```  
  
## <a name="using-a-custom-servicehost-in-self-host"></a>Uso di un ServiceHost personalizzato in host indipendente  
 Ora che è stata completata l'implementazione personalizzata di ServiceHost, è possibile usarlo per aggiungere il comportamento di pubblicazione dei metadati a qualsiasi servizio ospitando tale servizio all'interno di un'istanza di `SelfDescribingServiceHost`. Nell'esempio di codice seguente viene illustrato come usarlo nello scenario di host indipendente.  
  
```csharp
SelfDescribingServiceHost host =
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 L'host personalizzato legge ancora la configurazione dell'endpoint del servizio dal file di configurazione dell'applicazione, come se fosse stata usata la <xref:System.ServiceModel.ServiceHost> classe predefinita per ospitare il servizio. Tuttavia, poiché è stata aggiunta la logica per abilitare la pubblicazione dei metadati all'interno dell'host personalizzato, non è più necessario abilitare in modo esplicito il comportamento di pubblicazione dei metadati nella configurazione. L'approccio offre un vantaggio evidente quando si compila un'applicazione che contiene diversi servizi e si desidera abilitare la pubblicazione dei metadati su ognuno di essi senza riscrivere ripetutamente gli stessi elementi di configurazione.  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a>Utilizzo di un ServiceHost personalizzato in IIS e WAS  
 L'uso di un host del servizio personalizzato in scenari di host indipendente è semplice in quanto spetta fondamentalmente al codice dell'applicazione la responsabilità di creare e aprire l'istanza dell'host del servizio. Nell'ambiente di hosting di IIS o WAS, tuttavia, l'infrastruttura WCF crea dinamicamente un'istanza dell'host del servizio in risposta ai messaggi in arrivo. Gli host del servizio personalizzati possono essere usati anche in questo ambiente di hosting, ma richiedono del codice aggiuntivo nel modulo di un ServiceHostFactory. Nel codice seguente è illustrato un derivato di <xref:System.ServiceModel.Activation.ServiceHostFactory> che restituisce istanze del `SelfDescribingServiceHost` personalizzato.  
  
```csharp
public class SelfDescribingServiceHostFactory : ServiceHostFactory  
{  
    protected override ServiceHost CreateServiceHost(Type serviceType,
     Uri[] baseAddresses)  
    {  
        //All the custom factory does is return a new instance  
        //of our custom host class. The bulk of the custom logic should  
        //live in the custom host (as opposed to the factory)
        //for maximum  
        //reuse value outside of the IIS/WAS hosting environment.  
        return new SelfDescribingServiceHost(serviceType,
                                             baseAddresses);  
    }  
}  
```  
  
 Come si può notare, l'implementazione di un ServiceHostFactory personalizzato è semplice. Tutta la logica personalizzata risiede all'interno dell'implementazione ServiceHost; la factory restituisce un'istanza della classe derivata.  
  
 Per usare una factory personalizzata con un'implementazione del servizio, è necessario aggiungere alcuni metadati aggiuntivi al file con estensione svc del servizio.  
  
```xml
<% @ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"
               language=c# Debug="true" %>
```
  
 Qui è stato aggiunto un attributo `Factory` aggiuntivo alla `@ServiceHost` direttiva e il nome del tipo CLR della factory personalizzata è stato passato come valore dell'attributo. Quando IIS o WAS riceve un messaggio per questo servizio, l'infrastruttura host WCF crea innanzitutto un'istanza di ServiceHostFactory e quindi crea un'istanza dell'host del servizio stesso chiamando `ServiceHostFactory.CreateServiceHost()`.  
  
## <a name="running-the-sample"></a>Esecuzione dell'esempio  
 Sebbene in questo esempio venga fornita un'implementazione di client e servizio completamente funzionante, il punto dell'esempio è illustrare come modificare il comportamento in fase di esecuzione di un servizio per mezzo di un host personalizzato. attenersi alla procedura seguente:  
  
### <a name="observe-the-effect-of-the-custom-host"></a>Osservare l'effetto dell'host personalizzato
  
1. Aprire il file Web. config del servizio e osservare che non è presente alcuna configurazione che Abilita in modo esplicito i metadati per il servizio.  
  
2. Aprire il file con estensione svc del servizio e osservare che @ServiceHost la direttiva contiene un attributo Factory che specifica il nome di un ServiceHostFactory personalizzato.  
  
### <a name="set-up-build-and-run-the-sample"></a>Configurare, compilare ed eseguire l'esempio
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).

3. Una volta compilata la soluzione, eseguire Setup. bat per configurare l'applicazione ServiceModelSamples in IIS 7,0. La directory ServiceModelSamples dovrebbe ora essere visualizzata come applicazione IIS 7,0.

4. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).

5. Per rimuovere l'applicazione IIS 7,0, eseguire *Cleanup. bat*.

## <a name="see-also"></a>Vedere anche

- [Procedura: ospitare un servizio WCF in IIS](../feature-details/how-to-host-a-wcf-service-in-iis.md)
