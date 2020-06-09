---
title: Controlli messaggi
ms.date: 03/30/2017
ms.assetid: 9bd1f305-ad03-4dd7-971f-fa1014b97c9b
ms.openlocfilehash: 1a5519e815a6714e087a77c69e943a3a8c65db68
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585078"
---
# <a name="message-inspectors"></a><span data-ttu-id="0058b-102">Controlli messaggi</span><span class="sxs-lookup"><span data-stu-id="0058b-102">Message Inspectors</span></span>
<span data-ttu-id="0058b-103">In questo esempio viene illustrato come implementare e configurare i controlli messaggi del client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="0058b-103">This sample demonstrates how to implement and configure client and service message inspectors.</span></span>  
  
 <span data-ttu-id="0058b-104">Un controllo messaggi è un oggetto extensibility che può essere utilizzato nella fase di esecuzione del client e della distribuzione del modello del servizio a livello di programmazione o tramite configurazione e che può esaminare e modificare i messaggi dopo che sono stati ricevuti o prima che siano inviati.</span><span class="sxs-lookup"><span data-stu-id="0058b-104">A message inspector is an extensibility object that can be used in the service model's client runtime and dispatch runtime programmatically or through configuration and that can inspect and alter messages after they are received or before they are sent.</span></span>  
  
 <span data-ttu-id="0058b-105">Questo esempio implementa un meccanismo di convalida dei messaggi di base del client e del servizio che convalida i messaggi in arrivo confrontandoli con un set di documenti di XML Schema configurabili.</span><span class="sxs-lookup"><span data-stu-id="0058b-105">This sample implements a basic client and service message validation mechanism that validates incoming messages against a set of configurable XML Schema documents.</span></span> <span data-ttu-id="0058b-106">Si noti che questo esempio non convalida i messaggi per ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="0058b-106">Note that this sample does not validate messages for each operation.</span></span> <span data-ttu-id="0058b-107">Si tratta di una semplificazione intenzionale.</span><span class="sxs-lookup"><span data-stu-id="0058b-107">This is an intentional simplification.</span></span>  
  
## <a name="message-inspector"></a><span data-ttu-id="0058b-108">Controllo messaggi</span><span class="sxs-lookup"><span data-stu-id="0058b-108">Message Inspector</span></span>  
 <span data-ttu-id="0058b-109">I controlli messaggi del client implementano l'interfaccia <xref:System.ServiceModel.Dispatcher.IClientMessageInspector>, e i controlli messaggi del servizio implementano l'interfaccia <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>.</span><span class="sxs-lookup"><span data-stu-id="0058b-109">Client message inspectors implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> interface and service message inspectors implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> interface.</span></span> <span data-ttu-id="0058b-110">Le implementazioni possono essere combinate in una sola classe per formare un controllo messaggi che funzioni per entrambi lati.</span><span class="sxs-lookup"><span data-stu-id="0058b-110">The implementations can be combined into a single class to form a message inspector that works for both sides.</span></span> <span data-ttu-id="0058b-111">Questo esempio implementa questo controllo messaggi combinato.</span><span class="sxs-lookup"><span data-stu-id="0058b-111">This sample implements such a combined message inspector.</span></span> <span data-ttu-id="0058b-112">Il controllo viene generato tramite il passaggio di un set di schemi con cui vengono confrontati i messaggi in ingresso e in uscita e consente allo sviluppatore di specificare se i messaggi in ingresso o in uscita sono convalidati e se il controllo si trova in modalità client o di distribuzione, cosa che influisce sulla gestione degli errori illustrata in un secondo momento in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0058b-112">The inspector is constructed passing in a set of schemas against which incoming and outgoing messages are validated and allows the developer to specify whether incoming or outgoing messages are validated and whether the inspector is in dispatch or client mode, which affects the error handling as discussed later in this topic.</span></span>  
  
