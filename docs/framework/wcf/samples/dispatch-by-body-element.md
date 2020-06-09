---
title: Distribuzione in base all'elemento corpo
ms.date: 03/30/2017
ms.assetid: f64a3c04-62b4-47b2-91d9-747a3af1659f
ms.openlocfilehash: 19913cdaa47d766f62a313e216a653ac69633a99
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594699"
---
# <a name="dispatch-by-body-element"></a><span data-ttu-id="d66f8-102">Distribuzione in base all'elemento corpo</span><span class="sxs-lookup"><span data-stu-id="d66f8-102">Dispatch by Body Element</span></span>
<span data-ttu-id="d66f8-103">Questo esempio dimostra come implementare un algoritmo alternativo per l'assegnazione di messaggi in arrivo alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="d66f8-103">This sample demonstrates how to implement an alternate algorithm for assigning incoming messages to operations.</span></span>  
  
 <span data-ttu-id="d66f8-104">Per impostazione predefinita, il dispatcher del modello di servizio seleziona il metodo di gestione appropriato per un messaggio in arrivo in base all'intestazione "Action" di WS-Addressing del messaggio o alle informazioni equivalenti nella richiesta HTTP SOAP.</span><span class="sxs-lookup"><span data-stu-id="d66f8-104">By default, the service model dispatcher selects the appropriate handling method for an incoming message based on the message's WS-Addressing "Action" header or the equivalent information in the HTTP SOAP request.</span></span>  
  
 <span data-ttu-id="d66f8-105">Alcuni stack dei servizi Web SOAP 1.1 non seguono le linee guida WS-I Basic Profile 1.1 di non distribuire messaggi basati sull'URI di azione, ma piuttosto sul nome completo XML del primo elemento all'interno del corpo SOAP.</span><span class="sxs-lookup"><span data-stu-id="d66f8-105">Some SOAP 1.1 Web services stacks that do not follow the WS-I Basic Profile 1.1 guidelines do not dispatch messages based on the Action URI, but rather based on the XML qualified name of the first element inside the SOAP body.</span></span> <span data-ttu-id="d66f8-106">In modo simile, il lato client di questi stack potrebbe inviare messaggi con un'intestazione HTTP SoapAction vuota o arbitraria, che è consentita dalle specifiche SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="d66f8-106">Likewise, the client side of these stacks might send messages with an empty or arbitrary HTTP SoapAction header, which was permitted by the SOAP 1.1 specification.</span></span>  
  
 <span data-ttu-id="d66f8-107">Per modificare la modalità di distribuzione dei messaggi ai metodi, l'esempio implementa l'interfaccia di estensibilità <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> su `DispatchByBodyElementOperationSelector`.</span><span class="sxs-lookup"><span data-stu-id="d66f8-107">To change the way messages are dispatched to methods, the sample implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> extensibility interface on the `DispatchByBodyElementOperationSelector`.</span></span> <span data-ttu-id="d66f8-108">Questa classe seleziona le operazioni in base al primo elemento del corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d66f8-108">This class selects operations based on the first element of the message body.</span></span>  
  
 <span data-ttu-id="d66f8-109">Il costruttore della classe si aspetta un dizionario popolato con coppie di `XmlQualifiedName` e stringhe, laddove i nomi completi indicano il nome del primo figlio del corpo SOAP e le stringhe indicano il nome dell'operazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d66f8-109">The class constructor expects a dictionary populated with pairs of `XmlQualifiedName` and strings, whereby the qualified names indicate the name of the first child of the SOAP body and the strings indicate the matching operation name.</span></span> <span data-ttu-id="d66f8-110">`defaultOperationName` è il nome dell'operazione che riceve tutti i messaggi privi di corrispondenza con questo dizionario:</span><span class="sxs-lookup"><span data-stu-id="d66f8-110">The `defaultOperationName` is the name of the operation that receives all messages that cannot be matched against this dictionary:</span></span>  
  
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
  
 <span data-ttu-id="d66f8-111">Le implementazioni di <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> sono molto semplici da compilare in quanto vi è solo un metodo nell'interfaccia: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.</span><span class="sxs-lookup"><span data-stu-id="d66f8-111"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementations are very straightforward to build as there is only one method on the interface: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.</span></span> <span data-ttu-id="d66f8-112">Il compito di questo metodo è ispezionare un messaggio in arrivo e restituire una stringa uguale al nome di un metodo nel contratto di servizio per l'endpoint corrente.</span><span class="sxs-lookup"><span data-stu-id="d66f8-112">The job of this method is to inspect an incoming message and to return a string that equals the name of a method on the service contract for the current endpoint.</span></span>  
  
 <span data-ttu-id="d66f8-113">In questo esempio, il selettore dell'operazione acquisisce un <xref:System.Xml.XmlDictionaryReader> per il corpo del messaggio in arrivo usando <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>.</span><span class="sxs-lookup"><span data-stu-id="d66f8-113">In this sample, the operation selector acquires an <xref:System.Xml.XmlDictionaryReader> for the incoming message's body using <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>.</span></span> <span data-ttu-id="d66f8-114">Questo metodo posiziona già il reader sul primo figlio del corpo del messaggio in modo che sia sufficiente ottenere il nome dell'elemento corrente e l'URI dello spazio dei nomi e combinarli in un `XmlQualifiedName` che viene quindi usato per cercare l'operazione corrispondente nel dizionario usato dal selettore dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d66f8-114">This method already positions the reader on the first child of the message's body so that it is sufficient to get the current element's name and namespace URI and combine them into an `XmlQualifiedName` that is then used for looking up the corresponding operation from the dictionary held by the operation selector.</span></span>  
  
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
  
 <span data-ttu-id="d66f8-115">L'accesso al corpo del messaggio tramite <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> o qualsiasi altro metodo che fornisce l'accesso al contenuto del corpo del messaggio determina il contrassegno del messaggio come "letto", che quindi non è valido per altre elaborazioni.</span><span class="sxs-lookup"><span data-stu-id="d66f8-115">Accessing the message body with <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> or any of the other methods that provide access to the message's body content causes the message to be marked as "read", which means that the message is invalid for any further processing.</span></span> <span data-ttu-id="d66f8-116">Di conseguenza, il selettore dell'operazione crea una copia del messaggio in arrivo tramite il metodo illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d66f8-116">Therefore, the operation selector creates a copy of the incoming message with the method shown in the following code.</span></span> <span data-ttu-id="d66f8-117">Poiché la posizione del lettore non è stata modificata durante l'ispezione, è possibile farvi riferimento dal messaggio appena creato nel quale sono state copiate anche le proprietà del messaggio e le intestazioni del messaggio, operazione che si traduce in un clone esatto del messaggio originale:</span><span class="sxs-lookup"><span data-stu-id="d66f8-117">Because the reader's position has not been changed during the inspection, it can be referenced by the newly created message to which the message properties and the message headers are also copied, which results in an exact clone of the original message:</span></span>  
  
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
  
