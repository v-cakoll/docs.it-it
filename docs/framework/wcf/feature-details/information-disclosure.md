---
title: Diffusione di informazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4064c89f-afa6-444a-aa7e-807ef072131c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1bf20f11e7077c981e73aa087c654b9cf0c87bcb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="information-disclosure"></a>Diffusione di informazioni
La diffusione di informazioni consente all'autore di un attacco di acquisire informazioni importanti su un sistema. Considerare sempre, pertanto, quali informazioni vengono rivelate e se possono essere utilizzate da un utente malintenzionato. Di seguito vengono elencati i possibili attacchi dovuti alla diffusione di informazioni e per ognuno di essi vengono forniti consigli per ridurne la pericolosità.  
  
## <a name="message-security-and-http"></a>Protezione dei messaggi e HTTP  
 Se si sta utilizzando la protezione a livello di messaggio su un livello di trasporto HTTP, è necessario sapere che questo tipo di sicurezza non protegge le intestazioni HTTP. L'unico modo per proteggerle è utilizzare il trasporto HTTPS anziché HTTP. L'utilizzo del trasporto HTTPS comporta la crittografia dell'intero messaggio, incluse le intestazioni HTTP, tramite il protocollo Secure Sockets Layer (SSL).  
  
## <a name="policy-information"></a>Informazioni sul criterio  
 La protezione del criterio è importante, specialmente negli scenari di federazioni dove i requisiti di riservatezza dei token emessi o le informazioni sugli emittenti dei token vengono esposti nel criterio. In questi casi, si consiglia di proteggere l'endpoint del criterio del servizio federato per impedire agli autori di attacchi di ottenere informazioni sul servizio, ad esempio il tipo di attestazioni da inserire nel token emesso, o di reindirizzare client a emittenti di token dannosi. L'autore di un attacco, ad esempio, potrebbe individuare coppie di nome utente/password riconfigurando la catena di trust federata in modo tale che termini in un emittente che esegua un attacco di tipo man-in-the-middle. È inoltre consigliabile che i client federati che ottengono le proprie associazioni tramite recupero dei criteri verifichino l'attendibilità degli emittenti nella catena di certificati federata ottenuta. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]scenari della federazione, vedere [federazione](../../../../docs/framework/wcf/feature-details/federation.md).  
  
## <a name="memory-dumps-can-reveal-claim-information"></a>Le immagini della memoria possono rivelare informazioni sulle attestazioni  
 Quando un'applicazione smette di funzionare, i file di log, ad esempio quelli prodotti da Dr. Watson, possono contenere le informazioni sull'attestazione. Tali informazioni non devono essere esportate ad altre entità, ad esempio team di supporto. In caso contrario, vengono esportate anche le informazioni sulle attestazioni che contengono dati privati. È possibile ridurre questo problema non inviando i file di log a entità sconosciute. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=89160).  
  
## <a name="endpoint-addresses"></a>Indirizzi endpoint  
 Un indirizzo endpoint contiene le informazioni necessarie per comunicare con un endpoint. La protezione SOAP deve includere l'indirizzo completo nei messaggi di negoziazione della protezione scambiati al fine di negoziare una chiave simmetrica tra un client e un server. Poiché la negoziazione di sicurezza è un processo bootstrap, le intestazioni degli indirizzi non possono essere crittografate durante tale processo. L'indirizzo, pertanto, non deve contenere dati riservati. In caso contrario, può portare ad attacchi di diffusione di informazioni.  
  
## <a name="certificates-transferred-unencrypted"></a>Certificati trasferiti non crittografati  
 Quando si utilizza un certificato X.509 per autenticare un client, il certificato viene trasferito in forma non crittografata, nell'intestazione SOAP. Questa situazione può comportare una potenziale diffusione di informazioni personali (PII). Non è un problema per la modalità `TransportWithMessageCredential` in cui l'intero messaggio viene crittografato con la protezione a livello di trasporto.  
  
## <a name="service-references"></a>Riferimenti al servizio  
 Un riferimento al servizio è un riferimento a un altro servizio. Un servizio, ad esempio, può passare a un client un riferimento al servizio nel corso di un'operazione. Il riferimento al servizio viene inoltre utilizzato con un *verificatore di identità di trust*, un componente interno che verifica l'identità dell'entità di destinazione prima della diffusione di informazioni quali dati dell'applicazione o le credenziali per la destinazione. Se l'identità di trust remota non può essere verificata o non è corretta, il mittente deve verificare che non sia stato diffuso nessun dato che possa compromettere se stesso, l'applicazione o l'utente.  
  
 Le possibili soluzioni sono le seguenti:  
  
-   I riferimenti a servizi sono normalmente considerati attendibili. Assicurarsi, ogni qualvolta si trasferiscono istanze del riferimento al servizio, che non siano stati alterati.  
  
-   Alcune applicazioni possono presentare un'esperienza utente che consente di stabilire in modo interattivo l'affidabilità in base ai dati nel riferimento al servizio e ai dati di attendibilità verificati dall'host remoto. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce punti di estendibilità per tale funzionalità che devono tuttavia essere implementati dall'utente.  
  
## <a name="ntlm"></a>NTLM  
 Nell'ambiente di dominio Windows, l'autenticazione di Windows utilizza per impostazione predefinita il protocollo Kerberos per autenticare e autorizzare utenti. Se, per qualche ragione, il protocollo Kerberos non può essere utilizzato, come fallback viene utilizzato NT LAN Manager (NTLM). Per disattivare questo comportamento, impostare la proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> su `false`. Quando si utilizza NTLM è consigliabile prendere in considerazione i problemi seguenti:  
  
-   Il nome utente client viene esposto in NTLM. Se il nome utente deve essere mantenuto riservato, impostare la proprietà `AllowNTLM` nell'associazione su `false`.  
  
-   L'autenticazione server non viene fornita in NTLM. Il client, pertanto, non è in grado di verificare se la comunicazione sia stata stabilita con il servizio corretto, quando si utilizza NTLM come protocollo di autenticazione.  
  
### <a name="specifying-client-credentials-or-invalid-identity-forces-ntlm-usage"></a>Specifica di credenziali client o di identità non valide che impongono l'utilizzo di NTLM  
 Quando si crea un client, la specifica di credenziali client senza un nome di dominio o la specifica di un'identità server non valida, provoca l'utilizzo di NTLM al posto del protocollo Kerberos (se la proprietà `AlllowNtlm` è impostata su `true`). Poiché l'autenticazione server non viene eseguita in NTLM, è possibile che le informazioni vengano diffuse.  
  
 È possibile, ad esempio, specificare credenziali client di Windows senza un nome di dominio, come illustrato nel codice [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] seguente.  
  
```  
MyChannelFactory.Credentials.Windows.ClientCredential = new System.Net.NetworkCredential("username", "password");  
```  
  
 Il codice non specifica un nome di dominio e pertanto verrà utilizzato NTLM.  
  
 NTLM viene utilizzato se viene specificato il dominio, ma viene specificato un nome dell'entità servizio non valido tramite la funzionalità di identità endpoint. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]come è specificato l'identità dell'endpoint, vedere [autenticazione e identità del servizio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Considerazioni sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Elevazione dei privilegi](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [Denial of Service](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [Manomissione](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [Scenari non supportati](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 [Attacchi di riproduzione](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
