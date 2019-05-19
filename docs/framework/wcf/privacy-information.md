---
title: Informazioni sulla privacy di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: 6da9e2a91fe8156c0631aa77594e3ed47d32cb8b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882192"
---
# <a name="windows-communication-foundation-privacy-information"></a><span data-ttu-id="43db8-102">Informazioni sulla privacy di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="43db8-102">Windows Communication Foundation Privacy Information</span></span>
<span data-ttu-id="43db8-103">Microsoft è impegnata a proteggere la privacy degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="43db8-103">Microsoft is committed to protecting end-users' privacy.</span></span> <span data-ttu-id="43db8-104">Quando si compila un'applicazione che usa Windows Communication Foundation (WCF), versione 3.0, l'applicazione può incidere sulla privacy degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="43db8-104">When you build an application using Windows Communication Foundation (WCF), version 3.0, your application may impact your end-users' privacy.</span></span> <span data-ttu-id="43db8-105">L'applicazione potrebbe, ad esempio, raccogliere in modo esplicito informazioni di contatto sugli utenti o richiedere o inviare informazioni in Internet al sito Web.</span><span class="sxs-lookup"><span data-stu-id="43db8-105">For example, your application may explicitly collect user contact information, or it may request or send information over the Internet to your Web site.</span></span> <span data-ttu-id="43db8-106">Se si incorpora la tecnologia Microsoft nell'applicazione, è possibile che tale tecnologia abbia un proprio comportamento che potrebbe influire sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="43db8-106">If you embed Microsoft technology in your application, that technology may have its own behavior that might affect privacy.</span></span> <span data-ttu-id="43db8-107">WCF non invia informazioni a Microsoft dall'applicazione, a meno che l'utente finale sceglie di inviarlo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43db8-107">WCF does not send any information to Microsoft from your application unless you or the end-user choose to send it to us.</span></span>  
  
## <a name="wcf-in-brief"></a><span data-ttu-id="43db8-108">WCF in breve</span><span class="sxs-lookup"><span data-stu-id="43db8-108">WCF in Brief</span></span>  
 <span data-ttu-id="43db8-109">WCF è un framework di messaggistica distribuito tramite Microsoft .NET Framework che consente agli sviluppatori di compilare applicazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="43db8-109">WCF is a distributed messaging framework using the Microsoft .NET Framework that allows developers to build distributed applications.</span></span> <span data-ttu-id="43db8-110">I messaggi comunicati tra due applicazioni contengono informazioni di intestazione e corpo.</span><span class="sxs-lookup"><span data-stu-id="43db8-110">Messages communicated between two applications contain header and body information.</span></span>  
  
 <span data-ttu-id="43db8-111">Le intestazioni possono contenere il routing dei messaggi, informazioni sulla sicurezza, transazioni e altro, a seconda dei servizi usati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-111">Headers may contain message routing, security information, transactions, and more depending on the services used by the application.</span></span> <span data-ttu-id="43db8-112">I messaggi vengono in genere crittografati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="43db8-112">Messages are typically encrypted by default.</span></span> <span data-ttu-id="43db8-113">L'unica eccezione a questa regola si verifica quando si usa `BasicHttpBinding`, che è stato progettato per l'uso con i servizi Web legacy, non-protetti.</span><span class="sxs-lookup"><span data-stu-id="43db8-113">The one exception is when using the `BasicHttpBinding`, which was designed for use with non-secured, legacy Web services.</span></span> <span data-ttu-id="43db8-114">I progettisti dell'applicazione sono responsabili della progettazione finale.</span><span class="sxs-lookup"><span data-stu-id="43db8-114">As the application designer, you are responsible for the final design.</span></span> <span data-ttu-id="43db8-115">I messaggi nel corpo SOAP contengono dati specifici dell'applicazione. Tuttavia, è possibile proteggere questi dati, ad esempio le informazioni personali definite dall'applicazione, usando le funzionalità di crittografia o riservatezza WCF.</span><span class="sxs-lookup"><span data-stu-id="43db8-115">Messages in the SOAP body contain application-specific data; however, this data, such as application-defined personal information, can be secured by using WCF encryption or confidentiality features.</span></span> <span data-ttu-id="43db8-116">Nelle sezioni seguenti vengono descritte le funzionalità che potrebbero avere un impatto sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="43db8-116">The following sections describe the features that potentially impact privacy.</span></span>  
  
## <a name="messaging"></a><span data-ttu-id="43db8-117">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="43db8-117">Messaging</span></span>  
 <span data-ttu-id="43db8-118">Ogni messaggio WCF presenta un'intestazione di indirizzo che specifica la destinazione del messaggio e in cui la risposta dovrebbe arrivare.</span><span class="sxs-lookup"><span data-stu-id="43db8-118">Each WCF message has an address header that specifies the message destination and where the reply should go.</span></span>  
  
 <span data-ttu-id="43db8-119">Il componente indirizzo di un endpoint è un URI (Uniform Resource Identifier) che identifica l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="43db8-119">The address component of an endpoint address is a Uniform Resource Identifier (URI) that identifies the endpoint.</span></span> <span data-ttu-id="43db8-120">L'indirizzo può essere un indirizzo di rete o logico.</span><span class="sxs-lookup"><span data-stu-id="43db8-120">The address can be a network address or a logical address.</span></span> <span data-ttu-id="43db8-121">L'indirizzo può includere il nome del computer (nome host, nome di dominio completo) e un indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="43db8-121">The address may include machine name (hostname, fully qualified domain name) and an IP address.</span></span> <span data-ttu-id="43db8-122">L'indirizzo dell'endpoint può inoltre contenere un GUID (Globally Unique Identifier) o una raccolta di GUID per indirizzamento temporaneo usato per discernere ogni indirizzo.</span><span class="sxs-lookup"><span data-stu-id="43db8-122">The endpoint address may also contain a globally unique identifier (GUID), or a collection of GUIDs for temporary addressing used to discern each address.</span></span> <span data-ttu-id="43db8-123">Ogni messaggio contiene un ID di messaggio che corrisponde a un GUID.</span><span class="sxs-lookup"><span data-stu-id="43db8-123">Each message contains a message ID that is a GUID.</span></span> <span data-ttu-id="43db8-124">Questa funzionalità segue lo standard di riferimento WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="43db8-124">This feature follows the WS-Addressing reference standard.</span></span>  
  
 <span data-ttu-id="43db8-125">Il livello di messaggistica di WCF non scrive informazioni personali nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="43db8-125">The WCF messaging layer does not write any personal information to the local machine.</span></span> <span data-ttu-id="43db8-126">Tuttavia, potrebbe propagare informazioni personali a livello di rete, se un sviluppatore di servizi ha creato un servizio che espone tali informazioni usando, ad esempio, il nome di una persona in un nome di endpoint o includendo informazioni personali nel linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) dell'endpoint senza richiedere però ai client di usare https per accedere al codice WSDL.</span><span class="sxs-lookup"><span data-stu-id="43db8-126">However, it might propagate personal information at the network level if a service developer has created a service that exposes such information (for example, by using a person's name in an endpoint name, or including personal information in the endpoint's Web Services Description Language but not requiring clients to use https to access the WSDL).</span></span> <span data-ttu-id="43db8-127">Inoltre, se uno sviluppatore è in esecuzione la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento su un endpoint che espone informazioni personali, l'output dello strumento potrebbe contenere tali informazioni e il file di output viene scritto il disco rigido locale.</span><span class="sxs-lookup"><span data-stu-id="43db8-127">Also, if a developer runs the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool against an endpoint that exposes personal information, the tool's output could contain that information, and the output file is written to the local hard disk.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="43db8-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="43db8-128">Hosting</span></span>  
 <span data-ttu-id="43db8-129">La funzionalità di hosting di WCF consente alle applicazioni per avviare su richiesta o per abilitare la condivisione delle porte tra più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="43db8-129">The hosting feature in WCF allows applications to start on demand or to enable port sharing between multiple applications.</span></span> <span data-ttu-id="43db8-130">Un'applicazione WCF può essere ospitata in Internet Information Services (IIS), simile a ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="43db8-130">An WCF application can be hosted in Internet Information Services (IIS), similar to ASP.NET.</span></span>  
  
 <span data-ttu-id="43db8-131">L'hosting non espone informazioni specifiche sulla rete e non implica il mantenimento di dati sul computer.</span><span class="sxs-lookup"><span data-stu-id="43db8-131">Hosting does not expose any specific information on the network and it does not keep data on the machine.</span></span>  
  
