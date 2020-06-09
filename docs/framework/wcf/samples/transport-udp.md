---
title: 'Trasporto: UDP'
ms.date: 03/30/2017
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
ms.openlocfilehash: 44e47dd2d291ffc27d1777a04b645d57984919cd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591436"
---
# <a name="transport-udp"></a><span data-ttu-id="40d28-102">Trasporto: UDP</span><span class="sxs-lookup"><span data-stu-id="40d28-102">Transport: UDP</span></span>
<span data-ttu-id="40d28-103">Nell'esempio di trasporto UDP viene illustrato come implementare unicast e multicast UDP come trasporto WCF (Custom Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="40d28-103">The UDP Transport sample demonstrates how to implement UDP unicast and multicast as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="40d28-104">Nell'esempio viene descritta la procedura consigliata per la creazione di un trasporto personalizzato in WCF, utilizzando il Framework del canale e le procedure consigliate WCF seguenti.</span><span class="sxs-lookup"><span data-stu-id="40d28-104">The sample describes the recommended procedure for creating a custom transport in WCF, by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="40d28-105">I passaggi per creare un trasporto personalizzato sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="40d28-105">The steps to create a custom transport are as follows:</span></span>  
  
1. <span data-ttu-id="40d28-106">Decidere quale [modello di scambio dei messaggi](#MessageExchangePatterns) del canale (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel o IReplyChannel) è supportato da ChannelFactory e ChannelListener.</span><span class="sxs-lookup"><span data-stu-id="40d28-106">Decide which of the channel [Message Exchange Patterns](#MessageExchangePatterns) (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel, or IReplyChannel) your ChannelFactory and ChannelListener will support.</span></span> <span data-ttu-id="40d28-107">Quindi decidere se si supporteranno le variazioni con sessione di tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="40d28-107">Then decide whether you will support the sessionful variations of these interfaces.</span></span>  
  
2. <span data-ttu-id="40d28-108">Creare una channel factory e un listener di canale che supportano il modello di scambio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="40d28-108">Create a channel factory and listener that support your Message Exchange Pattern.</span></span>  
  
3. <span data-ttu-id="40d28-109">Assicurarsi che eventuali eccezioni specifiche della rete vengano normalizzate nella classe derivata appropriata di <xref:System.ServiceModel.CommunicationException>.</span><span class="sxs-lookup"><span data-stu-id="40d28-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
4. <span data-ttu-id="40d28-110">Aggiungere un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento che aggiunge il trasporto personalizzato a uno stack di canali.</span><span class="sxs-lookup"><span data-stu-id="40d28-110">Add a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="40d28-111">Per ulteriori informazioni, vedere [aggiunta di un elemento di associazione](#AddingABindingElement).</span><span class="sxs-lookup"><span data-stu-id="40d28-111">For more information, see [Adding a Binding Element](#AddingABindingElement).</span></span>  
  
5. <span data-ttu-id="40d28-112">Aggiungere una sezione di estensione degli elementi di associazione per esporre il nuovo elemento di associazione al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-112">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
6. <span data-ttu-id="40d28-113">Aggiungere le estensioni dei metadati per comunicare le funzionalità agli altri endpoint.</span><span class="sxs-lookup"><span data-stu-id="40d28-113">Add metadata extensions to communicate capabilities to other endpoints.</span></span>  
  
7. <span data-ttu-id="40d28-114">Aggiungere un'associazione che preconfigura uno stack di elementi di associazione secondo un profilo ben definito.</span><span class="sxs-lookup"><span data-stu-id="40d28-114">Add a binding that pre-configures a stack of binding elements according to a well-defined profile.</span></span> <span data-ttu-id="40d28-115">Per ulteriori informazioni, vedere [aggiunta di un'associazione standard](#AddingAStandardBinding).</span><span class="sxs-lookup"><span data-stu-id="40d28-115">For more information, see [Adding a Standard Binding](#AddingAStandardBinding).</span></span>  
  
8. <span data-ttu-id="40d28-116">Aggiungere una sezione dell'associazione e un elemento di configurazione dell'associazione per esporre l'associazione al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-116">Add a binding section and binding configuration element to expose the binding to the configuration system.</span></span> <span data-ttu-id="40d28-117">Per ulteriori informazioni, vedere [aggiunta del supporto](#AddingConfigurationSupport)per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-117">For more information, see [Adding Configuration Support](#AddingConfigurationSupport).</span></span>  
  
<a name="MessageExchangePatterns"></a>
## <a name="message-exchange-patterns"></a><span data-ttu-id="40d28-118">Modelli di scambio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="40d28-118">Message Exchange Patterns</span></span>  
 <span data-ttu-id="40d28-119">Per scrivere un trasporto personalizzato, è necessario innanzitutto stabilire quali modelli di scambio dei messaggi (o MEP, Message Exchange Pattern) sono necessari per il trasporto.</span><span class="sxs-lookup"><span data-stu-id="40d28-119">The first step in writing a custom transport is to decide which Message Exchange Patterns (MEPs) are required for the transport.</span></span> <span data-ttu-id="40d28-120">Sono disponibili tre modelli di scambio dei messaggi:</span><span class="sxs-lookup"><span data-stu-id="40d28-120">There are three MEPs to choose from:</span></span>  
  
- <span data-ttu-id="40d28-121">Datagramma (IInputChannel/IOutputChannel)</span><span class="sxs-lookup"><span data-stu-id="40d28-121">Datagram (IInputChannel/IOutputChannel)</span></span>  
  
     <span data-ttu-id="40d28-122">Quando si utilizza un modello datagramma, un client invia un messaggio utilizzando uno scambio di tipo "fire and forget".</span><span class="sxs-lookup"><span data-stu-id="40d28-122">When using a datagram MEP, a client sends a message using a "fire and forget" exchange.</span></span> <span data-ttu-id="40d28-123">Tale scambio richiede una conferma fuori banda di recapito con esito positivo.</span><span class="sxs-lookup"><span data-stu-id="40d28-123">A fire and forget exchange is one that requires out-of-band confirmation of successful delivery.</span></span> <span data-ttu-id="40d28-124">Il messaggio potrebbe infatti andare perso durante il transito e non raggiungere mai il servizio.</span><span class="sxs-lookup"><span data-stu-id="40d28-124">The message might be lost in transit and never reach the service.</span></span> <span data-ttu-id="40d28-125">Se l'operazione di invio viene completata correttamente sul lato client, non c'è garanzia che l'endpoint remoto abbia ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="40d28-125">If the send operation completes successfully at the client end, it does not guarantee that the remote endpoint has received the message.</span></span> <span data-ttu-id="40d28-126">Il datagramma è un componente fondamentale per i messaggi, poiché sulla sua base è possibile compilare protocolli propri, tra cui protocolli affidabili e protocolli sicuri.</span><span class="sxs-lookup"><span data-stu-id="40d28-126">The datagram is a fundamental building block for messaging, as you can build your own protocols on top of it—including reliable protocols and secure protocols.</span></span> <span data-ttu-id="40d28-127">I canali del datagramma del client implementano l'interfaccia <xref:System.ServiceModel.Channels.IOutputChannel>, mentre i canali del datagramma del servizio implementano l'interfaccia <xref:System.ServiceModel.Channels.IInputChannel>.</span><span class="sxs-lookup"><span data-stu-id="40d28-127">Client datagram channels implement the <xref:System.ServiceModel.Channels.IOutputChannel> interface and service datagram channels implement the <xref:System.ServiceModel.Channels.IInputChannel> interface.</span></span>  
  
- <span data-ttu-id="40d28-128">Richiesta-risposta (IRequestChannel/IReplyChannel)</span><span class="sxs-lookup"><span data-stu-id="40d28-128">Request-Response (IRequestChannel/IReplyChannel)</span></span>  
  
     <span data-ttu-id="40d28-129">In questo modello di scambio, viene inviato un messaggio e viene ricevuta una risposta.</span><span class="sxs-lookup"><span data-stu-id="40d28-129">In this MEP, a message is sent, and a reply is received.</span></span> <span data-ttu-id="40d28-130">Il modello è costituito da coppie richiesta-risposta.</span><span class="sxs-lookup"><span data-stu-id="40d28-130">The pattern consists of request-response pairs.</span></span> <span data-ttu-id="40d28-131">Esempi di chiamate richiesta-risposta sono le chiamate RPC (Remote Procedure Call, chiamata a procedura remota) e le richieste GETs del browser.</span><span class="sxs-lookup"><span data-stu-id="40d28-131">Examples of request-response calls are remote procedure calls (RPC) and browser GETs.</span></span> <span data-ttu-id="40d28-132">Questo modello è anche noto come half-duplex.</span><span class="sxs-lookup"><span data-stu-id="40d28-132">This pattern is also known as Half-Duplex.</span></span> <span data-ttu-id="40d28-133">In tale modello, i canali client implementano l'interfaccia <xref:System.ServiceModel.Channels.IRequestChannel>, mentre i canali del servizio implementano l'interfaccia <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="40d28-133">In this MEP, client channels implement <xref:System.ServiceModel.Channels.IRequestChannel> and service channels implement <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span>  
  
- <span data-ttu-id="40d28-134">Duplex (IDuplexChannel)</span><span class="sxs-lookup"><span data-stu-id="40d28-134">Duplex (IDuplexChannel)</span></span>  
  
     <span data-ttu-id="40d28-135">Il modello di scambio duplex consente l'invio di un numero arbitrario di messaggi da parte di un client e la ricezione in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="40d28-135">The duplex MEP allows an arbitrary number of messages to be sent by a client and received in any order.</span></span> <span data-ttu-id="40d28-136">Tale modello è simile a una conversazione telefonica, in cui ogni parola pronunciata è un messaggio.</span><span class="sxs-lookup"><span data-stu-id="40d28-136">The duplex MEP is like a phone conversation, where each word being spoken is a message.</span></span> <span data-ttu-id="40d28-137">Poiché in questo modello i due lati possono entrambi inviare e ricevere messaggi, l'interfaccia implementata dai canali client e del servizio è <xref:System.ServiceModel.Channels.IDuplexChannel>.</span><span class="sxs-lookup"><span data-stu-id="40d28-137">Because both sides can send and receive in this MEP, the interface implemented by the client and service channels is <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
 <span data-ttu-id="40d28-138">Ognuno di questi modelli può inoltre supportare sessioni.</span><span class="sxs-lookup"><span data-stu-id="40d28-138">Each of these MEPs can also support sessions.</span></span> <span data-ttu-id="40d28-139">La funzionalità aggiuntiva fornita da un canale con supporto della sessione è che correla tutti i messaggi inviati e ricevuti su un canale.</span><span class="sxs-lookup"><span data-stu-id="40d28-139">The added functionality provided by a session-aware channel is that it correlates all messages sent and received on a channel.</span></span> <span data-ttu-id="40d28-140">Il modello richiesta-risposta è una sessione autonoma a due messaggi, poiché la richiesta e la risposta sono correlate.</span><span class="sxs-lookup"><span data-stu-id="40d28-140">The Request-Response pattern is a stand-alone two-message session, as the request and reply are correlated.</span></span> <span data-ttu-id="40d28-141">Il modello request/response che supporta sessioni implica invece che tutte le coppie request/response nel canale siano correlate le une alle altre.</span><span class="sxs-lookup"><span data-stu-id="40d28-141">In contrast, the Request-Response pattern that supports sessions implies that all request/response pairs on that channel are correlated with each other.</span></span> <span data-ttu-id="40d28-142">Gli dà un totale di sei modelli tra cui scegliere: Datagramma, Richiesta-risposta, Duplex, Datagramma con sessioni, Richiesta-Risposta con sessioni e Duplex con sessioni.</span><span class="sxs-lookup"><span data-stu-id="40d28-142">This gives you a total of six MEPs—Datagram, Request-Response, Duplex, Datagram with sessions, Request-Response with sessions, and Duplex with sessions—to choose from.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40d28-143">Per il trasporto UDP, l'unico modello di scambio dei messaggi supportato è il datagramma, poiché il protocollo UPD è di tipo "fire and forget".</span><span class="sxs-lookup"><span data-stu-id="40d28-143">For the UDP transport, the only MEP that is supported is Datagram, because UDP is inherently a "fire and forget" protocol.</span></span>  
  
### <a name="the-icommunicationobject-and-the-wcf-object-lifecycle"></a><span data-ttu-id="40d28-144">Ciclo di vita di  ICommunicationObject e dell'oggetto WCF</span><span class="sxs-lookup"><span data-stu-id="40d28-144">The ICommunicationObject and the WCF object lifecycle</span></span>  
 <span data-ttu-id="40d28-145">WCF dispone di una macchina a stati comune utilizzata per gestire il ciclo di vita di oggetti quali <xref:System.ServiceModel.Channels.IChannel> , <xref:System.ServiceModel.Channels.IChannelFactory> e <xref:System.ServiceModel.Channels.IChannelListener> utilizzati per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-145">WCF has a common state machine that is used for managing the lifecycle of objects like <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory>, and <xref:System.ServiceModel.Channels.IChannelListener> that are used for communication.</span></span> <span data-ttu-id="40d28-146">Ci sono cinque stati in cui questi oggetti di comunicazione possono esistere.</span><span class="sxs-lookup"><span data-stu-id="40d28-146">There are five states in which these communication objects can exist.</span></span> <span data-ttu-id="40d28-147">Questi stati sono rappresentati dall'enumerazione <xref:System.ServiceModel.CommunicationState> e sono elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="40d28-147">These states are represented by the <xref:System.ServiceModel.CommunicationState> enumeration, and are as follows:</span></span>  
  
- <span data-ttu-id="40d28-148">Creato: questo è lo stato di un oggetto <xref:System.ServiceModel.ICommunicationObject> quando viene creato come istanza.</span><span class="sxs-lookup"><span data-stu-id="40d28-148">Created: This is the state of a <xref:System.ServiceModel.ICommunicationObject> when it is first instantiated.</span></span> <span data-ttu-id="40d28-149">In questo stato non può aver luogo alcun input o output (I/O).</span><span class="sxs-lookup"><span data-stu-id="40d28-149">No input/output (I/O) occurs in this state.</span></span>  
  
- <span data-ttu-id="40d28-150">Apertura: gli oggetti passano a questo stato quando viene chiamato il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="40d28-150">Opening: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="40d28-151">In questa fase le proprietà diventano immutabili e l'input/output può iniziare.</span><span class="sxs-lookup"><span data-stu-id="40d28-151">At this point properties are made immutable, and input/output can begin.</span></span> <span data-ttu-id="40d28-152">Tale transizione è valida solo dallo stato Creato.</span><span class="sxs-lookup"><span data-stu-id="40d28-152">This transition is valid only from the Created state.</span></span>  
  
- <span data-ttu-id="40d28-153">Aperto: gli oggetti passano a questo stato al termine del processo di apertura.</span><span class="sxs-lookup"><span data-stu-id="40d28-153">Opened: Objects transition to this state when the open process completes.</span></span> <span data-ttu-id="40d28-154">Tale transizione è valida solo dallo stato Apertura.</span><span class="sxs-lookup"><span data-stu-id="40d28-154">This transition is valid only from the Opening state.</span></span> <span data-ttu-id="40d28-155">In questa fase, l'oggetto è pienamente utilizzabile per il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="40d28-155">At this point, the object is fully usable for transfer.</span></span>  
  
- <span data-ttu-id="40d28-156">Chiusura: gli oggetti passano a questo stato quando viene chiamato il metodo <xref:System.ServiceModel.ICommunicationObject.Close%2A> per un arresto normale.</span><span class="sxs-lookup"><span data-stu-id="40d28-156">Closing: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Close%2A> is called for a graceful shutdown.</span></span> <span data-ttu-id="40d28-157">Tale transizione è valida solo dallo stato Aperto.</span><span class="sxs-lookup"><span data-stu-id="40d28-157">This transition is valid only from the Opened state.</span></span>  
  
- <span data-ttu-id="40d28-158">Chiuso: gli oggetti con stato Chiuso nono sono più utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="40d28-158">Closed: In the Closed state objects are no longer usable.</span></span> <span data-ttu-id="40d28-159">In generale, la configurazione è ancora accessibile per essere esaminata, ma non può verificarsi nessuna comunicazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-159">In general, most configuration is still accessible for inspection, but no communication can occur.</span></span> <span data-ttu-id="40d28-160">Questo stato è equivalente all'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-160">This state is equivalent to being disposed.</span></span>  
  
- <span data-ttu-id="40d28-161">Non riuscito: nello stato Non riuscito, gli oggetti sono accessibili per essere esaminati ma non sono più utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="40d28-161">Faulted: In the Faulted state, objects are accessible to inspection but no longer usable.</span></span> <span data-ttu-id="40d28-162">Quando si verifica un errore irreversibile, l'oggetto passa a questo stato.</span><span class="sxs-lookup"><span data-stu-id="40d28-162">When a non-recoverable error occurs, the object transitions into this state.</span></span> <span data-ttu-id="40d28-163">L'unica transizione valida da questo stato è nello `Closed` stato.</span><span class="sxs-lookup"><span data-stu-id="40d28-163">The only valid transition from this state is into the `Closed` state.</span></span>  
  
 <span data-ttu-id="40d28-164">Ci sono eventi che generano per ogni passaggio di stato.</span><span class="sxs-lookup"><span data-stu-id="40d28-164">There are events that fire for each state transition.</span></span> <span data-ttu-id="40d28-165">Il metodo <xref:System.ServiceModel.ICommunicationObject.Abort%2A> può essere chiamato in ogni momento, esso fa in modo che l'oggetto passi immediatamente allo stato Chiuso.</span><span class="sxs-lookup"><span data-stu-id="40d28-165">The <xref:System.ServiceModel.ICommunicationObject.Abort%2A> method can be called at any time, and causes the object to transition immediately from its current state into the Closed state.</span></span> <span data-ttu-id="40d28-166">Una chiamata al metodo <xref:System.ServiceModel.ICommunicationObject.Abort%2A> termina qualsiasi lavoro non finito.</span><span class="sxs-lookup"><span data-stu-id="40d28-166">Calling <xref:System.ServiceModel.ICommunicationObject.Abort%2A> terminates any unfinished work.</span></span>  
  
<a name="ChannelAndChannelListener"></a>
## <a name="channel-factory-and-channel-listener"></a><span data-ttu-id="40d28-167">Channel factory e listener del canale</span><span class="sxs-lookup"><span data-stu-id="40d28-167">Channel Factory and Channel Listener</span></span>  
 <span data-ttu-id="40d28-168">Il passaggio successivo per scrivere un trasporto TCP personalizzato consiste nel creare un'implementazione di <xref:System.ServiceModel.Channels.IChannelFactory> per i canali client e di <xref:System.ServiceModel.Channels.IChannelListener> per i canali del servizio.</span><span class="sxs-lookup"><span data-stu-id="40d28-168">The next step in writing a custom transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span> <span data-ttu-id="40d28-169">Il livello del canale usa un modello della factory per costruire canali.</span><span class="sxs-lookup"><span data-stu-id="40d28-169">The channel layer uses a factory pattern for constructing channels.</span></span> <span data-ttu-id="40d28-170">WCF fornisce helper della classe di base per questo processo.</span><span class="sxs-lookup"><span data-stu-id="40d28-170">WCF provides base class helpers for this process.</span></span>  
  
- <span data-ttu-id="40d28-171">La classe <xref:System.ServiceModel.Channels.CommunicationObject> implementa <xref:System.ServiceModel.ICommunicationObject> e attiva la macchina a stati precedentemente descritta nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="40d28-171">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine previously described in Step 2.</span></span>

- <span data-ttu-id="40d28-172">La <xref:System.ServiceModel.Channels.ChannelManagerBase> classe implementa <xref:System.ServiceModel.Channels.CommunicationObject> e fornisce una classe base unificata per <xref:System.ServiceModel.Channels.ChannelFactoryBase> e <xref:System.ServiceModel.Channels.ChannelListenerBase> .</span><span class="sxs-lookup"><span data-stu-id="40d28-172">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase> and <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span></span> <span data-ttu-id="40d28-173">La classe <xref:System.ServiceModel.Channels.ChannelManagerBase> opera unitamente alla classe <xref:System.ServiceModel.Channels.ChannelBase>, una classe di base che implementa l'interfaccia <xref:System.ServiceModel.Channels.IChannel>.</span><span class="sxs-lookup"><span data-stu-id="40d28-173">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>  
  
- <span data-ttu-id="40d28-174">La <xref:System.ServiceModel.Channels.ChannelFactoryBase> classe implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> e <xref:System.ServiceModel.Channels.IChannelFactory> e consolida gli `CreateChannel` Overload in un unico `OnCreateChannel` metodo astratto.</span><span class="sxs-lookup"><span data-stu-id="40d28-174">The <xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>  
  
- <span data-ttu-id="40d28-175">La <xref:System.ServiceModel.Channels.ChannelListenerBase> classe implementa <xref:System.ServiceModel.Channels.IChannelListener> .</span><span class="sxs-lookup"><span data-stu-id="40d28-175">The <xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="40d28-176">Si occupa della gestione dello stato di base.</span><span class="sxs-lookup"><span data-stu-id="40d28-176">It takes care of basic state management.</span></span>  
  
 <span data-ttu-id="40d28-177">In questo esempio, l'implementazione della factory è contenuta in UdpChannelFactory.cs e l'implementazione del listener è contenuta in UdpChannelListener.cs.</span><span class="sxs-lookup"><span data-stu-id="40d28-177">In this sample, the factory implementation is contained in UdpChannelFactory.cs and the listener implementation is contained in UdpChannelListener.cs.</span></span> <span data-ttu-id="40d28-178">Le implementazioni di <xref:System.ServiceModel.Channels.IChannel> sono in UdpOutputChannel.cs e UdpInputChannel.cs.</span><span class="sxs-lookup"><span data-stu-id="40d28-178">The <xref:System.ServiceModel.Channels.IChannel> implementations are in UdpOutputChannel.cs and UdpInputChannel.cs.</span></span>  
  
### <a name="the-udp-channel-factory"></a><span data-ttu-id="40d28-179">Channel factory UDP</span><span class="sxs-lookup"><span data-stu-id="40d28-179">The UDP Channel Factory</span></span>  
 <span data-ttu-id="40d28-180">`UdpChannelFactory` deriva da <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span><span class="sxs-lookup"><span data-stu-id="40d28-180">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="40d28-181">L'esempio esegue l'override di <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> per fornire accesso alla versione del messaggio del codificatore di messaggi.</span><span class="sxs-lookup"><span data-stu-id="40d28-181">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="40d28-182">L'esempio esegue inoltre l'override di <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> per chiudere l'istanza di <xref:System.ServiceModel.Channels.BufferManager> quando la macchina a stati esegue la transizione.</span><span class="sxs-lookup"><span data-stu-id="40d28-182">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> so that we can tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="40d28-183">Canale di output UDP</span><span class="sxs-lookup"><span data-stu-id="40d28-183">The UDP Output Channel</span></span>  
 <span data-ttu-id="40d28-184">`UdpOutputChannel` implementa <xref:System.ServiceModel.Channels.IOutputChannel>.</span><span class="sxs-lookup"><span data-stu-id="40d28-184">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="40d28-185">Il costruttore convalida gli argomenti e costruisce un oggetto <xref:System.Net.EndPoint> di destinazione basato sull'elemento <xref:System.ServiceModel.EndpointAddress> che viene passato.</span><span class="sxs-lookup"><span data-stu-id="40d28-185">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
```csharp
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
```  
  
 <span data-ttu-id="40d28-186">Il canale può essere chiuso normalmente o in modo anomalo.</span><span class="sxs-lookup"><span data-stu-id="40d28-186">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="40d28-187">Se il canale viene chiuso normalmente, il socket viene chiuso e viene eseguita una chiamata al metodo `OnClose` della classe di base.</span><span class="sxs-lookup"><span data-stu-id="40d28-187">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="40d28-188">Se viene generata un'eccezione, l'infrastruttura chiama `Abort` per verificare che il canale sia pulito.</span><span class="sxs-lookup"><span data-stu-id="40d28-188">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```csharp
this.socket.Close(0);  
```  
  
 <span data-ttu-id="40d28-189">Vengono quindi implementati `Send()` e `BeginSend()` / `EndSend()` .</span><span class="sxs-lookup"><span data-stu-id="40d28-189">We then implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="40d28-190">In questo modo si ottengono due sezioni principali.</span><span class="sxs-lookup"><span data-stu-id="40d28-190">This breaks down into two main sections.</span></span> <span data-ttu-id="40d28-191">Prima serializzare il messaggio in una matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="40d28-191">First we serialize the message into a byte array.</span></span>  
  
```csharp
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="40d28-192">Inviare quindi i dati risultanti sulla rete.</span><span class="sxs-lookup"><span data-stu-id="40d28-192">Then we send the resulting data on the wire.</span></span>  
  
```csharp
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### <a name="the-udpchannellistener"></a><span data-ttu-id="40d28-193">Listener canale UDP</span><span class="sxs-lookup"><span data-stu-id="40d28-193">The UdpChannelListener</span></span>  
 <span data-ttu-id="40d28-194">L'oggetto `UdpChannelListener` implementato dall'esempio deriva dalla <xref:System.ServiceModel.Channels.ChannelListenerBase> classe.</span><span class="sxs-lookup"><span data-stu-id="40d28-194">The `UdpChannelListener` that the sample implements derives from the <xref:System.ServiceModel.Channels.ChannelListenerBase> class.</span></span> <span data-ttu-id="40d28-195">Utilizza un solo socket UDP per ricevere datagrammi.</span><span class="sxs-lookup"><span data-stu-id="40d28-195">It uses a single UDP socket to receive datagrams.</span></span> <span data-ttu-id="40d28-196">Il metodo `OnOpen` riceve dati utilizzando il socket UDP in un ciclo asincrono.</span><span class="sxs-lookup"><span data-stu-id="40d28-196">The `OnOpen` method receives data using the UDP socket in an asynchronous loop.</span></span> <span data-ttu-id="40d28-197">I dati vengono quindi convertiti in messaggi utilizzando il sistema di codifica messaggi:</span><span class="sxs-lookup"><span data-stu-id="40d28-197">The data are then converted into messages using the Message Encoding Framework.</span></span>  
  
```csharp
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 <span data-ttu-id="40d28-198">Poiché lo stesso canale del datagramma rappresenta messaggi in arrivo da un certo numero di origini, `UdpChannelListener` è un listener singleton.</span><span class="sxs-lookup"><span data-stu-id="40d28-198">Because the same datagram channel represents messages that arrive from a number of sources, the `UdpChannelListener` is a singleton listener.</span></span> <span data-ttu-id="40d28-199">Esiste al massimo un elemento attivo associato a <xref:System.ServiceModel.Channels.IChannel> questo listener alla volta.</span><span class="sxs-lookup"><span data-stu-id="40d28-199">There is, at most, one active <xref:System.ServiceModel.Channels.IChannel> associated with this listener at a time.</span></span> <span data-ttu-id="40d28-200">Nell'esempio ne viene generato un altro solo se un canale restituito dal metodo `AcceptChannel` viene successivamente eliminato.</span><span class="sxs-lookup"><span data-stu-id="40d28-200">The sample generates another one only if a channel that is returned by the `AcceptChannel` method is subsequently disposed.</span></span> <span data-ttu-id="40d28-201">Quando un messaggio viene ricevuto, viene accodato in questo canale singleton.</span><span class="sxs-lookup"><span data-stu-id="40d28-201">When a message is received, it is enqueued into this singleton channel.</span></span>  
  
#### <a name="udpinputchannel"></a><span data-ttu-id="40d28-202">UdpInputChannel</span><span class="sxs-lookup"><span data-stu-id="40d28-202">UdpInputChannel</span></span>  
 <span data-ttu-id="40d28-203">La `UdpInputChannel` classe implementa `IInputChannel` .</span><span class="sxs-lookup"><span data-stu-id="40d28-203">The `UdpInputChannel` class implements `IInputChannel`.</span></span> <span data-ttu-id="40d28-204">È composta da una coda di messaggi in arrivo popolata dal socket di `UdpChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="40d28-204">It consists of a queue of incoming messages that is populated by the `UdpChannelListener`'s socket.</span></span> <span data-ttu-id="40d28-205">La coda di questi messaggi viene annullata dal metodo `IInputChannel.Receive`.</span><span class="sxs-lookup"><span data-stu-id="40d28-205">These messages are dequeued by the `IInputChannel.Receive` method.</span></span>  
  
<a name="AddingABindingElement"></a>
## <a name="adding-a-binding-element"></a><span data-ttu-id="40d28-206">Aggiunta di un elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-206">Adding a Binding Element</span></span>  
 <span data-ttu-id="40d28-207">Ora che le factory e i canali sono compilati, devono essere esposti al runtime di ServiceModel tramite un'associazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-207">Now that the factories and channels are built, we must expose them to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="40d28-208">Un'associazione è una raccolta di elementi di associazione che rappresentano lo stack di comunicazione associato a un indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="40d28-208">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="40d28-209">Ogni elemento dello stack è rappresentato da un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="40d28-209">Each element in the stack is represented by a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
 <span data-ttu-id="40d28-210">Nell'esempio, l'elemento di associazione è `UdpTransportBindingElement`, che deriva dalla classe <xref:System.ServiceModel.Channels.TransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="40d28-210">In the sample, the binding element is `UdpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="40d28-211">Esso esegue l'override dei metodi seguenti per compilare le factory associate all'associazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-211">It overrides the following methods to build the factories associated with our binding.</span></span>  
  
```csharp
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 <span data-ttu-id="40d28-212">Contiene inoltre membri per duplicare `BindingElement` e restituire lo schema (soap.udp).</span><span class="sxs-lookup"><span data-stu-id="40d28-212">It also contains members for cloning the `BindingElement` and returning our scheme (soap.udp).</span></span>  
  
## <a name="adding-metadata-support-for-a-transport-binding-element"></a><span data-ttu-id="40d28-213">Aggiunta del supporto dei metadati per un elemento di associazione del trasporto</span><span class="sxs-lookup"><span data-stu-id="40d28-213">Adding Metadata Support for a Transport Binding Element</span></span>  
 <span data-ttu-id="40d28-214">Per essere integrato in un sistema di metadati, il trasporto deve supportare sia l'importazione che l'esportazione di un criterio.</span><span class="sxs-lookup"><span data-stu-id="40d28-214">To integrate our transport into the metadata system, we must support both the import and export of policy.</span></span> <span data-ttu-id="40d28-215">In questo modo è possibile generare client dell'associazione tramite lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="40d28-215">This allows us to generate clients of our binding through the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="40d28-216">Aggiunta di supporto WSDL</span><span class="sxs-lookup"><span data-stu-id="40d28-216">Adding WSDL Support</span></span>  
 <span data-ttu-id="40d28-217">L'elemento di associazione del trasporto in un'associazione è responsabile dell'esportazione e importazione delle informazioni di indirizzamento nei metadati.</span><span class="sxs-lookup"><span data-stu-id="40d28-217">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="40d28-218">Quando si utilizza un'associazione SOAP, l'elemento di associazione del trasporto deve esportare anche un URI di trasporto corretto nei metadati.</span><span class="sxs-lookup"><span data-stu-id="40d28-218">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="40d28-219">Esportazione WSDL</span><span class="sxs-lookup"><span data-stu-id="40d28-219">WSDL Export</span></span>  
 <span data-ttu-id="40d28-220">Per esportare informazioni di indirizzamento, `UdpTransportBindingElement` implementa l'interfaccia `IWsdlExportExtension`.</span><span class="sxs-lookup"><span data-stu-id="40d28-220">To export addressing information the `UdpTransportBindingElement` implements the `IWsdlExportExtension` interface.</span></span> <span data-ttu-id="40d28-221">Il metodo `ExportEndpoint` aggiunge le informazioni di indirizzamento corrette alla porta WSDL.</span><span class="sxs-lookup"><span data-stu-id="40d28-221">The `ExportEndpoint` method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="40d28-222">L'implementazione di `UdpTransportBindingElement` del metodo `ExportEndpoint` esporta anche un URI di trasporto quando l'endpoint utilizza un'associazione SOAP.</span><span class="sxs-lookup"><span data-stu-id="40d28-222">The `UdpTransportBindingElement` implementation of the `ExportEndpoint` method also exports a transport URI when the endpoint uses a SOAP binding.</span></span>  
  
```csharp
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="40d28-223">Importazione WSDL</span><span class="sxs-lookup"><span data-stu-id="40d28-223">WSDL Import</span></span>  
 <span data-ttu-id="40d28-224">Per estendere il sistema di importazione WSDL in modo da gestire l'importazione degli indirizzi, aggiungere la configurazione seguente al file di configurazione per Svcutil.exe, come illustrato nel file Svcutil.exe.config:</span><span class="sxs-lookup"><span data-stu-id="40d28-224">To extend the WSDL import system to handle importing the addresses, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="40d28-225">Quando si esegue Svcutil.exe, esistono due opzioni per ottenere che Svcutil.exe carichi le estensioni di importazione WSDL:</span><span class="sxs-lookup"><span data-stu-id="40d28-225">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1. <span data-ttu-id="40d28-226">Puntare Svcutil. exe al file di configurazione usando/SvcutilConfig: \<file> .</span><span class="sxs-lookup"><span data-stu-id="40d28-226">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="40d28-227">Aggiungere la sezione di configurazione a Svcutil.exe.config nella stessa directory di Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="40d28-227">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="40d28-228">Il tipo `UdpBindingElementImporter` implementa l'interfaccia `IWsdlImportExtension`.</span><span class="sxs-lookup"><span data-stu-id="40d28-228">The `UdpBindingElementImporter` type implements the `IWsdlImportExtension` interface.</span></span> <span data-ttu-id="40d28-229">Il metodo `ImportEndpoint` importa l'indirizzo dalla porta WSDL.</span><span class="sxs-lookup"><span data-stu-id="40d28-229">The `ImportEndpoint` method imports the address from the WSDL port.</span></span>  
  
```csharp
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="40d28-230">Aggiunta del supporto dei criteri</span><span class="sxs-lookup"><span data-stu-id="40d28-230">Adding Policy Support</span></span>  
 <span data-ttu-id="40d28-231">L'elemento di associazione personalizzato è in grado di esportare asserzioni di criteri nell'associazione WSDL affinché un endpoint del servizio esprima le funzionalità di quell'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-231">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="40d28-232">Esportazione di criteri</span><span class="sxs-lookup"><span data-stu-id="40d28-232">Policy Export</span></span>  
 <span data-ttu-id="40d28-233">Il `UdpTransportBindingElement` tipo implementa `IPolicyExportExtension` per aggiungere il supporto per l'esportazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="40d28-233">The `UdpTransportBindingElement` type implements `IPolicyExportExtension` to add support for exporting policy.</span></span> <span data-ttu-id="40d28-234">Di conseguenza, `System.ServiceModel.MetadataExporter` include `UdpTransportBindingElement` nella generazione del criterio per qualsiasi associazione in cui è incluso.</span><span class="sxs-lookup"><span data-stu-id="40d28-234">As a result, `System.ServiceModel.MetadataExporter` includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="40d28-235">In `IPolicyExportExtension.ExportPolicy`, aggiungere un'asserzione per UDP e un'altra asserzione se il canale è in modalità multicast.</span><span class="sxs-lookup"><span data-stu-id="40d28-235">In `IPolicyExportExtension.ExportPolicy`, we add an assertion for UDP and another assertion if we are in multicast mode.</span></span> <span data-ttu-id="40d28-236">Ciò è dovuto al fatto che la modalità multicast influisce sul modo in cui viene costruito lo stack di comunicazione, pertanto deve essere coordinato tra entrambi i lati.</span><span class="sxs-lookup"><span data-stu-id="40d28-236">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
```csharp
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(
        UdpPolicyStrings.Prefix,
        UdpPolicyStrings.MulticastAssertion,
        UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 <span data-ttu-id="40d28-237">Dato che gli elementi di associazione di trasporto personalizzati sono responsabili della gestione dell'indirizzamento, l'implementazione di `IPolicyExportExtension` in `UdpTransportBindingElement` deve gestire anche l'esportazione delle asserzioni di criteri di WS-Addressing appropriate per indicare la versione di WS-Addressing utilizzata.</span><span class="sxs-lookup"><span data-stu-id="40d28-237">Because custom transport binding elements are responsible for handling addressing, the `IPolicyExportExtension` implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="40d28-238">Importazione di criteri</span><span class="sxs-lookup"><span data-stu-id="40d28-238">Policy Import</span></span>  
 <span data-ttu-id="40d28-239">Per estendere il sistema di importazione dei criteri, aggiungere la configurazione seguente al file di configurazione per Svcutil.exe, come illustrato nel file Svcutil.exe.config:</span><span class="sxs-lookup"><span data-stu-id="40d28-239">To extend the Policy Import system, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="40d28-240">Implementare quindi `IPolicyImporterExtension` dalla classe registrata (`UdpBindingElementImporter`).</span><span class="sxs-lookup"><span data-stu-id="40d28-240">Then we implement `IPolicyImporterExtension` from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="40d28-241">In `ImportPolicy()`, esaminare le asserzioni nello spazio dei nomi appropriato ed elaborare quelle per generare il trasporto e controllare se è multicast.</span><span class="sxs-lookup"><span data-stu-id="40d28-241">In `ImportPolicy()`, we look through the assertions in our namespace, and process the ones for generating the transport and check whether it is multicast.</span></span> <span data-ttu-id="40d28-242">Rimuovere inoltre dall'elenco delle asserzioni di associazione quelle gestite dall'importatore.</span><span class="sxs-lookup"><span data-stu-id="40d28-242">We also must remove the assertions we handle from the list of binding assertions.</span></span> <span data-ttu-id="40d28-243">Anche in questo caso, quando si esegue Svcutil.exe esistono due opzioni per l'integrazione:</span><span class="sxs-lookup"><span data-stu-id="40d28-243">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1. <span data-ttu-id="40d28-244">Puntare Svcutil. exe al file di configurazione usando/SvcutilConfig: \<file> .</span><span class="sxs-lookup"><span data-stu-id="40d28-244">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="40d28-245">Aggiungere la sezione di configurazione a Svcutil.exe.config nella stessa directory di Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="40d28-245">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
<a name="AddingAStandardBinding"></a>
## <a name="adding-a-standard-binding"></a><span data-ttu-id="40d28-246">Aggiunta di un elemento di associazione standard</span><span class="sxs-lookup"><span data-stu-id="40d28-246">Adding a Standard Binding</span></span>  
 <span data-ttu-id="40d28-247">L'elemento di associazione è utilizzabile nei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="40d28-247">Our binding element can be used in the following two ways:</span></span>  
  
- <span data-ttu-id="40d28-248">Tramite un'associazione personalizzata: un'associazione personalizzata consente all'utente di creare associazioni basate su un set arbitrario di elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-248">Through a custom binding: A custom binding allows the user to create their own binding based on an arbitrary set of binding elements.</span></span>  
  
- <span data-ttu-id="40d28-249">Utilizzando un'associazione fornita dal sistema che includa l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-249">By using a system-provided binding that includes our binding element.</span></span> <span data-ttu-id="40d28-250">In WCF sono disponibili diverse associazioni definite dal sistema, ad esempio `BasicHttpBinding` , `NetTcpBinding` e `WsHttpBinding` .</span><span class="sxs-lookup"><span data-stu-id="40d28-250">WCF provides a number of these system-defined bindings, such as `BasicHttpBinding`, `NetTcpBinding`, and `WsHttpBinding`.</span></span> <span data-ttu-id="40d28-251">Ognuna di queste associazioni è associata a un profilo ben definito.</span><span class="sxs-lookup"><span data-stu-id="40d28-251">Each of these bindings is associated with a well-defined profile.</span></span>  
  
 <span data-ttu-id="40d28-252">L'esempio implementa il profilo di associazione in `SampleProfileUdpBinding`, che deriva dalla classe <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="40d28-252">The sample implements profile binding in `SampleProfileUdpBinding`, which derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="40d28-253">`SampleProfileUdpBinding` contiene fino a quattro elementi di associazione al suo interno: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` e `ReliableSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="40d28-253">The `SampleProfileUdpBinding` contains up to four binding elements within it: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement`, and `ReliableSessionBindingElement`.</span></span>  
  
```csharp
public override BindingElementCollection CreateBindingElements()  
{
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="40d28-254">Aggiunta di un importatore di associazione standard personalizzato</span><span class="sxs-lookup"><span data-stu-id="40d28-254">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="40d28-255">Per impostazione predefinita, Svcutil.exe e il tipo `WsdlImporter` riconoscono e importano associazioni fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="40d28-255">Svcutil.exe and the `WsdlImporter` type, by default, recognizes and imports system-defined bindings.</span></span> <span data-ttu-id="40d28-256">In caso contrario, l'associazione viene importata come istanza `CustomBinding`.</span><span class="sxs-lookup"><span data-stu-id="40d28-256">Otherwise, the binding gets imported as a `CustomBinding` instance.</span></span> <span data-ttu-id="40d28-257">Per consentire a Svcutil.exe e a `WsdlImporter` di importare `SampleProfileUdpBinding`, `UdpBindingElementImporter` funge anche da importatore di associazione standard personalizzato.</span><span class="sxs-lookup"><span data-stu-id="40d28-257">To enable Svcutil.exe and the `WsdlImporter` to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="40d28-258">Un importatore di associazione standard personalizzato implementa il metodo `ImportEndpoint` nell'interfaccia `IWsdlImportExtension` per esaminare l'istanza `CustomBinding` importata dai metadati per controllare se poteva essere generata da un'associazione standard specifica.</span><span class="sxs-lookup"><span data-stu-id="40d28-258">A custom standard binding importer implements the `ImportEndpoint` method on the `IWsdlImportExtension` interface to examine the `CustomBinding` instance imported from metadata to see whether it could have been generated by a specific standard binding.</span></span>  
  
```csharp
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="40d28-259">In genere, l'implementazione di un importatore dell'associazione standard personalizzato implica il controllo delle proprietà degli elementi di associazione importati per verificare che siano cambiate solo le proprietà che avrebbero potuto essere impostate dall'associazione standard e che tutte le altre siano rimaste sulle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="40d28-259">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="40d28-260">Una strategia di base per l'implementazione di un importatore dell'associazione standard consiste nel creare un'istanza dell'associazione standard, propagare le proprietà dagli elementi di associazione all'istanza dell'associazione standard supportata dall'associazione standard e nel confrontare gli elementi di associazione dall'associazione standard con gli elementi di associazione importati.</span><span class="sxs-lookup"><span data-stu-id="40d28-260">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>  
  
<a name="AddingConfigurationSupport"></a>
## <a name="adding-configuration-support"></a><span data-ttu-id="40d28-261">Aggiunta del supporto di configurazione</span><span class="sxs-lookup"><span data-stu-id="40d28-261">Adding Configuration Support</span></span>  
 <span data-ttu-id="40d28-262">Per esporre il trasporto tramite configurazione si devono implementare due sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-262">To expose our transport through configuration, we must implement two configuration sections.</span></span> <span data-ttu-id="40d28-263">La prima è una classe `BindingElementExtensionElement` per `UdpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="40d28-263">The first is a `BindingElementExtensionElement` for `UdpTransportBindingElement`.</span></span> <span data-ttu-id="40d28-264">Serve per fare in modo che le implementazioni di `CustomBinding` possano fare riferimento all'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-264">This is so that `CustomBinding` implementations can reference our binding element.</span></span> <span data-ttu-id="40d28-265">La seconda è una `Configuration` per `SampleProfileUdpBinding`.</span><span class="sxs-lookup"><span data-stu-id="40d28-265">The second is a `Configuration` for our `SampleProfileUdpBinding`.</span></span>  
  
### <a name="binding-element-extension-element"></a><span data-ttu-id="40d28-266">Elemento di estensione dell'elemento di associazione</span><span class="sxs-lookup"><span data-stu-id="40d28-266">Binding Element Extension Element</span></span>  
 <span data-ttu-id="40d28-267">La sezione `UdpTransportElement` è una classe `BindingElementExtensionElement` che espone `UdpTransportBindingElement` al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-267">The section `UdpTransportElement` is a `BindingElementExtensionElement` that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="40d28-268">Con alcuni override di base, vengono definiti il nome della sezione di configurazione, il tipo dell'elemento di associazione e come creare l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-268">With a few basic overrides, we define our configuration section name, the type of our binding element and how to create our binding element.</span></span> <span data-ttu-id="40d28-269">Gli utenti possono quindi registrare la sezione di estensione in un file di configurazione come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="40d28-269">We can then register our extension section in a configuration file as shown in the following code.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport" />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="40d28-270">È possibile fare riferimento all'estensione da associazioni personalizzate per utilizzare UDP come trasporto.</span><span class="sxs-lookup"><span data-stu-id="40d28-270">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="binding-section"></a><span data-ttu-id="40d28-271">Sezione dell'associazione</span><span class="sxs-lookup"><span data-stu-id="40d28-271">Binding Section</span></span>  
 <span data-ttu-id="40d28-272">La sezione `SampleProfileUdpBindingCollectionElement` è una classe `StandardBindingCollectionElement` che espone `SampleProfileUdpBinding` al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-272">The section `SampleProfileUdpBindingCollectionElement` is a `StandardBindingCollectionElement` that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="40d28-273">La maggior parte dell'implementazione viene delegata a `SampleProfileUdpBindingConfigurationElement` che deriva da `StandardBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="40d28-273">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from `StandardBindingElement`.</span></span> <span data-ttu-id="40d28-274">`SampleProfileUdpBindingConfigurationElement`Dispone di proprietà che corrispondono alle proprietà in `SampleProfileUdpBinding` e alle funzioni di cui eseguire il mapping dall' `ConfigurationElement` associazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-274">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="40d28-275">Infine, viene eseguito l'override del metodo `OnApplyConfiguration` in `SampleProfileUdpBinding`, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="40d28-275">Finally, override the `OnApplyConfiguration` method in our `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
    if (binding == null)
        throw new ArgumentNullException("binding");

    if (binding.GetType() != typeof(SampleProfileUdpBinding))
    {
        throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,
            "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",
            typeof(SampleProfileUdpBinding).AssemblyQualifiedName,
            binding.GetType().AssemblyQualifiedName));
    }
    SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;

    udpBinding.OrderedSession = this.OrderedSession;
    udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;
    udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;
    if (this.ClientBaseAddress != null)
        udpBinding.ClientBaseAddress = ClientBaseAddress;
}
```  
  
 <span data-ttu-id="40d28-276">Per registrare questo gestore nel sistema di configurazione, aggiungere la sezione seguente al file di configurazione pertinente.</span><span class="sxs-lookup"><span data-stu-id="40d28-276">To register this handler with the configuration system, we add the following section to the relevant configuration file.</span></span>  
  
```xml
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
        <sectionGroup name="bindings">  
          <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
        </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 <span data-ttu-id="40d28-277">È possibile farvi riferimento dalla sezione di configurazione modello servizi.</span><span class="sxs-lookup"><span data-stu-id="40d28-277">It can then be referenced from the serviceModel configuration section.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="the-udp-test-service-and-client"></a><span data-ttu-id="40d28-278">UDP Test Service e client</span><span class="sxs-lookup"><span data-stu-id="40d28-278">The UDP Test Service and Client</span></span>  
 <span data-ttu-id="40d28-279">Il codice di test per l'utilizzo di questo trasporto di esempio è disponibile nelle directory UdpTestService e UdpTestClient.</span><span class="sxs-lookup"><span data-stu-id="40d28-279">Test code for using this sample transport is available in the UdpTestService and UdpTestClient directories.</span></span> <span data-ttu-id="40d28-280">Il codice servizio è costituito da due test. Il primo imposta associazioni ed endpoint tramite codice e l'altro lo fa tramite configurazione.</span><span class="sxs-lookup"><span data-stu-id="40d28-280">The service code consists of two tests—one test sets up bindings and endpoints from code and the other does it through configuration.</span></span> <span data-ttu-id="40d28-281">Entrambi i test utilizzano due endpoint.</span><span class="sxs-lookup"><span data-stu-id="40d28-281">Both tests use two endpoints.</span></span> <span data-ttu-id="40d28-282">Un endpoint USA `SampleUdpProfileBinding` con [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) impostato su `true` .</span><span class="sxs-lookup"><span data-stu-id="40d28-282">One endpoint uses the `SampleUdpProfileBinding` with [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) set to `true`.</span></span> <span data-ttu-id="40d28-283">L'altro endpoint utilizza un'associazione personalizzata con `UdpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="40d28-283">The other endpoint uses a custom binding with `UdpTransportBindingElement`.</span></span> <span data-ttu-id="40d28-284">Equivale a usare `SampleUdpProfileBinding` con [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) impostato su `false` .</span><span class="sxs-lookup"><span data-stu-id="40d28-284">This is equivalent to using `SampleUdpProfileBinding` with [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) set to `false`.</span></span> <span data-ttu-id="40d28-285">Entrambi i test creano un servizio, aggiungono un endpoint per ogni associazione, aprono il servizio e quindi aspettano che l'utente prema INVIO prima di chiudere il servizio.</span><span class="sxs-lookup"><span data-stu-id="40d28-285">Both tests create a service, add an endpoint for each binding, open the service and then wait for the user to hit ENTER before closing the service.</span></span>  
  
 <span data-ttu-id="40d28-286">Quando si avvia l'applicazione per testare il servizio, l'output sarà come segue:</span><span class="sxs-lookup"><span data-stu-id="40d28-286">When you start the service test application you should see the following output.</span></span>  
  
```console
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 <span data-ttu-id="40d28-287">È quindi possibile eseguire l'applicazione per testare il client sugli endpoint pubblicati.</span><span class="sxs-lookup"><span data-stu-id="40d28-287">You can then run the test client application against the published endpoints.</span></span> <span data-ttu-id="40d28-288">L'applicazione per testare il client crea un client per ogni endpoint e invia cinque messaggi a ogni endpoint.</span><span class="sxs-lookup"><span data-stu-id="40d28-288">The client test application creates a client for each endpoint and sends five messages to each endpoint.</span></span> <span data-ttu-id="40d28-289">Di seguito è riportato l'output del client.</span><span class="sxs-lookup"><span data-stu-id="40d28-289">The following output is on the client.</span></span>  
  