## <a name="adding-an-operation-selector-to-a-service"></a><span data-ttu-id="d66f8-118">Aggiunta di un selettore dell'operazione a un servizio</span><span class="sxs-lookup"><span data-stu-id="d66f8-118">Adding an Operation Selector to a Service</span></span>  
 <span data-ttu-id="d66f8-119">I selettori dell'operazione di distribuzione del servizio sono estensioni per il dispatcher di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d66f8-119">Service dispatch operation selectors are extensions to the Windows Communication Foundation (WCF) dispatcher.</span></span> <span data-ttu-id="d66f8-120">Per la selezione dei metodi nel canale di callback dei contratti duplex, sono disponibili anche selettori dell'operazione client che funzionano in modo simile ai selettori dell'operazione di distribuzione descritti qui, ma che non sono trattati in modo esplicito in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d66f8-120">For selecting methods on the callback channel of duplex contracts, there are also client operation selectors, which work very much like the dispatch operation selectors described here, but which are not explicitly covered in this sample.</span></span>  
  
 <span data-ttu-id="d66f8-121">Analogamente alla maggior parte delle estensioni del modello di servizi, i selettori dell'operazione di distribuzione vengono aggiunti al dispatcher usando i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="d66f8-121">Like most service model extensions, dispatch operation selectors are added to the dispatcher using behaviors.</span></span> <span data-ttu-id="d66f8-122">Un *comportamento* è un oggetto di configurazione che aggiunge una o più estensioni al runtime di invio (o al runtime client) o modifica le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d66f8-122">A *behavior* is a configuration object, which either adds one or more extensions to the dispatch runtime (or to the client runtime) or otherwise changes its settings.</span></span>  
  
 <span data-ttu-id="d66f8-123">Poiché i selettori dell'operazione hanno l'ambito del contratto, il comportamento appropriato da implementare qui è <xref:System.ServiceModel.Description.IContractBehavior>.</span><span class="sxs-lookup"><span data-stu-id="d66f8-123">Because operation selectors have contract scope, the appropriate behavior to implement here is the <xref:System.ServiceModel.Description.IContractBehavior>.</span></span> <span data-ttu-id="d66f8-124">Poiché l'interfaccia è implementata in una classe derivata <xref:System.Attribute> come illustrato nel codice seguente, il comportamento può essere aggiunto in modo dichiarativo a qualsiasi contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="d66f8-124">Because the interface is implemented on a <xref:System.Attribute> derived class as shown in the following code, the behavior can be declaratively added to any service contract.</span></span> <span data-ttu-id="d66f8-125">Ogni volta che viene aperto un <xref:System.ServiceModel.ServiceHost> e il runtime della distribuzione viene compilato, tutti i comportamenti trovati come attributi in contratti, operazioni e implementazioni del servizio o come elemento nella configurazione del servizio vengono aggiunti e successivamente richiesti per contribuire alle estensioni o modificare la configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d66f8-125">Whenever a <xref:System.ServiceModel.ServiceHost> is opened and the dispatch runtime is built, all behaviors found either as attributes on contracts, operations, and service implementations or as element in the service configuration are automatically added and subsequently asked to contribute extensions or modify the default configuration.</span></span>  
  
 <span data-ttu-id="d66f8-126">Per brevità, nella porzione di codice seguente è illustrata solo l'implementazione del metodo <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, che esegue le modifiche di configurazione per il dispatcher in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d66f8-126">For brevity, the following code excerpt only shows the implementation of the method <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, which effects the configuration changes for the dispatcher in this sample.</span></span> <span data-ttu-id="d66f8-127">Gli altri metodi non sono illustrati perché ritornano al chiamante senza svolgere alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="d66f8-127">The other methods are not shown because they return to the caller without doing any work.</span></span>  
  
