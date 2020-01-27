---
title: 'Modelli di progettazione: pubblicazione-sottoscrizione basata su elenchi'
ms.date: 03/30/2017
ms.assetid: f4257abc-12df-4736-a03b-0731becf0fd4
ms.openlocfilehash: 3a62b09a29ec0b7e241bf2fdc09df6eaba5420c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728836"
---
# <a name="design-patterns-list-based-publish-subscribe"></a>Modelli di progettazione: pubblicazione-sottoscrizione basata su elenchi
Questo esempio illustra il modello di pubblicazione-sottoscrizione basato su elenchi implementato come programma Windows Communication Foundation (WCF).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il modello di progettazione di pubblicazione-sottoscrizione basato su elenchi viene descritto nella pubblicazione di Microsoft Patterns & Practices, [modelli di integrazione](https://docs.microsoft.com/previous-versions/msp-n-p/ff647309(v=pandp.10)). Il modello di pubblicazione-sottoscrizione passa le informazioni a una raccolta di destinatari che hanno sottoscritto un argomento di informazioni. La pubblicazione-sottoscrizione basata su elenchi gestisce un elenco di sottoscrittori. Quando esistono informazioni da condividere, una copia viene inviata a ogni sottoscrittore presente nell'elenco. In questo esempio viene illustrato un modello di pubblicazione-sottoscrizione basato su elenchi dinamici, in cui i client possono effettuare la sottoscrizione o annullare la sottoscrizione ogni volta che lo desiderano.  
  
 L'esempio di pubblicazione-sottoscrizione basata su elenchi consiste in un client, un servizio e un programma dell'origine dati. È consentita l'esecuzione di più client e più programmi delle origini dati. I client sottoscrivono il servizio, ricevono le notifiche e annullano la sottoscrizione. I programmi delle origini dati inviano informazioni al servizio da condividere con tutti i sottoscrittori correnti.  
  
 In questo esempio il client e l'origine dati sono programmi della console (file con estensione exe) e il servizio è una libreria (con estensione dll) ospitata in Internet Information Services (IIS). Le attività del client e dell'origine dati sono visibili sul desktop.  
  
 Il servizio usa la comunicazione duplex. Il contratto di servizio `ISampleContract` è accoppiato a un contratto di callback `ISampleClientCallback`. Il servizio implementa operazioni del servizio di sottoscrizione e annullamento della sottoscrizione che consentono ai client di essere aggiunti o rimossi dall'elenco dei sottoscrittori. Il servizio implementa inoltre l'operazione del servizio `PublishPriceChange` chiamata dal programma dell'origine dati per fornire nuove informazioni al servizio. Il programma client implementa l'operazione del servizio `PriceChange` chiamata dal servizio per notificare a tutti i sottoscrittori la modifica di un prezzo.  
  
```csharp  
// Create a service contract and define the service operations.  
// NOTE: The service operations must be declared explicitly.  
[ServiceContract(SessionMode=SessionMode.Required,  
      CallbackContract=typeof(ISampleClientContract))]  
public interface ISampleContract  
{  
    [OperationContract(IsOneWay = false, IsInitiating=true)]  
    void Subscribe();  
    [OperationContract(IsOneWay = false, IsTerminating=true)]  
    void Unsubscribe();  
    [OperationContract(IsOneWay = true)]  
    void PublishPriceChange(string item, double price,   
                                     double change);  
}  
  
public interface ISampleClientContract  
{  
    [OperationContract(IsOneWay = true)]  
    void PriceChange(string item, double price, double change);  
}  
```  
  
 Il servizio usa un evento .NET Framework come meccanismo per informare tutti i sottoscrittori dell'esistenza di nuove informazioni. L'aggiunta di un client al servizio tramite una chiamata a Subscribe determina la disponibilità di un gestore eventi. La rimozione di un client dal servizio determina l'annullamento della sottoscrizione del relativo gestore eventi. Quando un'origine dati chiama il servizio per segnalare la modifica di un prezzo, il servizio genera l'evento, che a sua volta chiama ogni istanza del servizio, una per ogni client che ha effettuato la sottoscrizione, e causa l'esecuzione dei relativi gestori eventi. Ogni gestore eventi passa le informazioni al client corrispondente tramite la relativa funzione di callback.  
  
```csharp
public class PriceChangeEventArgs : EventArgs  
    {  
        public string Item;  
        public double Price;  
        public double Change;  
    }  
  
    // The Service implementation implements your service contract.  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    public class SampleService : ISampleContract  
    {  
        public static event PriceChangeEventHandler PriceChangeEvent;  
        public delegate void PriceChangeEventHandler(object sender, PriceChangeEventArgs e);  
  
        ISampleClientContract callback = null;  
  
        PriceChangeEventHandler priceChangeHandler = null;  
  
        //Clients call this service operation to subscribe.  
        //A price change event handler is registered for this client instance.  
  
        public void Subscribe()  
        {  
            callback = OperationContext.Current.GetCallbackChannel<ISampleClientContract>();  
            priceChangeHandler = new PriceChangeEventHandler(PriceChangeHandler);  
            PriceChangeEvent += priceChangeHandler;  
        }  
  
        //Clients call this service operation to unsubscribe.  
        //The previous price change event handler is unregistered.  
  
        public void Unsubscribe()  
        {  
            PriceChangeEvent -= priceChangeHandler;  
        }  
  
        //Information source clients call this service operation to report a price change.  
        //A price change event is raised. The price change event handlers for each subscriber will execute.  
  
        public void PublishPriceChange(string item, double price, double change)  
        {  
            PriceChangeEventArgs e = new PriceChangeEventArgs();  
            e.Item = item;  
            e.Price = price;  
            e.Change = change;  
            PriceChangeEvent(this, e);  
        }  
  
        //This event handler runs when a PriceChange event is raised.  
        //The client's PriceChange service operation is invoked to provide notification about the price change.  
  
        public void PriceChangeHandler(object sender, PriceChangeEventArgs e)  
        {  
            callback.PriceChange(e.Item, e.Price, e.Change);  
        }  
  
    }  
```  
  
 Eseguire l'esempio avviando più client. I client sottoscrivono il servizio. Eseguire quindi il programma dell'origine dati che invia informazioni al servizio. Il servizio passa le informazioni a tutti i sottoscrittori. In ogni console client sono visibili le attività, a conferma dell'avvenuta ricezione delle informazioni. Premere INVIO nella finestra del client per arrestare il client.  
  
### <a name="to-set-up-and-build-the-sample"></a>Per impostare e compilare l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-machine"></a>Per eseguire l'esempio sullo stesso computer  
  
1. Verificare che sia possibile accedere al servizio utilizzando un browser immettendo l'indirizzo seguente: `http://localhost/servicemodelsamples/service.svc`. In risposta, viene visualizzata un pagina di conferma.  
  
2. Eseguire client. exe da \client\bin\\\, dalla cartella specifica del linguaggio. L'attività del client viene visualizzata nella finestra della console client. Avviare più client.  
  
3. Eseguire DataSource. exe da \datasource\bin\\, dalla cartella specifica del linguaggio. L'attività dell'origine dati viene visualizzata nella finestra della console. Dopo l'invio delle informazioni al servizio da parte dell'origine dati, è necessario che tali informazioni vengano inviate a ogni client.  
  
4. Se il client, l'origine dati e i programmi di servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-machines"></a>Per eseguire l'esempio tra più computer  
  
1. Configurare il computer del servizio:  
  
    1. Sul computer del servizio, creare una directory virtuale denominata ServiceModelSamples. Il file batch Setupvroot. bat dalla [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) può essere utilizzato per creare la directory del disco e la directory virtuale.  
  
    2. Copiare i file del programma del servizio da %SystemDrive%\Inetpub\wwwroot\servicemodelsamples alla directory virtuale di ServiceModelSamples sul computer del servizio. Verificare di includere i file nella directory \bin.  
  
    3. Verificare che sia possibile accedere al servizio dal computer client usando un browser.  
  
2. Configurare i computer client:  
  
    1. Copiare i file del programma client dalla cartella \client\bin\, nella cartella specifica del linguaggio, all'interno dei computer client.  
  
    2. In ogni file di configurazione del client modificare il valore dell'indirizzo della definizione dell'endpoint affinché corrisponda al nuovo indirizzo del servizio. Nell'indirizzo sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo.  
  
3. Configurare il computer dell'origine dati:  
  
    1. Copiare i file del programma dell'origine dati dalla cartella \datasource\bin\, nella cartella specifica del linguaggio, all'interno del computer dell'origine dati.  
  
    2. Nel file di configurazione dell'origine dati modificare il valore dell'indirizzo della definizione dell'endpoint affinché corrisponda al nuovo indirizzo del servizio. Nell'indirizzo sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo.  
  
4. Nei computer client avviare Client.exe da un prompt dei comandi.  
  
5. Nel computer dell'origine dati avviare Datasource.exe da un prompt dei comandi.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DesignPatterns/ListBasedPublishSubscribe`  
