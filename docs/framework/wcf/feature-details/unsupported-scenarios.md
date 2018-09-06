---
title: Scenari non supportati
ms.date: 03/30/2017
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
ms.openlocfilehash: 6c0ee061f754e85244bffdc06cbe23aee68d2222
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858065"
---
# <a name="unsupported-scenarios"></a>Scenari non supportati
Per vari motivi, Windows Communication Foundation (WCF) non supporta alcuni scenari di sicurezza specifico. Ad esempio, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition può neimplementuje metodu i protocolli di autenticazione SSPI o Kerberos, e pertanto WCF non supporta l'esecuzione di un servizio con l'autenticazione di Windows che utilizzano tale piattaforma. Durante l'esecuzione di WCF in Windows XP Home Edition, sono supportati altri meccanismi di autenticazione, ad esempio nome utente/password e l'autenticazione integrata di HTTP/HTTPS.  
  
## <a name="impersonation-scenarios"></a>Scenari di rappresentazione  
  
### <a name="impersonated-identity-might-not-flow-when-clients-make-asynchronous-calls"></a>L'identità rappresentata potrebbe non fluire quando i client effettuano chiamate asincrone  
 Quando un client WCF effettua chiamate asincrone a un servizio WCF utilizzando l'autenticazione di Windows sotto rappresentazione, potrebbe verificarsi l'autenticazione con l'identità del processo client anziché con l'identità rappresentata.  
  
### <a name="windows-xp-and-secure-context-token-cookie-enabled"></a>Windows XP con cookie di token del contesto di sicurezza attivo  
 WCF non supporta la rappresentazione e un <xref:System.InvalidOperationException> viene generata quando si verificano le condizioni seguenti:  
  