```csharp
public class SchemaValidationMessageInspector : IClientMessageInspector, IDispatchMessageInspector  
{  
    XmlSchemaSet schemaSet;  
    bool validateRequest;  
    bool validateReply;  
    bool isClientSide;  
    [ThreadStatic]  
    bool isRequest;  
  
    public SchemaValidationMessageInspector(XmlSchemaSet schemaSet,  
         bool validateRequest, bool validateReply, bool isClientSide)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = validateReply;  
        this.validateRequest = validateRequest;  
        this.isClientSide = isClientSide;  
    }  
```  
  
 <span data-ttu-id="0058b-113">Qualsiasi controllo messaggi del servizio (dispatcher) deve implementare i due metodi <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> e <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.</span><span class="sxs-lookup"><span data-stu-id="0058b-113">Any service (dispatcher) message inspector must implement the two <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> methods <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.</span></span>  
  
 <span data-ttu-id="0058b-114"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> viene richiamato dal dispatcher quando un messaggio è stato ricevuto, elaborato dallo stack di canali e assegnato a un servizio, ma prima che venga deserializzato e inviato a un'operazione.</span><span class="sxs-lookup"><span data-stu-id="0058b-114"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> is invoked by the dispatcher when a message has been received, processed by the channel stack and assigned to a service, but before it is deserialized and dispatched to an operation.</span></span> <span data-ttu-id="0058b-115">Se il messaggio in arrivo è crittografato, il messaggio arriva al controllo messaggi già decrittografato.</span><span class="sxs-lookup"><span data-stu-id="0058b-115">If the incoming message was encrypted, the message is already decrypted when it reaches the message inspector.</span></span> <span data-ttu-id="0058b-116">Il metodo ottiene il messaggio `request` passato come un parametro per riferimento, il che significa che il messaggio potrà essere controllato, modificato o sostituito in base alla necessità.</span><span class="sxs-lookup"><span data-stu-id="0058b-116">The method gets the `request` message passed as a reference parameter, which allows the message to be inspected, manipulated or replaced as required.</span></span> <span data-ttu-id="0058b-117">Il valore restituito può essere qualsiasi oggetto e può essere utilizzato come oggetto dello stato di correlazione che viene passato a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> quando il servizio restituisce una risposta al messaggio corrente.</span><span class="sxs-lookup"><span data-stu-id="0058b-117">The return value can be any object and is used as a correlation state object that is passed to <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> when the service returns a reply to the current message.</span></span> <span data-ttu-id="0058b-118">In questo esempio, <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> delega l'esame (la convalida) del messaggio al metodo privato e locale `ValidateMessageBody` e non restituisce oggetti dello stato di correlazione.</span><span class="sxs-lookup"><span data-stu-id="0058b-118">In this sample, <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> delegates the inspection (validation) of the message to the private, local method `ValidateMessageBody` and returns no correlation state object.</span></span> <span data-ttu-id="0058b-119">Questo metodo assicura che non passino messaggi non validi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="0058b-119">This method ensures that no invalid messages pass into the service.</span></span>  
  
```csharp  
object IDispatchMessageInspector.AfterReceiveRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel, System.ServiceModel.InstanceContext instanceContext)  
{  
    if (validateRequest)  
    {  
        // inspect the message. If a validation error occurs,  
        // the thrown fault exception bubbles up.  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 <span data-ttu-id="0058b-120"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> viene richiamato ogni volta che una risposta è pronta per essere restituita a un client o, nel caso di messaggi unidirezionali, quando il messaggio in arrivo è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="0058b-120"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> is invoked whenever a reply is ready to be sent back to a client, or in the case of one-way messages, when the incoming message has been processed.</span></span> <span data-ttu-id="0058b-121">Questo consente alle estensioni di essere chiamate simmetricamente, indipendentemente da MEP.</span><span class="sxs-lookup"><span data-stu-id="0058b-121">This allows extensions to count on being called symmetrically, regardless of MEP.</span></span> <span data-ttu-id="0058b-122">Come con <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, il messaggio viene passato come un parametro per riferimento e può essere controllato, modificato o sostituito.</span><span class="sxs-lookup"><span data-stu-id="0058b-122">As with <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, the message is passed as a reference parameter and can be inspected, modified or replaced.</span></span> <span data-ttu-id="0058b-123">La convalida del messaggio eseguita in questo esempio è delegata nuovamente al metodo `ValidMessageBody`, ma la gestione degli errori di convalida è leggermente diversa in questo caso.</span><span class="sxs-lookup"><span data-stu-id="0058b-123">The validation of the message that is performed in this sample is again delegated to the `ValidMessageBody` method, but the handling of validation errors is slightly different in this case.</span></span>  
  
 <span data-ttu-id="0058b-124">Se si verifica un errore di convalida nel servizio, il metodo `ValidateMessageBody` genera eccezioni derivate da <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="0058b-124">If a validation error occurs on the service, the `ValidateMessageBody` method throws <xref:System.ServiceModel.FaultException>-derived exceptions.</span></span> <span data-ttu-id="0058b-125">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, queste eccezioni possono essere inserite nell'infrastruttura del modello di servizi, dove vengono automaticamente trasformate in errori SOAP e inoltrate al client.</span><span class="sxs-lookup"><span data-stu-id="0058b-125">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, these exceptions can be put into the service model infrastructure where they are automatically transformed into SOAP faults and relayed to the client.</span></span> <span data-ttu-id="0058b-126">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>, le eccezioni <xref:System.ServiceModel.FaultException> non possono essere inserite nell'infrastruttura, perché la trasformazione di eccezioni d'errore generate dal servizio avviene prima che il controllo messaggi venga chiamato.</span><span class="sxs-lookup"><span data-stu-id="0058b-126">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>, <xref:System.ServiceModel.FaultException> exceptions must not be put into the infrastructure, because the transformation of fault exceptions thrown by the service occurs before the message inspector is called.</span></span> <span data-ttu-id="0058b-127">Pertanto l'implementazione seguente rileva l'eccezione `ReplyValidationFault` nota e sostituisce il messaggio di risposta con un messaggio di errore esplicito.</span><span class="sxs-lookup"><span data-stu-id="0058b-127">Therefore the following implementation catches the known `ReplyValidationFault` exception and replaces the reply message with an explicit fault message.</span></span> <span data-ttu-id="0058b-128">Questo metodo assicura che non vengano restituiti messaggi non validi dall'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="0058b-128">This method ensures that no invalid messages are returned by the service implementation.</span></span>  
  
```csharp  
void IDispatchMessageInspector.BeforeSendReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        // Inspect the reply, catch a possible validation error
        try  
        {  
            ValidateMessageBody(ref reply, false);  
        }  
        catch (ReplyValidationFault fault)  
        {  
            // if a validation error occurred, the message is replaced  
            // with the validation fault.  
            reply = Message.CreateMessage(reply.Version,
                    fault.CreateMessageFault(), reply.Headers.Action);  
        }  
    }  
