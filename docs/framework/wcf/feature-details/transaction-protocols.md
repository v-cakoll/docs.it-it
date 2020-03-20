---
title: Protocolli di transazione
ms.date: 03/30/2017
ms.assetid: 2820b0ec-2f32-430c-b299-1f0e95e1f2dc
ms.openlocfilehash: 5ae8aa5112f737d3000e221d0a199c3ee36eac46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184359"
---
# <a name="transaction-protocols"></a><span data-ttu-id="3431b-102">Protocolli di transazione</span><span class="sxs-lookup"><span data-stu-id="3431b-102">Transaction Protocols</span></span>
<span data-ttu-id="3431b-103">Windows Communication Foundation (WCF) implementa i protocolli WS-Atomic Transaction e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="3431b-103">Windows Communication Foundation (WCF) implements WS-Atomic Transaction and WS-Coordination protocols.</span></span>  
  
|<span data-ttu-id="3431b-104">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="3431b-104">Specification/Document</span></span>|<span data-ttu-id="3431b-105">Versione</span><span class="sxs-lookup"><span data-stu-id="3431b-105">Version</span></span>|<span data-ttu-id="3431b-106">Collegamento</span><span class="sxs-lookup"><span data-stu-id="3431b-106">Link</span></span>|  
|-----------------------------|-------------|----------|  
|<span data-ttu-id="3431b-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="3431b-107">WS-Coordination</span></span>|<span data-ttu-id="3431b-108">1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-108">1.0</span></span><br /><br /> <span data-ttu-id="3431b-109">1.1</span><span class="sxs-lookup"><span data-stu-id="3431b-109">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|<span data-ttu-id="3431b-110">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="3431b-110">WS-AtomicTransaction</span></span>|<span data-ttu-id="3431b-111">1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-111">1.0</span></span><br /><br /> <span data-ttu-id="3431b-112">1.1</span><span class="sxs-lookup"><span data-stu-id="3431b-112">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
  
 <span data-ttu-id="3431b-113">Su queste specifiche del protocollo è richiesta l'interoperabilità a due livelli: tra le applicazioni e tra i gestori delle transazioni (vedere la figura seguente).</span><span class="sxs-lookup"><span data-stu-id="3431b-113">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="3431b-114">Le specifiche descrivono dettagliatamente i formati dei messaggi e lo scambio di messaggi per entrambi i livelli di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="3431b-114">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="3431b-115">Alcune protezioni, affidabilità e codifiche per lo scambio tra le applicazioni si applicano come per il normale scambio tra applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3431b-115">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="3431b-116">Perché, tuttavia, sia possibile l'interoperabilità tra i gestori delle transazioni, è necessario che vi sia un accordo sull'associazione interessata dato che in genere non è configurata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3431b-116">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="3431b-117">In questo argomento vengono illustrate una composizione della specifica WS-Atomic Transaction (WS-AT) con protezione e l'associazione protetta per la comunicazione tra i gestori di transazioni.</span><span class="sxs-lookup"><span data-stu-id="3431b-117">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="3431b-118">L'approccio descritto in questo documento è stato testato con successo con altre implementazioni di WS-AT e WS-Coordination, compresi IBM, IONA, Sun Microsystems e altri.</span><span class="sxs-lookup"><span data-stu-id="3431b-118">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="3431b-119">Nella figura seguente viene illustrata l'interoperabilità tra due gestori delle transazioni, Transaction Manager 1 e Transaction Manager 2, e due applicazioni, Application 1 e Application 2:</span><span class="sxs-lookup"><span data-stu-id="3431b-119">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![Screenshot che mostra l'interazione tra gestori di transazioni.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="3431b-121">Si consideri un tipico scenario WS-Coordination/WS-Atomic Transaction con un Iniziatore (I) e un Partecipante (P).</span><span class="sxs-lookup"><span data-stu-id="3431b-121">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="3431b-122">Sia l'Iniziatore che il Partecipante hanno gestori transazioni (ITM e PTM, rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="3431b-122">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="3431b-123">In questo argomento, il commit in due fasi viene chiamato 2PC.</span><span class="sxs-lookup"><span data-stu-id="3431b-123">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3431b-124">1. CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="3431b-124">1. CreateCoordinationContext</span></span>|<span data-ttu-id="3431b-125">12. Risposta ai messaggi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3431b-125">12. Application Message Response</span></span>|  
|<span data-ttu-id="3431b-126">2. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="3431b-126">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="3431b-127">13. Commit (completamento)</span><span class="sxs-lookup"><span data-stu-id="3431b-127">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="3431b-128">3. Registrati (Completamento)</span><span class="sxs-lookup"><span data-stu-id="3431b-128">3. Register (Completion)</span></span>|<span data-ttu-id="3431b-129">14. Preparazione (2PC)</span><span class="sxs-lookup"><span data-stu-id="3431b-129">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="3431b-130">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="3431b-130">4. RegisterResponse</span></span>|<span data-ttu-id="3431b-131">15. Preparazione (2PC)</span><span class="sxs-lookup"><span data-stu-id="3431b-131">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="3431b-132">5. Messaggio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3431b-132">5. Application Message</span></span>|<span data-ttu-id="3431b-133">16. Preparato (2PC)</span><span class="sxs-lookup"><span data-stu-id="3431b-133">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="3431b-134">6. CreateCoordinationContext con contesto</span><span class="sxs-lookup"><span data-stu-id="3431b-134">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="3431b-135">17. Preparato (2PC)</span><span class="sxs-lookup"><span data-stu-id="3431b-135">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="3431b-136">7. Registrati (Durable)</span><span class="sxs-lookup"><span data-stu-id="3431b-136">7. Register (Durable)</span></span>|<span data-ttu-id="3431b-137">18. Impegnato (Completamento)</span><span class="sxs-lookup"><span data-stu-id="3431b-137">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="3431b-138">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="3431b-138">8. RegisterResponse</span></span>|<span data-ttu-id="3431b-139">19. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="3431b-139">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="3431b-140">9. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="3431b-140">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="3431b-141">20. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="3431b-141">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="3431b-142">10. Registro (durable)</span><span class="sxs-lookup"><span data-stu-id="3431b-142">10. Register (Durable)</span></span>|<span data-ttu-id="3431b-143">21. Impegnato (2PC)</span><span class="sxs-lookup"><span data-stu-id="3431b-143">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="3431b-144">11. Risposta di Registro</span><span class="sxs-lookup"><span data-stu-id="3431b-144">11. RegisterResponse</span></span>|<span data-ttu-id="3431b-145">22. Impegnato (2PC)</span><span class="sxs-lookup"><span data-stu-id="3431b-145">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="3431b-146">In questo documento vengono illustrate una composizione della specifica WS-AtomicTransaction con protezione e l'associazione protetta per la comunicazione tra i gestori di transazioni.</span><span class="sxs-lookup"><span data-stu-id="3431b-146">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="3431b-147">L'approccio descritto in questo documento è stato testato con successo con altre implementazioni di WS-AT e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="3431b-147">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="3431b-148">Nella figura e nella tabella vengono illustrate quattro classi di messaggi dal punto di vista della protezione:</span><span class="sxs-lookup"><span data-stu-id="3431b-148">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="3431b-149">Messaggi di attivazione (CreateCoordinationContext e CreateCoordinationContextResponse).</span><span class="sxs-lookup"><span data-stu-id="3431b-149">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="3431b-150">Messaggi di registrazione (Register e RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="3431b-150">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="3431b-151">Messaggi di protocollo (Prepare, Rollback, Commit, Aborted e così via).</span><span class="sxs-lookup"><span data-stu-id="3431b-151">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="3431b-152">Messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3431b-152">Application messages.</span></span>  
  
 <span data-ttu-id="3431b-153">Le prime tre classi di messaggi sono considerate messaggi del gestore transazioni e la loro configurazione dell'associazione viene descritta in "Scambio di messaggi dell'applicazione", più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3431b-153">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="3431b-154">La quarta classe di messaggi riguarda i messaggi da applicazione ad applicazione e viene descritta nella sezione "Esempi di messaggi", più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3431b-154">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="3431b-155">In questa sezione vengono descritte le associazioni di protocollo utilizzate per ognuna di queste classi da WCF.</span><span class="sxs-lookup"><span data-stu-id="3431b-155">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="3431b-156">In questo documento vengono utilizzati gli spazi dei nomi XML e i relativi prefissi associati seguenti.</span><span class="sxs-lookup"><span data-stu-id="3431b-156">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="3431b-157">Prefisso</span><span class="sxs-lookup"><span data-stu-id="3431b-157">Prefix</span></span>|<span data-ttu-id="3431b-158">Versione</span><span class="sxs-lookup"><span data-stu-id="3431b-158">Version</span></span>|<span data-ttu-id="3431b-159">URI dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3431b-159">Namespace URI</span></span>|  
|------------|-------------|-------------------|  
|<span data-ttu-id="3431b-160">s11</span><span class="sxs-lookup"><span data-stu-id="3431b-160">s11</span></span>||<https://schemas.xmlsoap.org/soap/envelope/>|  
|<span data-ttu-id="3431b-161">wsa</span><span class="sxs-lookup"><span data-stu-id="3431b-161">wsa</span></span>|<span data-ttu-id="3431b-162">Precedente alla 1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-162">Pre-1.0</span></span><br /><br /> <span data-ttu-id="3431b-163">1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-163">1.0</span></span>|`http://www.w3.org/2004/08/addressing`<br /><br /> <https://www.w3.org/2005/08/addressing/>|  
|<span data-ttu-id="3431b-164">wscoor</span><span class="sxs-lookup"><span data-stu-id="3431b-164">wscoor</span></span>|<span data-ttu-id="3431b-165">1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-165">1.0</span></span><br /><br /> <span data-ttu-id="3431b-166">1.1</span><span class="sxs-lookup"><span data-stu-id="3431b-166">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|<span data-ttu-id="3431b-167">wsat</span><span class="sxs-lookup"><span data-stu-id="3431b-167">wsat</span></span>|<span data-ttu-id="3431b-168">1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-168">1.0</span></span><br /><br /> <span data-ttu-id="3431b-169">1.1</span><span class="sxs-lookup"><span data-stu-id="3431b-169">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
|<span data-ttu-id="3431b-170">t</span><span class="sxs-lookup"><span data-stu-id="3431b-170">t</span></span>|<span data-ttu-id="3431b-171">Pre-1.3</span><span class="sxs-lookup"><span data-stu-id="3431b-171">Pre-1.3</span></span><br /><br /> <span data-ttu-id="3431b-172">1.3</span><span class="sxs-lookup"><span data-stu-id="3431b-172">1.3</span></span>|<http://schemas.xmlsoap.org/ws/2005/02/trust/><br /><br /> <https://docs.oasis-open.org/ws-sx/ws-trust/200512>|  
|<span data-ttu-id="3431b-173">o</span><span class="sxs-lookup"><span data-stu-id="3431b-173">o</span></span>||<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd>|  
|<span data-ttu-id="3431b-174">xsd</span><span class="sxs-lookup"><span data-stu-id="3431b-174">xsd</span></span>||<https://www.w3.org/2001/XMLSchema>|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="3431b-175">Associazioni dei gestori transazioni</span><span class="sxs-lookup"><span data-stu-id="3431b-175">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="3431b-176">R1001: i gestori delle transazioni che partecipano a una transazione WS-AT 1.0 devono utilizzare SOAP 1.1 e WS-Addressing 2004/08 per gli scambi di messaggi WS-Atomic Transaction e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="3431b-176">R1001: Transaction Managers participating in a WS-AT 1.0 transaction must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="3431b-177">R1002: i gestori transazioni che partecipano a una transazione WS-AT 1.1 devono utilizzare SOAP 1.1 e WS-Addressing 2005/08 per gli scambi di messaggi WS-Atomic Transaction e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="3431b-177">R1002: Transaction Managers participating in a WS-AT 1.1 transaction must use SOAP 1.1 and WS-Addressing 2005/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="3431b-178">I messaggi dell'applicazione non sono vincolati a queste associazioni e vengono descritti più avanti.</span><span class="sxs-lookup"><span data-stu-id="3431b-178">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="3431b-179">Associazione HTTP dei gestori transazioni</span><span class="sxs-lookup"><span data-stu-id="3431b-179">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="3431b-180">L'associazione HTTPS dei gestori transazioni si basa unicamente sulla protezione del trasporto per ottenere la protezione e stabilire relazioni di trust tra ogni coppia mittente-destinatario nell'albero delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="3431b-180">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="3431b-181">Configurazione di trasporto HTTPS</span><span class="sxs-lookup"><span data-stu-id="3431b-181">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="3431b-182">I certificati X.509 sono utilizzati per stabilire l'identità del gestore transazioni.</span><span class="sxs-lookup"><span data-stu-id="3431b-182">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="3431b-183">L'autenticazione client/server è obbligatoria, mentre l'autorizzazione client/server viene lasciata come dettaglio di implementazione:</span><span class="sxs-lookup"><span data-stu-id="3431b-183">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="3431b-184">R1111: i certificati X.509 presentati sulla rete devono avere un nome soggetto che corrisponde al nome di dominio completo (FQDN) del computer di origine.</span><span class="sxs-lookup"><span data-stu-id="3431b-184">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="3431b-185">B1112: perché i controlli del nome soggetto X.509 abbiano esito positivo, il DNS deve essere funzionale tra ogni coppia mittente-destinatario nel sistema.</span><span class="sxs-lookup"><span data-stu-id="3431b-185">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="3431b-186">Attivazione e configurazione dell'associazione di registrazione</span><span class="sxs-lookup"><span data-stu-id="3431b-186">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="3431b-187">WCF richiede l'associazione duplex richiesta/risposta con correlazione su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3431b-187">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="3431b-188">Per ulteriori informazioni sulla correlazione e descrizioni dei modelli di scambio dei messaggi request/reply, vedere WS-Atomic Transaction, Sezione 8.</span><span class="sxs-lookup"><span data-stu-id="3431b-188">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="3431b-189">Configurazione del binding del protocollo 2PC</span><span class="sxs-lookup"><span data-stu-id="3431b-189">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="3431b-190">WCF supporta i messaggi unidirezionali (datagramma) su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3431b-190">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="3431b-191">La correlazione tra i messaggi viene lasciata come dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="3431b-191">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="3431b-192">B1131: le implementazioni devono supportare `wsa:ReferenceParameters` come descritto in WS-Addressing per ottenere la correlazione dei messaggi 2PC di WCF.</span><span class="sxs-lookup"><span data-stu-id="3431b-192">B1131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="3431b-193">Associazione di sicurezza mista del gestore transazioni</span><span class="sxs-lookup"><span data-stu-id="3431b-193">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="3431b-194">Questa è un'associazione alternativa (modalità mista) che utilizza la protezione del trasporto assieme al modello del token emesso WS-Coordination allo scopo di stabilire l'identità.</span><span class="sxs-lookup"><span data-stu-id="3431b-194">This is an alternate (mixed mode) binding that uses transport security combined with the WS-Coordination Issued Token model for identity establishment purposes.</span></span> <span data-ttu-id="3431b-195">L'attivazione e la registrazione sono gli unici elementi che differiscono tra le due associazioni.</span><span class="sxs-lookup"><span data-stu-id="3431b-195">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="3431b-196">Configurazione di trasporto HTTPS</span><span class="sxs-lookup"><span data-stu-id="3431b-196">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="3431b-197">I certificati X.509 sono utilizzati per stabilire l'identità del gestore transazioni.</span><span class="sxs-lookup"><span data-stu-id="3431b-197">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="3431b-198">L'autenticazione client/server è obbligatoria, mentre l'autorizzazione client/server viene lasciata come dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="3431b-198">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="3431b-199">Configurazione dell'associazione dei messaggi di attivazione</span><span class="sxs-lookup"><span data-stu-id="3431b-199">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="3431b-200">I messaggi di attivazione in genere non partecipano all'interoperabilità perché si verificano normalmente tra un'applicazione e il suo gestore transazioni locale.</span><span class="sxs-lookup"><span data-stu-id="3431b-200">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="3431b-201">B1221: WCF utilizza l'associazione HTTPS duplex (descritta in Protocolli di [messaggistica](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) per i messaggi di attivazione.</span><span class="sxs-lookup"><span data-stu-id="3431b-201">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="3431b-202">I messaggi di richiesta e risposta sono correlati utilizzando WS-Addressing 2004/08 per WS-AT 1.0 e WS-Addressing 2005/08 per WS-AT 1.1.</span><span class="sxs-lookup"><span data-stu-id="3431b-202">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="3431b-203">La specifica WS-Atomic Transaction, Sezione 8, descrive ulteriori dettagli sulla correlazione e sui modelli di scambio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3431b-203">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="3431b-204">R1222: alla ricezione di un `CreateCoordinationContext`, il coordinatore deve emettere un `SecurityContextToken` con il segreto `STx` associato.</span><span class="sxs-lookup"><span data-stu-id="3431b-204">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="3431b-205">Tale token viene restituito in un'intestazione `t:IssuedTokens` dopo la specifica WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="3431b-205">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="3431b-206">R1223: se l'attivazione si verifica all'interno di un contesto di coordinamento esistente, l'intestazione `t:IssuedTokens` con il `SecurityContextToken` associato al contesto esistente deve propagarsi sul messaggio `CreateCoordinationContext`.</span><span class="sxs-lookup"><span data-stu-id="3431b-206">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="3431b-207">È `t:IssuedTokens` necessario generare una nuova intestazione per l'associazione al messaggio in uscita. `wscoor:CreateCoordinationContextResponse`</span><span class="sxs-lookup"><span data-stu-id="3431b-207">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="3431b-208">Configurazione dell'associazione dei messaggi di registrazione</span><span class="sxs-lookup"><span data-stu-id="3431b-208">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="3431b-209">B1231: WCF utilizza l'associazione HTTPS duplex (descritta in Protocolli di [messaggistica](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="3431b-209">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="3431b-210">I messaggi di richiesta e risposta sono correlati utilizzando WS-Addressing 2004/08 per WS-AT 1.0 e WS-Addressing 2005/08 per WS-AT 1.1.</span><span class="sxs-lookup"><span data-stu-id="3431b-210">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="3431b-211">In WS-AtomicTransaction, Sezione 8, vengono descritti più dettagliatamente la correlazione e i modelli di scambio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3431b-211">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="3431b-212">R1232: `wscoor:Register` i messaggi `IssuedTokenOverTransport` in uscita devono utilizzare la modalità di autenticazione descritta in Protocolli di [protezione](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="3431b-212">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="3431b-213">L'elemento `wsse:Timestamp` deve essere `SecurityContextToken STx` firmato utilizzando l'oggetto issued.</span><span class="sxs-lookup"><span data-stu-id="3431b-213">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="3431b-214">Questa firma è una prova del possesso del token associato a una particolare transazione ed è utilizzata per autenticare l'inserimento di un partecipante nella transazione.</span><span class="sxs-lookup"><span data-stu-id="3431b-214">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="3431b-215">Il messaggio RegistrationResponse viene inviato su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3431b-215">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="3431b-216">Configurazione del binding del protocollo 2PC</span><span class="sxs-lookup"><span data-stu-id="3431b-216">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="3431b-217">WCF supporta i messaggi unidirezionali (datagramma) su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3431b-217">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="3431b-218">La correlazione tra i messaggi viene lasciata come dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="3431b-218">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="3431b-219">B1241: le implementazioni devono supportare `wsa:ReferenceParameters` come descritto in WS-Addressing per ottenere la correlazione dei messaggi 2PC di WCF.</span><span class="sxs-lookup"><span data-stu-id="3431b-219">B1241: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="3431b-220">Scambio di messaggi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3431b-220">Application Message Exchange</span></span>  
 <span data-ttu-id="3431b-221">Le applicazioni possono utilizzare qualsiasi particolare associazione per i messaggi da applicazione ad applicazione, a condizione che l'associazione soddisfi i requisiti di sicurezza seguenti:</span><span class="sxs-lookup"><span data-stu-id="3431b-221">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="3431b-222">R2001: i messaggi da applicazione ad applicazione devono propagarsi nell'intestazione `t:IssuedTokens` insieme al `CoordinationContext` nell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3431b-222">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="3431b-223">R2002: è necessario fornire l'integrità e la riservatezza di `t:IssuedToken`.</span><span class="sxs-lookup"><span data-stu-id="3431b-223">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="3431b-224">L'intestazione `CoordinationContext` contiene `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="3431b-224">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="3431b-225">Mentre la `xsd:AnyURI` definizione di consente l'utilizzo di URI `wscoor:Identifiers`assoluti e relativi, WCF supporta solo , che sono URI assoluti.</span><span class="sxs-lookup"><span data-stu-id="3431b-225">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="3431b-226">B2003: se `wscoor:Identifier` `wscoor:CoordinationContext` l'oggetto è un URI relativo, gli errori verranno restituiti dai servizi WCF transazionali.</span><span class="sxs-lookup"><span data-stu-id="3431b-226">B2003: If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="3431b-227">Esempi di messaggi</span><span class="sxs-lookup"><span data-stu-id="3431b-227">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="3431b-228">Messaggi di richiesta/risposta CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="3431b-228">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="3431b-229">I messaggi seguenti seguono un modello richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="3431b-229">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext-with-wscoor-10"></a><span data-ttu-id="3431b-230">CreateCoordinationContext con WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-230">CreateCoordinationContext with WSCoor 1.0</span></span>  
  
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
  
#### <a name="createcoordinationcontext-with-wscoor-11"></a><span data-ttu-id="3431b-231">CreateCoordinationContext con WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="3431b-231">CreateCoordinationContext with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>
<s:Header>  
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContext</Action>  
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
  
#### <a name="createcoordinationcontextresponse-with-trust-pre-13-and-wscoor-10"></a><span data-ttu-id="3431b-232">CreateCoordinationContextResponse con Trust Pre-1.3 e WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-232">CreateCoordinationContextResponse with Trust Pre-1.3 and WSCoor 1.0</span></span>  
  
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
  
#### <a name="createcoordinationcontextresponse-with-trust-13-and-wscoor-11"></a><span data-ttu-id="3431b-233">CreateCoordinationContextResponse con Trust 1.3 e WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="3431b-233">CreateCoordinationContextResponse with Trust 1.3 and WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<!-- Data below is shown in the clear for illustration purposes only. -->
<s:Header>
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContextResponse </a:Action>  
<a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
<a:To s:mustUnderstand="1">https://... </a:To>
<t:IssuedTokens>
<wst:RequestSecurityTokenResponse
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"
xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"  
xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
<wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
<wst:RequestedSecurityToken>
<wsc:SecurityContextToken>
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>
</wsc:SecurityContextToken>
</wst:RequestedSecurityToken>
<wsp:AppliesTo> http://fabrikam123.com/CCi </wsp:AppliesTo>  
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
  Type="http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey">  
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
<wscoor:Identifier> http://fabrikam123.com/CCi  
</wscoor:Identifier>
<wscoor:Expires>...</wscoor:Expires>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
<wscoor:RegistrationService>
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ...  
</a:ReferenceParameters>  
</wscoor:RegistrationService>
</wscoor:CoordinationContext>
</wscoor:CreateCoordinationContextResponse>
</s:Body>
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="3431b-234">Messaggi di registrazione</span><span class="sxs-lookup"><span data-stu-id="3431b-234">Registration Messages</span></span>  
 <span data-ttu-id="3431b-235">I messaggi seguenti sono messaggi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3431b-235">The following messages are registration messages.</span></span>  
  
#### <a name="register-with-wscoor-10"></a><span data-ttu-id="3431b-236">Registrati con WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-236">Register with WSCoor 1.0</span></span>  
  
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
  
#### <a name="register-with-wscoor-11"></a><span data-ttu-id="3431b-237">Register con WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="3431b-237">Register with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/Register</a:Action>
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
<wssu:Identifier> http://fabrikam123.com/SCTi  
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
<ds:DigestMethod  
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>
<ds:DigestValue> alRzyhjLgoUOYoh8cx4n75eTcUk=  
</ds:DigestValue>
</ds:Reference>
</ds:SignedInfo>  
<ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=  
</ds:SignatureValue>  
<ds:KeyInfo>
<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
  <wsse:Reference URI="http://fabrikam123.com/SCTi"/>  
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
  
#### <a name="register-response-with-wscoor-10"></a><span data-ttu-id="3431b-238">Registra risposta con WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-238">Register Response with WSCoor 1.0</span></span>  
  
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
  
#### <a name="register-response-with-wscoor-11"></a><span data-ttu-id="3431b-239">Register Response con WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="3431b-239">Register Response with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>
<a:Action> http://docs.oasis-open.org/ws-tx/wscoor/2006/06/RegisterResponse  
</a:Action>
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
<a:RelatesTo> urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e </a:RelatesTo>  
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
<a:ReferenceParameters> ... </a:ReferenceParameters>  
</wscoor:CoordinatorProtocolService>
</wscoor:RegisterResponse>
</s:Body>
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="3431b-240">Messaggi del protocollo di commit a due fasi</span><span class="sxs-lookup"><span data-stu-id="3431b-240">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="3431b-241">Il messaggio seguente si riferisce al protocollo di commit a due fasi (2PC).</span><span class="sxs-lookup"><span data-stu-id="3431b-241">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit-with-wsat-10"></a><span data-ttu-id="3431b-242">Eseguire il commit con WSAT 1.0Commit with WSAT 1.0</span><span class="sxs-lookup"><span data-stu-id="3431b-242">Commit with WSAT 1.0</span></span>  
  
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
  
#### <a name="commit-with-wsat-11"></a><span data-ttu-id="3431b-243">Commit con WSAT 1.1</span><span class="sxs-lookup"><span data-stu-id="3431b-243">Commit with WSAT 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>
<a:Action>http://docs.oasis-open.org/ws-tx/wsat/2006/06</a:Action>  
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
  
### <a name="application-messages"></a><span data-ttu-id="3431b-244">Messaggi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3431b-244">Application Messages</span></span>  
 <span data-ttu-id="3431b-245">I messaggi seguenti sono messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3431b-245">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="3431b-246">Messaggio dell'applicazione - Richiesta</span><span class="sxs-lookup"><span data-stu-id="3431b-246">Application message-Request</span></span>  
  
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