```csharp
[AttributeUsage(AttributeTargets.Class|AttributeTargets.Interface)]  
class DispatchByBodyElementBehaviorAttribute : Attribute, IContractBehavior  
{  
    // public void AddBindingParameters(...)
    // public void ApplyClientBehavior(...)  
    // public void Validate(...)  
```  
  
 <span data-ttu-id="d66f8-128">Prima, l'implementazione <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> imposta sul dizionario di ricerca per il selettore dell'operazione eseguendo l'iterazione tra gli elementi <xref:System.ServiceModel.Description.OperationDescription> nella <xref:System.ServiceModel.Description.ContractDescription> dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="d66f8-128">First, the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> implementation sets up the lookup dictionary for the operation selector by iterating over the <xref:System.ServiceModel.Description.OperationDescription> elements in the service endpoint's <xref:System.ServiceModel.Description.ContractDescription>.</span></span> <span data-ttu-id="d66f8-129">Quindi, in ciascuna descrizione dell'operazione viene controllata la presenza del comportamento `DispatchBodyElementAttribute`, un'implementazione della classe <xref:System.ServiceModel.Description.IOperationBehavior> che è definita anch'essa in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d66f8-129">Then, each operation description is inspected for the presence of the `DispatchBodyElementAttribute` behavior, an implementation of <xref:System.ServiceModel.Description.IOperationBehavior> that is also defined in this sample.</span></span> <span data-ttu-id="d66f8-130">Pur essendo un comportamento, questa classe è passiva e non contribuisce attivamente ad alcuna modifica di configurazione nel runtime di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d66f8-130">While this class is also a behavior, it is passive and does not actively contribute any configuration changes to the dispatch runtime.</span></span> <span data-ttu-id="d66f8-131">Tutti i relativi metodi ritornano al chiamante senza intraprendere alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d66f8-131">All of its methods return to the caller without taking any actions.</span></span> <span data-ttu-id="d66f8-132">Il comportamento dell'operazione esiste solo per consentire che i metadati necessari per il nuovo meccanismo di distribuzione, vale a dire il nome completo dell'elemento corpo nella cui occorrenza è selezionata un'operazione, possano essere associati alle rispettive operazioni.</span><span class="sxs-lookup"><span data-stu-id="d66f8-132">The operation behavior only exists so that the metadata required for the new dispatch mechanism, namely the qualified name of the body element on whose occurrence an operation is selected, can be associated with the respective operations.</span></span>  
  
 <span data-ttu-id="d66f8-133">Se tale comportamento viene trovato, una coppia di valori creata con il nome completo XML (proprietà `QName`) e il nome dell'operazione (proprietà `Name`) viene aggiunta al dizionario.</span><span class="sxs-lookup"><span data-stu-id="d66f8-133">If such a behavior is found, a value pair created from the XML qualified name (`QName` property) and the operation name (`Name` property) is added to the dictionary.</span></span>  
  
 <span data-ttu-id="d66f8-134">Dopo che il dizionario è stato popolato, viene costruito un nuovo `DispatchByBodyElementOperationSelector` con queste informazioni e impostato come selettore dell'operazione del runtime di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="d66f8-134">Once the dictionary is populated, a new `DispatchByBodyElementOperationSelector` is constructed with this information and set as the operation selector of the dispatch runtime:</span></span>  
  
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
  