```console
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 <span data-ttu-id="40d28-290">Di seguito è riportato l'output completo del servizio.</span><span class="sxs-lookup"><span data-stu-id="40d28-290">The following is the full output on the service.</span></span>  
  
```console
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
   adding 0 + 0  
   adding 1 + 2  
   adding 2 + 4  
   adding 3 + 6  
   adding 4 + 8  
```  
  
 <span data-ttu-id="40d28-291">Per eseguire l'applicazione client su endpoint pubblicati utilizzando la configurazione, premere INVIO nel servizio e quindi eseguire nuovamente il client di prova.</span><span class="sxs-lookup"><span data-stu-id="40d28-291">To run the client application against endpoints published using configuration, hit ENTER on the service and then run the test client again.</span></span> <span data-ttu-id="40d28-292">Nel servizio, si dovrebbe vedere l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="40d28-292">You should see the following output on the service.</span></span>  
  
```console
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 <span data-ttu-id="40d28-293">Una nuova esecuzione del client restituisce gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="40d28-293">Running the client again yields the same as the preceding results.</span></span>  
  
 <span data-ttu-id="40d28-294">Per rigenerare il codice client e la configurazione tramite Svcutil.exe, avviare l'applicazione di servizio e quindi eseguire il seguente Svcutil.exe dalla directory radice dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="40d28-294">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe from the root directory of the sample.</span></span>  
  
```console
svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 <span data-ttu-id="40d28-295">Notare che Svcutil.exe non genera la configurazione di estensione di associazione per `SampleProfileUdpBinding`, quindi è necessario aggiungerla manualmente.</span><span class="sxs-lookup"><span data-stu-id="40d28-295">Note that Svcutil.exe does not generate the binding extension configuration for the `SampleProfileUdpBinding`, so you must add it manually.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>
    <extensions>  
      <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
      <bindingExtensions>  
        <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
      </bindingExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="40d28-296">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="40d28-296">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="40d28-297">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="40d28-297">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="40d28-298">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="40d28-298">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="40d28-299">Fare riferimento alla sezione precedente "UDP Test Service e client".</span><span class="sxs-lookup"><span data-stu-id="40d28-299">Refer to the preceding "The UDP Test Service and Client" section.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="40d28-300">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="40d28-300">The samples may already be installed on your machine.</span></span> <span data-ttu-id="40d28-301">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="40d28-301">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="40d28-302">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="40d28-302">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="40d28-303">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="40d28-303">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`