```  
  
 <span data-ttu-id="0058b-129">Il controllo messaggi del client è molto simile.</span><span class="sxs-lookup"><span data-stu-id="0058b-129">The client message inspector is very similar.</span></span> <span data-ttu-id="0058b-130">I due metodi da implementare da <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> sono <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> e <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.</span><span class="sxs-lookup"><span data-stu-id="0058b-130">The two methods that must be implemented from <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> are <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> and <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.</span></span>  
  
 <span data-ttu-id="0058b-131"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> viene richiamato quando il messaggio è stato composto dall'applicazione client o dal formattatore dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="0058b-131"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> is invoked when the message has been composed either by the client application or by the operation formatter.</span></span> <span data-ttu-id="0058b-132">Come per i controlli messaggi del dispatcher, il messaggio può essere solo controllato o completamente sostituito.</span><span class="sxs-lookup"><span data-stu-id="0058b-132">As with the dispatcher message inspectors, the message can just be inspected or entirely replaced.</span></span> <span data-ttu-id="0058b-133">In questo esempio, l'ispettore delega allo stesso metodo di supporto locale `ValidateMessageBody` che viene utilizzato anche per i controlli messaggi della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0058b-133">In this sample, the inspector delegates to the same local `ValidateMessageBody` helper method that is also used for the dispatch message inspectors.</span></span>  
  
 <span data-ttu-id="0058b-134">La differenza di comportamento tra la convalida del client e quella del servizio (come specificato nel costruttore) è che la convalida del client genera eccezioni locali che vengono inserite nel codice utente perché si verificano localmente e non a causa di un errore del servizio.</span><span class="sxs-lookup"><span data-stu-id="0058b-134">The behavioral difference between the client and service validation (as specified in the constructor) is that the client validation throws local exceptions that are put into the user code because they occur locally and not because of a service failure.</span></span> <span data-ttu-id="0058b-135">In genere, la regola è che i controlli dispatcher del servizio generano errori e che i controlli del client generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="0058b-135">Generally, the rule is that service dispatcher inspectors throw faults and that client inspectors throw exceptions.</span></span>  
  
 <span data-ttu-id="0058b-136">Questa implementazione <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> assicura che non vengano inviati messaggi non validi al servizio.</span><span class="sxs-lookup"><span data-stu-id="0058b-136">This <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> implementation ensures that no invalid messages are sent to the service.</span></span>  
  
```csharp  
object IClientMessageInspector.BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
{  
    if (validateRequest)  
    {  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 <span data-ttu-id="0058b-137">L'implementazione `AfterReceiveReply` assicura che nessun messaggio non valido ricevuto dal servizio venga inoltrato al codice utente del client.</span><span class="sxs-lookup"><span data-stu-id="0058b-137">The `AfterReceiveReply` implementation ensures that no invalid messages received from the service are relayed to the client user code.</span></span>  
  
```csharp  
void IClientMessageInspector.AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        ValidateMessageBody(ref reply, false);  
    }  
}  
```  
  
 <span data-ttu-id="0058b-138">L'elemento essenziale di questo particolare controllo messaggi è il metodo `ValidateMessageBody`.</span><span class="sxs-lookup"><span data-stu-id="0058b-138">The heart of this particular message inspector is the `ValidateMessageBody` method.</span></span> <span data-ttu-id="0058b-139">Per eseguire il lavoro, esegue il wrapping di un <xref:System.Xml.XmlReader> di convalida sul sottoalbero del contenuto del corpo del messaggio passato.</span><span class="sxs-lookup"><span data-stu-id="0058b-139">To perform its work, it wraps a validating <xref:System.Xml.XmlReader> around the body content sub-tree of the passed message.</span></span> <span data-ttu-id="0058b-140">Il lettore viene popolato con il set di schemi contenuti dal controllo messaggi e il callback di convalida viene impostato su un delegato che fa riferimento all'elemento `InspectionValidationHandler` definito insieme al metodo.</span><span class="sxs-lookup"><span data-stu-id="0058b-140">The reader is populated with the set of schemas that the message inspector holds and the validation callback is set to a delegate referring to the `InspectionValidationHandler` that is defined alongside this method.</span></span> <span data-ttu-id="0058b-141">Per eseguire la convalida, il messaggio viene letto e ne viene eseguito lo spooling in una memoria <xref:System.Xml.XmlDictionaryWriter> basata sul flusso.</span><span class="sxs-lookup"><span data-stu-id="0058b-141">To perform the validation, the message is then read and spooled into a memory stream-backed <xref:System.Xml.XmlDictionaryWriter>.</span></span> <span data-ttu-id="0058b-142">Se si verifica un errore di convalida o un avviso durante il processo, il metodo di callback viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="0058b-142">If a validation error or warning occurs in the process, the callback method is invoked.</span></span>  
  
 <span data-ttu-id="0058b-143">Se non si verificano errori, viene costruito un nuovo messaggio che copia le proprietà e le intestazioni dal messaggio originale e utilizza l'InfoSet convalidato nel flusso di memoria, racchiuso in un <xref:System.Xml.XmlDictionaryReader> e aggiunto al messaggio sostitutivo.</span><span class="sxs-lookup"><span data-stu-id="0058b-143">If no error occurs, a new message is constructed that copies the properties and headers from the original message and uses the now-validated infoset in the memory stream, which is wrapped by an <xref:System.Xml.XmlDictionaryReader> and added to the replacement message.</span></span>  
  
```csharp  
void ValidateMessageBody(ref System.ServiceModel.Channels.Message message, bool isRequest)  
{  
    if (!message.IsFault)  
    {  
        XmlDictionaryReaderQuotas quotas =
                new XmlDictionaryReaderQuotas();  
        XmlReader bodyReader =
            message.GetReaderAtBodyContents().ReadSubtree();  
        XmlReaderSettings wrapperSettings =
                              new XmlReaderSettings();  
        wrapperSettings.CloseInput = true;  
        wrapperSettings.Schemas = schemaSet;  
        wrapperSettings.ValidationFlags =
                                XmlSchemaValidationFlags.None;  
        wrapperSettings.ValidationType = ValidationType.Schema;  
        wrapperSettings.ValidationEventHandler += new
           ValidationEventHandler(InspectionValidationHandler);  
        XmlReader wrappedReader = XmlReader.Create(bodyReader,
                                            wrapperSettings);  
  
        // pull body into a memory backed writer to validate  
        this.isRequest = isRequest;  
        MemoryStream memStream = new MemoryStream();  
        XmlDictionaryWriter xdw =  
              XmlDictionaryWriter.CreateBinaryWriter(memStream);  
        xdw.WriteNode(wrappedReader, false);  
        xdw.Flush(); memStream.Position = 0;  
        XmlDictionaryReader xdr =
        XmlDictionaryReader.CreateBinaryReader(memStream, quotas);  
  
        // reconstruct the message with the validated body  
        Message replacedMessage =
            Message.CreateMessage(message.Version, null, xdr);  
        replacedMessage.Headers.CopyHeadersFrom(message.Headers);  
        replacedMessage.Properties.CopyProperties(message.Properties);  
        message = replacedMessage;  
    }  
}  
```  
  
 <span data-ttu-id="0058b-144">Il metodo `InspectionValidationHandler` viene chiamato dal <xref:System.Xml.XmlReader> di convalida ogni volta che si verifica un errore o un avviso di convalida.</span><span class="sxs-lookup"><span data-stu-id="0058b-144">The `InspectionValidationHandler` method is called by the validating <xref:System.Xml.XmlReader> whenever a schema validation error or warning occurs.</span></span> <span data-ttu-id="0058b-145">L'implementazione seguente funziona solo con gli errori e ignora tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="0058b-145">The following implementation only works with errors and ignores all warnings.</span></span>  
  
 <span data-ttu-id="0058b-146">A prima vista. potrebbe sembrare possibile inserire un <xref:System.Xml.XmlReader> di convalida nel messaggio insieme al controllo messaggi e lasciare che la convalida si verifichi automaticamente quando viene elaborato il messaggio e senza memorizzarlo nel buffer.</span><span class="sxs-lookup"><span data-stu-id="0058b-146">On first consideration, it might seem possible to inject a validating <xref:System.Xml.XmlReader> into the message with the message inspector and let the validation happen as the message is processed and without buffering the message.</span></span> <span data-ttu-id="0058b-147">Tuttavia, ciò significa che questo callback genera le eccezioni di convalida da qualche parte nell'infrastruttura del modello del servizio o nel codice utente quando vengono rilevati nodi XML non validi, risultando in un comportamento imprevedibile.</span><span class="sxs-lookup"><span data-stu-id="0058b-147">That, however, means that this callback throws the validation exceptions somewhere into the service model infrastructure or the user code as invalid XML nodes are detected, resulting in unpredictable behavior.</span></span> <span data-ttu-id="0058b-148">Memorizzando il messaggio nel buffer, si protegge completamente il codice utente dai messaggi non validi.</span><span class="sxs-lookup"><span data-stu-id="0058b-148">The buffering approach shields the user code from invalid messages, entirely.</span></span>  
  
 <span data-ttu-id="0058b-149">Come illustrato precedentemente, le eccezioni generate dal gestore sono diverse per il client e per il servizio.</span><span class="sxs-lookup"><span data-stu-id="0058b-149">As previously discussed, the exceptions thrown by the handler differ between the client and the service.</span></span> <span data-ttu-id="0058b-150">Nel servizio, le eccezioni derivano da <xref:System.ServiceModel.FaultException>, mentre nel client che le eccezioni sono normali eccezioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="0058b-150">On the service, the exceptions are derived from <xref:System.ServiceModel.FaultException>, on the client the exceptions are regular custom exceptions.</span></span>  
  
```csharp  
        void InspectionValidationHandler(object sender, ValidationEventArgs e)  
{  
    if (e.Severity == XmlSeverityType.Error)  
    {  
        // We are treating client and service side validation errors  
        // differently here. Client side errors cause exceptions  
        // and are thrown straight up to the user code. Service side  
        // validations cause faults.  
        if (isClientSide)  
        {  
            if (isRequest)  
            {  
                throw new RequestClientValidationException(e.Message);  
            }  
            else  
            {  
                throw new ReplyClientValidationException(e.Message);  
            }  
        }  
        else  
        {  
            if (isRequest)  
            {  
                // this fault is caught by the ServiceModel
                // infrastructure and turned into a fault reply.  
                throw new RequestValidationFault(e.Message);  
             }  
             else  
             {  
                // this fault is caught and turned into a fault message  
                // in BeforeSendReply in this class  
                throw new ReplyValidationFault(e.Message);  
              }  
          }  
      }  
    }  
```  
  
## <a name="behavior"></a><span data-ttu-id="0058b-151">Comportamento</span><span class="sxs-lookup"><span data-stu-id="0058b-151">Behavior</span></span>  
 <span data-ttu-id="0058b-152">I controlli messaggi sono estensioni alla fase di esecuzione del client o della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0058b-152">Message inspectors are extensions to the client runtime or the dispatch runtime.</span></span> <span data-ttu-id="0058b-153">Tali estensioni vengono configurate utilizzando i *comportamenti*.</span><span class="sxs-lookup"><span data-stu-id="0058b-153">Such extensions are configured using *behaviors*.</span></span> <span data-ttu-id="0058b-154">Un comportamento è una classe che modifica il comportamento della fase di esecuzione del modello del servizio modificando la configurazione predefinita o aggiungendole estensioni (ad esempio controlli messaggi).</span><span class="sxs-lookup"><span data-stu-id="0058b-154">A behavior is a class that changes the behavior of the service model runtime by changing the default configuration or adding extensions (such as message inspectors) to it.</span></span>  
  
 <span data-ttu-id="0058b-155">La classe `SchemaValidationBehavior` seguente rappresenta il comportamento utilizzato per aggiungere il controllo messaggi di questo esempio alla fase di esecuzione del client o della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0058b-155">The following `SchemaValidationBehavior` class is the behavior used to add this sample's message inspector to the client or dispatch runtime.</span></span> <span data-ttu-id="0058b-156">L'implementazione è piuttosto semplice in entrambi casi.</span><span class="sxs-lookup"><span data-stu-id="0058b-156">The implementation is rather basic in both cases.</span></span> <span data-ttu-id="0058b-157">In <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> e <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A>, il controllo messaggi viene creato e aggiunto alla raccolta <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> della rispettiva fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0058b-157">In <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> and <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A>, the message inspector is created and added to the <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> collection of the respective runtime.</span></span>  
  
```csharp
public class SchemaValidationBehavior : IEndpointBehavior  
{  
    XmlSchemaSet schemaSet;
    bool validateRequest;
    bool validateReply;  
  
    public SchemaValidationBehavior(XmlSchemaSet schemaSet, bool
                           inspectRequest, bool inspectReply)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = inspectReply;  
        this.validateRequest = inspectRequest;  
    }  
    #region IEndpointBehavior Members  
  
    public void AddBindingParameters(ServiceEndpoint endpoint,
       System.ServiceModel.Channels.BindingParameterCollection
                                            bindingParameters)  
    {  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint,
            System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
    {  
        SchemaValidationMessageInspector inspector =
           new SchemaValidationMessageInspector(schemaSet,
                      validateRequest, validateReply, true);  
            clientRuntime.MessageInspectors.Add(inspector);  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint,
         System.ServiceModel.Dispatcher.EndpointDispatcher
                                          endpointDispatcher)  
    {  
        SchemaValidationMessageInspector inspector =
           new SchemaValidationMessageInspector(schemaSet,
                        validateRequest, validateReply, false);  
   endpointDispatcher.DispatchRuntime.MessageInspectors.Add(inspector);  
    }  
  
   public void Validate(ServiceEndpoint endpoint)  
   {  
   }  
  
    #endregion  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="0058b-158">Questo particolare comportamento non funge anche da attributo e pertanto non può essere aggiunto in modo dichiarativo a un tipo di contratto di un tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="0058b-158">This particular behavior does not double as an attribute and therefore cannot be added declaratively onto a contract type of a service type.</span></span> <span data-ttu-id="0058b-159">Si tratta di una decisione presa a livello di programmazione perché la raccolta di schemi non può essere caricata in una dichiarazione di attributo e fare riferimento a un ulteriore percorso di configurazione (per esempio alle impostazioni dell'applicazione) in questo attributo significa creare un elemento di configurazione non coerente con il resto della configurazione del modello del servizio.</span><span class="sxs-lookup"><span data-stu-id="0058b-159">This is a by-design decision made because the schema collection cannot be loaded in an attribute declaration and referring to an extra configuration location (for instance to the application settings) in this attribute means creating a configuration element that is not consistent with the rest of the service model configuration.</span></span> <span data-ttu-id="0058b-160">Pertanto, questo comportamento può essere aggiunto soltanto in modo imperativo tramite codice o tramite un'estensione di configurazione del modello del servizio.</span><span class="sxs-lookup"><span data-stu-id="0058b-160">Therefore, this behavior can only be added imperatively through code and through a service model configuration extension.</span></span>  
  
## <a name="adding-the-message-inspector-through-configuration"></a><span data-ttu-id="0058b-161">Aggiunta del controllo messaggi tramite configurazione</span><span class="sxs-lookup"><span data-stu-id="0058b-161">Adding the Message Inspector through Configuration</span></span>  
 <span data-ttu-id="0058b-162">Per la configurazione di un comportamento personalizzato in un endpoint nel file di configurazione dell'applicazione, il modello di servizio richiede agli implementatori di creare un *elemento di estensione* di configurazione rappresentato da una classe derivata da <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> .</span><span class="sxs-lookup"><span data-stu-id="0058b-162">For configuring a custom behavior on an endpoint in the application configuration file, the service model requires implementers to create a configuration *extension element* represented by a class derived from <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>.</span></span> <span data-ttu-id="0058b-163">Questa estensione deve essere quindi aggiunta alla sezione di configurazione del modello del servizio per le estensioni come illustrato per le seguenti estensioni in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0058b-163">This extension must then be added to the service model's configuration section for extensions as shown for the following extension discussed in this section.</span></span>  
  
```xml  
<system.serviceModel>  
…  
   <extensions>  
      <behaviorExtensions>  
        <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
      </behaviorExtensions>  
    </extensions>  
…  
</system.serviceModel>  
```  
  
 <span data-ttu-id="0058b-164">Le estensioni possono essere aggiunte all'applicazione o al file di configurazione ASP.NET, che rappresenta la scelta più comune, oppure nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="0058b-164">Extensions can be added in the application or ASP.NET configuration file, which is the most common choice, or in the machine configuration file.</span></span>  
  
 <span data-ttu-id="0058b-165">Quando l'estensione viene aggiunta a un ambito di configurazione, il comportamento può essere aggiunto a una configurazione di comportamento come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0058b-165">When the extension is added to a configuration scope, the behavior can be added to a behavior configuration as it is shown in the following code.</span></span> <span data-ttu-id="0058b-166">Le configurazioni di comportamento sono elementi riutilizzabili che possono essere applicati a più endpoint, in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="0058b-166">Behavior configurations are reusable elements that can be applied to multiple endpoints as required.</span></span> <span data-ttu-id="0058b-167">Poiché il comportamento da configurare in questa situazione implementa <xref:System.ServiceModel.Description.IEndpointBehavior>, è valido solo nella rispettiva sezione di configurazione del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0058b-167">Because the particular behavior to be configured here implements <xref:System.ServiceModel.Description.IEndpointBehavior>, it is only valid in the respective configuration section in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
   <behaviors>  
      …  
     <endpointBehaviors>  
        <behavior name="HelloServiceEndpointBehavior">  
          <schemaValidator validateRequest="True" validateReply="True">  
            <schemas>  
              <add location="messages.xsd" />
            </schemas>  
          </schemaValidator>  
        </behavior>  
      </endpointBehaviors>  
      …  
    </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="0058b-168">L'elemento `<schemaValidator>` che configura il controllo messaggi si bassa sulla classe `SchemaValidationBehaviorExtensionElement`.</span><span class="sxs-lookup"><span data-stu-id="0058b-168">The `<schemaValidator>` element that configures the message inspector is backed by the `SchemaValidationBehaviorExtensionElement` class.</span></span> <span data-ttu-id="0058b-169">La classe espone due proprietà pubbliche booleane denominate `ValidateRequest` e `ValidateReply`.</span><span class="sxs-lookup"><span data-stu-id="0058b-169">The class exposes two Boolean public properties named `ValidateRequest` and `ValidateReply`.</span></span> <span data-ttu-id="0058b-170">Entrambi queste proprietà sono contrassegnate da un <xref:System.Configuration.ConfigurationPropertyAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0058b-170">Both of these are marked with a <xref:System.Configuration.ConfigurationPropertyAttribute>.</span></span> <span data-ttu-id="0058b-171">Questo attributo rappresenta il collegamento tra le proprietà del codice e gli attributi XML che possono essere visualizzati nell'elemento di configurazione XML precedente.</span><span class="sxs-lookup"><span data-stu-id="0058b-171">This attribute constitutes the link between the code properties and the XML attributes that can be seen on the preceding XML configuration element.</span></span> <span data-ttu-id="0058b-172">La classe è inoltre dotata di una proprietà `Schemas` che è contrassegnata ulteriormente da <xref:System.Configuration.ConfigurationCollectionAttribute> ed è del tipo `SchemaCollection`, che fa parte di questo esempio ma è stato omesso da questo documento per motivi di brevità.</span><span class="sxs-lookup"><span data-stu-id="0058b-172">The class also has a property `Schemas` that is additionally marked with the <xref:System.Configuration.ConfigurationCollectionAttribute> and is of the type `SchemaCollection`, which is also part of this sample but omitted from this document for brevity.</span></span> <span data-ttu-id="0058b-173">Questa proprietà, con la raccolta e la classe di elementi della raccolta `SchemaConfigElement` si basa sull'elemento `<schemas>` presente nel frammento di configurazione precedente e consente di aggiungere una raccolta di schemi al set di convalida.</span><span class="sxs-lookup"><span data-stu-id="0058b-173">This property along with the collection and the collection element class `SchemaConfigElement` backs the `<schemas>` element in the preceding configuration snippet and allows adding a collection of schemas to the validation set.</span></span>  
  
 <span data-ttu-id="0058b-174">Il metodo `CreateBehavior` sottoposto a override trasforma i dati di configurazione in un oggetto di comportamento quando la fase di esecuzione valuta i dati di configurazione mentre compila un client o un endpoint.</span><span class="sxs-lookup"><span data-stu-id="0058b-174">The overridden `CreateBehavior` method turns the configuration data into a behavior object when the runtime evaluates the configuration data as it builds a client or an endpoint.</span></span>  
  
```csharp
public class SchemaValidationBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public SchemaValidationBehaviorExtensionElement()  
    {  
    }  
  
    public override Type BehaviorType
    {
        get  
        {  
            return typeof(SchemaValidationBehavior);  
        }
    }  
  
    protected override object CreateBehavior()  
    {  
        XmlSchemaSet schemaSet = new XmlSchemaSet();  
        foreach (SchemaConfigElement schemaCfg in this.Schemas)  
        {  
            Uri baseSchema = new
                Uri(AppDomain.CurrentDomain.BaseDirectory);  
            string location = new
                Uri(baseSchema,schemaCfg.Location).ToString();  
            XmlSchema schema =
                XmlSchema.Read(new XmlTextReader(location), null);  
            schemaSet.Add(schema);  
        }  
     return new
     SchemaValidationBehavior(schemaSet,ValidateRequest,ValidateReply);  
    }  
  
[ConfigurationProperty("validateRequest",DefaultValue=false,IsRequired=false)]  
public bool ValidateRequest  
{  
    get { return (bool)base["validateRequest"]; }  
    set { base["validateRequest"] = value; }  
}  
  
[ConfigurationProperty("validateReply", DefaultValue = false, IsRequired = false)]  
        public bool ValidateReply  
        {  
            get { return (bool)base["validateReply"]; }  
            set { base["validateReply"] = value; }  
        }  
  
     //Declare the Schema collection property.  
     //Note: the "IsDefaultCollection = false" instructs
     //.NET Framework to build a nested section of
     //the kind <Schema> ...</Schema>.  
    [ConfigurationProperty("schemas", IsDefaultCollection = true)]  
    [ConfigurationCollection(typeof(SchemasCollection),  
        AddItemName = "add",  
        ClearItemsName = "clear",  
        RemoveItemName = "remove")]  
    public SchemasCollection Schemas  
    {  
        get  
        {  
            SchemasCollection SchemasCollection =  
            (SchemasCollection)base["schemas"];  
            return SchemasCollection;  
        }  
    }  
}  
```  
  
## <a name="adding-message-inspectors-imperatively"></a><span data-ttu-id="0058b-175">Aggiunta di controlli messaggi in modo imperativo</span><span class="sxs-lookup"><span data-stu-id="0058b-175">Adding Message Inspectors Imperatively</span></span>  
 <span data-ttu-id="0058b-176">I comportamenti possono essere aggiunti facilmente alla fase di esecuzione del client e o del servizio utilizzando il codice imperativo, ma non utilizzando attributi (funzione non supportata in questo esempio per la ragione sopra citata) e configurazione.</span><span class="sxs-lookup"><span data-stu-id="0058b-176">Except through attributes (which is not supported in this sample for the reason cited previously) and configuration, behaviors can quite easily be added to a client and service runtime using imperative code.</span></span> <span data-ttu-id="0058b-177">In questo esempio, questa operazione viene eseguita nell'applicazione client per testare il controllo messaggi del client.</span><span class="sxs-lookup"><span data-stu-id="0058b-177">In this sample, this is done in the client application to test the client message inspector.</span></span> <span data-ttu-id="0058b-178">La classe `GenericClient` deriva da <xref:System.ServiceModel.ClientBase%601>, che espone la configurazione dell'endpoint al codice utente.</span><span class="sxs-lookup"><span data-stu-id="0058b-178">The `GenericClient` class is derived from <xref:System.ServiceModel.ClientBase%601>, which exposes the endpoint configuration to the user code.</span></span> <span data-ttu-id="0058b-179">Prima che il client venga aperto in modo implicito, la configurazione dell'endpoint può essere modificata, ad esempio aggiungendo i comportamenti come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0058b-179">Before the client is implicitly opened the endpoint configuration can be changed, for instance by adding behaviors as shown in the following code.</span></span> <span data-ttu-id="0058b-180">L'aggiunta del comportamento al servizio è praticamente equivalente alla tecnica per client illustrata e deve essere eseguita prima che l'host del servizio venga aperto.</span><span class="sxs-lookup"><span data-stu-id="0058b-180">Adding the behavior on the service is largely equivalent to the client technique shown here and must be performed before the service host is opened.</span></span>  
  
```csharp  
try  
{  
    Console.WriteLine("*** Call 'Hello' with generic client, with client behavior");  
    GenericClient client = new GenericClient();  
  
    // Configure client programmatically, adding behavior  
    XmlSchema schema = XmlSchema.Read(new StreamReader("messages.xsd"),
                                                          null);  
    XmlSchemaSet schemaSet = new XmlSchemaSet();  
    schemaSet.Add(schema);  
    client.Endpoint.Behaviors.Add(new
                SchemaValidationBehavior(schemaSet, true, true));  
  
    Console.WriteLine("--- Sending valid client request:");  
    GenericCallValid(client, helloAction);  
    Console.WriteLine("--- Sending invalid client request:");  
    GenericCallInvalid(client, helloAction);  
  
    client.Close();  
}  
catch (Exception e)  
{  
    DumpException(e);  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0058b-181">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0058b-181">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0058b-182">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0058b-182">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0058b-183">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0058b-183">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0058b-184">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0058b-184">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0058b-185">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0058b-185">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0058b-186">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0058b-186">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0058b-187">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="0058b-187">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0058b-188">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0058b-188">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageInspectors`  