## <a name="implementing-the-service"></a><span data-ttu-id="d66f8-135">Implementazione del servizio</span><span class="sxs-lookup"><span data-stu-id="d66f8-135">Implementing the Service</span></span>  
 <span data-ttu-id="d66f8-136">Il comportamento implementato in questo esempio influisce direttamente sul modo in cui i messaggi dal collegamento vengono interpretati e distribuiti, che è una funzione del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="d66f8-136">The behavior implemented in this sample directly affects how messages from the wire are interpreted and dispatched, which is a function of the service contract.</span></span> <span data-ttu-id="d66f8-137">Di conseguenza, il comportamento deve essere dichiarato nel livello del contratto di servizio in qualsiasi implementazione del servizio che sceglie di usarlo.</span><span class="sxs-lookup"><span data-stu-id="d66f8-137">Consequently, the behavior should be declared on the service contract level in any service implementation that chooses to use it.</span></span>  
  
 <span data-ttu-id="d66f8-138">Il servizio del progetto di esempio applica il `DispatchByBodyElementBehaviorAttribute` comportamento del contratto al `IDispatchedByBody` contratto di servizio ed etichetta ognuna delle due operazioni `OperationForBodyA()` e `OperationForBodyB()` con un `DispatchBodyElementAttribute` comportamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d66f8-138">The sample project service applies the `DispatchByBodyElementBehaviorAttribute` contract behavior to the `IDispatchedByBody` service contract and labels each of the two operations `OperationForBodyA()` and `OperationForBodyB()` with a `DispatchBodyElementAttribute` operation behavior.</span></span> <span data-ttu-id="d66f8-139">Quando un host del servizio per un servizio che implementa questo contratto viene aperto, questi metadati vengono prelevati dal generatore del dispatcher come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d66f8-139">When a service host for a service that implements this contract is opened, this metadata is picked up by the dispatcher builder as previously described.</span></span>  
  
 <span data-ttu-id="d66f8-140">Poiché il selettore dell'operazione esegue la distribuzione solo in base all'elemento del corpo di messaggio e ignora "Action", è necessario indicare al runtime di non controllare l'intestazione "Action" nelle risposte restituite assegnando il carattere jolly "\*" alla proprietà `ReplyAction` di <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d66f8-140">Because the operation selector dispatches solely based on the message body element and ignores the "Action", it is required to tell the runtime not to check the "Action" header on the returned replies by assigning the wildcard "\*" to the `ReplyAction` property of <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="d66f8-141">Inoltre, è necessario disporre di un'operazione predefinita con la proprietà "Action" impostata sul carattere jolly " \* ".</span><span class="sxs-lookup"><span data-stu-id="d66f8-141">Furthermore, it is required to have a default operation that has the "Action" property set to the wildcard "\*".</span></span> <span data-ttu-id="d66f8-142">L'operazione predefinita riceve tutti i messaggi che non possono essere distribuiti e sono privi di `DispatchBodyElementAttribute`:</span><span class="sxs-lookup"><span data-stu-id="d66f8-142">The default operation receives all messages which cannot be dispatched and does not have a `DispatchBodyElementAttribute`:</span></span>  
  
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
  
 <span data-ttu-id="d66f8-143">L'implementazione del servizio di esempio è semplice.</span><span class="sxs-lookup"><span data-stu-id="d66f8-143">The sample service implementation is straightforward.</span></span> <span data-ttu-id="d66f8-144">Ogni metodo esegue il wrapping del messaggio ricevuto in un messaggio di risposta e lo restituisce al client.</span><span class="sxs-lookup"><span data-stu-id="d66f8-144">Every method wraps the received message into a reply message and echoes it back to the client.</span></span>  
  
