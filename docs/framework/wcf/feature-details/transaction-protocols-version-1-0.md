---
title: Protocolli di transazione versione 1.0
ms.date: 03/30/2017
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
ms.openlocfilehash: a19329b56bb569a04195b38877a42d635996ff1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184383"
---
# <a name="transaction-protocols-version-10"></a><span data-ttu-id="d4b99-102">Protocolli di transazione versione 1.0</span><span class="sxs-lookup"><span data-stu-id="d4b99-102">Transaction Protocols version 1.0</span></span>
<span data-ttu-id="d4b99-103">Windows Communication Foundation (WCF) versione 1 implementa la versione 1.0 dei protocolli WS-Atomic Transaction e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="d4b99-103">Windows Communication Foundation (WCF) version 1 implements version 1.0 of the WS-Atomic Transaction and WS-Coordination protocols.</span></span> <span data-ttu-id="d4b99-104">Per ulteriori informazioni sulla versione 1.1, vedere Protocolli di [transazione](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="d4b99-104">For more information about version 1.1, see [Transaction Protocols](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span></span>  
  
|<span data-ttu-id="d4b99-105">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="d4b99-105">Specification/Document</span></span>|<span data-ttu-id="d4b99-106">Collegamento</span><span class="sxs-lookup"><span data-stu-id="d4b99-106">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="d4b99-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="d4b99-107">WS-Coordination</span></span>|<https://specs.xmlsoap.org/ws/2004/10/wscoor/wscoor.pdf>|  
|<span data-ttu-id="d4b99-108">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="d4b99-108">WS-AtomicTransaction</span></span>|<https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf>|  
  
 <span data-ttu-id="d4b99-109">Su queste specifiche del protocollo è richiesta l'interoperabilità a due livelli: tra le applicazioni e tra i gestori delle transazioni (vedere la figura seguente).</span><span class="sxs-lookup"><span data-stu-id="d4b99-109">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="d4b99-110">Le specifiche descrivono dettagliatamente i formati dei messaggi e lo scambio di messaggi per entrambi i livelli di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="d4b99-110">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="d4b99-111">Alcune protezioni, affidabilità e codifiche per lo scambio tra le applicazioni si applicano come per il normale scambio tra applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d4b99-111">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="d4b99-112">Perché, tuttavia, sia possibile l'interoperabilità tra i gestori delle transazioni, è necessario che vi sia un accordo sull'associazione interessata dato che in genere non è configurata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d4b99-112">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="d4b99-113">In questo argomento vengono illustrate una composizione della specifica WS-Atomic Transaction (WS-AT) con protezione e l'associazione protetta per la comunicazione tra i gestori di transazioni.</span><span class="sxs-lookup"><span data-stu-id="d4b99-113">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="d4b99-114">L'approccio descritto in questo documento è stato testato con successo con altre implementazioni di WS-AT e WS-Coordination, compresi IBM, IONA, Sun Microsystems e altri.</span><span class="sxs-lookup"><span data-stu-id="d4b99-114">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="d4b99-115">Nella figura seguente viene illustrata l'interoperabilità tra due gestori delle transazioni, Transaction Manager 1 e Transaction Manager 2, e due applicazioni, Application 1 e Application 2:</span><span class="sxs-lookup"><span data-stu-id="d4b99-115">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![Screenshot che mostra l'interazione tra gestori di transazioni.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="d4b99-117">Si consideri un tipico scenario WS-Coordination/WS-Atomic Transaction con un Iniziatore (I) e un Partecipante (P).</span><span class="sxs-lookup"><span data-stu-id="d4b99-117">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="d4b99-118">Sia l'Iniziatore che il Partecipante hanno gestori transazioni (ITM e PTM, rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="d4b99-118">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="d4b99-119">In questo argomento, il commit in due fasi viene chiamato 2PC.</span><span class="sxs-lookup"><span data-stu-id="d4b99-119">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4b99-120">1. CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="d4b99-120">1. CreateCoordinationContext</span></span>|<span data-ttu-id="d4b99-121">12. Risposta ai messaggi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d4b99-121">12. Application Message Response</span></span>|  
|<span data-ttu-id="d4b99-122">2. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="d4b99-122">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="d4b99-123">13. Commit (completamento)</span><span class="sxs-lookup"><span data-stu-id="d4b99-123">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="d4b99-124">3. Registrati (Completamento)</span><span class="sxs-lookup"><span data-stu-id="d4b99-124">3. Register (Completion)</span></span>|<span data-ttu-id="d4b99-125">14. Preparazione (2PC)</span><span class="sxs-lookup"><span data-stu-id="d4b99-125">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="d4b99-126">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="d4b99-126">4. RegisterResponse</span></span>|<span data-ttu-id="d4b99-127">15. Preparazione (2PC)</span><span class="sxs-lookup"><span data-stu-id="d4b99-127">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="d4b99-128">5. Messaggio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d4b99-128">5. Application Message</span></span>|<span data-ttu-id="d4b99-129">16. Preparato (2PC)</span><span class="sxs-lookup"><span data-stu-id="d4b99-129">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="d4b99-130">6. CreateCoordinationContext con contesto</span><span class="sxs-lookup"><span data-stu-id="d4b99-130">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="d4b99-131">17. Preparato (2PC)</span><span class="sxs-lookup"><span data-stu-id="d4b99-131">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="d4b99-132">7. Registrati (Durable)</span><span class="sxs-lookup"><span data-stu-id="d4b99-132">7. Register (Durable)</span></span>|<span data-ttu-id="d4b99-133">18. Impegnato (Completamento)</span><span class="sxs-lookup"><span data-stu-id="d4b99-133">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="d4b99-134">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="d4b99-134">8. RegisterResponse</span></span>|<span data-ttu-id="d4b99-135">19. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="d4b99-135">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="d4b99-136">9. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="d4b99-136">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="d4b99-137">20. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="d4b99-137">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="d4b99-138">10. Registro (durable)</span><span class="sxs-lookup"><span data-stu-id="d4b99-138">10. Register (Durable)</span></span>|<span data-ttu-id="d4b99-139">21. Impegnato (2PC)</span><span class="sxs-lookup"><span data-stu-id="d4b99-139">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="d4b99-140">11. Risposta di Registro</span><span class="sxs-lookup"><span data-stu-id="d4b99-140">11. RegisterResponse</span></span>|<span data-ttu-id="d4b99-141">22. Impegnato (2PC)</span><span class="sxs-lookup"><span data-stu-id="d4b99-141">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="d4b99-142">In questo documento vengono illustrate una composizione della specifica WS-AtomicTransaction con protezione e l'associazione protetta per la comunicazione tra i gestori di transazioni.</span><span class="sxs-lookup"><span data-stu-id="d4b99-142">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="d4b99-143">L'approccio descritto in questo documento è stato testato con successo con altre implementazioni di WS-AT e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="d4b99-143">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="d4b99-144">Nella figura e nella tabella vengono illustrate quattro classi di messaggi dal punto di vista della protezione:</span><span class="sxs-lookup"><span data-stu-id="d4b99-144">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="d4b99-145">Messaggi di attivazione (CreateCoordinationContext e CreateCoordinationContextResponse).</span><span class="sxs-lookup"><span data-stu-id="d4b99-145">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="d4b99-146">Messaggi di registrazione (Register e RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="d4b99-146">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="d4b99-147">Messaggi di protocollo (Prepare, Rollback, Commit, Aborted e così via).</span><span class="sxs-lookup"><span data-stu-id="d4b99-147">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="d4b99-148">Messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4b99-148">Application messages.</span></span>  
  
 <span data-ttu-id="d4b99-149">Le prime tre classi di messaggi sono considerate messaggi del gestore transazioni e la loro configurazione dell'associazione viene descritta in "Scambio di messaggi dell'applicazione", più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d4b99-149">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="d4b99-150">La quarta classe di messaggi riguarda i messaggi da applicazione ad applicazione e viene descritta nella sezione "Esempi di messaggi", più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d4b99-150">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="d4b99-151">In questa sezione vengono descritte le associazioni di protocollo utilizzate per ognuna di queste classi da WCF.</span><span class="sxs-lookup"><span data-stu-id="d4b99-151">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="d4b99-152">In questo documento vengono utilizzati gli spazi dei nomi XML e i relativi prefissi associati seguenti.</span><span class="sxs-lookup"><span data-stu-id="d4b99-152">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="d4b99-153">Prefisso</span><span class="sxs-lookup"><span data-stu-id="d4b99-153">Prefix</span></span>|<span data-ttu-id="d4b99-154">URI dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d4b99-154">Namespace URI</span></span>|  
|------------|-------------------|  
|<span data-ttu-id="d4b99-155">s11</span><span class="sxs-lookup"><span data-stu-id="d4b99-155">s11</span></span>|http://schemas.xmlsoap.org/soap/envelope|  
|<span data-ttu-id="d4b99-156">wsa</span><span class="sxs-lookup"><span data-stu-id="d4b99-156">wsa</span></span>|http://www.w3.org/2004/08/addressing|  
|<span data-ttu-id="d4b99-157">wscoor</span><span class="sxs-lookup"><span data-stu-id="d4b99-157">wscoor</span></span>|http://schemas.xmlsoap.org/ws/2004/10/wscoor|  
|<span data-ttu-id="d4b99-158">wsat</span><span class="sxs-lookup"><span data-stu-id="d4b99-158">wsat</span></span>|http://schemas.xmlsoap.org/ws/2004/10/wsat|  
|<span data-ttu-id="d4b99-159">t</span><span class="sxs-lookup"><span data-stu-id="d4b99-159">t</span></span>|http://schemas.xmlsoap.org/ws/2005/02/trust|  
|<span data-ttu-id="d4b99-160">o</span><span class="sxs-lookup"><span data-stu-id="d4b99-160">o</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="d4b99-161">xsd</span><span class="sxs-lookup"><span data-stu-id="d4b99-161">xsd</span></span>|http://www.w3.org/2001/XMLSchema|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="d4b99-162">Associazioni dei gestori transazioni</span><span class="sxs-lookup"><span data-stu-id="d4b99-162">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="d4b99-163">R1001: i gestori transazioni devono utilizzare SOAP 1.1 e WS-Addressing 2004/08 per gli scambi di messaggi WS-Atomic Transaction e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="d4b99-163">R1001: Transaction Managers must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="d4b99-164">I messaggi dell'applicazione non sono vincolati a queste associazioni e vengono descritti più avanti.</span><span class="sxs-lookup"><span data-stu-id="d4b99-164">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="d4b99-165">Associazione HTTP dei gestori transazioni</span><span class="sxs-lookup"><span data-stu-id="d4b99-165">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="d4b99-166">L'associazione HTTPS dei gestori transazioni si basa unicamente sulla protezione del trasporto per ottenere la protezione e stabilire relazioni di trust tra ogni coppia mittente-destinatario nell'albero delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="d4b99-166">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="d4b99-167">Configurazione di trasporto HTTPS</span><span class="sxs-lookup"><span data-stu-id="d4b99-167">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="d4b99-168">I certificati X.509 sono utilizzati per stabilire l'identità del gestore transazioni.</span><span class="sxs-lookup"><span data-stu-id="d4b99-168">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="d4b99-169">L'autenticazione client/server è obbligatoria, mentre l'autorizzazione client/server viene lasciata come dettaglio di implementazione:</span><span class="sxs-lookup"><span data-stu-id="d4b99-169">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="d4b99-170">R1111: i certificati X.509 presentati sulla rete devono avere un nome soggetto che corrisponde al nome di dominio completo (FQDN) del computer di origine.</span><span class="sxs-lookup"><span data-stu-id="d4b99-170">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="d4b99-171">B1112: perché i controlli del nome soggetto X.509 abbiano esito positivo, il DNS deve essere funzionale tra ogni coppia mittente-destinatario nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d4b99-171">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="d4b99-172">Attivazione e configurazione dell'associazione di registrazione</span><span class="sxs-lookup"><span data-stu-id="d4b99-172">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="d4b99-173">WCF richiede l'associazione duplex richiesta/risposta con correlazione su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d4b99-173">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="d4b99-174">Per ulteriori informazioni sulla correlazione e descrizioni dei modelli di scambio dei messaggi request/reply, vedere WS-Atomic Transaction, Sezione 8.</span><span class="sxs-lookup"><span data-stu-id="d4b99-174">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="d4b99-175">Configurazione del binding del protocollo 2PC</span><span class="sxs-lookup"><span data-stu-id="d4b99-175">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="d4b99-176">WCF supporta i messaggi unidirezionali (datagramma) su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d4b99-176">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="d4b99-177">La correlazione tra i messaggi viene lasciata come dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d4b99-177">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="d4b99-178">B2131: le implementazioni devono supportare `wsa:ReferenceParameters` come descritto in WS-Addressing per ottenere la correlazione dei messaggi 2PC di WCF.</span><span class="sxs-lookup"><span data-stu-id="d4b99-178">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="d4b99-179">Associazione di sicurezza mista del gestore transazioni</span><span class="sxs-lookup"><span data-stu-id="d4b99-179">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="d4b99-180">Si tratta di un'associazione alternativa (modalità mista) che utilizza la sicurezza del trasporto combinata con il modello WS-Coordination Issued Token per scopi di imposizione.</span><span class="sxs-lookup"><span data-stu-id="d4b99-180">This is an alternate (mixed mode) binding that uses transport security combined with the  WS-Coordination Issued Token model for identity establishment purposes.</span></span>  <span data-ttu-id="d4b99-181">L'attivazione e la registrazione sono gli unici elementi che differiscono tra le due associazioni.</span><span class="sxs-lookup"><span data-stu-id="d4b99-181">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="d4b99-182">Configurazione di trasporto HTTPS</span><span class="sxs-lookup"><span data-stu-id="d4b99-182">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="d4b99-183">I certificati X.509 sono utilizzati per stabilire l'identità del gestore transazioni.</span><span class="sxs-lookup"><span data-stu-id="d4b99-183">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="d4b99-184">L'autenticazione client/server è obbligatoria, mentre l'autorizzazione client/server viene lasciata come dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d4b99-184">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="d4b99-185">Configurazione dell'associazione dei messaggi di attivazione</span><span class="sxs-lookup"><span data-stu-id="d4b99-185">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="d4b99-186">I messaggi di attivazione in genere non partecipano all'interoperabilità perché si verificano normalmente tra un'applicazione e il suo gestore transazioni locale.</span><span class="sxs-lookup"><span data-stu-id="d4b99-186">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="d4b99-187">B1221: WCF utilizza l'associazione HTTPS duplex (descritta in Protocolli di [messaggistica](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) per i messaggi di attivazione.</span><span class="sxs-lookup"><span data-stu-id="d4b99-187">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="d4b99-188">I messaggi di richiesta e risposta sono correlati utilizzando WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="d4b99-188">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="d4b99-189">La specifica WS-Atomic Transaction, Sezione 8, descrive ulteriori dettagli sulla correlazione e sui modelli di scambio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d4b99-189">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="d4b99-190">R1222: alla ricezione di un `CreateCoordinationContext`, il coordinatore deve emettere un `SecurityContextToken` con il segreto `STx` associato.</span><span class="sxs-lookup"><span data-stu-id="d4b99-190">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="d4b99-191">Tale token viene restituito in un'intestazione `t:IssuedTokens` dopo la specifica WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="d4b99-191">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="d4b99-192">R1223: se l'attivazione si verifica all'interno di un contesto di coordinamento esistente, l'intestazione `t:IssuedTokens` con il `SecurityContextToken` associato al contesto esistente deve propagarsi sul messaggio `CreateCoordinationContext`.</span><span class="sxs-lookup"><span data-stu-id="d4b99-192">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="d4b99-193">È `t:IssuedTokens` necessario generare una nuova intestazione per l'associazione al messaggio in uscita. `wscoor:CreateCoordinationContextResponse`</span><span class="sxs-lookup"><span data-stu-id="d4b99-193">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="d4b99-194">Configurazione dell'associazione dei messaggi di registrazione</span><span class="sxs-lookup"><span data-stu-id="d4b99-194">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="d4b99-195">B1231: WCF utilizza l'associazione HTTPS duplex (descritta in Protocolli di [messaggistica](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="d4b99-195">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="d4b99-196">I messaggi di richiesta e risposta sono correlati utilizzando WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="d4b99-196">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="d4b99-197">In WS-AtomicTransaction, Sezione 8, vengono descritti più dettagliatamente la correlazione e i modelli di scambio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d4b99-197">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="d4b99-198">R1232: `wscoor:Register` i messaggi `IssuedTokenOverTransport` in uscita devono utilizzare la modalità di autenticazione descritta in Protocolli di [protezione](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="d4b99-198">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="d4b99-199">L'elemento `wsse:Timestamp` deve essere `SecurityContextToken STx` firmato utilizzando l'oggetto issued.</span><span class="sxs-lookup"><span data-stu-id="d4b99-199">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="d4b99-200">Questa firma è una prova del possesso del token associato a una particolare transazione ed è utilizzata per autenticare l'inserimento di un partecipante nella transazione.</span><span class="sxs-lookup"><span data-stu-id="d4b99-200">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="d4b99-201">Il messaggio RegistrationResponse viene inviato su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d4b99-201">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="d4b99-202">Configurazione del binding del protocollo 2PC</span><span class="sxs-lookup"><span data-stu-id="d4b99-202">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="d4b99-203">WCF supporta i messaggi unidirezionali (datagramma) su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d4b99-203">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="d4b99-204">La correlazione tra i messaggi viene lasciata come dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d4b99-204">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="d4b99-205">B2131: le implementazioni devono supportare `wsa:ReferenceParameters` come descritto in WS-Addressing per ottenere la correlazione dei messaggi 2PC di WCF.</span><span class="sxs-lookup"><span data-stu-id="d4b99-205">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="d4b99-206">Scambio di messaggi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d4b99-206">Application Message Exchange</span></span>  
 <span data-ttu-id="d4b99-207">Le applicazioni possono utilizzare qualsiasi particolare associazione per i messaggi da applicazione ad applicazione, a condizione che l'associazione soddisfi i requisiti di sicurezza seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4b99-207">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="d4b99-208">R2001: i messaggi da applicazione ad applicazione devono propagarsi nell'intestazione `t:IssuedTokens` insieme al `CoordinationContext` nell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d4b99-208">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="d4b99-209">R2002: è necessario fornire l'integrità e la riservatezza di `t:IssuedToken`.</span><span class="sxs-lookup"><span data-stu-id="d4b99-209">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="d4b99-210">L'intestazione `CoordinationContext` contiene `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="d4b99-210">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="d4b99-211">Mentre la `xsd:AnyURI` definizione di consente l'utilizzo di URI `wscoor:Identifiers`assoluti e relativi, WCF supporta solo , che sono URI assoluti.</span><span class="sxs-lookup"><span data-stu-id="d4b99-211">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="d4b99-212">Se `wscoor:Identifier` `wscoor:CoordinationContext` l'oggetto è un URI relativo, gli errori verranno restituiti dai servizi WCF transazionali.</span><span class="sxs-lookup"><span data-stu-id="d4b99-212">If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="d4b99-213">Esempi di messaggi</span><span class="sxs-lookup"><span data-stu-id="d4b99-213">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="d4b99-214">Messaggi di richiesta/risposta CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="d4b99-214">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="d4b99-215">I messaggi seguenti seguono un modello richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="d4b99-215">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext"></a><span data-ttu-id="d4b99-216">CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="d4b99-216">CreateCoordinationContext</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse"></a><span data-ttu-id="d4b99-217">CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="d4b99-217">CreateCoordinationContextResponse</span></span>  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="d4b99-218">Messaggi di registrazione</span><span class="sxs-lookup"><span data-stu-id="d4b99-218">Registration Messages</span></span>  
 <span data-ttu-id="d4b99-219">I messaggi seguenti sono messaggi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d4b99-219">The following messages are registration messages.</span></span>  
  
#### <a name="register"></a><span data-ttu-id="d4b99-220">Register</span><span class="sxs-lookup"><span data-stu-id="d4b99-220">Register</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response"></a><span data-ttu-id="d4b99-221">RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="d4b99-221">Register Response</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="d4b99-222">Messaggi del protocollo di commit a due fasi</span><span class="sxs-lookup"><span data-stu-id="d4b99-222">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="d4b99-223">Il messaggio seguente si riferisce al protocollo di commit a due fasi (2PC).</span><span class="sxs-lookup"><span data-stu-id="d4b99-223">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit"></a><span data-ttu-id="d4b99-224">Commit</span><span class="sxs-lookup"><span data-stu-id="d4b99-224">Commit</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="application-messages"></a><span data-ttu-id="d4b99-225">Messaggi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d4b99-225">Application Messages</span></span>  
 <span data-ttu-id="d4b99-226">I messaggi seguenti sono messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4b99-226">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="d4b99-227">Messaggio dell'applicazione - Richiesta</span><span class="sxs-lookup"><span data-stu-id="d4b99-227">Application message-Request</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken
          wssu:Id="IA_Certificate"
          ValueType="...#X509v3"
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->
    <e:EncryptedData Id="encrypted_body"
           Type="http://www.w3.org/2001/04/xmlenc#Content"
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
