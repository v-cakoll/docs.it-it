---
title: Distribuzione in base all'elemento corpo
ms.date: 03/30/2017
ms.assetid: f64a3c04-62b4-47b2-91d9-747a3af1659f
ms.openlocfilehash: 754151f856dfe09b8fd12912ab06d1d8720be016
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183715"
---
# <a name="dispatch-by-body-element"></a>Distribuzione in base all'elemento corpo
Questo esempio dimostra come implementare un algoritmo alternativo per l'assegnazione di messaggi in arrivo alle operazioni.  
  
 Per impostazione predefinita, il dispatcher del modello di servizio seleziona il metodo di gestione appropriato per un messaggio in arrivo in base all'intestazione "Action" di WS-Addressing del messaggio o alle informazioni equivalenti nella richiesta HTTP SOAP.  
  
 Alcuni stack dei servizi Web SOAP 1.1 non seguono le linee guida WS-I Basic Profile 1.1 di non distribuire messaggi basati sull'URI di azione, ma piuttosto sul nome completo XML del primo elemento all'interno del corpo SOAP. In modo simile, il lato client di questi stack potrebbe inviare messaggi con un'intestazione HTTP SoapAction vuota o arbitraria, che è consentita dalle specifiche SOAP 1.1.  
  
 Per modificare la modalità di distribuzione dei messaggi ai metodi, l'esempio implementa l'interfaccia di estensibilità <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> su `DispatchByBodyElementOperationSelector`. Questa classe seleziona le operazioni in base al primo elemento del corpo del messaggio.  
  
 Il costruttore della classe si aspetta un dizionario popolato con coppie di `XmlQualifiedName` e stringhe, laddove i nomi completi indicano il nome del primo figlio del corpo SOAP e le stringhe indicano il nome dell'operazione corrispondente. `defaultOperationName` è il nome dell'operazione che riceve tutti i messaggi privi di corrispondenza con questo dizionario:  
  
```csharp
class DispatchByBodyElementOperationSelector : IDispatchOperationSelector  
{  
    Dictionary<XmlQualifiedName, string> dispatchDictionary;  
    string defaultOperationName;  
  
    public DispatchByBodyElementOperationSelector(Dictionary<XmlQualifiedName,string> dispatchDictionary, string defaultOperationName)  
    {  
        this.dispatchDictionary = dispatchDictionary;  
        this.defaultOperationName = defaultOperationName;  
    }  
}
```  
  
 Le implementazioni di <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> sono molto semplici da compilare in quanto vi è solo un metodo nell'interfaccia: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>. Il compito di questo metodo è ispezionare un messaggio in arrivo e restituire una stringa uguale al nome di un metodo nel contratto di servizio per l'endpoint corrente.  
  
 In questo esempio, il selettore dell'operazione acquisisce un <xref:System.Xml.XmlDictionaryReader> per il corpo del messaggio in arrivo usando <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>. Questo metodo posiziona già il reader sul primo figlio del corpo del messaggio in modo che sia sufficiente ottenere il nome dell'elemento corrente e l'URI dello spazio dei nomi e combinarli in un `XmlQualifiedName` che viene quindi usato per cercare l'operazione corrispondente nel dizionario usato dal selettore dell'operazione.  
  
```csharp
public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
{  
    XmlDictionaryReader bodyReader = message.GetReaderAtBodyContents();  
    XmlQualifiedName lookupQName = new  
       XmlQualifiedName(bodyReader.LocalName, bodyReader.NamespaceURI);  
    message = CreateMessageCopy(message,bodyReader);  
    if (dispatchDictionary.ContainsKey(lookupQName))  
    {  
         return dispatchDictionary[lookupQName];  
    }  
    else  
    {  
        return defaultOperationName;  
    }  
}  
```  
  
 L'accesso al corpo del messaggio tramite <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> o qualsiasi altro metodo che fornisce l'accesso al contenuto del corpo del messaggio determina il contrassegno del messaggio come "letto", che quindi non è valido per altre elaborazioni. Di conseguenza, il selettore dell'operazione crea una copia del messaggio in arrivo tramite il metodo illustrato nel codice seguente. Poiché la posizione del lettore non è stata modificata durante l'ispezione, è possibile farvi riferimento dal messaggio appena creato nel quale sono state copiate anche le proprietà del messaggio e le intestazioni del messaggio, operazione che si traduce in un clone esatto del messaggio originale:  
  