## <a name="message-security"></a><span data-ttu-id="43db8-132">Sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="43db8-132">Message Security</span></span>  
 <span data-ttu-id="43db8-133">Sicurezza WCF fornisce le funzionalità di sicurezza per le applicazioni di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="43db8-133">WCF security provides the security capabilities for messaging applications.</span></span> <span data-ttu-id="43db8-134">Le funzioni di sicurezza previste includono autenticazione e autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-134">The security functions provided include authentication and authorization.</span></span>  
  
 <span data-ttu-id="43db8-135">L'autenticazione viene eseguita passando credenziali tra i client e i servizi.</span><span class="sxs-lookup"><span data-stu-id="43db8-135">Authentication is performed by passing credentials between the clients and services.</span></span> <span data-ttu-id="43db8-136">L'autenticazione può avvenire tramite la sicurezza a livello di trasporto o tramite la sicurezza a livello di messaggio SOAP, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="43db8-136">Authentication can be either through transport-level security or through SOAP message-level security, as follows:</span></span>  
  
- <span data-ttu-id="43db8-137">Nella sicurezza dei messaggi SOAP, l'autenticazione viene eseguita tramite credenziali quali nome utente/password, certificati X.509, ticket Kerberos e token SAML, tutti elementi che potrebbero contenere informazioni personali, a seconda dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="43db8-137">In SOAP message security, authentication is performed through credentials like username/passwords, X.509 certificates, Kerberos tickets, and SAML tokens, all of which might contain personal information, depending on the issuer.</span></span>  
  
- <span data-ttu-id="43db8-138">Con la sicurezza del trasporto, l'autenticazione viene eseguita tramite tradizionali meccanismi di autenticazione del trasporto quali gli schemi di autenticazione HTTP (di base, digest, Negotiate, autenticazione integrata di Windows, NTLM, Nessuno e accesso anonimo) e l'autenticazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="43db8-138">Using transport security, authentication is done through traditional transport authentication mechanisms like HTTP authentication schemes (Basic, Digest, Negotiate, Integrated Windows Authorization, NTLM, None, and Anonymous), and form authentication.</span></span>  
  
 <span data-ttu-id="43db8-139">Il risultato dell'autenticazione può essere una sessione protetta stabilita tra gli endpoint di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-139">Authentication can result in a secure session established between the communicating endpoints.</span></span> <span data-ttu-id="43db8-140">La sessione viene identificata da un GUID che ha la durata della sessione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="43db8-140">The session is identified by a GUID that lasts the lifetime of the security session.</span></span> <span data-ttu-id="43db8-141">Nella tabella seguente viene mostrato cosa viene mantenuto e dove.</span><span class="sxs-lookup"><span data-stu-id="43db8-141">The following table shows what is kept and where.</span></span>  
  
|<span data-ttu-id="43db8-142">Dati</span><span class="sxs-lookup"><span data-stu-id="43db8-142">Data</span></span>|<span data-ttu-id="43db8-143">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="43db8-143">Storage</span></span>|  
|----------|-------------|  
|<span data-ttu-id="43db8-144">Credenziali di presentazione, ad esempio nome utente, certificati X.509, token Kerberos e riferimenti alle credenziali.</span><span class="sxs-lookup"><span data-stu-id="43db8-144">Presentation credentials, such as username, X.509 certificates, Kerberos tokens, and references to credentials.</span></span>|<span data-ttu-id="43db8-145">Meccanismi di gestione delle credenziali standard di Windows, ad esempio l'archivio certificati di Windows.</span><span class="sxs-lookup"><span data-stu-id="43db8-145">Standard Windows credential management mechanisms such as the Windows certificate store.</span></span>|  
|<span data-ttu-id="43db8-146">Informazioni relative all'appartenenza degli utenti, ad esempio nomi utente e password.</span><span class="sxs-lookup"><span data-stu-id="43db8-146">User membership information, such as usernames and passwords.</span></span>|<span data-ttu-id="43db8-147">Provider di appartenenze ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="43db8-147">ASP.NET membership providers.</span></span>|  
|<span data-ttu-id="43db8-148">Informazioni di identità sul servizio usato per autenticare il servizio sui client.</span><span class="sxs-lookup"><span data-stu-id="43db8-148">Identity information about the service used to authenticate the service to clients.</span></span>|<span data-ttu-id="43db8-149">Indirizzo dell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="43db8-149">Endpoint address of the service.</span></span>|  
|<span data-ttu-id="43db8-150">Informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="43db8-150">Caller information.</span></span>|<span data-ttu-id="43db8-151">Registri di controllo.</span><span class="sxs-lookup"><span data-stu-id="43db8-151">Auditing logs.</span></span>|  
  
## <a name="auditing"></a><span data-ttu-id="43db8-152">Controllo</span><span class="sxs-lookup"><span data-stu-id="43db8-152">Auditing</span></span>  
 <span data-ttu-id="43db8-153">Il controllo registra l'esito positivo o negativo degli eventi di autenticazione e autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-153">Auditing records the success and failure of authentication and authorization events.</span></span> <span data-ttu-id="43db8-154">I record di controllo contengono i dati seguenti: URI del servizio, URI dell'azione e identificazione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="43db8-154">Auditing records contain the following data: service URI, action URI, and the caller's identification.</span></span>  
  
 <span data-ttu-id="43db8-155">Il controllo registra inoltre quando l'amministratore modifica la configurazione della registrazione messaggi (attivandola o disattivandola), poiché la registrazione messaggi può registrare dati specifici dell'applicazione in intestazioni e corpi.</span><span class="sxs-lookup"><span data-stu-id="43db8-155">Auditing also records when the administrator modifies the configuration of message logging (turning it on or off), because message logging may log application-specific data in headers and bodies.</span></span> <span data-ttu-id="43db8-156">Per [!INCLUDE[wxp](../../../includes/wxp-md.md)], viene registrato un record nel registro eventi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-156">For [!INCLUDE[wxp](../../../includes/wxp-md.md)], a record is logged in the application event log.</span></span> <span data-ttu-id="43db8-157">Per [!INCLUDE[wv](../../../includes/wv-md.md)] e [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], viene registrato un record nel registro eventi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="43db8-157">For [!INCLUDE[wv](../../../includes/wv-md.md)] and [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], a record is logged in the security event log.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="43db8-158">Transazioni</span><span class="sxs-lookup"><span data-stu-id="43db8-158">Transactions</span></span>  
 <span data-ttu-id="43db8-159">La funzionalità transazioni fornisce servizi transazionali a un'applicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="43db8-159">The transactions feature provides transactional services to a WCF application.</span></span>  
  
 <span data-ttu-id="43db8-160">Le intestazioni delle transazioni usate nella propagazione delle transazioni possono contenere ID di transazione o ID di integrazione, che sono GUID.</span><span class="sxs-lookup"><span data-stu-id="43db8-160">Transaction headers used in transaction propagation may contain Transaction IDs or Enlistment IDs, which are GUIDs.</span></span>  
  
 <span data-ttu-id="43db8-161">La funzionalità Transazioni usa gestione transazioni MSDTC (Microsoft Distributed Transaction Coordinator), un componente di Window, per gestire lo stato delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="43db8-161">The Transactions feature uses the Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (a Windows component) to manage transaction state.</span></span> <span data-ttu-id="43db8-162">Per impostazione predefinita, le comunicazioni tra i gestori transazioni vengono crittografate.</span><span class="sxs-lookup"><span data-stu-id="43db8-162">By default, communications between Transactions Managers are encrypted.</span></span> <span data-ttu-id="43db8-163">I gestori transazioni possono registrare riferimenti agli endpoint, ID di transazione e ID di integrazione come parte del proprio stato durevole.</span><span class="sxs-lookup"><span data-stu-id="43db8-163">Transaction Managers may log endpoint references, Transaction IDs, and Enlistment IDs as part of their durable state.</span></span> <span data-ttu-id="43db8-164">La durata di questo stato è determinata dalla durata del file di log della gestione transazioni.</span><span class="sxs-lookup"><span data-stu-id="43db8-164">The lifetime of this state is determined by the lifetime of the Transaction Manager’s log file.</span></span> <span data-ttu-id="43db8-165">Il servizio MSDTC possiede e gestisce questo log.</span><span class="sxs-lookup"><span data-stu-id="43db8-165">The MSDTC service owns and maintains this log.</span></span>  
  
 <span data-ttu-id="43db8-166">La funzionalità Transazioni implementa gli standard WS-Coordination e WS-Atomic Transaction.</span><span class="sxs-lookup"><span data-stu-id="43db8-166">The Transactions feature implements the WS-Coordination and WS-Atomic Transaction standards.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="43db8-167">Sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="43db8-167">Reliable Sessions</span></span>  
 <span data-ttu-id="43db8-168">Le sessioni affidabili in WCF forniscono il trasferimento dei messaggi quando si verificano errori di intermediari o trasporto.</span><span class="sxs-lookup"><span data-stu-id="43db8-168">Reliable sessions in WCF provide the transfer of messages when transport or intermediary failures occur.</span></span> <span data-ttu-id="43db8-169">Esse garantiscono un trasferimento di tipo exactly-once dei messaggi anche quando il trasporto sottostante si disconnette (ad esempio, una connessione TCP su una rete wireless ) o perde un messaggio (un proxy HTTP che rilascia un messaggio in uscita o in ingresso).</span><span class="sxs-lookup"><span data-stu-id="43db8-169">They provide an exactly-once transfer of messages even when the underlying transport disconnects (for example, a TCP connection on a wireless network) or loses a message (an HTTP proxy dropping an outgoing or incoming message).</span></span> <span data-ttu-id="43db8-170">Le sessioni affidabili recuperano inoltre il riordinamento dei messaggi (come può accadere nel caso del routing a percorsi multipli), preservando l'ordine di invio.</span><span class="sxs-lookup"><span data-stu-id="43db8-170">Reliable sessions also recover message reordering (as may happen in the case of multipath routing), preserving the order in which the messages were sent.</span></span>  
  
 <span data-ttu-id="43db8-171">Le sessioni affidabili vengono implementate usando il protocollo WS-RM (WS-ReliableMessaging)</span><span class="sxs-lookup"><span data-stu-id="43db8-171">Reliable sessions are implemented using the WS-ReliableMessaging (WS-RM) protocol.</span></span> <span data-ttu-id="43db8-172">e aggiungono intestazioni WS-RM che contengono informazioni sulle sessioni usate per identificare tutti i messaggi associati a una particolare sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="43db8-172">They add WS-RM headers that contain session information, which is used to identify all messages associated with a particular reliable session.</span></span> <span data-ttu-id="43db8-173">Ogni sessione WS-RM ha un identificatore corrispondente a un GUID.</span><span class="sxs-lookup"><span data-stu-id="43db8-173">Each WS-RM session has an identifier, which is a GUID.</span></span>  
  
 <span data-ttu-id="43db8-174">Nessuna informazione personale viene mantenuta sul computer dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="43db8-174">No personal information is retained on the end-user's machine.</span></span>  
  