## <a name="running-and-building-the-sample"></a><span data-ttu-id="d66f8-145">Esecuzione e compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="d66f8-145">Running and Building the Sample</span></span>  
 <span data-ttu-id="d66f8-146">Quando si esegue l'esempio, il contenuto del corpo delle risposte dell'operazione viene visualizzato nella finestra della console client simile all'output seguente formattato.</span><span class="sxs-lookup"><span data-stu-id="d66f8-146">When you run the sample, the body content of the operation responses are displayed in the client console window similar to the following (formatted) output.</span></span>  
  
 <span data-ttu-id="d66f8-147">Il client invia tre messaggi al servizio il cui elemento del contenuto del corpo è denominato `bodyA`, `bodyB` e `bodyX`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="d66f8-147">The client sends three messages to the service whose body content element is named `bodyA`, `bodyB`, and `bodyX`, respectively.</span></span> <span data-ttu-id="d66f8-148">Come è possibile dedurre dalla descrizione precedente e dal contratto di servizio illustrato, il messaggio in arrivo con l'elemento `bodyA` viene distribuito al metodo `OperationForBodyA()`.</span><span class="sxs-lookup"><span data-stu-id="d66f8-148">As can be deferred from the previous description and the service contract shown, the incoming message with the `bodyA` element is dispatched to the `OperationForBodyA()` method.</span></span> <span data-ttu-id="d66f8-149">Poiché non vi è una destinazione esplicita della distribuzione per il messaggio con l'elemento del corpo `bodyX`, il messaggio viene distribuito a `DefaultOperation()`.</span><span class="sxs-lookup"><span data-stu-id="d66f8-149">Because there is no explicit dispatch target for the message with the `bodyX` body element, the message is dispatched to the `DefaultOperation()`.</span></span> <span data-ttu-id="d66f8-150">Ciascuna delle operazioni del servizio esegue il wrapping del corpo del messaggio ricevuto in un elemento specifico del metodo e lo restituisce, operazione volta a correlare chiaramente i messaggi di input e output per questo esempio:</span><span class="sxs-lookup"><span data-stu-id="d66f8-150">Each of the service operations wraps the received message body into an element specific to the method and returns it, which is done to correlate input and output messages clearly for this sample:</span></span>  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d66f8-151">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="d66f8-151">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d66f8-152">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d66f8-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="d66f8-153">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d66f8-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="d66f8-154">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d66f8-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d66f8-155">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d66f8-155">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d66f8-156">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d66f8-156">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d66f8-157">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="d66f8-157">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d66f8-158">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d66f8-158">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\AdvancedDispatchByBody`  
