---
title: Programmazione di rete in .NET Framework
description: Usare queste risorse per integrare l'implementazione a più livelli, estendibile e gestita dei servizi Internet forniti dal .NET Framework nelle applicazioni.
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
ms.openlocfilehash: 117fce887a04def7f9b3f7654a8e9e675ea462d2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502405"
---
# <a name="network-programming-in-the-net-framework"></a><span data-ttu-id="db364-103">Programmazione di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="db364-103">Network Programming in the .NET Framework</span></span>
<span data-ttu-id="db364-104">Con Microsoft .NET Framework viene fornita un'implementazione a più livelli, estendibile e gestita, di servizi Internet che possono essere integrati nelle applicazioni in modo rapido e semplice.</span><span class="sxs-lookup"><span data-stu-id="db364-104">The Microsoft .NET Framework provides a layered, extensible, and managed implementation of Internet services that can be quickly and easily integrated into your applications.</span></span> <span data-ttu-id="db364-105">Le applicazioni di rete possono essere compilate su protocolli modulari per usufruire automaticamente di nuovi protocolli Internet oppure possono utilizzare un'implementazione gestita dell'interfaccia Windows Sockets per utilizzare la rete a livello di socket.</span><span class="sxs-lookup"><span data-stu-id="db364-105">Your network applications can build on pluggable protocols to automatically take advantage of new Internet protocols, or they can use a managed implementation of the Windows socket interface to work with the network on the socket level.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db364-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="db364-106">In This Section</span></span>  

 [<span data-ttu-id="db364-107">Introduzione ai protocolli di collegamento</span><span class="sxs-lookup"><span data-stu-id="db364-107">Introducing Pluggable Protocols</span></span>](introducing-pluggable-protocols.md)  
 <span data-ttu-id="db364-108">Viene descritto come accedere a una risorsa Internet indipendentemente dal protocollo di accesso richiesto.</span><span class="sxs-lookup"><span data-stu-id="db364-108">Describes how to access an Internet resource without regard to the access protocol that it requires.</span></span>  
  
 [<span data-ttu-id="db364-109">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="db364-109">Requesting Data</span></span>](requesting-data.md)  
 <span data-ttu-id="db364-110">Viene illustrato come utilizzare i protocolli modulari per caricare e scaricare i dati dalle risorse Internet.</span><span class="sxs-lookup"><span data-stu-id="db364-110">Explains how to use pluggable protocols to upload and download data from Internet resources.</span></span>  
  
 [<span data-ttu-id="db364-111">programmazione di protocolli di collegamento</span><span class="sxs-lookup"><span data-stu-id="db364-111">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)  
 <span data-ttu-id="db364-112">Viene illustrato come derivare classi specifiche del protocollo per implementare protocolli modulari.</span><span class="sxs-lookup"><span data-stu-id="db364-112">Explains how to derive protocol-specific classes to implement pluggable protocols.</span></span>  
  
 [<span data-ttu-id="db364-113">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="db364-113">Using Application Protocols</span></span>](using-application-protocols.md)  
 <span data-ttu-id="db364-114">Viene descritta la programmazione di applicazioni che utilizzano protocolli di rete come TCP, UDP e HTTP.</span><span class="sxs-lookup"><span data-stu-id="db364-114">Describes programming applications that take advantage of network protocols such as TCP, UDP, and HTTP.</span></span>  
  
 [<span data-ttu-id="db364-115">Protocollo IP versione 6</span><span class="sxs-lookup"><span data-stu-id="db364-115">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)  
 <span data-ttu-id="db364-116">Vengono illustrati i vantaggi della versione 6 (IPv6) del protocollo Internet rispetto alla versione corrente della famiglia di prodotti del protocollo Internet (IPv4), vengono descritti l'indirizzamento, il routing e la configurazione automatica del protocollo IPv6 e come abilitare e disabilitare il protocollo IPv6.</span><span class="sxs-lookup"><span data-stu-id="db364-116">Describes the advantages of Internet Protocol version 6 (IPv6) over the current version of the Internet Protocol suite (IPv4), describes IPv6 addressing, routing and auto-configuration, and how to enable and disable IPv6.</span></span>  
  
 [<span data-ttu-id="db364-117">Configurazione di applicazioni Internet</span><span class="sxs-lookup"><span data-stu-id="db364-117">Configuring Internet Applications</span></span>](configuring-internet-applications.md)  
 <span data-ttu-id="db364-118">Viene spiegato come utilizzare i file di configurazione di .NET Framework per configurare le applicazioni Internet.</span><span class="sxs-lookup"><span data-stu-id="db364-118">Explains how to use the .NET Framework configuration files to configure Internet applications.</span></span>  
  
 [<span data-ttu-id="db364-119">Traccia di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="db364-119">Network Tracing in the .NET Framework</span></span>](network-tracing.md)  
 <span data-ttu-id="db364-120">Viene spiegato come utilizzare la traccia di rete per ottenere informazioni sulle chiamate ai metodi e sul traffico di rete generato da un'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="db364-120">Explains how to use network tracing to get information about method invocations and network traffic generated by a managed application.</span></span>  
  
 [<span data-ttu-id="db364-121">Gestione della cache per le applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="db364-121">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)  
 <span data-ttu-id="db364-122">Viene descritto come utilizzare la memorizzazione nella cache per le applicazioni che utilizzano le classi <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>e <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="db364-122">Describes how to use caching for applications that use the <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>, and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 [<span data-ttu-id="db364-123">Sicurezza nella programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="db364-123">Security in Network Programming</span></span>](security-in-network-programming.md)  
 <span data-ttu-id="db364-124">Viene descritto come utilizzare le tecniche standard di sicurezza e di autenticazione Internet.</span><span class="sxs-lookup"><span data-stu-id="db364-124">Describes how to use standard Internet security and authentication techniques.</span></span>  
  
 [<span data-ttu-id="db364-125">Procedure consigliate per le classi System.Net</span><span class="sxs-lookup"><span data-stu-id="db364-125">Best Practices for System.Net Classes</span></span>](best-practices-for-system-net-classes.md)  
 <span data-ttu-id="db364-126">Vengono forniti consigli e suggerimenti per usufruire al meglio delle applicazioni Internet.</span><span class="sxs-lookup"><span data-stu-id="db364-126">Provides tips and tricks for getting the most out of your Internet applications.</span></span>  
  
 [<span data-ttu-id="db364-127">Accesso a Internet tramite un proxy</span><span class="sxs-lookup"><span data-stu-id="db364-127">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)  
 <span data-ttu-id="db364-128">Viene descritto come configurare i proxy.</span><span class="sxs-lookup"><span data-stu-id="db364-128">Describes how to configure proxies.</span></span>  
  
 [<span data-ttu-id="db364-129">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="db364-129">NetworkInformation</span></span>](networkinformation.md)  
 <span data-ttu-id="db364-130">Viene descritto come raccogliere informazioni sugli eventi, le modifiche, le statistiche e le proprietà di rete e viene inoltre illustrato come determinare se un host remoto è raggiungibile tramite la classe <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="db364-130">Describes how to gather information about network events, changes, statistics, and properties and also explains how to determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
 [<span data-ttu-id="db364-131">Modifiche allo spazio dei nomi System. URI nella versione 2,0</span><span class="sxs-lookup"><span data-stu-id="db364-131">Changes to the System.Uri namespace in Version 2.0</span></span>](changes-to-the-system-uri-namespace-in-version-2-0.md)  
 <span data-ttu-id="db364-132">Vengono illustrate varie modifiche apportate alla classe <xref:System.Uri?displayProperty=nameWithType> nella versione 2.0 per correggere un comportamento non corretto, migliorare l'usabilità e aumentare la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="db364-132">Describes several changes made to the <xref:System.Uri?displayProperty=nameWithType> class in Version 2.0 to fixed incorrect behavior, enhance usability, and enhance security.</span></span>  
  
 [<span data-ttu-id="db364-133">Supporto per IRI (International Resource Identifier) in System.Uri</span><span class="sxs-lookup"><span data-stu-id="db364-133">International Resource Identifier Support in System.Uri</span></span>](international-resource-identifier-support-in-system-uri.md)  
 <span data-ttu-id="db364-134">Vengono descritti i miglioramenti alla classe <xref:System.Uri?displayProperty=nameWithType> nelle versioni 3.5, 3.0 SP1 e 2.0 SP1 per il supporto dell'IRI (International Resource Identifier) e l'IDN (Internationalized Domain Name).</span><span class="sxs-lookup"><span data-stu-id="db364-134">Describes enhancements to the <xref:System.Uri?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 for International Resource Identifier (IRI) and Internationalized Domain Name (IDN) support.</span></span>  
  
 [<span data-ttu-id="db364-135">Miglioramenti apportati alle prestazioni dei socket nella versione 3.5</span><span class="sxs-lookup"><span data-stu-id="db364-135">Socket Performance Enhancements in Version 3.5</span></span>](socket-performance-enhancements-in-version-3-5.md)  
 <span data-ttu-id="db364-136">Viene descritta una serie di miglioramenti apportati alla classe <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> nelle versioni 3.5, 3.0 SP1 e 2.0 SP1 che forniscono un modello asincrono alternativo che può essere utilizzato da applicazioni socket ad alte prestazioni specializzate.</span><span class="sxs-lookup"><span data-stu-id="db364-136">Describes a set of enhancements to the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 that provide an alternative asynchronous pattern that can be used by specialized high-performance socket applications.</span></span>  
  
 [<span data-ttu-id="db364-137">Protocollo PNRP (Peer Name Resolution Protocol)</span><span class="sxs-lookup"><span data-stu-id="db364-137">Peer Name Resolution Protocol</span></span>](peer-name-resolution-protocol.md)  
 <span data-ttu-id="db364-138">Viene descritto il supporto aggiunto nella versione 3.5 per supportare il protocollo PNRP (Peer Name Resolution Protocol), un protocollo di risoluzione dei nomi e di registrazione dei nomi dinamica senza server.</span><span class="sxs-lookup"><span data-stu-id="db364-138">Describes support added in Version 3.5 to support the Peer Name Resolution Protocol (PNRP), a serverless and dynamic name registration and name resolution protocol.</span></span> <span data-ttu-id="db364-139">Queste nuove funzionalità sono supportate dallo spazio dei nomi <xref:System.Net.PeerToPeer?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="db364-139">These new features are supported by the <xref:System.Net.PeerToPeer?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="db364-140">Collaborazione peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="db364-140">Peer-to-Peer Collaboration</span></span>](peer-to-peer-collaboration.md)  
 <span data-ttu-id="db364-141">Viene descritto il supporto aggiunto nella versione 3.5 per supportare la collaborazione peer-to-peer che sfrutta il protocollo PNRP.</span><span class="sxs-lookup"><span data-stu-id="db364-141">Describes support added in Version 3.5 to support the Peer-to-Peer Collaboration that builds on PNRP.</span></span> <span data-ttu-id="db364-142">Queste nuove funzionalità sono supportate dallo spazio dei nomi <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="db364-142">These new features are supported by the <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="db364-143">Modifiche apportate all'autenticazione NTLM per HttpWebRequest nella versione 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="db364-143">Changes to NTLM authentication for HttpWebRequest in Version 3.5 SP1</span></span>](changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 <span data-ttu-id="db364-144">Vengono descritte le modifiche di sicurezza apportate nella versione 3.5 SP1 che influiscono sul modo in cui l'autenticazione Windows integrata viene gestita da <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>e le classi correlate nello spazio dei nomi System.Net.</span><span class="sxs-lookup"><span data-stu-id="db364-144">Describes security changes made in Version 3.5 SP1 that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the System.Net namespace.</span></span>  
  
 [<span data-ttu-id="db364-145">Integrated Windows Authentication with Extended Protection (autenticazione integrata di Windows con protezione estesa)</span><span class="sxs-lookup"><span data-stu-id="db364-145">Integrated Windows Authentication with Extended Protection</span></span>](integrated-windows-authentication-with-extended-protection.md)  
 <span data-ttu-id="db364-146">Vengono descritti i miglioramenti alla protezione estesa che influiscono sul modo in cui l'autenticazione Windows integrata viene gestita da <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>e le classi correlate nello spazio dei nomi <xref:System.Net?displayProperty=nameWithType> e in quelli correlati.</span><span class="sxs-lookup"><span data-stu-id="db364-146">Describes enhancements for extended protection that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the <xref:System.Net?displayProperty=nameWithType> and related namespaces.</span></span>  
  
 <span data-ttu-id="db364-147">[NAT Traversal using IPv6 and Teredo](nat-traversal-using-ipv6-and-teredo.md) (Attraversamento NAT con IPv6 e Teredo)</span><span class="sxs-lookup"><span data-stu-id="db364-147">[NAT Traversal using IPv6 and Teredo](nat-traversal-using-ipv6-and-teredo.md)</span></span>  
 <span data-ttu-id="db364-148">Vengono descritti i miglioramenti aggiunti agli spazi dei nomi <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>e <xref:System.Net.Sockets?displayProperty=nameWithType> per il supporto dell'attraversamento NAT tramite IPv6 e Teredo.</span><span class="sxs-lookup"><span data-stu-id="db364-148">Describes enhancements added to the <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>, and <xref:System.Net.Sockets?displayProperty=nameWithType> namespaces to support NAT traversal using IPv6 and Teredo.</span></span>  
  
 <span data-ttu-id="db364-149">[Network Isolation for Windows Store Apps](network-isolation-for-windows-store-apps.md) (Isolamento rete per app di Windows Store)</span><span class="sxs-lookup"><span data-stu-id="db364-149">[Network Isolation for Windows Store Apps](network-isolation-for-windows-store-apps.md)</span></span>  
 <span data-ttu-id="db364-150">Descrive l'effetto dell'isolamento di rete quando le classi <xref:System.Net> negli <xref:System.Net.Http> <xref:System.Net.Http.Headers> spazi dei nomi, e vengono usate nelle app di Windows 8. x Store.</span><span class="sxs-lookup"><span data-stu-id="db364-150">Describes the impact of network isolation when classes in the <xref:System.Net>, <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces are used in Windows 8.x Store apps.</span></span>  
  
 [<span data-ttu-id="db364-151">Esempi di programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="db364-151">Network Programming Samples</span></span>](network-programming-samples.md)  
 <span data-ttu-id="db364-152">Collegamenti a esempi scaricabili di programmazione di rete che utilizzano le classi negli spazi dei nomi <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> .</span><span class="sxs-lookup"><span data-stu-id="db364-152">Links to downloadable network programming samples that use classes in the <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> namespaces.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="db364-153">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="db364-153">Reference</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <span data-ttu-id="db364-154">Fornisce una semplice interfaccia di programmazione per molti dei protocolli attualmente usati per le reti.</span><span class="sxs-lookup"><span data-stu-id="db364-154">Provides a simple programming interface for many of the protocols used on networks today.</span></span> <span data-ttu-id="db364-155">Le classi <xref:System.Net.WebRequest?displayProperty=nameWithType> e <xref:System.Net.WebResponse?displayProperty=nameWithType> in questo spazio dei nomi sono la base dei protocolli modulari.</span><span class="sxs-lookup"><span data-stu-id="db364-155">The <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.WebResponse?displayProperty=nameWithType> classes in this namespace are the basis for pluggable protocols.</span></span>  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 <span data-ttu-id="db364-156">Definisce i tipi e le enumerazioni utilizzati per specificare i criteri di cache per le risorse ottenute mediante le classi <xref:System.Net.WebRequest?displayProperty=nameWithType> e <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="db364-156">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="db364-157">Classi utilizzate dalle applicazioni per accedere a livello di codice alle impostazioni di configurazione dello spazio dei nomi System.Net e per aggiornarle.</span><span class="sxs-lookup"><span data-stu-id="db364-157">Classes that applications use to programmatically access and update configuration settings for the System.Net namespaces.</span></span>  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 <span data-ttu-id="db364-158">Classi che forniscono un'interfaccia di programmazione per le moderne applicazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="db364-158">Classes that provides a programming interface for modern HTTP applications.</span></span>  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 <span data-ttu-id="db364-159">Fornisce il supporto per le raccolte di intestazioni HTTP utilizzate dallo spazio dei nomi <xref:System.Net.Http?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="db364-159">Provides support for collections of HTTP headers used by the <xref:System.Net.Http?displayProperty=nameWithType> namespace</span></span>  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 <span data-ttu-id="db364-160">Classi per creare e inviare messaggi di posta elettronica utilizzando il protocollo SMTP.</span><span class="sxs-lookup"><span data-stu-id="db364-160">Classes to compose and send mail using the SMTP protocol.</span></span>  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 <span data-ttu-id="db364-161">Definisce i tipi che sono utilizzati per rappresentare le intestazioni MIME (Multipurpose Internet Mail Exchange) utilizzate dalle classi nello spazio dei nomi <xref:System.Net.Mail?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="db364-161">Defines types that are used to represent Multipurpose Internet Mail Exchange (MIME) headers used by classes in the <xref:System.Net.Mail?displayProperty=nameWithType> namespace.</span></span>  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 <span data-ttu-id="db364-162">Classi per raccogliere a livello di codice informazioni sugli eventi, le modifiche, le statistiche e le proprietà della rete.</span><span class="sxs-lookup"><span data-stu-id="db364-162">Classes to programmatically gather information about network events, changes, statistics, and properties.</span></span>  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 <span data-ttu-id="db364-163">Fornisce un'implementazione gestita del protocollo PNRP (Peer Name Resolution Protocol) per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="db364-163">Provides a managed implementation of the Peer Name Resolution Protocol (PNRP) for developers.</span></span>  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 <span data-ttu-id="db364-164">Fornisce un'implementazione gestita dell'interfaccia di collaborazione peer-to-peer per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="db364-164">Provides a managed implementation of the Peer-to-Peer Collaboration interface for developers.</span></span>  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 <span data-ttu-id="db364-165">Classi per fornire i flussi di rete per comunicazioni sicure tra host.</span><span class="sxs-lookup"><span data-stu-id="db364-165">Classes to provide network streams for secure communications between hosts.</span></span>  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <span data-ttu-id="db364-166">Fornisce un'implementazione gestita dell'interfaccia Windows Sockets (Winsock) per sviluppatori che hanno la necessità di mantenere sotto controllo l'accesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="db364-166">Provides a managed implementation of the Windows Sockets (Winsock) interface for developers who need to help control access to the network.</span></span>  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 <span data-ttu-id="db364-167">Fornisce un'implementazione gestita dell'interfaccia WebSocket per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="db364-167">Provides a managed implementation of the WebSocket interface for developers.</span></span>  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 <span data-ttu-id="db364-168">Fornisce una rappresentazione dell'oggetto di un URI (Uniform Resource Identifier) e l'accesso facile alle parti dell'URI.</span><span class="sxs-lookup"><span data-stu-id="db364-168">Provides an object representation of a uniform resource identifier (URI) and easy access to the parts of the URI.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 <span data-ttu-id="db364-169">Fornisce il supporto per l'autenticazione utilizzando la protezione estesa per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="db364-169">Provides support for authentication using extended protection for applications.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="db364-170">Fornisce il supporto per la configurazione dell'autenticazione utilizzando la protezione estesa per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="db364-170">Provides support for configuration of authentication using extended protection for applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db364-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db364-171">See also</span></span>

- [<span data-ttu-id="db364-172">Procedure consigliate per Transport Layer Security (TLS) con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="db364-172">Transport Layer Security (TLS) best practices with .NET Framework</span></span>](tls.md)
- [<span data-ttu-id="db364-173">Procedure per la programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="db364-173">Network Programming How-to Topics</span></span>](network-programming-how-to-topics.md)
- [<span data-ttu-id="db364-174">Esempi di programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="db364-174">Network Programming Samples</span></span>](network-programming-samples.md)
- <span data-ttu-id="db364-175">[HttpClient Sample](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664) (Esempio con HttpClient)</span><span class="sxs-lookup"><span data-stu-id="db364-175">[HttpClient Sample](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)</span></span>
