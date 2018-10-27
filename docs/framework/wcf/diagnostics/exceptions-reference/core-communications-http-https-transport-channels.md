---
title: 'Comunicazioni principali: Canali di trasporto HTTP-HTTPS'
ms.date: 03/30/2017
ms.assetid: 6c0a23c9-a663-461c-bdab-58b4d3e23642
ms.openlocfilehash: 4c4a2537ae615943ffac299a8c8cd00c67094360
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2018
ms.locfileid: "50045405"
---
# <a name="core-communications-httphttps-transport-channels"></a>Comunicazioni principali: canali di trasporto HTTP/HTTPS
Questo argomento elenca tutte le eccezioni generate dai canali di Windows Communication Foundation (WCF) trasporto HTTP/HTTPS.  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|DigestExplicitCredsImpersonationLevel|È stato specificato il livello di rappresentazione specificato. L'autenticazione Digest HTTP supporta il livello "Rappresentazione" solo quando viene usata con una credenziale esplicita.|  
|FramingContentTypeMismatch|Il tipo di contenuto specificato non è supportato dal servizio specificato. È possibile che le associazioni di client e servizio non corrispondano fra loro.|  
|Hosting_SslSettingsMisconfigured|Le impostazioni del protocollo Secure Sockets Layer del servizio specificato non corrispondono a quelle di Internet Information Services.|  
|HttpAuthSchemeAndClientCert|La listener factory HTTPS è stata configurata in modo da richiedere un certificato client e lo schema di autenticazione specificato. Tuttavia, è consentito richiedere una sola forma di autenticazione client alla volta.|  
|HttpReceiveFailure|Si è verificato un errore durante la ricezione della risposta HTTP all'entità specificata. È possibile che l'associazione dell'endpoint del servizio non utilizzi il protocollo HTTP o che un contesto di richiesta HTTP sia stato interrotto dal server a causa dell'arresto di un servizio. Per altre informazioni, vedere i registri del server.|  
|HttpRegistrationAccessDenied|Il protocollo HTTP non è in grado di registrare l'URL specificato. Il processo non dispone dei diritti di accesso per questo spazio dei nomi (vedere [prenotazioni Namespace, registrazioni e Routing](/windows/desktop/http/namespace-reservations-registrations-and-routing) per informazioni dettagliate).|  
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