```csharp
private Message CreateMessageCopy(Message message,
                                     XmlDictionaryReader body)  
{  
    Message copy = Message.CreateMessage(message.Version,message.Headers.Action,body);  
    copy.Headers.CopyHeaderFrom(message,0);  
    copy.Properties.CopyProperties(message.Properties);  
    return copy;  
}  
```  
  
## <a name="adding-an-operation-selector-to-a-service"></a>Aggiunta di un selettore dell'operazione a un servizio  
 I selettori delle operazioni di invio del servizio sono estensioni del dispatcher di Windows Communication Foundation (WCF). Per la selezione dei metodi nel canale di callback dei contratti duplex, sono disponibili anche selettori dell'operazione client che funzionano in modo simile ai selettori dell'operazione di distribuzione descritti qui, ma che non sono trattati in modo esplicito in questo esempio.  
  
 Analogamente alla maggior parte delle estensioni del modello di servizi, i selettori dell'operazione di distribuzione vengono aggiunti al dispatcher usando i comportamenti. Un *comportamento* è un oggetto di configurazione, che aggiunge una o più estensioni al runtime di invio (o al runtime client) o ne modifica in altro modo le impostazioni.  
  
 Poiché i selettori dell'operazione hanno l'ambito del contratto, il comportamento appropriato da implementare qui è <xref:System.ServiceModel.Description.IContractBehavior>. Poiché l'interfaccia è implementata in una classe derivata <xref:System.Attribute> come illustrato nel codice seguente, il comportamento può essere aggiunto in modo dichiarativo a qualsiasi contratto di servizio. Ogni volta che viene aperto un <xref:System.ServiceModel.ServiceHost> e il runtime della distribuzione viene compilato, tutti i comportamenti trovati come attributi in contratti, operazioni e implementazioni del servizio o come elemento nella configurazione del servizio vengono aggiunti e successivamente richiesti per contribuire alle estensioni o modificare la configurazione predefinita.  
  
 Per brevità, nella porzione di codice seguente è illustrata solo l'implementazione del metodo <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, che esegue le modifiche di configurazione per il dispatcher in questo esempio. Gli altri metodi non sono illustrati perché ritornano al chiamante senza svolgere alcuna operazione.  
  
```csharp
[AttributeUsage(AttributeTargets.Class|AttributeTargets.Interface)]  
class DispatchByBodyElementBehaviorAttribute : Attribute, IContractBehavior  
{  
    // public void AddBindingParameters(...)
    // public void ApplyClientBehavior(...)  
    // public void Validate(...)  
```  
  
 Prima, l'implementazione <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> imposta sul dizionario di ricerca per il selettore dell'operazione eseguendo l'iterazione tra gli elementi <xref:System.ServiceModel.Description.OperationDescription> nella <xref:System.ServiceModel.Description.ContractDescription> dell'endpoint del servizio. Quindi, in ciascuna descrizione dell'operazione viene controllata la presenza del comportamento `DispatchBodyElementAttribute`, un'implementazione della classe <xref:System.ServiceModel.Description.IOperationBehavior> che è definita anch'essa in questo esempio. Pur essendo un comportamento, questa classe è passiva e non contribuisce attivamente ad alcuna modifica di configurazione nel runtime di distribuzione. Tutti i relativi metodi ritornano al chiamante senza intraprendere alcuna azione. Il comportamento dell'operazione esiste solo per consentire che i metadati necessari per il nuovo meccanismo di distribuzione, vale a dire il nome completo dell'elemento corpo nella cui occorrenza è selezionata un'operazione, possano essere associati alle rispettive operazioni.  
  
 Se tale comportamento viene trovato, una coppia di valori creata con il nome completo XML (proprietà `QName`) e il nome dell'operazione (proprietà `Name`) viene aggiunta al dizionario.  
  
 Dopo che il dizionario è stato popolato, viene costruito un nuovo `DispatchByBodyElementOperationSelector` con queste informazioni e impostato come selettore dell'operazione del runtime di distribuzione:  
  