## <a name="queued-channels"></a><span data-ttu-id="43db8-175">Canali in coda</span><span class="sxs-lookup"><span data-stu-id="43db8-175">Queued Channels</span></span>  
 <span data-ttu-id="43db8-176">Le code archiviano messaggi provenienti da un'applicazione mittente per conto di un'applicazione ricevente e quindi inoltrano tali messaggi all'applicazione ricevente.</span><span class="sxs-lookup"><span data-stu-id="43db8-176">Queues store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span> <span data-ttu-id="43db8-177">Esse consentono di assicurare il trasferimento dei messaggi dalle applicazioni mittenti alle applicazioni riceventi quando, ad esempio, l'applicazione ricevente è temporanea.</span><span class="sxs-lookup"><span data-stu-id="43db8-177">They help ensure the transfer of messages from sending applications to receiving applications when, for example, the receiving application is transient.</span></span> <span data-ttu-id="43db8-178">WCF fornisce supporto per l'accodamento utilizzando Accodamento messaggi Microsoft (MSMQ) come trasporto.</span><span class="sxs-lookup"><span data-stu-id="43db8-178">WCF provides support for queuing by using Microsoft Message Queuing (MSMQ) as a transport.</span></span>  
  
 <span data-ttu-id="43db8-179">La funzionalità dei canali in coda non aggiunge intestazioni a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="43db8-179">The queued channels feature does not add headers to a message.</span></span> <span data-ttu-id="43db8-180">Crea invece un messaggio di accodamento messaggi con le proprietà del messaggio di accodamento messaggi appropriate impostate e richiama metodi di accodamento messaggi per inserire il messaggio nella coda di accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="43db8-180">Instead it creates a Message Queuing message with appropriate Message Queuing message properties set, and invokes Message Queuing methods to put the message in the Message Queuing queue.</span></span> <span data-ttu-id="43db8-181">Il servizio di accodamento messaggi è un componente facoltativo fornito con Windows.</span><span class="sxs-lookup"><span data-stu-id="43db8-181">Message Queuing is an optional component that ships with Windows.</span></span>  
  
 <span data-ttu-id="43db8-182">La funzionalità dei canali in coda non conserva alcuna informazione sul computer dell'utente finale, perché usa l'accodamento messaggi come infrastruttura di accodamento.</span><span class="sxs-lookup"><span data-stu-id="43db8-182">No information is retained on the end-user's machine by the queued channels feature, because it uses Message Queuing as the queuing infrastructure.</span></span>  
  
## <a name="com-integration"></a><span data-ttu-id="43db8-183">Integrazione COM+</span><span class="sxs-lookup"><span data-stu-id="43db8-183">COM+ Integration</span></span>  
 <span data-ttu-id="43db8-184">Questa funzionalità esegue il wrapping di funzionalità COM e COM+ esistenti per creare servizi compatibili con i servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="43db8-184">This feature wraps existing COM and COM+ functionality to create services that are compatible with WCF services.</span></span> <span data-ttu-id="43db8-185">Essa non usa intestazioni specifiche e non conserva dati sul computer dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="43db8-185">This feature does not use specific headers and it does not retain data on the end-user's machine.</span></span>  
  
## <a name="com-service-moniker"></a><span data-ttu-id="43db8-186">Moniker servizio COM</span><span class="sxs-lookup"><span data-stu-id="43db8-186">COM Service Moniker</span></span>  
 <span data-ttu-id="43db8-187">Questo fornisce un wrapper non gestito a un client WCF standard.</span><span class="sxs-lookup"><span data-stu-id="43db8-187">This provides an unmanaged wrapper to a standard WCF client.</span></span> <span data-ttu-id="43db8-188">Essa non prevede intestazioni specifiche in transito né conserva dati sul computer.</span><span class="sxs-lookup"><span data-stu-id="43db8-188">This feature does not have specific headers on the wire nor does it persist data on the machine.</span></span>  
  
## <a name="peer-channel"></a><span data-ttu-id="43db8-189">Canale del peer</span><span class="sxs-lookup"><span data-stu-id="43db8-189">Peer Channel</span></span>  
 <span data-ttu-id="43db8-190">Il canale peer consente lo sviluppo di applicazioni a più parti tramite WCF.</span><span class="sxs-lookup"><span data-stu-id="43db8-190">A peer channel enables development of multiparty applications using WCF.</span></span> <span data-ttu-id="43db8-191">La messaggistica a più parti si verifica nel contesto di una rete.</span><span class="sxs-lookup"><span data-stu-id="43db8-191">Multiparty messaging occurs in the context of a mesh.</span></span> <span data-ttu-id="43db8-192">Le reti vengono identificate da un nome a cui i nodi possono connettersi.</span><span class="sxs-lookup"><span data-stu-id="43db8-192">Meshes are identified by a name that nodes can join.</span></span> <span data-ttu-id="43db8-193">Ogni nodo nel canale del peer crea un listener TCP su una porta specificata dall'utente e stabilisce connessioni con altri nodi nella rete per assicurare la flessibilità.</span><span class="sxs-lookup"><span data-stu-id="43db8-193">Each node in the peer channel creates a TCP listener at a user-specified port and establishes connections with other nodes in the mesh to ensure resiliency.</span></span> <span data-ttu-id="43db8-194">Per connettersi ad altri nodi nella rete, i nodi si scambiano anche alcuni dati, incluso l'indirizzo del listener e gli indirizzi IP del computer.</span><span class="sxs-lookup"><span data-stu-id="43db8-194">To connect to other nodes in the mesh, nodes also exchange some data, including the listener address and the machine's IP addresses, with other nodes in the mesh.</span></span> <span data-ttu-id="43db8-195">I messaggi inviati nella rete possono contenere informazioni di sicurezza relative al mittente, per impedire lo spoofing e la manomissione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="43db8-195">Messages sent around in the mesh can contain security information that pertains to the sender to prevent message spoofing and tampering.</span></span>  
  
 <span data-ttu-id="43db8-196">Non vengono archiviate informazioni personali sul computer dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="43db8-196">No personal information is stored on the end-user's machine.</span></span>  
  