-   Il sistema operativo è [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
-   La modalità di autenticazione genera un'identità Windows.  
  
-   La proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> di <xref:System.ServiceModel.OperationBehaviorAttribute> è impostata su <xref:System.ServiceModel.ImpersonationOption.Required>.  
  
-   Viene creato un token del contesto di sicurezza SCT (Security Context Token) basato sullo stato. Per impostazione predefinita, la creazione è disattivata.  
  
 Il token SCT basato sullo stato può essere creato solo tramite un'associazione personalizzata. Per altre informazioni, vedere [procedura: creare un Token del contesto di sicurezza per una sessione Secure](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).) In codice, per attivare il token occorre creare un elemento di associazione di sicurezza (<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>) utilizzando il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=nameWithType> o il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=nameWithType> e impostando il parametro `requireCancellation` su `false`. Il parametro fa riferimento alla memorizzazione nella cache del token SCT. L'impostazione del valore su `false` comporta l'attivazione della funzionalità del token SCT basato sullo stato.  
  
 In alternativa, nella configurazione, il token è abilitato per la creazione di un <`customBinding`>, quindi aggiungendo un <`security`> elemento e impostazione il `authenticationMode` attributo su SecureConversation e il `requireSecurityContextCancellation` dell'attributo `true`.  
  
> [!NOTE]
>  I requisiti precedenti sono specifici. Ad esempio, il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> crea un elemento di associazione che genera un'identità Windows senza tuttavia creare un token SCT. È pertanto possibile utilizzare questa identità con l'opzione `Required` di [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
### <a name="possible-aspnet-conflict"></a>Possibile conflitto con ASP.NET  
 WCF e [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] possono entrambi attivare o disabilitare la rappresentazione. Quando [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ospita un'applicazione WCF, potrebbe esistere un conflitto tra WCF e [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] le impostazioni di configurazione. In caso di conflitto, l'impostazione di WCF ha la precedenza, a meno che il <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> è impostata su <xref:System.ServiceModel.ImpersonationOption.NotAllowed>, nel qual caso il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] rappresentazione impostazione ha la precedenza.  
  
### <a name="assembly-loads-may-fail-under-impersonation"></a>Possibilità di esito negativo dei caricamenti dell'assembly in caso di utilizzo della rappresentazione  
 Se il contesto rappresentato non dispone delle autorizzazioni di accesso per caricare un assembly e se è la prima volta che il Common Language Runtime (CLR) tenta di caricare l'assembly per tale dominio applicazione, il dominio <xref:System.AppDomain> memorizza l'errore nella cache. I tentativi successivi di caricamento dell'assembly (o degli assembly) hanno esito negativo, anche dopo aver ripristinato la rappresentazione e anche se il contesto ripristinato dispone delle autorizzazioni di accesso per caricare l'assembly. Ciò è dovuto al fatto che CLR non esegue nuovi tentativi di caricamento dopo che il contesto utente è cambiato. Per risolvere il problema è necessario riavviare il dominio applicazione.  
  
> [!NOTE]
>  Il valore predefinito della proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> della classe <xref:System.ServiceModel.Security.WindowsClientCredential> è <xref:System.Security.Principal.TokenImpersonationLevel.Identification>. Nella maggior parte dei casi, un contesto di rappresentazione a livello di identificazione non dispone di alcun diritto che consenta il caricamento di assembly aggiuntivi. Poiché si tratta di un valore predefinito, questo caso risulta essere molto comune e merita particolare attenzione. La rappresentazione a livello di identificazione si verifica anche quando il processo di rappresentazione non dispone del privilegio `SeImpersonate`. Per altre informazioni, vedere [delega e rappresentazione](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
### <a name="delegation-requires-credential-negotiation"></a>Requisito di negoziazione della credenziale in caso di delega  
 Per poter essere utilizzato con la funzionalità di delega, il protocollo di autenticazione Kerberos deve essere implementato con la negoziazione delle credenziali. Questa versione di Kerberos è talvolta nota come Kerberos multifase. Se si implementa l'autenticazione Kerberos senza negoziazione delle credenziali (ovvero una versione di Kerberos anche nota come monofase o monopassaggio), verrà generata un'eccezione. Per altre informazioni su come implementare la negoziazione della credenziale, vedere [debug degli errori di autenticazione di Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md).  
  
## <a name="cryptography"></a>Crittografia  
  
### <a name="sha-256-supported-only-for-symmetric-key-usages"></a>Supporto di SHA-256 solo in caso di utilizzo di chiavi simmetriche  
 WCF supporta un'ampia gamma di crittografia e gli algoritmi di creazione del digest della firma che è possibile specificare utilizzando la suite di algoritmi nelle associazioni fornite dal sistema. Per migliorare la sicurezza, WCF supporta gli algoritmi Secure Hash Algorithm (SHA) 2, in particolare SHA-256, per creare hash digest di firme. Questa versione supporta l'algoritmo SHA-256 solo nei casi in cui si utilizzano chiavi simmetriche, ad esempio le chiavi Kerberos, e nei casi in cui i messaggi non vengono firmati tramite un certificato X.509. WCF non supporta le firme RSA (utilizzate nei certificati X.509) usando l'hash SHA-256 a causa della mancanza del supporto per RSA-SHA256 nel [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
### <a name="fips-compliant-sha-256-hashes-not-supported"></a>Mancanza del supporto per gli hash SHA-256 conformi agli standard FIPS  
 WCF non supporta gli hash SHA-256 conformi a FIPS, in modo che i gruppi di algoritmi che utilizzino SHA-256 non sono supportati da WCF nei sistemi in cui è necessario utilizzare algoritmi conformi a FIPS.  
  
### <a name="fips-compliant-algorithms-may-fail-if-registry-is-edited"></a>Possibilità di esito negativo degli algoritmi conformi agli standard FIPS in caso di modifica del Registro di sistema  
 Lo snap-in Impostazioni protezione locale di Microsoft Management Console (MMC) consente di attivare e disattivare gli algoritmi conformi agli standard FIPS. Questa impostazione può inoltre essere eseguita nel Registro di sistema. Si noti tuttavia che WCF non supporta l'uso del Registro di sistema per reimpostare l'impostazione. Se si esegue questa impostazione utilizzando un valore diverso da 1 oppure 0 è possibile che si verifichino risultati incoerenti tra il runtime CLR e il sistema operativo.  
  
### <a name="fips-compliant-aes-encryption-limitation"></a>Restrizione sulla crittografia AES conforme agli standard FIPS  
 La crittografia AES conforme agli standard FIPS non funziona nei callback duplex nel contesto di una rappresentazione di livello di identificazione.  
  
### <a name="cngksp-certificates"></a>Certificati CNG/KSP  
 *Cryptography API: Next Generation (CNG)* è la sostituzione a lungo termine di CryptoAPI. Questa API è disponibile nel codice non gestito in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)] e versioni successive di Windows.  
  
 .NET framework 4.6.1 e versioni precedenti non supportano questi certificati perché usano la funzione CryptoAPI legacy per la gestione dei certificati CNG/KSP. L'uso di questi certificati con .NET Framework 4.6.1 e versioni precedenti genererà un'eccezione.  
  
 Esistono due modi possibili per stabilire se un certificato utilizza KSP:  
  
-   Eseguire `p/invoke` di `CertGetCertificateContextProperty` e controllare `dwProvType` sulla proprietà `CertGetCertificateContextProperty` restituita.  
  
-   Usare il `certutil` comando dalla riga di comando per eseguire query sui certificati. Per altre informazioni, vedere [attività di Certutil per la risoluzione dei problemi dei certificati](https://go.microsoft.com/fwlink/?LinkId=120056).  
  
## <a name="message-security-fails-if-using-aspnet-impersonation-and-aspnet-compatibility-is-required"></a>Errore di sicurezza a livello di messaggio quando si utilizza la rappresentazione ASP.NET e la compatibilità con ASP.NET è obbligatoria  
 WCF non supporta la combinazione di impostazioni seguente perché possono impedire l'autenticazione di client che si verifichi:  
  
-   È stata attivata la rappresentazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Questa operazione viene eseguita nel file Web. config impostando il `impersonate` attributo del <`identity`> elemento `true`.  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] modalità di compatibilità viene abilitata impostando il `aspNetCompatibilityEnabled` attributo del [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) a `true`.  
  
-   Viene utilizzata la protezione a livello di messaggio.  
  
 Per risolvere questo problema è sufficiente disattivare la modalità di compatibilità con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Oppure, se il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] è necessaria la modalità di compatibilità, disabilitare il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] la rappresentazione delle funzionalità e usare invece la rappresentazione fornita da WCF. Per altre informazioni, vedere [delega e rappresentazione](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="ipv6-literal-address-failure"></a>Errore di indirizzo letterale IPv6  
 Le richieste di sicurezza hanno esito negativo quando il client e il servizio si trovano nello stesso computer e gli indirizzi letterali Ipv6 vengono utilizzati per il servizio.   
  
 Gli indirizzi di questo tipo funzionano se il servizio e il client sono sui computer diversi.  
  
## <a name="wsdl-retrieval-failures-with-federated-trust"></a>Errori di recupero di WSDL con trust federati  
 WCF richiede esattamente un documento WSDL per ogni nodo nella catena di trust federativa. È opportuno prestare attenzione a non impostare un ciclo quando si specificano gli endpoint. È possibile che si verifichi un ciclo quando si utilizza un download WSDL di catene di trust federati con due o più collegamenti nello stesso documento WSDL. Uno scenario comune in cui può verificarsi questo problema consiste in un servizio federato in cui il server di token di sicurezza e il servizio sono contenuti nello stesso ServiceHost.  
  
 Un esempio di questa situazione è dato da un servizio con i tre indirizzi endpoint seguenti:  
  
-   http://localhost/CalculatorService/service (servizio)  
  
-   http://localhost/CalculatorService/issue_ticket (STS)  
  
-   http://localhost/CalculatorService/mex (l'endpoint dei metadati)  
  
 Viene generata un'eccezione.  
  
 È possibile risolvere questo scenario collocando l'endpoint `issue_ticket` in un'altra posizione.  
  
## <a name="wsdl-import-attributes-can-be-lost"></a>Gli attributi di importazione di WSDL possono andare persi  
 In WCF si perde traccia degli attributi in un elemento `<wst:Claims>`RST in un modello`RST` quando viene eseguita un'importazione WSDL. Questa situazione avviene durante un'importazione WSDL se si specifica `<Claims>` direttamente in `WSFederationHttpBinding.Security.Message.TokenRequestParameters` o `IssuedSecurityTokenRequestParameters.AdditionalRequestParameters` anziché usare direttamente le raccolte dei tipi di attestazione.  Poiché l'importazione perde gli attributi, l'associazione non esegue correttamente una sequenza di andata e ritorno attraverso WSDL e quindi risulta errata sul lato client.  
  
 Per risolvere il problema è necessario modificare l'associazione direttamente nel client dopo aver eseguito l'importazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Considerazioni sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Divulgazione di informazioni](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [Elevazione dei privilegi](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [Negazione del servizio](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [Manomissioni](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [Attacchi di tipo replay](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