```csharp
public void ApplyDispatchBehavior(ContractDescription contractDescription, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatchRuntime)  
{  
    Dictionary<XmlQualifiedName,string> dispatchDictionary =
                     new Dictionary<XmlQualifiedName,string>();  
    foreach( OperationDescription operationDescription in
                              contractDescription.Operations )  
    {  
        DispatchBodyElementAttribute dispatchBodyElement =
   operationDescription.Behaviors.Find<DispatchBodyElementAttribute>();  
        if ( dispatchBodyElement != null )  
        {  
             dispatchDictionary.Add(dispatchBodyElement.QName,
                              operationDescription.Name);  
        }  
    }  
    dispatchRuntime.OperationSelector =
            new DispatchByBodyElementOperationSelector(  
               dispatchDictionary,
               dispatchRuntime.UnhandledDispatchOperation.Name);  
    }  
}  
```  
  
## <a name="implementing-the-service"></a>Implementazione del servizio  
 Il comportamento implementato in questo esempio influisce direttamente sul modo in cui i messaggi dal collegamento vengono interpretati e distribuiti, che è una funzione del contratto di servizio. Di conseguenza, il comportamento deve essere dichiarato nel livello del contratto di servizio in qualsiasi implementazione del servizio che sceglie di usarlo.  
  
 Il servizio di `DispatchByBodyElementBehaviorAttribute` progetto di `IDispatchedByBody` esempio applica il comportamento del `OperationForBodyA()` `OperationForBodyB()` contratto `DispatchBodyElementAttribute` al contratto di servizio ed etichetta ognuna delle due operazioni e con un comportamento di operazione. Quando un host del servizio per un servizio che implementa questo contratto viene aperto, questi metadati vengono prelevati dal generatore del dispatcher come descritto in precedenza.  
  
 Poiché il selettore dell'operazione esegue la distribuzione solo in base all'elemento del corpo di messaggio e ignora "Action", è necessario indicare al runtime di non controllare l'intestazione "Action" nelle risposte restituite assegnando il carattere jolly "*" alla proprietà `ReplyAction` di <xref:System.ServiceModel.OperationContractAttribute>. Inoltre, è necessario disporre di un'operazione predefinita con la proprietà\*"Action" impostata sul carattere jolly " ". L'operazione predefinita riceve tutti i messaggi che non possono essere distribuiti e sono privi di `DispatchBodyElementAttribute`:  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
                            DispatchByBodyElementBehavior]  
public interface IDispatchedByBody  
{  
    [OperationContract(ReplyAction="*"),
     DispatchBodyElement("bodyA","http://tempuri.org")]  
    Message OperationForBodyA(Message msg);  
    [OperationContract(ReplyAction = "*"),
     DispatchBodyElement("bodyB", "http://tempuri.org")]  
    Message OperationForBodyB(Message msg);  
    [OperationContract(Action="*", ReplyAction="*")]  
    Message DefaultOperation(Message msg);  
}  
```  
  
 L'implementazione del servizio di esempio è semplice. Ogni metodo esegue il wrapping del messaggio ricevuto in un messaggio di risposta e lo restituisce al client.  
  
## <a name="running-and-building-the-sample"></a>Esecuzione e compilazione dell'esempio  
 Quando si esegue l'esempio, il contenuto del corpo delle risposte dell'operazione viene visualizzato nella finestra della console client simile all'output seguente formattato.  
  
 Il client invia tre messaggi al servizio il cui elemento del contenuto del corpo è denominato `bodyA`, `bodyB` e `bodyX`, rispettivamente. Come è possibile dedurre dalla descrizione precedente e dal contratto di servizio illustrato, il messaggio in arrivo con l'elemento `bodyA` viene distribuito al metodo `OperationForBodyA()`. Poiché non vi è una destinazione esplicita della distribuzione per il messaggio con l'elemento del corpo `bodyX`, il messaggio viene distribuito a `DefaultOperation()`. Ciascuna delle operazioni del servizio esegue il wrapping del corpo del messaggio ricevuto in un elemento specifico del metodo e lo restituisce, operazione volta a correlare chiaramente i messaggi di input e output per questo esempio:  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyA xmlns="http://tempuri.org">  
   <q:bodyA xmlns:q="http://tempuri.org">test</q:bodyA>  
</replyBodyA>  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyB xmlns="http://tempuri.org">  
  <q:bodyB xmlns:q="http://tempuri.org">test</q:bodyB>  
</replyBodyB>  
<?xml version="1.0" encoding="IBM437"?>  
<replyDefault xmlns="http://tempuri.org">  
   <q:bodyX xmlns:q="http://tempuri.org">test</q:bodyX>  
</replyDefault>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\AdvancedDispatchByBody`  