## <a name="it-professional-experience"></a><span data-ttu-id="43db8-197">Esperienza dei professionisti IT</span><span class="sxs-lookup"><span data-stu-id="43db8-197">IT Professional Experience</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="43db8-198">Traccia</span><span class="sxs-lookup"><span data-stu-id="43db8-198">Tracing</span></span>  
 <span data-ttu-id="43db8-199">La funzionalità di diagnostica dell'infrastruttura di WCF registra i messaggi che passano attraverso il trasporto e livelli del modello di servizio e le attività e gli eventi associati a questi messaggi.</span><span class="sxs-lookup"><span data-stu-id="43db8-199">The diagnostics feature of the WCF infrastructure logs messages that pass through the transport and service model layers, and the activities and events associated with these messages.</span></span> <span data-ttu-id="43db8-200">Questa funzionalità è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="43db8-200">This feature is turned off by default.</span></span> <span data-ttu-id="43db8-201">Viene attivata usando il file di configurazione dell'applicazione e il comportamento della traccia può essere modificato usando il provider WMI per WCF in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="43db8-201">It is enabled using the application’s configuration file and the tracing behavior may be modified using the WCF WMI provider at run time.</span></span> <span data-ttu-id="43db8-202">Quando viene attivata, l'infrastruttura di traccia emette una traccia di diagnostica che contiene messaggi, attività ed eventi di elaborazione per i listener configurati.</span><span class="sxs-lookup"><span data-stu-id="43db8-202">When enabled, the tracing infrastructure emits a diagnostic trace that contains messages, activities, and processing events to configured listeners.</span></span> <span data-ttu-id="43db8-203">Il formato e la posizione dell'output vengono determinati dalle scelte di configurazione dei listener dell'amministratore, ma l'output è in genere un file con formattazione XML.</span><span class="sxs-lookup"><span data-stu-id="43db8-203">The format and location of the output are determined by the administrator’s listener configuration choices, but is typically an XML formatted file.</span></span> <span data-ttu-id="43db8-204">L'amministratore è responsabile dell'impostazione dell'elenco di controllo di accesso sui file di traccia.</span><span class="sxs-lookup"><span data-stu-id="43db8-204">The administrator is responsible for setting the access control list (ACL) on the trace files.</span></span> <span data-ttu-id="43db8-205">In particolare, in caso di hosting in Windows Activation System (WAS), l'amministratore deve verificare che i file non vengano servizi dalla directory radice virtuale pubblica, se non lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="43db8-205">In particular, when hosted by Windows Activation System (WAS), the administrator should make sure the files are not served from the public virtual root directory if that is not desired.</span></span>  
  
 <span data-ttu-id="43db8-206">Esistono due tipi di traccia: La registrazione dei messaggi e modello del servizio diagnostica tracing, descritto nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="43db8-206">There are two types of tracing: Message logging and Service Model diagnostic tracing, described in the following section.</span></span> <span data-ttu-id="43db8-207">Ogni tipo viene configurato tramite la propria origine di traccia: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> e <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="43db8-207">Each type is configured through its own trace source: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> and <xref:System.ServiceModel>.</span></span> <span data-ttu-id="43db8-208">Entrambe queste origini di traccia di registrazione acquisiscono dati locali rispetto all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-208">Both of these logging trace sources capture data that is local to the application.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="43db8-209">Registrazione messaggi</span><span class="sxs-lookup"><span data-stu-id="43db8-209">Message Logging</span></span>  
 <span data-ttu-id="43db8-210">L'origine di traccia della registrazione messaggi (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) consente a un amministratore di registrare messaggi che fluiscono attraverso il sistema.</span><span class="sxs-lookup"><span data-stu-id="43db8-210">The message logging trace source (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) allows an administrator to log the messages that flow through the system.</span></span> <span data-ttu-id="43db8-211">Tramite la configurazione, l'utente può decidere di registrare interi messaggi o solo intestazioni, se eseguire la registrazione a livello di trasporto e/o di modello di servizio e se includere messaggi in formato non valido.</span><span class="sxs-lookup"><span data-stu-id="43db8-211">Through configuration, the user may decide to log entire messages or message headers only, whether to log at the transport and/or service model layers, and whether to include malformed messages.</span></span> <span data-ttu-id="43db8-212">Inoltre, può configurare il filtro per limitare il numero di messaggi registrati.</span><span class="sxs-lookup"><span data-stu-id="43db8-212">Also, the user may configure filtering to restrict which messages are logged.</span></span>  
  
 <span data-ttu-id="43db8-213">Per impostazione predefinita, la registrazione messaggi è disattivata.</span><span class="sxs-lookup"><span data-stu-id="43db8-213">By default, message logging is disabled.</span></span> <span data-ttu-id="43db8-214">L'amministratore del computer locale può impedire che l'amministratore a livello di applicazione attivi la registrazione messaggi.</span><span class="sxs-lookup"><span data-stu-id="43db8-214">The local machine administrator can prevent the application-level administrator from turning message logging on.</span></span>  
  
