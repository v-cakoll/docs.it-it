---
title: Formattatore e selettore dell'operazione
ms.date: 03/30/2017
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
ms.openlocfilehash: 344d3122d03e89a7f20e391db49005d0e085dfa6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575154"
---
# <a name="operation-formatter-and-operation-selector"></a><span data-ttu-id="a9584-102">Formattatore e selettore dell'operazione</span><span class="sxs-lookup"><span data-stu-id="a9584-102">Operation Formatter and Operation Selector</span></span>
<span data-ttu-id="a9584-103">In questo esempio viene illustrato come utilizzare i punti di estendibilità di Windows Communication Foundation (WCF) per consentire i dati del messaggio in un formato diverso da quello previsto da WCF.</span><span class="sxs-lookup"><span data-stu-id="a9584-103">This sample demonstrates how Windows Communication Foundation (WCF) extensibility points can be used to allow message data in a different format from what WCF expects.</span></span> <span data-ttu-id="a9584-104">Per impostazione predefinita, i formattatori WCF prevedono l'inclusione dei parametri del metodo nell' `soap:body` elemento.</span><span class="sxs-lookup"><span data-stu-id="a9584-104">By default, WCF formatters expect method parameters to be included under the `soap:body` element.</span></span> <span data-ttu-id="a9584-105">In realtà, nell'esempio viene illustrato come implementare un formattatore dell'operazione personalizzato che analizza i dati dei parametri da una stringa di query HTTP GET e richiama i metodi utilizzando tali dati.</span><span class="sxs-lookup"><span data-stu-id="a9584-105">The sample shows how to implement a custom operation formatter that parses parameter data from an HTTP GET query string instead and invokes methods using that data.</span></span>  
  
 <span data-ttu-id="a9584-106">L'esempio è basato sulla [Introduzione](getting-started-sample.md), che implementa il `ICalculator` contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="a9584-106">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="a9584-107">Viene mostrato come i messaggi Add, Subtract, Multiply e Divide possono essere modificati per utilizzare HTTP GET per le richieste client-server e HTTP POST con i messaggi POX per le risposte server-client.</span><span class="sxs-lookup"><span data-stu-id="a9584-107">It shows how Add, Subtract, Multiply, and Divide messages can be changed to use HTTP GET for client-to-server requests and HTTP POST with POX messages for server-to-client responses.</span></span>  
  
 <span data-ttu-id="a9584-108">Per questo scopo, nell'esempio vengono forniti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9584-108">To do so, the sample provides the following:</span></span>  
  
- <span data-ttu-id="a9584-109">`QueryStringFormatter`, che implementa <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> e <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> per il client e server, rispettivamente, ed elabora i dati nella stringa di query.</span><span class="sxs-lookup"><span data-stu-id="a9584-109">`QueryStringFormatter`, which implements <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> for the client and server, respectively, and processes the data in the query string.</span></span>  
  
- <span data-ttu-id="a9584-110">`UriOperationSelector`, che implementa <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> nel server per eseguire l'operazione di distribuzione in base al nome dell'operazione nella richiesta GET.</span><span class="sxs-lookup"><span data-stu-id="a9584-110">`UriOperationSelector`, which implements <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> on the server to perform operation dispatch based on the operation name in the GET request.</span></span>  
  
- <span data-ttu-id="a9584-111">Comportamento dell'endpoint `EnableHttpGetRequestsBehavior` (e configurazione corrispondente), che aggiunge il selettore dell'operazione necessario al runtime.</span><span class="sxs-lookup"><span data-stu-id="a9584-111">`EnableHttpGetRequestsBehavior` endpoint behavior (and corresponding configuration), which adds the necessary operation selector to the runtime.</span></span>  
  
- <span data-ttu-id="a9584-112">Viene illustrato come inserire un nuovo formattatore dell'operazione nel runtime.</span><span class="sxs-lookup"><span data-stu-id="a9584-112">Shows how to insert a new operation formatter into the runtime.</span></span>  
  
