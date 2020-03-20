---
title: Programmazione di rete in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
ms.openlocfilehash: 1e7f0123ab07fd4e83eea957b72bf79eeeecef2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74204686"
---
# <a name="network-programming-in-the-net-framework"></a>Programmazione di rete in .NET Framework
Con Microsoft .NET Framework viene fornita un'implementazione a più livelli, estendibile e gestita, di servizi Internet che possono essere integrati nelle applicazioni in modo rapido e semplice. Le applicazioni di rete possono essere compilate su protocolli modulari per usufruire automaticamente di nuovi protocolli Internet oppure possono utilizzare un'implementazione gestita dell'interfaccia Windows Sockets per utilizzare la rete a livello di socket.  
  
## <a name="in-this-section"></a>Contenuto della sezione  

 [Introduzione ai protocolli di collegamento](introducing-pluggable-protocols.md)  
 Viene descritto come accedere a una risorsa Internet indipendentemente dal protocollo di accesso richiesto.  
  
 [Richiesta di dati](requesting-data.md)  
 Viene illustrato come utilizzare i protocolli modulari per caricare e scaricare i dati dalle risorse Internet.  
  
 [programmazione di protocolli di collegamento](programming-pluggable-protocols.md)  
 Viene illustrato come derivare classi specifiche del protocollo per implementare protocolli modulari.  
  
 [Uso di protocolli applicativi](using-application-protocols.md)  
 Viene descritta la programmazione di applicazioni che utilizzano protocolli di rete come TCP, UDP e HTTP.  
  
 [Protocollo Internet versione 6](internet-protocol-version-6.md)  
 Vengono illustrati i vantaggi della versione 6 (IPv6) del protocollo Internet rispetto alla versione corrente della famiglia di prodotti del protocollo Internet (IPv4), vengono descritti l'indirizzamento, il routing e la configurazione automatica del protocollo IPv6 e come abilitare e disabilitare il protocollo IPv6.  
  
 [Configurazione di applicazioni Internet](configuring-internet-applications.md)  
 Viene spiegato come utilizzare i file di configurazione di .NET Framework per configurare le applicazioni Internet.  
  
 [Traccia di rete in .NET Framework](network-tracing.md)  
 Viene spiegato come utilizzare la traccia di rete per ottenere informazioni sulle chiamate ai metodi e sul traffico di rete generato da un'applicazione gestita.  
  
 [Gestione della cache per le applicazioni di rete](cache-management-for-network-applications.md)  
 Viene descritto come utilizzare la memorizzazione nella cache per le applicazioni che utilizzano le classi <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>e <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .  
  
 [Sicurezza nella programmazione di rete](security-in-network-programming.md)  
 Viene descritto come utilizzare le tecniche standard di sicurezza e di autenticazione Internet.  
  
 [Procedure consigliate per le classi System.Net](best-practices-for-system-net-classes.md)  
 Vengono forniti consigli e suggerimenti per usufruire al meglio delle applicazioni Internet.  
  
 [Accesso a Internet tramite un proxy](accessing-the-internet-through-a-proxy.md)  
 Viene descritto come configurare i proxy.  
  
 [NetworkInformation](networkinformation.md)  
 Viene descritto come raccogliere informazioni sugli eventi, le modifiche, le statistiche e le proprietà di rete e viene inoltre illustrato come determinare se un host remoto è raggiungibile tramite la classe <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> .  
  
 [Modifiche allo spazio dei nomi System.Uri nella versione 2.0Changes to the System.Uri namespace in Version 2.0](changes-to-the-system-uri-namespace-in-version-2-0.md)  
 Vengono illustrate varie modifiche apportate alla classe <xref:System.Uri?displayProperty=nameWithType> nella versione 2.0 per correggere un comportamento non corretto, migliorare l'usabilità e aumentare la sicurezza.  
  
 [Supporto per IRI (International Resource Identifier) in System.Uri](international-resource-identifier-support-in-system-uri.md)  
 Vengono descritti i miglioramenti alla classe <xref:System.Uri?displayProperty=nameWithType> nelle versioni 3.5, 3.0 SP1 e 2.0 SP1 per il supporto dell'IRI (International Resource Identifier) e l'IDN (Internationalized Domain Name).  
  
 [Miglioramenti apportati alle prestazioni dei socket nella versione 3.5](socket-performance-enhancements-in-version-3-5.md)  
 Viene descritta una serie di miglioramenti apportati alla classe <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> nelle versioni 3.5, 3.0 SP1 e 2.0 SP1 che forniscono un modello asincrono alternativo che può essere utilizzato da applicazioni socket ad alte prestazioni specializzate.  
  
 [Protocollo PNRP (Peer Name Resolution Protocol)](peer-name-resolution-protocol.md)  
 Viene descritto il supporto aggiunto nella versione 3.5 per supportare il protocollo PNRP (Peer Name Resolution Protocol), un protocollo di risoluzione dei nomi e di registrazione dei nomi dinamica senza server. Queste nuove funzionalità sono supportate dallo spazio dei nomi <xref:System.Net.PeerToPeer?displayProperty=nameWithType> .  
  
 [Collaborazione peer-to-peer](peer-to-peer-collaboration.md)  
 Viene descritto il supporto aggiunto nella versione 3.5 per supportare la collaborazione peer-to-peer che sfrutta il protocollo PNRP. Queste nuove funzionalità sono supportate dallo spazio dei nomi <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> .  
  
 [Modifiche apportate all'autenticazione NTLM per HttpWebRequest nella versione 3.5 SP1](changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 Vengono descritte le modifiche di sicurezza apportate nella versione 3.5 SP1 che influiscono sul modo in cui l'autenticazione Windows integrata viene gestita da <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>e le classi correlate nello spazio dei nomi System.Net.  
  
 [Integrated Windows Authentication with Extended Protection (autenticazione integrata di Windows con protezione estesa)](integrated-windows-authentication-with-extended-protection.md)  
 Vengono descritti i miglioramenti alla protezione estesa che influiscono sul modo in cui l'autenticazione Windows integrata viene gestita da <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>e le classi correlate nello spazio dei nomi <xref:System.Net?displayProperty=nameWithType> e in quelli correlati.  
  
 [NAT Traversal using IPv6 and Teredo](nat-traversal-using-ipv6-and-teredo.md) (Attraversamento NAT con IPv6 e Teredo)  
 Vengono descritti i miglioramenti aggiunti agli spazi dei nomi <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>e <xref:System.Net.Sockets?displayProperty=nameWithType> per il supporto dell'attraversamento NAT tramite IPv6 e Teredo.  
  
 [Network Isolation for Windows Store Apps](network-isolation-for-windows-store-apps.md) (Isolamento rete per app di Windows Store)  
 Descrive l'impatto dell'isolamento rete <xref:System.Net> <xref:System.Net.Http>quando <xref:System.Net.Http.Headers> le classi negli spazi dei nomi , , e vengono utilizzate nelle app di Windows 8.x Store.  
  
 [Esempi di programmazione di rete](network-programming-samples.md)  
 Collegamenti a esempi scaricabili di programmazione di rete che utilizzano le classi negli spazi dei nomi <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> .  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Net?displayProperty=nameWithType>  
 Fornisce una semplice interfaccia di programmazione per molti dei protocolli attualmente usati per le reti. Le classi <xref:System.Net.WebRequest?displayProperty=nameWithType> e <xref:System.Net.WebResponse?displayProperty=nameWithType> in questo spazio dei nomi sono la base dei protocolli modulari.  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 Definisce i tipi e le enumerazioni utilizzati per specificare i criteri di cache per le risorse ottenute mediante le classi <xref:System.Net.WebRequest?displayProperty=nameWithType> e <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 Classi utilizzate dalle applicazioni per accedere a livello di codice alle impostazioni di configurazione dello spazio dei nomi System.Net e per aggiornarle.  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 Classi che forniscono un'interfaccia di programmazione per le moderne applicazioni HTTP.  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 Fornisce il supporto per le raccolte di intestazioni HTTP utilizzate dallo spazio dei nomi <xref:System.Net.Http?displayProperty=nameWithType> .  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 Classi per creare e inviare messaggi di posta elettronica utilizzando il protocollo SMTP.  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 Definisce i tipi che sono utilizzati per rappresentare le intestazioni MIME (Multipurpose Internet Mail Exchange) utilizzate dalle classi nello spazio dei nomi <xref:System.Net.Mail?displayProperty=nameWithType> .  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 Classi per raccogliere a livello di codice informazioni sugli eventi, le modifiche, le statistiche e le proprietà della rete.  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 Fornisce un'implementazione gestita del protocollo PNRP (Peer Name Resolution Protocol) per gli sviluppatori.  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 Fornisce un'implementazione gestita dell'interfaccia di collaborazione peer-to-peer per gli sviluppatori.  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 Classi per fornire i flussi di rete per comunicazioni sicure tra host.  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 Fornisce un'implementazione gestita dell'interfaccia Windows Sockets (Winsock) per sviluppatori che hanno la necessità di mantenere sotto controllo l'accesso alla rete.  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 Fornisce un'implementazione gestita dell'interfaccia WebSocket per gli sviluppatori.  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 Fornisce una rappresentazione dell'oggetto di un URI (Uniform Resource Identifier) e l'accesso facile alle parti dell'URI.  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 Fornisce il supporto per l'autenticazione utilizzando la protezione estesa per le applicazioni.  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 Fornisce il supporto per la configurazione dell'autenticazione utilizzando la protezione estesa per le applicazioni.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure consigliate per Transport Layer Security (TLS) con .NET Framework](tls.md)
- [Procedure per la programmazione di rete](network-programming-how-to-topics.md)
- [Esempi di programmazione di rete](network-programming-samples.md)
- [HttpClient Sample](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664) (Esempio con HttpClient)
