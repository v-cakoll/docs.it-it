---
title: 'Comunicazioni principali: Canali di trasporto HTTP-HTTPS'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c0a23c9-a663-461c-bdab-58b4d3e23642
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81eb778d70722cb44fa8dd4bc3f1152a12d87199
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="core-communications-httphttps-transport-channels"></a>Comunicazioni principali: canali di trasporto HTTP/HTTPS
In questo argomento vengono elencate tutte le eccezioni generate dai canali di trasporto HTTP/HTTPS di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|DigestExplicitCredsImpersonationLevel|È stato specificato il livello di rappresentazione specificato. L'autenticazione Digest HTTP supporta il livello "Rappresentazione" solo quando viene usata con una credenziale esplicita.|  
|FramingContentTypeMismatch|Il tipo di contenuto specificato non è supportato dal servizio specificato. È possibile che le associazioni di client e servizio non corrispondano fra loro.|  
|Hosting_SslSettingsMisconfigured|Le impostazioni del protocollo Secure Sockets Layer del servizio specificato non corrispondono a quelle di Internet Information Services.|  
|HttpAuthSchemeAndClientCert|La listener factory HTTPS è stata configurata in modo da richiedere un certificato client e lo schema di autenticazione specificato. Tuttavia, è consentito richiedere una sola forma di autenticazione client alla volta.|  
|HttpReceiveFailure|Si è verificato un errore durante la ricezione della risposta HTTP all'entità specificata. È possibile che l'associazione dell'endpoint del servizio non utilizzi il protocollo HTTP o che un contesto di richiesta HTTP sia stato interrotto dal server a causa dell'arresto di un servizio. Per altre informazioni, vedere i registri del server.|  
|HttpRegistrationAccessDenied|Il protocollo HTTP non è in grado di registrare l'URL specificato. Il processo non dispone dei diritti di accesso a questo spazio dei nomi (per informazioni dettagliate vedere http://msdn.microsoft.com/library/default.asp?url=/library/http/http/namespace_reservations_registrations_and_routing.asp).|  
|HttpRegistrationAlreadyExists|Il protocollo HTTP non è in grado di registrare l'URL specificato. Un'altra applicazione ha già registrato questo URL in HTTP.SYS.|  
|HttpRegistrationPortInUse|Il protocollo HTTP non è in grado di registrare l'URL specificato poiché la porta TCP specificata è usata da un'altra applicazione.|  
|HttpSendFailure|Si è verificato un errore durante la creazione della richiesta HTTP all'entità specificata. Verificare che questo errore non sia dovuto a una mancata corrispondenza fra associazioni di sicurezza. Verificare inoltre che il servizio non sia stato configurato per usare il protocollo Secure Sockets Layer.|  
|MessageXmlProtocolError|Si è verificato un problema con l'XML ricevuto dalla rete. Per maggiori dettagli, vedere l'eccezione interna.|  
|MissingContentType|Il destinatario ha restituito un errore che indica che nella richiesta all'entità specificata manca il tipo di contenuto. Per altre informazioni, vedere l'eccezione interna.|  
|ProxyAuthenticationLevelMismatch|La credenziale di autenticazione del proxy HTTP ha specificato un requisito di autenticazione reciproca più restrittivo rispetto al requisito per l'autenticazione server di destinazione.|  
|ProxyImpersonationLevelMismatch|La credenziale di autenticazione del proxy HTTP ha specificato una restrizione del livello di rappresentazione più limitante rispetto alla restrizione per l'autenticazione server di destinazione.|  
|SecureChannelFailure|Impossibile stabilire un canale protetto mediante il protocollo SSL/TLS (Secure Socket Layer/Transport Layer Security) con l'autorità specificata.|  
|TrustFailure|Impossibile stabilire relazioni di trust per il canale protetto SSL/TLS (Secure Socket Layer/ Transport Layer Security) con l'autorità specificata.|  
|UseDefaultWebProxyCantBeUsedWithExplicitProxyAddress|Impossibile specificare un indirizzo proxy esplicito insieme a UseDefaultWebProxy=true nell'elemento di associazione HttpTransportBinding.|