- <span data-ttu-id="a9584-113">In questo esempio sia il client che il servizio sono applicazioni console (con estensione exe).</span><span class="sxs-lookup"><span data-stu-id="a9584-113">In this sample, both the client and the service are console applications (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9584-114">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a9584-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="key-concepts"></a><span data-ttu-id="a9584-115">Concetti chiave</span><span class="sxs-lookup"><span data-stu-id="a9584-115">Key Concepts</span></span>  
 <span data-ttu-id="a9584-116">`QueryStringFormatter`-Il formattatore dell'operazione è il componente in WCF responsabile della conversione di un messaggio in una matrice di oggetti Parameter e di una matrice di oggetti Parameter in un messaggio.</span><span class="sxs-lookup"><span data-stu-id="a9584-116">`QueryStringFormatter` - The operation formatter is the component in WCF that is responsible for converting a message into an array of parameter objects and an array of parameter objects into a message.</span></span> <span data-ttu-id="a9584-117">Questa operazione viene eseguita nel client utilizzando l'interfaccia <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> e nel server con l'interfaccia <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>.</span><span class="sxs-lookup"><span data-stu-id="a9584-117">This is done on the client using the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> interface and on the server with the <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface.</span></span> <span data-ttu-id="a9584-118">Queste interfacce consentono agli utenti di ottenere i messaggi di richiesta e risposta dai metodi `Serialize` e `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="a9584-118">These interfaces enable users to get the request and response messages from the `Serialize` and `Deserialize` methods.</span></span>  
  
 <span data-ttu-id="a9584-119">In questo esempio, `QueryStringFormatter` implementa entrambe le interfacce e viene implementato nel client e nel server.</span><span class="sxs-lookup"><span data-stu-id="a9584-119">In this sample, `QueryStringFormatter` implements both of these interfaces and is implemented on the client and server.</span></span>  
  
 <span data-ttu-id="a9584-120">Richiesta:</span><span class="sxs-lookup"><span data-stu-id="a9584-120">Request:</span></span>  
  
- <span data-ttu-id="a9584-121">Nell'esempio viene utilizzata la classe <xref:System.ComponentModel.TypeConverter> per convertire i dati dei parametri nel messaggio di richiesta da e verso le stringhe.</span><span class="sxs-lookup"><span data-stu-id="a9584-121">The sample uses the <xref:System.ComponentModel.TypeConverter> class to convert parameter data in the request message to and from strings.</span></span> <span data-ttu-id="a9584-122">Se non è disponibile una classe <xref:System.ComponentModel.TypeConverter> per un tipo specifico, il formattatore di esempio genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a9584-122">If a <xref:System.ComponentModel.TypeConverter> is not available for a specific type, the sample formatter throws an exception.</span></span>  
  
- <span data-ttu-id="a9584-123">Nel metodo `IClientMessageFormatter.SerializeRequest` sul client, il formattatore crea un URI con l'indirizzo A appropriato e aggiunge il nome dell'operazione come suffisso.</span><span class="sxs-lookup"><span data-stu-id="a9584-123">In the `IClientMessageFormatter.SerializeRequest` method on the client, the formatter creates a URI with the appropriate To address and appends the operation name as a suffix.</span></span> <span data-ttu-id="a9584-124">Tale nome viene utilizzato per distribuire l'operazione appropriata sul server.</span><span class="sxs-lookup"><span data-stu-id="a9584-124">This name is used to dispatch to the appropriate operation on the server.</span></span> <span data-ttu-id="a9584-125">Il formattatore prende quindi la matrice di oggetti parametro e serializza i dati dei parametri nella stringa di query dell'URI utilizzando i nomi di parametro e i valori convertiti dalla classe <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="a9584-125">It then takes the array of parameter objects and serializes the parameter data to the URI query string using parameter names and the values converted by the <xref:System.ComponentModel.TypeConverter> class.</span></span> <span data-ttu-id="a9584-126">Le proprietà <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> e <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> vengono quindi impostate su questo URI.</span><span class="sxs-lookup"><span data-stu-id="a9584-126">The <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> and <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> properties are then set to this URI.</span></span> <span data-ttu-id="a9584-127">È possibile accedere all'oggetto <xref:System.ServiceModel.Channels.MessageProperties> attraverso la proprietà <xref:System.ServiceModel.Channels.Message.Properties%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9584-127"><xref:System.ServiceModel.Channels.MessageProperties> is accessed through the <xref:System.ServiceModel.Channels.Message.Properties%2A> property.</span></span>  
  
- <span data-ttu-id="a9584-128">Nel metodo `IDispatchMessageFormatter.DeserializeRequest` sul server, il formattatore recupera l'URI `Via` nelle proprietà del messaggio di richiesta in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a9584-128">In the `IDispatchMessageFormatter.DeserializeRequest` method on the server, the formatter retrieves the `Via` URI in the incoming request message properties.</span></span> <span data-ttu-id="a9584-129">Analizza le coppie nome-valore nella stringa di query dell'URI nei nomi e valori di parametro e utilizza i nomi e valori di parametro per popolare la matrice di parametri passata nel metodo.</span><span class="sxs-lookup"><span data-stu-id="a9584-129">It parses the name-value pairs in the URI query string into parameter names and values and uses the parameter names and values to populate the array of parameters passed into the method.</span></span> <span data-ttu-id="a9584-130">Si noti che l'operazione di distribuzione è già stata eseguita, pertanto il suffisso del nome dell'operazione viene ignorato in questo metodo.</span><span class="sxs-lookup"><span data-stu-id="a9584-130">Note that operation dispatch has already occurred, so the operation name suffix is ignored in this method.</span></span>  
  
 <span data-ttu-id="a9584-131">Risposta:</span><span class="sxs-lookup"><span data-stu-id="a9584-131">Response:</span></span>  
  
- <span data-ttu-id="a9584-132">In questo esempio, HTTP GET viene utilizzato solo per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="a9584-132">In this sample, HTTP GET is used only for the request.</span></span> <span data-ttu-id="a9584-133">Il formattatore delega l'invio della risposta al formattatore originale che sarebbe stato utilizzato per generare un messaggio XML.</span><span class="sxs-lookup"><span data-stu-id="a9584-133">The formatter delegates the sending of the response to the original formatter that would have been used to generate an XML message.</span></span> <span data-ttu-id="a9584-134">Uno degli obiettivi di questo esempio è mostrare come implementare tale formattatore delegato.</span><span class="sxs-lookup"><span data-stu-id="a9584-134">One of the goals of this sample is to show how such a delegating formatter can be implemented.</span></span>  
  
### <a name="uripathsuffixoperationselector-class"></a><span data-ttu-id="a9584-135">Classe UriPathSuffixOperationSelector</span><span class="sxs-lookup"><span data-stu-id="a9584-135">UriPathSuffixOperationSelector Class</span></span>  
 <span data-ttu-id="a9584-136">L'interfaccia <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> consente agli utenti di implementare una logica personalizzata che richiede l'invio di un messaggio particolare.</span><span class="sxs-lookup"><span data-stu-id="a9584-136">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface enables users to implement their own logic for which operation a particular message should be dispatched.</span></span>  
  
 <span data-ttu-id="a9584-137">In questo esempio, `UriPathSuffixOperationSelector` deve essere implementato nel server per selezionare l'operazione appropriata poiché il nome dell'operazione è incluso nell'URI HTTP GET anziché in un'intestazione dell'azione nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="a9584-137">In this sample, `UriPathSuffixOperationSelector` must be implemented on the server to select the appropriate operation because the operation name is included in the HTTP GET URI rather than an action header in the message.</span></span> <span data-ttu-id="a9584-138">L'esempio è configurato per consentire solo i nomi dell'operazione senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="a9584-138">The sample is set up to allow only case-insensitive operation names.</span></span>  
  
 <span data-ttu-id="a9584-139">Il metodo `SelectOperation` accetta il messaggio in arrivo e cerca l'URI `Via` nelle proprietà del messaggio.</span><span class="sxs-lookup"><span data-stu-id="a9584-139">The `SelectOperation` method takes the incoming message and looks up the `Via` URI in its message properties.</span></span> <span data-ttu-id="a9584-140">Estrae il suffisso del nome dell'operazione dall'URI, cerca una tabella interna per ottenere il nome dell'operazione al quale il messaggio deve essere inviato e restituisce tale nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="a9584-140">It extracts the operation name suffix from the URI, looks up an internal table to get the operation name that the message should be dispatched to, and returns that operation name.</span></span>  
  
### <a name="enablehttpgetrequestsbehavior-class"></a><span data-ttu-id="a9584-141">Classe EnableHttpGetRequestsBehavior</span><span class="sxs-lookup"><span data-stu-id="a9584-141">EnableHttpGetRequestsBehavior Class</span></span>  
 <span data-ttu-id="a9584-142">Il componente `UriPathSuffixOperationSelector` può essere impostato a livello di codice o tramite un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a9584-142">The `UriPathSuffixOperationSelector` component can be set up programmatically or through an endpoint behavior.</span></span> <span data-ttu-id="a9584-143">Nell'esempio viene implementato il comportamento `EnableHttpGetRequestsBehavior`, specificato nel file di configurazione dell'applicazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="a9584-143">The sample implements the `EnableHttpGetRequestsBehavior` behavior, which is specified in service’s application configuration file.</span></span>  
  
 <span data-ttu-id="a9584-144">Nel server:</span><span class="sxs-lookup"><span data-stu-id="a9584-144">On the server:</span></span>  
  
 <span data-ttu-id="a9584-145">La proprietà <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> è impostata sull'implementazione di <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.</span><span class="sxs-lookup"><span data-stu-id="a9584-145">The <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> is set to the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementation.</span></span>  
  
 <span data-ttu-id="a9584-146">Per impostazione predefinita, WCF utilizza un filtro di indirizzo con corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="a9584-146">By default, WCF uses an exact-match address filter.</span></span> <span data-ttu-id="a9584-147">L'URI del messaggio in ingresso contiene un suffisso del nome dell'operazione seguito da una stringa di query che contiene i dati dei parametri, pertanto il comportamento dell'endpoint modifica anche il filtro dell'indirizzo in modo da renderlo un filtro Prefisso corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a9584-147">The URI on the incoming message contains an operation name suffix followed by a query string that contains parameter data, so the endpoint behavior also changes the address filter to be a prefix match filter.</span></span> <span data-ttu-id="a9584-148">USA WCF <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="a9584-148">It uses the WCF<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> for this purpose.</span></span>  
  
### <a name="installing-operation-formatters"></a><span data-ttu-id="a9584-149">Installazione di formattatori dell'operazione</span><span class="sxs-lookup"><span data-stu-id="a9584-149">Installing operation formatters</span></span>  
 <span data-ttu-id="a9584-150">I comportamenti dell'operazione che specificano i formattatori sono univoci.</span><span class="sxs-lookup"><span data-stu-id="a9584-150">Operation behaviors that specify formatters are unique.</span></span> <span data-ttu-id="a9584-151">Un comportamento di questo tipo viene sempre implementato per impostazione predefinita per ogni operazione allo scopo di creare il formattatore dell'operazione necessario.</span><span class="sxs-lookup"><span data-stu-id="a9584-151">One such behavior is always implemented by default for every operation to create the necessary operation formatter.</span></span> <span data-ttu-id="a9584-152">Tuttavia, questi comportamenti hanno lo stesso aspetto degli altri comportamenti dell'operazione e non possono essere identificati da qualsiasi altro attributo.</span><span class="sxs-lookup"><span data-stu-id="a9584-152">However, these behaviors look like just another operation behavior; they are not identifiable by any other attribute.</span></span> <span data-ttu-id="a9584-153">Per installare un comportamento di sostituzione, l'implementazione deve cercare specifici comportamenti del formattatore installati dal caricatore del tipo WCF per impostazione predefinita e sostituirli o aggiungere un comportamento compatibile da eseguire dopo il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="a9584-153">To install a replacement behavior, the implementation must look for specific formatter behaviors that are installed by the WCF type loader by default and either replace it or add a compatible behavior to run after the default behavior.</span></span>  
  
 <span data-ttu-id="a9584-154">Questi comportamenti dei formattatori dell'operazione possono essere impostati a livello di codice prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> o specificando un comportamento dell'operazione da eseguire dopo quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="a9584-154">These operation formatters behaviors can be set up programmatically prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> or by specifying an operation behavior that is executed after the default one.</span></span> <span data-ttu-id="a9584-155">Tuttavia, non può essere configurato facilmente da un comportamento dell'endpoint (e pertanto mediante la configurazione) perché il modello di comportamento non consente la sostituzione di un comportamento con un altro o la modifica dell'albero di descrizione.</span><span class="sxs-lookup"><span data-stu-id="a9584-155">However, it cannot easily be set up by an endpoint behavior (and therefore by configuration) because the behavior model does not allow a behavior to replace other behaviors or otherwise modify the description tree.</span></span>  
  
 <span data-ttu-id="a9584-156">Nel client:</span><span class="sxs-lookup"><span data-stu-id="a9584-156">On the client:</span></span>  
  
 <span data-ttu-id="a9584-157">L'implementazione <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> deve essere implementata in modo che possa convertire le richieste in richieste HTTP GET e delegare le risposte al formattatore originale.</span><span class="sxs-lookup"><span data-stu-id="a9584-157">The <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> implementation must be implemented so that it can convert the requests into HTTP GET requests and delegate to the original formatter for responses.</span></span> <span data-ttu-id="a9584-158">Questo processo viene eseguito chiamando il metodo helper `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`.</span><span class="sxs-lookup"><span data-stu-id="a9584-158">This is done by calling the `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method.</span></span>  
  
 <span data-ttu-id="a9584-159">È necessario effettuare questo passaggio prima di chiamare `CreateChannel`.</span><span class="sxs-lookup"><span data-stu-id="a9584-159">This must be done before calling `CreateChannel`.</span></span>  
  
```csharp  
void ReplaceFormatterBehavior(OperationDescription operationDescription, EndpointAddress address)  
{  
    // Remove the DataContract behavior if it is present.  
    IOperationBehavior formatterBehavior = operationDescription.Behaviors.Remove<DataContractSerializerOperationBehavior>();  
    if (formatterBehavior == null)  
    {  
        // Remove the XmlSerializer behavior if it is present.  
        formatterBehavior = operationDescription.Behaviors.Remove<XmlSerializerOperationBehavior>();  
        ...  
    }  
  
    // Remember what the innerFormatterBehavior was.  
    DelegatingFormatterBehavior delegatingFormatterBehavior = new DelegatingFormatterBehavior(address);  
    delegatingFormatterBehavior.InnerFormatterBehavior = formatterBehavior;  
   operationDescription.Behaviors.Add(delegatingFormatterBehavior);  
}  
```  
  
 <span data-ttu-id="a9584-160">Nel server:</span><span class="sxs-lookup"><span data-stu-id="a9584-160">On the server:</span></span>  
  
- <span data-ttu-id="a9584-161">L'interfaccia <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> deve essere implementata in modo che possa leggere le richieste in richieste HTTP GET e delegare la scrittura delle risposte al formattatore originale.</span><span class="sxs-lookup"><span data-stu-id="a9584-161">The <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface must be implemented so that it can read HTTP GET requests and delegate to the original formatter for writing responses.</span></span> <span data-ttu-id="a9584-162">Questo processo viene eseguito chiamando lo stesso metodo helper `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` del client (vedere l'esempio di codice precedente).</span><span class="sxs-lookup"><span data-stu-id="a9584-162">This is done by calling the same `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method as the client (see the previous code sample).</span></span>  
  
- <span data-ttu-id="a9584-163">È necessario effettuare questo passaggio prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9584-163">This must be done before <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="a9584-164">In questo esempio viene illustrato come il formattatore viene modificato manualmente prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9584-164">In this sample, we show how the formatter is manually modified before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="a9584-165">Un altro modo per ottenere lo stesso risultato consiste nel derivare una classe da <xref:System.ServiceModel.ServiceHost> che effettua le chiamate a `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` prima dell'apertura (vedere documentazione di hosting e gli esempi).</span><span class="sxs-lookup"><span data-stu-id="a9584-165">Another way to achieve the same thing is to derive a class from <xref:System.ServiceModel.ServiceHost> that makes the calls to `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` before opening (please see hosting documentation and samples for examples).</span></span>  
  
### <a name="user-experience"></a><span data-ttu-id="a9584-166">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="a9584-166">User experience</span></span>  
 <span data-ttu-id="a9584-167">Nel server:</span><span class="sxs-lookup"><span data-stu-id="a9584-167">On the server:</span></span>  
  
- <span data-ttu-id="a9584-168">Non è necessario modificare l'implementazione `ICalculator` del server.</span><span class="sxs-lookup"><span data-stu-id="a9584-168">The server `ICalculator` implementation does not need to change.</span></span>  
  
- <span data-ttu-id="a9584-169">Il file App.config per il servizio deve utilizzare un'associazione POX personalizzata che imposta l'attributo `messageVersion` dell'elemento `textMessageEncoding` su `None`.</span><span class="sxs-lookup"><span data-stu-id="a9584-169">The App.config for the service must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- <span data-ttu-id="a9584-170">Tale file deve inoltre specificare anche il comportamento `EnableHttpGetRequestsBehavior` personalizzato aggiungendolo alla sezione delle estensioni di comportamento e utilizzandolo.</span><span class="sxs-lookup"><span data-stu-id="a9584-170">The App.config for the service also must specify the custom `EnableHttpGetRequestsBehavior` by adding it to the behavior extensions section and using it.</span></span>  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="enableHttpGetRequestsBehavior">  
          <enableHttpGetRequests />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
    <extensions>  
      <behaviorExtensions>  
        <!-- Enabling HTTP GET requests: Behavior Extension -->  
        <add
          name="enableHttpGetRequests"           type="Microsoft.ServiceModel.Samples.EnableHttpGetRequestsBehaviorElement, QueryStringFormatter, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
    ```  
  
