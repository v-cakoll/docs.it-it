---
title: Protocolli di transazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2820b0ec-2f32-430c-b299-1f0e95e1f2dc
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13784a3a5062705abba1b3bbb33a04e66bd22072
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-protocols"></a><span data-ttu-id="14742-102">Protocolli di transazione</span><span class="sxs-lookup"><span data-stu-id="14742-102">Transaction Protocols</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="14742-103"> implementa i protocolli WS-Atomic Transaction e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="14742-103"> implements WS-Atomic Transaction and WS-Coordination protocols.</span></span>  
  
|<span data-ttu-id="14742-104">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="14742-104">Specification/Document</span></span>|<span data-ttu-id="14742-105">Versione</span><span class="sxs-lookup"><span data-stu-id="14742-105">Version</span></span>|<span data-ttu-id="14742-106">Collegamento</span><span class="sxs-lookup"><span data-stu-id="14742-106">Link</span></span>|  
|-----------------------------|-------------|----------|  
|<span data-ttu-id="14742-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="14742-107">WS-Coordination</span></span>|<span data-ttu-id="14742-108">1.0</span><span class="sxs-lookup"><span data-stu-id="14742-108">1.0</span></span><br /><br /> <span data-ttu-id="14742-109">1.1</span><span class="sxs-lookup"><span data-stu-id="14742-109">1.1</span></span>|[<span data-ttu-id="14742-110">http://go.microsoft.com/fwlink/?LinkId=96104</span><span class="sxs-lookup"><span data-stu-id="14742-110">http://go.microsoft.com/fwlink/?LinkId=96104</span></span>](http://go.microsoft.com/fwlink/?LinkId=96104)<br /><br /> [<span data-ttu-id="14742-111">http://go.microsoft.com/fwlink/?LinkId=96079</span><span class="sxs-lookup"><span data-stu-id="14742-111">http://go.microsoft.com/fwlink/?LinkId=96079</span></span>](http://go.microsoft.com/fwlink/?LinkId=96079)|  
|<span data-ttu-id="14742-112">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="14742-112">WS-AtomicTransaction</span></span>|<span data-ttu-id="14742-113">1.0</span><span class="sxs-lookup"><span data-stu-id="14742-113">1.0</span></span><br /><br /> <span data-ttu-id="14742-114">1.1</span><span class="sxs-lookup"><span data-stu-id="14742-114">1.1</span></span>|[<span data-ttu-id="14742-115">http://go.microsoft.com/fwlink/?LinkId=96080</span><span class="sxs-lookup"><span data-stu-id="14742-115">http://go.microsoft.com/fwlink/?LinkId=96080</span></span>](http://go.microsoft.com/fwlink/?LinkId=96080)<br /><br /> <span data-ttu-id="14742-116">http://go.microsoft.com/fwlink/?LinkId=96081</span><span class="sxs-lookup"><span data-stu-id="14742-116">http://go.microsoft.com/fwlink/?LinkId=96081</span></span>|  
  
 <span data-ttu-id="14742-117">Su queste specifiche del protocollo è richiesta l'interoperabilità a due livelli: tra le applicazioni e tra i gestori delle transazioni (vedere la figura seguente).</span><span class="sxs-lookup"><span data-stu-id="14742-117">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="14742-118">Le specifiche descrivono dettagliatamente i formati dei messaggi e lo scambio di messaggi per entrambi i livelli di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="14742-118">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="14742-119">Alcune protezioni, affidabilità e codifiche per lo scambio tra le applicazioni si applicano come per il normale scambio tra applicazioni.</span><span class="sxs-lookup"><span data-stu-id="14742-119">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="14742-120">Perché, tuttavia, sia possibile l'interoperabilità tra i gestori delle transazioni, è necessario che vi sia un accordo sull'associazione interessata dato che in genere non è configurata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="14742-120">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="14742-121">In questo argomento vengono illustrate una composizione della specifica WS-Atomic Transaction (WS-AT) con protezione e l'associazione protetta per la comunicazione tra i gestori di transazioni.</span><span class="sxs-lookup"><span data-stu-id="14742-121">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="14742-122">L'approccio descritto in questo documento è stato testato con successo con altre implementazioni di WS-AT e WS-Coordination, compresi IBM, IONA, Sun Microsystems e altri.</span><span class="sxs-lookup"><span data-stu-id="14742-122">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="14742-123">Nella figura seguente è riportata l'interoperabilità tra due gestori di transazioni, Gestore transazioni 1 e Gestore transazioni 2 e due applicazioni, Applicazione 1 e Applicazione 2.</span><span class="sxs-lookup"><span data-stu-id="14742-123">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2.</span></span>  
  
 <span data-ttu-id="14742-124">![Protocolli di transazione](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "TransactionManagers")</span><span class="sxs-lookup"><span data-stu-id="14742-124">![Transaction Protocols](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "TransactionManagers")</span></span>  
  
 <span data-ttu-id="14742-125">Si consideri un tipico scenario WS-Coordination/WS-Atomic Transaction con un Iniziatore (I) e un Partecipante (P).</span><span class="sxs-lookup"><span data-stu-id="14742-125">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="14742-126">Sia l'Iniziatore che il Partecipante hanno gestori transazioni (ITM e PTM, rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="14742-126">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="14742-127">In questo argomento, il commit in due fasi viene chiamato 2PC.</span><span class="sxs-lookup"><span data-stu-id="14742-127">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14742-128">1. CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="14742-128">1. CreateCoordinationContext</span></span>|<span data-ttu-id="14742-129">12. Risposta al messaggio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="14742-129">12. Application Message Response</span></span>|  
|<span data-ttu-id="14742-130">2. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="14742-130">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="14742-131">13. Commit (completamento)</span><span class="sxs-lookup"><span data-stu-id="14742-131">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="14742-132">3. Register (completamento)</span><span class="sxs-lookup"><span data-stu-id="14742-132">3. Register (Completion)</span></span>|<span data-ttu-id="14742-133">14. Preparare (2PC)</span><span class="sxs-lookup"><span data-stu-id="14742-133">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="14742-134">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="14742-134">4. RegisterResponse</span></span>|<span data-ttu-id="14742-135">15. Preparare (2PC)</span><span class="sxs-lookup"><span data-stu-id="14742-135">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="14742-136">5. Messaggio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="14742-136">5. Application Message</span></span>|<span data-ttu-id="14742-137">16. Prepared (2PC)</span><span class="sxs-lookup"><span data-stu-id="14742-137">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="14742-138">6. CreateCoordinationContext con Context</span><span class="sxs-lookup"><span data-stu-id="14742-138">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="14742-139">17. Prepared (2PC)</span><span class="sxs-lookup"><span data-stu-id="14742-139">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="14742-140">7. Register (durevole)</span><span class="sxs-lookup"><span data-stu-id="14742-140">7. Register (Durable)</span></span>|<span data-ttu-id="14742-141">18. Committed (completamento)</span><span class="sxs-lookup"><span data-stu-id="14742-141">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="14742-142">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="14742-142">8. RegisterResponse</span></span>|<span data-ttu-id="14742-143">19. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="14742-143">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="14742-144">9. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="14742-144">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="14742-145">20. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="14742-145">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="14742-146">10. Register (durevole)</span><span class="sxs-lookup"><span data-stu-id="14742-146">10. Register (Durable)</span></span>|<span data-ttu-id="14742-147">21. Committed (2PC)</span><span class="sxs-lookup"><span data-stu-id="14742-147">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="14742-148">11. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="14742-148">11. RegisterResponse</span></span>|<span data-ttu-id="14742-149">22. Committed (2PC)</span><span class="sxs-lookup"><span data-stu-id="14742-149">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="14742-150">In questo documento vengono illustrate una composizione della specifica WS-AtomicTransaction con protezione e l'associazione protetta per la comunicazione tra i gestori di transazioni.</span><span class="sxs-lookup"><span data-stu-id="14742-150">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="14742-151">L'approccio descritto in questo documento è stato testato con successo con altre implementazioni di WS-AT e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="14742-151">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="14742-152">Nella figura e nella tabella vengono illustrate quattro classi di messaggi dal punto di vista della protezione:</span><span class="sxs-lookup"><span data-stu-id="14742-152">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
-   <span data-ttu-id="14742-153">Messaggi di attivazione (CreateCoordinationContext e CreateCoordinationContextResponse).</span><span class="sxs-lookup"><span data-stu-id="14742-153">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
-   <span data-ttu-id="14742-154">Messaggi di registrazione (Register e RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="14742-154">Registration messages (Register and RegisterResponse)</span></span>  
  
-   <span data-ttu-id="14742-155">Messaggi di protocollo (Prepare, Rollback, Commit, Aborted e così via).</span><span class="sxs-lookup"><span data-stu-id="14742-155">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
-   <span data-ttu-id="14742-156">Messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14742-156">Application messages.</span></span>  
  
 <span data-ttu-id="14742-157">Le prime tre classi di messaggi sono considerate messaggi del gestore transazioni e la loro configurazione dell'associazione viene descritta in "Scambio di messaggi dell'applicazione", più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="14742-157">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="14742-158">La quarta classe di messaggi riguarda i messaggi da applicazione ad applicazione e viene descritta nella sezione "Esempi di messaggi", più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="14742-158">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="14742-159">Contenuto della sezione vengono illustrati i binding del protocollo utilizzati per ognuna di queste classi da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14742-159">This section describes the protocol bindings used for each of these classes by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="14742-160">In questo documento vengono utilizzati gli spazi dei nomi XML e i relativi prefissi associati seguenti.</span><span class="sxs-lookup"><span data-stu-id="14742-160">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="14742-161">Prefisso</span><span class="sxs-lookup"><span data-stu-id="14742-161">Prefix</span></span>|<span data-ttu-id="14742-162">Versione</span><span class="sxs-lookup"><span data-stu-id="14742-162">Version</span></span>|<span data-ttu-id="14742-163">URI dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="14742-163">Namespace URI</span></span>|  
|------------|-------------|-------------------|  
|<span data-ttu-id="14742-164">s11</span><span class="sxs-lookup"><span data-stu-id="14742-164">s11</span></span>||[<span data-ttu-id="14742-165">http://go.microsoft.com/fwlink/?LinkId=96014</span><span class="sxs-lookup"><span data-stu-id="14742-165">http://go.microsoft.com/fwlink/?LinkId=96014</span></span>](http://go.microsoft.com/fwlink/?LinkId=96014)|  
|<span data-ttu-id="14742-166">wsa</span><span class="sxs-lookup"><span data-stu-id="14742-166">wsa</span></span>|<span data-ttu-id="14742-167">Pre-1,0</span><span class="sxs-lookup"><span data-stu-id="14742-167">Pre-1.0</span></span><br /><br /> <span data-ttu-id="14742-168">1.0</span><span class="sxs-lookup"><span data-stu-id="14742-168">1.0</span></span>|<span data-ttu-id="14742-169">http://www.w3.org/2004/08/Addressing</span><span class="sxs-lookup"><span data-stu-id="14742-169">http://www.w3.org/2004/08/addressing</span></span><br /><br /> [<span data-ttu-id="14742-170">http://go.microsoft.com/fwlink/?LinkId=96022</span><span class="sxs-lookup"><span data-stu-id="14742-170">http://go.microsoft.com/fwlink/?LinkId=96022</span></span>](http://go.microsoft.com/fwlink/?LinkId=96022)|  
|<span data-ttu-id="14742-171">wscoor</span><span class="sxs-lookup"><span data-stu-id="14742-171">wscoor</span></span>|<span data-ttu-id="14742-172">1.0</span><span class="sxs-lookup"><span data-stu-id="14742-172">1.0</span></span><br /><br /> <span data-ttu-id="14742-173">1.1</span><span class="sxs-lookup"><span data-stu-id="14742-173">1.1</span></span>|[<span data-ttu-id="14742-174">http://go.microsoft.com/fwlink/?LinkId=96078</span><span class="sxs-lookup"><span data-stu-id="14742-174">http://go.microsoft.com/fwlink/?LinkId=96078</span></span>](http://go.microsoft.com/fwlink/?LinkId=96078)<br /><br /> [<span data-ttu-id="14742-175">http://go.microsoft.com/fwlink/?LinkId=96079</span><span class="sxs-lookup"><span data-stu-id="14742-175">http://go.microsoft.com/fwlink/?LinkId=96079</span></span>](http://go.microsoft.com/fwlink/?LinkId=96079)|  
|<span data-ttu-id="14742-176">wsat</span><span class="sxs-lookup"><span data-stu-id="14742-176">wsat</span></span>|<span data-ttu-id="14742-177">1.0</span><span class="sxs-lookup"><span data-stu-id="14742-177">1.0</span></span><br /><br /> <span data-ttu-id="14742-178">1.1</span><span class="sxs-lookup"><span data-stu-id="14742-178">1.1</span></span>|[<span data-ttu-id="14742-179">http://go.microsoft.com/fwlink/?LinkId=96080</span><span class="sxs-lookup"><span data-stu-id="14742-179">http://go.microsoft.com/fwlink/?LinkId=96080</span></span>](http://go.microsoft.com/fwlink/?LinkId=96080)<br /><br /> [<span data-ttu-id="14742-180">http://go.microsoft.com/fwlink/?LinkId=96081</span><span class="sxs-lookup"><span data-stu-id="14742-180">http://go.microsoft.com/fwlink/?LinkId=96081</span></span>](http://go.microsoft.com/fwlink/?LinkId=96081)|  
|<span data-ttu-id="14742-181">t</span><span class="sxs-lookup"><span data-stu-id="14742-181">t</span></span>|<span data-ttu-id="14742-182">Pre-1.3</span><span class="sxs-lookup"><span data-stu-id="14742-182">Pre-1.3</span></span><br /><br /> <span data-ttu-id="14742-183">1.3</span><span class="sxs-lookup"><span data-stu-id="14742-183">1.3</span></span>|[<span data-ttu-id="14742-184">http://go.microsoft.com/fwlink/?LinkId=96082</span><span class="sxs-lookup"><span data-stu-id="14742-184">http://go.microsoft.com/fwlink/?LinkId=96082</span></span>](http://go.microsoft.com/fwlink/?LinkId=96082)<br /><br /> [<span data-ttu-id="14742-185">http://go.microsoft.com/fwlink/?LinkId=96100</span><span class="sxs-lookup"><span data-stu-id="14742-185">http://go.microsoft.com/fwlink/?LinkId=96100</span></span>](http://go.microsoft.com/fwlink/?LinkId=96100)|  
|<span data-ttu-id="14742-186">o</span><span class="sxs-lookup"><span data-stu-id="14742-186">o</span></span>||[<span data-ttu-id="14742-187">http://go.microsoft.com/fwlink/?LinkId=96101</span><span class="sxs-lookup"><span data-stu-id="14742-187">http://go.microsoft.com/fwlink/?LinkId=96101</span></span>](http://go.microsoft.com/fwlink/?LinkId=96101)|  
|<span data-ttu-id="14742-188">xsd</span><span class="sxs-lookup"><span data-stu-id="14742-188">xsd</span></span>||[<span data-ttu-id="14742-189">http://go.microsoft.com/fwlink/?LinkId=96102</span><span class="sxs-lookup"><span data-stu-id="14742-189">http://go.microsoft.com/fwlink/?LinkId=96102</span></span>](http://go.microsoft.com/fwlink/?LinkId=96102)|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="14742-190">Associazioni dei gestori transazioni</span><span class="sxs-lookup"><span data-stu-id="14742-190">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="14742-191">R1001: I gestori delle transazioni che fanno parte di una transazione WS-AT 1.0 devono utilizzare SOAP 1.1 e WS-Addressing 2004/08 per gli scambi di messaggi di WS-Coordination e WS-Atomic Transaction.</span><span class="sxs-lookup"><span data-stu-id="14742-191">R1001: Transaction Managers participating in a WS-AT 1.0 transaction must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="14742-192">R1002: i gestori transazioni che partecipano a una transazione WS-AT 1.1 devono utilizzare SOAP 1.1 e WS-Addressing 2005/08 per gli scambi di messaggi WS-Atomic Transaction e WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="14742-192">R1002: Transaction Managers participating in a WS-AT 1.1 transaction must use SOAP 1.1 and WS-Addressing 2005/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="14742-193">I messaggi dell'applicazione non sono vincolati a queste associazioni e vengono descritti più avanti.</span><span class="sxs-lookup"><span data-stu-id="14742-193">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="14742-194">Associazione HTTP dei gestori transazioni</span><span class="sxs-lookup"><span data-stu-id="14742-194">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="14742-195">L'associazione HTTPS dei gestori transazioni si basa unicamente sulla protezione del trasporto per ottenere la protezione e stabilire relazioni di trust tra ogni coppia mittente-destinatario nell'albero delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="14742-195">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="14742-196">Configurazione di trasporto HTTPS</span><span class="sxs-lookup"><span data-stu-id="14742-196">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="14742-197">I certificati X.509 sono utilizzati per stabilire l'identità del gestore transazioni.</span><span class="sxs-lookup"><span data-stu-id="14742-197">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="14742-198">L'autenticazione client/server è obbligatoria, mentre l'autorizzazione client/server viene lasciata come dettaglio di implementazione:</span><span class="sxs-lookup"><span data-stu-id="14742-198">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
-   <span data-ttu-id="14742-199">R1111: i certificati X.509 presentati sulla rete devono avere un nome soggetto che corrisponde al nome di dominio completo (FQDN) del computer di origine.</span><span class="sxs-lookup"><span data-stu-id="14742-199">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
-   <span data-ttu-id="14742-200">B1112: perché i controlli del nome soggetto X.509 abbiano esito positivo, il DNS deve essere funzionale tra ogni coppia mittente-destinatario nel sistema.</span><span class="sxs-lookup"><span data-stu-id="14742-200">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="14742-201">Attivazione e configurazione dell'associazione di registrazione</span><span class="sxs-lookup"><span data-stu-id="14742-201">Activation and Registration Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="14742-202"> richiede un'associazione duplex request/reply con correlazione su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="14742-202"> requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="14742-203">Per ulteriori informazioni sulla correlazione e descrizioni dei modelli di scambio dei messaggi request/reply, vedere WS-Atomic Transaction, Sezione 8.</span><span class="sxs-lookup"><span data-stu-id="14742-203">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="14742-204">Configurazione dell'associazione del protocollo 2PC</span><span class="sxs-lookup"><span data-stu-id="14742-204">2PC Protocol Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="14742-205"> supporta messaggi unidirezionali (datagramma) su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="14742-205"> supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="14742-206">La correlazione tra i messaggi viene lasciata come dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="14742-206">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="14742-207">B1131: Le implementazioni devono supportare `wsa:ReferenceParameters` come descritto in WS-Addressing per ottenere la correlazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]del messaggi 2PC.</span><span class="sxs-lookup"><span data-stu-id="14742-207">B1131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="14742-208">Associazione di sicurezza mista del gestore transazioni</span><span class="sxs-lookup"><span data-stu-id="14742-208">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="14742-209">Questa è un'associazione alternativa (modalità mista) che utilizza la protezione del trasporto assieme al modello del token emesso WS-Coordination allo scopo di stabilire l'identità.</span><span class="sxs-lookup"><span data-stu-id="14742-209">This is an alternate (mixed mode) binding that uses transport security combined with the WS-Coordination Issued Token model for identity establishment purposes.</span></span> <span data-ttu-id="14742-210">L'attivazione e la registrazione sono gli unici elementi che differiscono tra le due associazioni.</span><span class="sxs-lookup"><span data-stu-id="14742-210">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="14742-211">Configurazione di trasporto HTTPS</span><span class="sxs-lookup"><span data-stu-id="14742-211">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="14742-212">I certificati X.509 sono utilizzati per stabilire l'identità del gestore transazioni.</span><span class="sxs-lookup"><span data-stu-id="14742-212">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="14742-213">L'autenticazione client/server è obbligatoria, mentre l'autorizzazione client/server viene lasciata come dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="14742-213">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="14742-214">Configurazione dell'associazione dei messaggi di attivazione</span><span class="sxs-lookup"><span data-stu-id="14742-214">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="14742-215">I messaggi di attivazione in genere non partecipano all'interoperabilità perché si verificano normalmente tra un'applicazione e il suo gestore transazioni locale.</span><span class="sxs-lookup"><span data-stu-id="14742-215">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="14742-216">B1221: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza l'associazione HTTPS duplex (descritto in [protocolli di messaggistica](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) per i messaggi di attivazione.</span><span class="sxs-lookup"><span data-stu-id="14742-216">B1221: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="14742-217">I messaggi di richiesta e risposta sono correlati utilizzando WS-Addressing 2004/08 per WS-AT 1.0 e WS-Addressing 2005/08 per WS-AT 1.1.</span><span class="sxs-lookup"><span data-stu-id="14742-217">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="14742-218">Nella specifica WS-Atomic Transaction, Sezione 8, vengono descritti più dettagliatamente la correlazione e i modelli di scambio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="14742-218">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
-   <span data-ttu-id="14742-219">R1222: alla ricezione di un `CreateCoordinationContext`, il coordinatore deve emettere un `SecurityContextToken` con il segreto `STx` associato.</span><span class="sxs-lookup"><span data-stu-id="14742-219">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="14742-220">Tale token viene restituito in un'intestazione `t:IssuedTokens` dopo la specifica WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="14742-220">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
-   <span data-ttu-id="14742-221">R1223: se l'attivazione si verifica all'interno di un contesto di coordinamento esistente, l'intestazione `t:IssuedTokens` con il `SecurityContextToken` associato al contesto esistente deve propagarsi sul messaggio `CreateCoordinationContext`.</span><span class="sxs-lookup"><span data-stu-id="14742-221">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="14742-222">Un nuovo `t:IssuedTokens` intestazione deve essere generata per associazione a in uscita `wscoor:CreateCoordinationContextResponse` messaggio.</span><span class="sxs-lookup"><span data-stu-id="14742-222">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="14742-223">Configurazione dell'associazione dei messaggi di registrazione</span><span class="sxs-lookup"><span data-stu-id="14742-223">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="14742-224">B1231: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza l'associazione HTTPS duplex (descritto in [protocolli di messaggistica](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="14742-224">B1231: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="14742-225">I messaggi di richiesta e risposta sono correlati utilizzando WS-Addressing 2004/08 per WS-AT 1.0 e WS-Addressing 2005/08 per WS-AT 1.1.</span><span class="sxs-lookup"><span data-stu-id="14742-225">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="14742-226">In WS-AtomicTransaction, Sezione 8, vengono descritti più dettagliatamente la correlazione e i modelli di scambio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="14742-226">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="14742-227">R1232: In uscita `wscoor:Register` messaggi è necessario utilizzare il `IssuedTokenOverTransport` modalità di autenticazione descritte [protocolli di sicurezza](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="14742-227">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="14742-228">Il `wsse:Timestamp` elemento deve essere firmato utilizzando il `SecurityContextToken``STx` rilasciato.</span><span class="sxs-lookup"><span data-stu-id="14742-228">The `wsse:Timestamp` element must be signed using the `SecurityContextToken``STx` issued.</span></span> <span data-ttu-id="14742-229">Questa firma è una prova del possesso del token associato a una particolare transazione ed è utilizzata per autenticare l'inserimento di un partecipante nella transazione.</span><span class="sxs-lookup"><span data-stu-id="14742-229">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="14742-230">Il messaggio RegistrationResponse viene inviato su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="14742-230">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="14742-231">Configurazione del binding del protocollo 2PC</span><span class="sxs-lookup"><span data-stu-id="14742-231">2PC Protocol Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="14742-232"> supporta messaggi unidirezionali (datagramma) su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="14742-232"> supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="14742-233">La correlazione tra i messaggi viene lasciata come dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="14742-233">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="14742-234">B1241: le implementazioni devono supportare `wsa:ReferenceParameters` come descritto in WS-Addressing per ottenere la correlazione dei messaggi 2PC di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14742-234">B1241: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="14742-235">Scambio di messaggi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="14742-235">Application Message Exchange</span></span>  
 <span data-ttu-id="14742-236">Le applicazioni possono utilizzare qualsiasi particolare associazione per i messaggi da applicazione ad applicazione, a condizione che l'associazione soddisfi i requisiti di sicurezza seguenti:</span><span class="sxs-lookup"><span data-stu-id="14742-236">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
-   <span data-ttu-id="14742-237">R2001: i messaggi da applicazione ad applicazione devono propagarsi nell'intestazione `t:IssuedTokens` insieme al `CoordinationContext` nell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="14742-237">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
-   <span data-ttu-id="14742-238">R2002: è necessario fornire l'integrità e la riservatezza di `t:IssuedToken`.</span><span class="sxs-lookup"><span data-stu-id="14742-238">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="14742-239">L'intestazione `CoordinationContext` contiene `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="14742-239">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="14742-240">Mentre la definizione di `xsd:AnyURI` consente di utilizzare URI sia assoluti che relativi. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supporta solo `wscoor:Identifiers` che sono URI assoluti.</span><span class="sxs-lookup"><span data-stu-id="14742-240">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="14742-241">B2003: se il `wscoor:Identifier` del `wscoor:CoordinationContext` è un URI relativo, i servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transazionali restituiranno degli errori.</span><span class="sxs-lookup"><span data-stu-id="14742-241">B2003: If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="14742-242">Esempi di messaggi</span><span class="sxs-lookup"><span data-stu-id="14742-242">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="14742-243">Messaggi di richiesta/risposta CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="14742-243">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="14742-244">I messaggi seguenti seguono un modello richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="14742-244">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext-with-wscoor-10"></a><span data-ttu-id="14742-245">CreateCoordinationContext con WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="14742-245">CreateCoordinationContext with WSCoor 1.0</span></span>  
  
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
  
#### <a name="createcoordinationcontext-with-wscoor-11"></a><span data-ttu-id="14742-246">CreateCoordinationContext con WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="14742-246">CreateCoordinationContext with WSCoor 1.1</span></span>  
  
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
  
#### <a name="createcoordinationcontextresponse-with-trust-pre-13-and-wscoor-10"></a><span data-ttu-id="14742-247">CreateCoordinationContextResponse con Trust Pre-1.3 e WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="14742-247">CreateCoordinationContextResponse with Trust Pre-1.3 and WSCoor 1.0</span></span>  
  
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
  
#### <a name="createcoordinationcontextresponse-with-trust-13-and-wscoor-11"></a><span data-ttu-id="14742-248">CreateCoordinationContextResponse con Trust 1.3 e WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="14742-248">CreateCoordinationContextResponse with Trust 1.3 and WSCoor 1.1</span></span>  
  
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
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-     wssecurity-utility-1.0.xsd"   
xmlns:wst=http://docs.oasis-open.org/ws-sx/ws-trust/200512  
xmlns:wsc=http://schemas.xmlsoap.org/ws/2005/02/sc  
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
  ValueType=http://schemas.xmlsoap.org/ws/2005/02/sc/sct  
  URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedAttachedReference>   
<wst:RequestedUnattachedReference>   
<wsse:SecurityTokenReference>   
<wsse:Reference  
 ValueType=http://schemas.xmlsoap.org/ws/2005/02/sc/sct  
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
  
### <a name="registration-messages"></a><span data-ttu-id="14742-249">Messaggi di registrazione</span><span class="sxs-lookup"><span data-stu-id="14742-249">Registration Messages</span></span>  
 <span data-ttu-id="14742-250">I messaggi seguenti sono messaggi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="14742-250">The following messages are registration messages.</span></span>  
  
#### <a name="register-with-wscoor-10"></a><span data-ttu-id="14742-251">Register con WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="14742-251">Register with WSCoor 1.0</span></span>  
  
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
  
#### <a name="register-with-wscoor-11"></a><span data-ttu-id="14742-252">Register con WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="14742-252">Register with WSCoor 1.1</span></span>  
  
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
  
#### <a name="register-response-with-wscoor-10"></a><span data-ttu-id="14742-253">Register Response con WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="14742-253">Register Response with WSCoor 1.0</span></span>  
  
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
  
#### <a name="register-response-with-wscoor-11"></a><span data-ttu-id="14742-254">Register Response con WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="14742-254">Register Response with WSCoor 1.1</span></span>  
  
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
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="14742-255">Messaggi del protocollo di commit a due fasi</span><span class="sxs-lookup"><span data-stu-id="14742-255">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="14742-256">Il messaggio seguente si riferisce al protocollo di commit a due fasi (2PC).</span><span class="sxs-lookup"><span data-stu-id="14742-256">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit-with-wsat-10"></a><span data-ttu-id="14742-257">Commit con WSAT 1.0</span><span class="sxs-lookup"><span data-stu-id="14742-257">Commit with WSAT 1.0</span></span>  
  
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
  
#### <a name="commit-with-wsat-11"></a><span data-ttu-id="14742-258">Commit con WSAT 1.1</span><span class="sxs-lookup"><span data-stu-id="14742-258">Commit with WSAT 1.1</span></span>  
  
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
  
### <a name="application-messages"></a><span data-ttu-id="14742-259">Messaggi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="14742-259">Application Messages</span></span>  
 <span data-ttu-id="14742-260">I messaggi seguenti sono messaggi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14742-260">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="14742-261">Messaggio dell'applicazione - Richiesta</span><span class="sxs-lookup"><span data-stu-id="14742-261">Application message-Request</span></span>  
  
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