#### <a name="encrypted-and-decrypted-message-logging"></a><span data-ttu-id="43db8-215">Registrazione di messaggi crittografati e decrittografati</span><span class="sxs-lookup"><span data-stu-id="43db8-215">Encrypted and Decrypted Message Logging</span></span>  
 <span data-ttu-id="43db8-216">I messaggi vengono registrati, crittografati o decrittografati, come descritto nei termini seguenti.</span><span class="sxs-lookup"><span data-stu-id="43db8-216">Messages are logged, encrypted, or decrypted, as described in the following terms.</span></span>  
  
 <span data-ttu-id="43db8-217">Registrazione trasporto</span><span class="sxs-lookup"><span data-stu-id="43db8-217">Transport Logging</span></span>  
 <span data-ttu-id="43db8-218">Registra messaggi ricevuti e inviati a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="43db8-218">Logs messages received and sent at the transport level.</span></span> <span data-ttu-id="43db8-219">Questi messaggi contengono tutte le intestazioni e possono essere crittografati prima dell'invio in rete e al momento della ricezione.</span><span class="sxs-lookup"><span data-stu-id="43db8-219">These messages contain all headers, and may be encrypted before being sent on the wire and when being received.</span></span>  
  
 <span data-ttu-id="43db8-220">Se i messaggi vengono crittografati prima dell'invio in rete e al momento della ricezione, vengono anche registrati in forma crittografata.</span><span class="sxs-lookup"><span data-stu-id="43db8-220">If messages are encrypted before being sent on the wire and when they are received, they are logged encrypted as well.</span></span> <span data-ttu-id="43db8-221">Si verifica un'eccezione a questa regola quando viene usato un protocollo di sicurezza (https). In questo caso, i messaggi vengono registrati in forma decrittografata prima dell'invio e dopo la ricezione, anche se risultano crittografati in rete.</span><span class="sxs-lookup"><span data-stu-id="43db8-221">An exception is when a security protocol is used (https): they are then logged decrypted before being sent and after being received even if they are encrypted on the wire.</span></span>  
  
 <span data-ttu-id="43db8-222">Registrazione servizio</span><span class="sxs-lookup"><span data-stu-id="43db8-222">Service Logging</span></span>  
 <span data-ttu-id="43db8-223">Registra i messaggi ricevuti o inviati a livello del modello di servizio, dopo l'elaborazione dell'intestazione di canale, immediatamente prima e dopo l'immissione del codice utente.</span><span class="sxs-lookup"><span data-stu-id="43db8-223">Logs messages received or sent at the service model level, after channel header processing has occurred, just before and after entering user code.</span></span>  
  
 <span data-ttu-id="43db8-224">I messaggi registrati a questo livello vengono decrittografati anche se sono stati protetti e crittografati durante il transito.</span><span class="sxs-lookup"><span data-stu-id="43db8-224">Messages logged at this level are decrypted even if they were secured and encrypted on the wire.</span></span>  
  
 <span data-ttu-id="43db8-225">Registrazione messaggi in formato non valido</span><span class="sxs-lookup"><span data-stu-id="43db8-225">Malformed Message Logging</span></span>  
 <span data-ttu-id="43db8-226">Registra i messaggi che non è possibile comprendere o elaborare l'infrastruttura WCF.</span><span class="sxs-lookup"><span data-stu-id="43db8-226">Logs messages that the WCF infrastructure cannot understand or process.</span></span>  
  
 <span data-ttu-id="43db8-227">I messaggi vengono registrati così come sono, ovvero in forma crittografata o decrittografata.</span><span class="sxs-lookup"><span data-stu-id="43db8-227">Messages are logged as-is, that is, encrypted or not</span></span>  
  
 <span data-ttu-id="43db8-228">Quando i messaggi vengono registrati forma decrittografata o non crittografata, per impostazione predefinita WCF rimuove le chiavi di sicurezza e potenziali informazioni personali dai messaggi prima la registrazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-228">When messages are logged in decrypted or unencrypted form, by default WCF removes security keys and potentially personal information from the messages before logging them.</span></span> <span data-ttu-id="43db8-229">Nelle sezioni successive vengono descritte quali informazioni vengono rimosse e quando.</span><span class="sxs-lookup"><span data-stu-id="43db8-229">The next sections describe what information is removed, and when.</span></span> <span data-ttu-id="43db8-230">L'amministratore del computer e il distributore dell'applicazione devono entrambi eseguire determinate operazioni di configurazione per modificare il comportamento predefinito al fine di registrare chiavi e potenziali informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="43db8-230">The machine administrator and application deployer must both take certain configuration actions to change the default behavior to log keys and potentially personal information.</span></span>  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="43db8-231">Informazioni rimosse dalle intestazioni dei messaggi in caso di registrazione di messaggi decrittografati/non crittografati</span><span class="sxs-lookup"><span data-stu-id="43db8-231">Information Removed from Message Headers When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="43db8-232">Quando i messaggi vengono registrati in forma decrittografata/non crittografata, le chiavi di sicurezza e le potenziali informazioni personali vengono rimosse, per impostazione predefinita, dalle intestazioni e dai corpi dei messaggi prima della registrazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-232">When messages are logged in decrypted/unencrypted form, security keys and potentially personal information are removed by default from message headers and message bodies before they are logged.</span></span> <span data-ttu-id="43db8-233">Nell'elenco seguente viene illustrato cosa WCF considera chiavi e potenziali informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="43db8-233">The following list shows what WCF considers keys and potentially personal information.</span></span>  
  
 <span data-ttu-id="43db8-234">Chiavi rimosse:</span><span class="sxs-lookup"><span data-stu-id="43db8-234">Keys that are removed:</span></span>  
  
 <span data-ttu-id="43db8-235">\- Per xmlns:wst = "http://schemas.xmlsoap.org/ws/2004/04/trust" e xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust"</span><span class="sxs-lookup"><span data-stu-id="43db8-235">\- For xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"</span></span>  
  
 <span data-ttu-id="43db8-236">wst:BinarySecret</span><span class="sxs-lookup"><span data-stu-id="43db8-236">wst:BinarySecret</span></span>  
  
 <span data-ttu-id="43db8-237">wst:Entropy</span><span class="sxs-lookup"><span data-stu-id="43db8-237">wst:Entropy</span></span>  
  
 <span data-ttu-id="43db8-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="43db8-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="43db8-239">wsse:Password</span><span class="sxs-lookup"><span data-stu-id="43db8-239">wsse:Password</span></span>  
  
 <span data-ttu-id="43db8-240">wsse:Nonce</span><span class="sxs-lookup"><span data-stu-id="43db8-240">wsse:Nonce</span></span>  
  
 <span data-ttu-id="43db8-241">Potenziali informazioni personali rimosse:</span><span class="sxs-lookup"><span data-stu-id="43db8-241">Potentially personal information that is removed:</span></span>  
  
 <span data-ttu-id="43db8-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="43db8-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="43db8-243">wsse:Username</span><span class="sxs-lookup"><span data-stu-id="43db8-243">wsse:Username</span></span>  
  
 <span data-ttu-id="43db8-244">wsse:BinarySecurityToken</span><span class="sxs-lookup"><span data-stu-id="43db8-244">wsse:BinarySecurityToken</span></span>  
  
 <span data-ttu-id="43db8-245">\- Per xmlns:SAML="urn:OASIS:Names:TC:SAML:1.0:Assertion ="urn: oasis: nomi: tc: SAML:1.0:assertion"vengono rimossi gli elementi in grassetto (seguenti):</span><span class="sxs-lookup"><span data-stu-id="43db8-245">\- For xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" the items in bold (below) are removed:</span></span>  
  
 <span data-ttu-id="43db8-246">\<Asserzione</span><span class="sxs-lookup"><span data-stu-id="43db8-246">\<Assertion</span></span>  
  
 <span data-ttu-id="43db8-247">MajorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="43db8-247">MajorVersion="1"</span></span>  
  
 <span data-ttu-id="43db8-248">MinorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="43db8-248">MinorVersion="1"</span></span>  
  
 <span data-ttu-id="43db8-249">AssertionId="[ID]"</span><span class="sxs-lookup"><span data-stu-id="43db8-249">AssertionId="[ID]"</span></span>  
  
 <span data-ttu-id="43db8-250">Issuer="[string]"</span><span class="sxs-lookup"><span data-stu-id="43db8-250">Issuer="[string]"</span></span>  
  
 <span data-ttu-id="43db8-251">IssueInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="43db8-251">IssueInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="43db8-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span><span class="sxs-lookup"><span data-stu-id="43db8-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span></span>  
  
 <span data-ttu-id="43db8-253">\<AudienceRestrictionCondition></span><span class="sxs-lookup"><span data-stu-id="43db8-253">\<AudienceRestrictionCondition></span></span>  
  
 <span data-ttu-id="43db8-254">\<Gruppo di destinatari > [uri]\</Audience > +</span><span class="sxs-lookup"><span data-stu-id="43db8-254">\<Audience>[uri]\</Audience>+</span></span>  
  
 <span data-ttu-id="43db8-255">\</AudienceRestrictionCondition>\*</span><span class="sxs-lookup"><span data-stu-id="43db8-255">\</AudienceRestrictionCondition>\*</span></span>  
  
 <span data-ttu-id="43db8-256">\<DoNotCacheCondition />\*</span><span class="sxs-lookup"><span data-stu-id="43db8-256">\<DoNotCacheCondition />\*</span></span>  
  
 <span data-ttu-id="43db8-257"><\!-tipo di base astratta</span><span class="sxs-lookup"><span data-stu-id="43db8-257"><\!-- abstract base type</span></span>  
  
 <span data-ttu-id="43db8-258">\<Condizione / > \*</span><span class="sxs-lookup"><span data-stu-id="43db8-258">\<Condition />\*</span></span>  
  
 -->  
  
 <span data-ttu-id="43db8-259">\</Conditions>?</span><span class="sxs-lookup"><span data-stu-id="43db8-259">\</Conditions>?</span></span>  
  
 <span data-ttu-id="43db8-260">\<Advice></span><span class="sxs-lookup"><span data-stu-id="43db8-260">\<Advice></span></span>  
  
 <span data-ttu-id="43db8-261">\<AssertionIDReference > [ID]\</AssertionIDReference > \*</span><span class="sxs-lookup"><span data-stu-id="43db8-261">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span></span>  
  
 <span data-ttu-id="43db8-262">\<Asserzione > [asserzione]\</Assertion > \*</span><span class="sxs-lookup"><span data-stu-id="43db8-262">\<Assertion>[assertion]\</Assertion>\*</span></span>  
  
 <span data-ttu-id="43db8-263">[any]\*</span><span class="sxs-lookup"><span data-stu-id="43db8-263">[any]\*</span></span>  
  
 <span data-ttu-id="43db8-264">\</Advice>?</span><span class="sxs-lookup"><span data-stu-id="43db8-264">\</Advice>?</span></span>  
  
 <span data-ttu-id="43db8-265"><\!: Tipi di base astratti</span><span class="sxs-lookup"><span data-stu-id="43db8-265"><\!-- Abstract base types</span></span>  
  
 <span data-ttu-id="43db8-266">\<Istruzione / > \*</span><span class="sxs-lookup"><span data-stu-id="43db8-266">\<Statement />\*</span></span>  
  
 <span data-ttu-id="43db8-267">\<SubjectStatement></span><span class="sxs-lookup"><span data-stu-id="43db8-267">\<SubjectStatement></span></span>  
  
 <span data-ttu-id="43db8-268">\<Subject></span><span class="sxs-lookup"><span data-stu-id="43db8-268">\<Subject></span></span>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 <span data-ttu-id="43db8-269">\<SubjectConfirmation></span><span class="sxs-lookup"><span data-stu-id="43db8-269">\<SubjectConfirmation></span></span>  
  
 <span data-ttu-id="43db8-270">\<ConfirmationMethod > [anyUri]\</ConfirmationMethod > +</span><span class="sxs-lookup"><span data-stu-id="43db8-270">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span></span>  
  
 <span data-ttu-id="43db8-271">\<SubjectConfirmationData > [qualsiasi]\</SubjectConfirmationData >?</span><span class="sxs-lookup"><span data-stu-id="43db8-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span></span>  
  
 <span data-ttu-id="43db8-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span><span class="sxs-lookup"><span data-stu-id="43db8-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span></span>  
  
 <span data-ttu-id="43db8-273">\</SubjectConfirmation>?</span><span class="sxs-lookup"><span data-stu-id="43db8-273">\</SubjectConfirmation>?</span></span>  
  
 <span data-ttu-id="43db8-274">\</Subject></span><span class="sxs-lookup"><span data-stu-id="43db8-274">\</Subject></span></span>  
  
 <span data-ttu-id="43db8-275">\</SubjectStatement>\*</span><span class="sxs-lookup"><span data-stu-id="43db8-275">\</SubjectStatement>\*</span></span>  
  
 -->  
  
 <span data-ttu-id="43db8-276">\<AuthenticationStatement</span><span class="sxs-lookup"><span data-stu-id="43db8-276">\<AuthenticationStatement</span></span>  
  
 <span data-ttu-id="43db8-277">AuthenticationMethod="[uri]"</span><span class="sxs-lookup"><span data-stu-id="43db8-277">AuthenticationMethod="[uri]"</span></span>  
  
 <span data-ttu-id="43db8-278">AuthenticationInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="43db8-278">AuthenticationInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="43db8-279">[Subject]</span><span class="sxs-lookup"><span data-stu-id="43db8-279">[Subject]</span></span>  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <span data-ttu-id="43db8-280"><AuthorityBinding</span><span class="sxs-lookup"><span data-stu-id="43db8-280"><AuthorityBinding</span></span>  
  
 <span data-ttu-id="43db8-281">AuthorityKind="[QName]"</span><span class="sxs-lookup"><span data-stu-id="43db8-281">AuthorityKind="[QName]"</span></span>  
  
 <span data-ttu-id="43db8-282">Location="[uri]"</span><span class="sxs-lookup"><span data-stu-id="43db8-282">Location="[uri]"</span></span>  
  
 <span data-ttu-id="43db8-283">Binding="[uri]"</span><span class="sxs-lookup"><span data-stu-id="43db8-283">Binding="[uri]"</span></span>  
  
 />*  
  
 <span data-ttu-id="43db8-284">\</AuthenticationStatement>\*</span><span class="sxs-lookup"><span data-stu-id="43db8-284">\</AuthenticationStatement>\*</span></span>  
  
 <span data-ttu-id="43db8-285">\<AttributeStatement></span><span class="sxs-lookup"><span data-stu-id="43db8-285">\<AttributeStatement></span></span>  
  
 <span data-ttu-id="43db8-286">[Subject]</span><span class="sxs-lookup"><span data-stu-id="43db8-286">[Subject]</span></span>  
  
 <span data-ttu-id="43db8-287">\<Attributo</span><span class="sxs-lookup"><span data-stu-id="43db8-287">\<Attribute</span></span>  
  
 <span data-ttu-id="43db8-288">AttributeName="[string]"</span><span class="sxs-lookup"><span data-stu-id="43db8-288">AttributeName="[string]"</span></span>  
  
 <span data-ttu-id="43db8-289">AttributeNamespace="[uri]"</span><span class="sxs-lookup"><span data-stu-id="43db8-289">AttributeNamespace="[uri]"</span></span>  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 <span data-ttu-id="43db8-290">\</ Attributo > +</span><span class="sxs-lookup"><span data-stu-id="43db8-290">\</Attribute>+</span></span>  
  
 <span data-ttu-id="43db8-291">\</AttributeStatement>\*</span><span class="sxs-lookup"><span data-stu-id="43db8-291">\</AttributeStatement>\*</span></span>  
  
 <span data-ttu-id="43db8-292">\<AuthorizationDecisionStatement</span><span class="sxs-lookup"><span data-stu-id="43db8-292">\<AuthorizationDecisionStatement</span></span>  
  
 <span data-ttu-id="43db8-293">Resource="[uri]"</span><span class="sxs-lookup"><span data-stu-id="43db8-293">Resource="[uri]"</span></span>  
  
 <span data-ttu-id="43db8-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span><span class="sxs-lookup"><span data-stu-id="43db8-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span></span>  
  
 >  
  
 <span data-ttu-id="43db8-295">[Subject]</span><span class="sxs-lookup"><span data-stu-id="43db8-295">[Subject]</span></span>  
  
 <span data-ttu-id="43db8-296">\<Action Namespace="[uri]">[string]\</Action>+</span><span class="sxs-lookup"><span data-stu-id="43db8-296">\<Action Namespace="[uri]">[string]\</Action>+</span></span>  
  
 <span data-ttu-id="43db8-297">\<Evidence></span><span class="sxs-lookup"><span data-stu-id="43db8-297">\<Evidence></span></span>  
  
 <span data-ttu-id="43db8-298">\<AssertionIDReference > [ID]\</AssertionIDReference > +</span><span class="sxs-lookup"><span data-stu-id="43db8-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span></span>  
  
 <span data-ttu-id="43db8-299">\<Asserzione > [asserzione]\</Assertion > +</span><span class="sxs-lookup"><span data-stu-id="43db8-299">\<Assertion>[assertion]\</Assertion>+</span></span>  
  
 <span data-ttu-id="43db8-300">\</Evidence>?</span><span class="sxs-lookup"><span data-stu-id="43db8-300">\</Evidence>?</span></span>  
  
 <span data-ttu-id="43db8-301">\</AuthorizationDecisionStatement>\*</span><span class="sxs-lookup"><span data-stu-id="43db8-301">\</AuthorizationDecisionStatement>\*</span></span>  
  
 <span data-ttu-id="43db8-302">\</ Asserzione ></span><span class="sxs-lookup"><span data-stu-id="43db8-302">\</Assertion></span></span>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="43db8-303">Informazioni rimosse dai corpi dei messaggi in caso di registrazione di messaggi decrittografati/non crittografati</span><span class="sxs-lookup"><span data-stu-id="43db8-303">Information Removed from Message Bodies When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="43db8-304">Come descritto in precedenza, WCF rimuove chiavi e potenziali informazioni personali note dalle intestazioni del messaggio per i messaggi decrittografati/non crittografati registrati.</span><span class="sxs-lookup"><span data-stu-id="43db8-304">As previously described, WCF removes keys and known potentially personal information from message headers for logged decrypted/unencrypted messages.</span></span> <span data-ttu-id="43db8-305">Inoltre, WCF consente di rimuovere le chiavi e potenziali informazioni personali note dai corpi dei messaggi per gli elementi di corpo e le azioni nell'elenco seguente, che descrivono messaggi di sicurezza coinvolti nello scambio di chiave.</span><span class="sxs-lookup"><span data-stu-id="43db8-305">In addition, WCF removes keys and known potentially personal information from message bodies for the body elements and actions in the following list, which describe security messages involved in key exchange.</span></span>  
  
 <span data-ttu-id="43db8-306">Per gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="43db8-306">For the following namespaces:</span></span>  
  
 <span data-ttu-id="43db8-307">xmlns:WST = "http://schemas.xmlsoap.org/ws/2004/04/trust" e xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust" (ad esempio, se nessuna azione disponibile)</span><span class="sxs-lookup"><span data-stu-id="43db8-307">xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (for example, if no action available)</span></span>  
  
 <span data-ttu-id="43db8-308">Vengono rimosse informazioni per questi elementi del corpo, che implicano lo scambio di chiavi:</span><span class="sxs-lookup"><span data-stu-id="43db8-308">Information is removed for these body elements, which involve key exchange:</span></span>  
  
 <span data-ttu-id="43db8-309">wst:RequestSecurityToken</span><span class="sxs-lookup"><span data-stu-id="43db8-309">wst:RequestSecurityToken</span></span>  
  
 <span data-ttu-id="43db8-310">wst:RequestSecurityTokenResponse</span><span class="sxs-lookup"><span data-stu-id="43db8-310">wst:RequestSecurityTokenResponse</span></span>  
  
 <span data-ttu-id="43db8-311">wst:RequestSecurityTokenResponseCollection</span><span class="sxs-lookup"><span data-stu-id="43db8-311">wst:RequestSecurityTokenResponseCollection</span></span>  
  
 <span data-ttu-id="43db8-312">Vengono inoltre rimosse informazioni per ognuna delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43db8-312">Information is also removed for each of the following Actions:</span></span>  
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend`
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a><span data-ttu-id="43db8-313">Non vengono rimosse informazioni dalle intestazioni e dai dati del corpo specifici dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="43db8-313">No Information Is Removed from Application-specific Headers and Body Data</span></span>  
 <span data-ttu-id="43db8-314">WCF non tiene traccia delle informazioni personali nelle intestazioni specifiche dell'applicazione (ad esempio, le stringhe di query) o dati del corpo (ad esempio, numero di carta di credito).</span><span class="sxs-lookup"><span data-stu-id="43db8-314">WCF does not track personal information in application-specific headers (for example, query strings) or body data (for example, credit card number).</span></span>  
  
 <span data-ttu-id="43db8-315">Quando la registrazione messaggi è attiva, le informazioni personali presenti in intestazioni e dati del corpo specifici dell'applicazione potrebbero essere visibili nei log.</span><span class="sxs-lookup"><span data-stu-id="43db8-315">When message logging is on, personal information in application-specific headers and body information may be visible in the logs.</span></span> <span data-ttu-id="43db8-316">È il distributore dell'applicazione ad essere, ancora una volta, responsabile dell'impostazione degli elenchi di controllo di accesso nei file di configurazione e di log.</span><span class="sxs-lookup"><span data-stu-id="43db8-316">Again, the application deployer is responsible for setting the ACLs on the configuration and log files.</span></span> <span data-ttu-id="43db8-317">Egli può inoltre disattivare la registrazione, se non desidera che queste informazioni siano visibili, o può filtrare le informazioni dai file di log dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-317">He also can turn off logging if he does not want this information to be visible, or he may filter out this information from the log files after it is logged.</span></span>  
  
### <a name="service-model-tracing"></a><span data-ttu-id="43db8-318">Traccia del modello di servizio</span><span class="sxs-lookup"><span data-stu-id="43db8-318">Service Model Tracing</span></span>  
 <span data-ttu-id="43db8-319">L'origine della traccia del modello di servizio (<xref:System.ServiceModel>) consente la traccia di attività ed eventi correlati all'elaborazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="43db8-319">The Service Model trace source (<xref:System.ServiceModel>) enables tracing of activities and events related to message processing.</span></span> <span data-ttu-id="43db8-320">Questa funzionalità usa la funzionalità di diagnostica di .NET Framework da <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="43db8-320">This feature uses the .NET Framework diagnostic functionality from <xref:System.Diagnostics>.</span></span> <span data-ttu-id="43db8-321">Come con la proprietà <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>, il percorso e il relativo elenco di controllo di accesso sono configurabili dall'utente mediante i file di configurazione dell'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="43db8-321">As with the <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> property, the location and its ACL are user-configurable using .NET Framework application configuration files.</span></span> <span data-ttu-id="43db8-322">Come con la registrazione messaggi, il percorso dei file viene sempre configurato quando l'amministratore attiva la traccia ed è quindi l'amministratore a controllare l'elenco di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="43db8-322">As with message logging, the file location is always configured when the administrator enables tracing; thus, the administrator controls the ACL.</span></span>  
  
 <span data-ttu-id="43db8-323">Le tracce contengono intestazioni di messaggio quando un messaggio è nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="43db8-323">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="43db8-324">Si applicano le stesse regole descritte nella sezione precedente per nascondere potenziali informazioni personali presenti nelle intestazioni dei messaggi: le informazioni personali precedentemente identificate vengono rimosse, per impostazione predefinita, dalle intestazioni nelle tracce.</span><span class="sxs-lookup"><span data-stu-id="43db8-324">The same rules for hiding potentially personal information in message headers in the previous section apply: the personal information previously identified is removed by default from the headers in traces.</span></span> <span data-ttu-id="43db8-325">L'amministratore del computer e il distributore dell'applicazione devono modificare la configurazione per poter registrare potenziali informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="43db8-325">Both the machine administrator and the application deployer must modify the configuration in order to log potentially personal information.</span></span> <span data-ttu-id="43db8-326">Tuttavia, le informazioni personali contenute nelle intestazioni specifiche dell'applicazione vengono registrate nelle tracce.</span><span class="sxs-lookup"><span data-stu-id="43db8-326">However, personal information contained in application-specific headers is logged in traces.</span></span> <span data-ttu-id="43db8-327">Il distributore dell'applicazione è responsabile dell'impostazione degli elenchi di controllo di accesso nei file di configurazione e di traccia.</span><span class="sxs-lookup"><span data-stu-id="43db8-327">The application deployer is responsible for setting the ACLs on the configuration and trace files.</span></span> <span data-ttu-id="43db8-328">Può inoltre disattivare la traccia se non desidera che queste informazioni siano visibili, o può filtrare le informazioni dai file di traccia dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-328">He also can turn off tracing if he does not want this information to be visible, or he can filter out this information from the trace files after it is logged.</span></span>  
  
 <span data-ttu-id="43db8-329">Come parte della traccia ServiceModel, ID univoci (denominati ID attività e GUID) collegano insieme attività differenti quando un messaggio passa attraverso diverse parti dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="43db8-329">As part of ServiceModel Tracing, Unique IDs (called Activity IDs, and typically a GUID) link different activities together as a message flows through different parts of the infrastructure.</span></span>  
  
#### <a name="custom-trace-listeners"></a><span data-ttu-id="43db8-330">Listener di traccia personalizzati</span><span class="sxs-lookup"><span data-stu-id="43db8-330">Custom Trace Listeners</span></span>  
 <span data-ttu-id="43db8-331">Per la registrazione e la traccia dei messaggi è possibile configurare un listener di traccia personalizzato che può inviare tracce e messaggi in rete, ad esempio, a un database remoto.</span><span class="sxs-lookup"><span data-stu-id="43db8-331">For both message logging and tracing, a custom trace listener can be configured, which can send traces and messages on the wire (for example, to a remote database).</span></span> <span data-ttu-id="43db8-332">Il distributore dell'applicazione è responsabile della configurazione di listener personalizzati o dell'abilitazione degli utenti a tale attività.</span><span class="sxs-lookup"><span data-stu-id="43db8-332">The application deployer is responsible for configuring custom listeners or enabling users to do so.</span></span> <span data-ttu-id="43db8-333">È inoltre responsabile di qualsiasi informazione personale esposta nel percorso remoto e della corretta applicazione di elenchi di controllo di accesso al percorso in questione.</span><span class="sxs-lookup"><span data-stu-id="43db8-333">He is also responsible for any personal information exposed at the remote location, and for properly applying ACLs to this location.</span></span>  
  
### <a name="other-features-for-it-professionals"></a><span data-ttu-id="43db8-334">Altre funzionalità per i professionisti IT</span><span class="sxs-lookup"><span data-stu-id="43db8-334">Other features for IT Professionals</span></span>  
 <span data-ttu-id="43db8-335">WCF include un provider WMI che espone le informazioni di configurazione dell'infrastruttura WCF tramite WMI (forniti con Windows).</span><span class="sxs-lookup"><span data-stu-id="43db8-335">WCF has a WMI provider that exposes the WCF infrastructure configuration information through WMI (shipped with Windows).</span></span> <span data-ttu-id="43db8-336">Per impostazione predefinita, l'interfaccia WMI è disponibile per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="43db8-336">By default, the WMI interface is available to administrators.</span></span>  
  
 <span data-ttu-id="43db8-337">Configurazione di WCF utilizza il meccanismo di configurazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="43db8-337">WCF configuration uses the .NET Framework configuration mechanism.</span></span> <span data-ttu-id="43db8-338">I file di configurazione vengono archiviati sul computer.</span><span class="sxs-lookup"><span data-stu-id="43db8-338">The configuration files are stored on the machine.</span></span> <span data-ttu-id="43db8-339">Lo sviluppatore dell'applicazione e l'amministratore creano i file di configurazione e l'elenco di controllo di accesso per ognuno dei requisiti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-339">The application developer and the administrator create the configuration files and ACL for each of the application's requirements.</span></span> <span data-ttu-id="43db8-340">Un file di configurazione può contenere indirizzi degli endpoint e collegamenti ai certificati nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="43db8-340">A configuration file can contain endpoint addresses and links to certificates in the certificate store.</span></span> <span data-ttu-id="43db8-341">I certificati possono essere usati per fornire dati dell'applicazione e configurare le varie proprietà delle funzionalità usate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-341">The certificates can be used to provide application data to configure various properties of the features used by the application.</span></span>  
  
 <span data-ttu-id="43db8-342">WCF Usa anche la funzionalità di dump di processo di .NET Framework chiamando il <xref:System.Environment.FailFast%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="43db8-342">WCF also uses the .NET Framework process dump functionality by calling the <xref:System.Environment.FailFast%2A> method.</span></span>  
  
### <a name="it-pro-tools"></a><span data-ttu-id="43db8-343">Strumenti per i professionisti IT</span><span class="sxs-lookup"><span data-stu-id="43db8-343">IT Pro Tools</span></span>  
 <span data-ttu-id="43db8-344">WCF fornisce anche gli strumenti professionali a IT seguenti, che vengono fornito con il SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="43db8-344">WCF also provides the following IT professional tools, which ship in the Windows SDK.</span></span>  
  
#### <a name="svctraceviewerexe"></a><span data-ttu-id="43db8-345">SvcTraceViewer.exe</span><span class="sxs-lookup"><span data-stu-id="43db8-345">SvcTraceViewer.exe</span></span>  
 <span data-ttu-id="43db8-346">Il Visualizzatore Visualizza file di traccia WCF.</span><span class="sxs-lookup"><span data-stu-id="43db8-346">The viewer displays WCF trace files.</span></span> <span data-ttu-id="43db8-347">Il visualizzatore mostra tutte le informazioni contenute nelle tracce.</span><span class="sxs-lookup"><span data-stu-id="43db8-347">The viewer shows whatever information is contained in the traces.</span></span>  
  
#### <a name="svcconfigeditorexe"></a><span data-ttu-id="43db8-348">SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="43db8-348">SvcConfigEditor.exe</span></span>  
 <span data-ttu-id="43db8-349">L'editor consente all'utente di creare e modificare i file di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="43db8-349">The editor allows the user to create and edit WCF configuration files.</span></span> <span data-ttu-id="43db8-350">L'editor mostra tutte le informazioni contenute nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-350">The editor shows whatever information is contained in the configuration files.</span></span> <span data-ttu-id="43db8-351">La stessa attività può essere eseguita con un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="43db8-351">The same task can be accomplished with a text editor.</span></span>  
  
#### <a name="servicemodelreg"></a><span data-ttu-id="43db8-352">ServiceModel_Reg</span><span class="sxs-lookup"><span data-stu-id="43db8-352">ServiceModel_Reg</span></span>  
 <span data-ttu-id="43db8-353">Questo strumento consente all'utente di gestire installazioni ServiceModel in un computer.</span><span class="sxs-lookup"><span data-stu-id="43db8-353">This tool allows the user to manage ServiceModel installs on a machine.</span></span> <span data-ttu-id="43db8-354">Lo strumento visualizza messaggi di stato nella finestra della console quando viene eseguito e, nel processo, possono essere visualizzate informazioni relative alla configurazione dell'installazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="43db8-354">The tool displays status messages in a console window when it runs and, in the process, may display information about the configuration of the WCF installation.</span></span>  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a><span data-ttu-id="43db8-355">WSATConfig.exe e WSATUI.dll</span><span class="sxs-lookup"><span data-stu-id="43db8-355">WSATConfig.exe and WSATUI.dll</span></span>  
 <span data-ttu-id="43db8-356">Questi strumenti consentono ai professionisti IT di configurare il supporto di rete interoperativo WS-AtomicTransaction in WCF.</span><span class="sxs-lookup"><span data-stu-id="43db8-356">These tools allow IT Professionals to configure interoperable WS-AtomicTransaction network support in WCF.</span></span> <span data-ttu-id="43db8-357">Gli strumenti visualizzano i valori delle impostazioni WS-AtomicTransaction più comunemente usate archiviati nel Registro di sistema e consentono all'utente di modificarli.</span><span class="sxs-lookup"><span data-stu-id="43db8-357">The tools display and allow the user to change the values of the most commonly used WS-AtomicTransaction settings stored in the registry.</span></span>  
  
## <a name="cross-cutting-features"></a><span data-ttu-id="43db8-358">Funzionalità a montaggio incrociato</span><span class="sxs-lookup"><span data-stu-id="43db8-358">Cross-cutting Features</span></span>  
 <span data-ttu-id="43db8-359">Le funzionalità seguenti sono a montaggio incrociato,</span><span class="sxs-lookup"><span data-stu-id="43db8-359">The following features are cross-cutting.</span></span> <span data-ttu-id="43db8-360">ovvero possono essere composte con qualsiasi funzionalità precedente.</span><span class="sxs-lookup"><span data-stu-id="43db8-360">That is, they can be composed with any of the preceding features.</span></span>  
  
### <a name="service-framework"></a><span data-ttu-id="43db8-361">Framework dei servizi</span><span class="sxs-lookup"><span data-stu-id="43db8-361">Service Framework</span></span>  
 <span data-ttu-id="43db8-362">Le intestazioni possono contenere un ID di istanza, che è un GUID che associa un messaggio a un'istanza di una classe CLR.</span><span class="sxs-lookup"><span data-stu-id="43db8-362">Headers can contain an instance ID, which is a GUID that associates a message with an instance of a CLR class.</span></span>  
  
 <span data-ttu-id="43db8-363">Il linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) contiene una definizione della porta.</span><span class="sxs-lookup"><span data-stu-id="43db8-363">The Web Services Description Language (WSDL) contains a definition of the port.</span></span> <span data-ttu-id="43db8-364">Ogni porta ha un indirizzo endpoint e un'associazione che rappresenta i servizi usati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-364">Each port has an endpoint address and a binding that represents the services used by the application.</span></span> <span data-ttu-id="43db8-365">L'esposizione del codice WSDL può essere disattivata usando la configurazione.</span><span class="sxs-lookup"><span data-stu-id="43db8-365">Exposing WSDL can be turned off using configuration.</span></span> <span data-ttu-id="43db8-366">Nessuna informazioni viene conservata sul computer.</span><span class="sxs-lookup"><span data-stu-id="43db8-366">No information is retained on the machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43db8-367">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43db8-367">See also</span></span>

- [<span data-ttu-id="43db8-368">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="43db8-368">Windows Communication Foundation</span></span>](index.md)
- [<span data-ttu-id="43db8-369">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="43db8-369">Security</span></span>](../../../docs/framework/wcf/feature-details/security.md)