- <span data-ttu-id="a9584-171">Aggiungere i formattatori dell'operazione prima di chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9584-171">Add operation formatters before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
 <span data-ttu-id="a9584-172">Nel client:</span><span class="sxs-lookup"><span data-stu-id="a9584-172">On the client:</span></span>  
  
- <span data-ttu-id="a9584-173">Non è necessario modificare l'implementazione client.</span><span class="sxs-lookup"><span data-stu-id="a9584-173">The client implementation does not need to change.</span></span>  
  
- <span data-ttu-id="a9584-174">Il file App.config per il client deve utilizzare un'associazione POX personalizzata che imposta l'attributo `messageVersion` dell'elemento `textMessageEncoding` su `None`.</span><span class="sxs-lookup"><span data-stu-id="a9584-174">The App.config for the client must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span> <span data-ttu-id="a9584-175">Una differenza rispetto al servizio è che il client deve abilitare l'indirizzamento manuale in modo da poter modificare gli indirizzi A in uscita.</span><span class="sxs-lookup"><span data-stu-id="a9584-175">One difference from the service is that the client must enable manual addressing so that the outgoing To address can be modified.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport manualAddressing="True" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- <span data-ttu-id="a9584-176">Il file App.config per il client deve specificare lo stesso comportamento `EnableHttpGetRequestsBehavior` personalizzato del server.</span><span class="sxs-lookup"><span data-stu-id="a9584-176">The App.config for the client must specify the same custom `EnableHttpGetRequestsBehavior` as the server.</span></span>  
  
- <span data-ttu-id="a9584-177">Aggiungere i formattatori dell'operazione prima di chiamare <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span><span class="sxs-lookup"><span data-stu-id="a9584-177">Add operation formatters before calling <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span></span>  
  
 <span data-ttu-id="a9584-178">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="a9584-178">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="a9584-179">Tutte le operazioni (Add, Subtract, Multiply e Divide) devono essere completate.</span><span class="sxs-lookup"><span data-stu-id="a9584-179">All four operations (Add, Subtract, Multiply, and Divide) must succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a9584-180">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a9584-180">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a9584-181">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a9584-181">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a9584-182">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="a9584-182">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9584-183">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a9584-183">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QueryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a9584-184">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="a9584-184">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a9584-185">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a9584-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="a9584-186">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a9584-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="a9584-187">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a9584-187">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
