---
title: Scenari non supportati
ms.date: 03/30/2017
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
ms.openlocfilehash: b643e6df8a877860ce36fc6ee34c4e4ca08ec748
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921165"
---
# <a name="unsupported-scenarios"></a>Scenari non supportati

Per diversi motivi, Windows Communication Foundation (WCF) non supporta alcuni scenari di sicurezza specifici. Windows XP Home Edition, ad esempio, non implementa i protocolli di autenticazione SSPI o Kerberos e pertanto WCF non supporta l'esecuzione di un servizio con l'autenticazione di Windows su tale piattaforma. Quando si esegue WCF in Windows XP Home Edition, sono supportati altri meccanismi di autenticazione, ad esempio nome utente/password e autenticazione integrata HTTP/HTTPS.

## <a name="impersonation-scenarios"></a>Scenari di rappresentazione

### <a name="impersonated-identity-might-not-flow-when-clients-make-asynchronous-calls"></a>L'identità rappresentata potrebbe non fluire quando i client effettuano chiamate asincrone
 Quando un client WCF effettua chiamate asincrone a un servizio WCF utilizzando l'autenticazione di Windows sotto rappresentazione, potrebbe verificarsi l'autenticazione con l'identità del processo client anziché con l'identità rappresentata.

### <a name="windows-xp-and-secure-context-token-cookie-enabled"></a>Cookie di Windows XP e del token del contesto protetto abilitato

WCF non supporta la rappresentazione e viene generata un'<xref:System.InvalidOperationException> quando sussistono le condizioni seguenti:

- Il sistema operativo è Windows XP.

- La modalità di autenticazione genera un'identità Windows.

- La proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> di <xref:System.ServiceModel.OperationBehaviorAttribute> è impostata su <xref:System.ServiceModel.ImpersonationOption.Required>.

- Viene creato un token del contesto di sicurezza SCT (Security Context Token) basato sullo stato. Per impostazione predefinita, la creazione è disattivata.

 Il token SCT basato sullo stato può essere creato solo tramite un'associazione personalizzata. Per altre informazioni, vedere [procedura: creare un token del contesto di sicurezza per una sessione protetta](how-to-create-a-security-context-token-for-a-secure-session.md). Nel codice, il token viene abilitato creando un elemento di associazione di sicurezza (<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>) utilizzando il <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=nameWithType> o il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=nameWithType> e impostando il `requireCancellation` parametro su `false`. Il parametro fa riferimento alla memorizzazione nella cache del token SCT. L'impostazione del valore su `false` comporta l'attivazione della funzionalità del token SCT basato sullo stato.

 In alternativa, in configurazione il token viene abilitato creando un <`customBinding`>, quindi aggiungendo un <`security`> elemento e impostando l'attributo `authenticationMode` su SecureConversation e l'attributo `requireSecurityContextCancellation` su `true`.

> [!NOTE]
> I requisiti precedenti sono specifici. Ad esempio, il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> crea un elemento di associazione che genera un'identità Windows senza tuttavia creare un token SCT. Pertanto, è possibile utilizzarlo con l'opzione `Required` in Windows XP.

### <a name="possible-aspnet-conflict"></a>Possibile conflitto ASP.NET

WCF e ASP.NET possono abilitare o disabilitare la rappresentazione. Quando ASP.NET ospita un'applicazione WCF, è possibile che esista un conflitto tra le impostazioni di configurazione di WCF e ASP.NET. In caso di conflitto, l'impostazione WCF ha la precedenza, a meno che la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> non sia impostata su <xref:System.ServiceModel.ImpersonationOption.NotAllowed>, nel qual caso l'impostazione di rappresentazione ASP.NET ha la precedenza.

### <a name="assembly-loads-may-fail-under-impersonation"></a>I caricamenti dell'assembly possono avere esito negativo in rappresentazione

Se il contesto rappresentato non dispone delle autorizzazioni di accesso per caricare un assembly e se è la prima volta che il Common Language Runtime (CLR) tenta di caricare l'assembly per tale dominio applicazione, il dominio <xref:System.AppDomain> memorizza l'errore nella cache. I tentativi successivi di caricamento dell'assembly (o degli assembly) hanno esito negativo, anche dopo aver ripristinato la rappresentazione e anche se il contesto ripristinato dispone delle autorizzazioni di accesso per caricare l'assembly. Questo è dovuto al fatto che CLR non tenta di eseguire nuovamente il caricamento dopo che il contesto utente è stato modificato. Per risolvere il problema è necessario riavviare il dominio applicazione.

> [!NOTE]
> Il valore predefinito della proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> della classe <xref:System.ServiceModel.Security.WindowsClientCredential> è <xref:System.Security.Principal.TokenImpersonationLevel.Identification>. Nella maggior parte dei casi, un contesto di rappresentazione a livello di identificazione non dispone di alcun diritto che consenta il caricamento di assembly aggiuntivi. Poiché si tratta di un valore predefinito, questo caso risulta essere molto comune e merita particolare attenzione. La rappresentazione a livello di identificazione si verifica anche quando il processo di rappresentazione non dispone del privilegio `SeImpersonate`. Per ulteriori informazioni, vedere [delega e rappresentazione](delegation-and-impersonation-with-wcf.md).

### <a name="delegation-requires-credential-negotiation"></a>La delega richiede la negoziazione delle credenziali

Per poter essere utilizzato con la funzionalità di delega, il protocollo di autenticazione Kerberos deve essere implementato con la negoziazione delle credenziali. Questa versione di Kerberos è talvolta nota come Kerberos multifase. Se si implementa l'autenticazione Kerberos senza negoziazione delle credenziali (ovvero una versione di Kerberos anche nota come monofase o monopassaggio), verrà generata un'eccezione. Per ulteriori informazioni sull'implementazione della negoziazione delle credenziali, vedere [debug degli errori di autenticazione di Windows](debugging-windows-authentication-errors.md).

## <a name="cryptography"></a>Crittografia

### <a name="sha-256-supported-only-for-symmetric-key-usages"></a>SHA-256 supportato solo per gli utilizzi di chiavi simmetriche

WCF supporta un'ampia gamma di algoritmi di creazione del digest della crittografia e della firma che è possibile specificare utilizzando la suite di algoritmi nelle associazioni fornite dal sistema. Per una maggiore sicurezza, WCF supporta gli algoritmi SHA (Secure Hash Algorithm) 2, in particolare SHA-256, per la creazione di hash del digest della firma. Questa versione supporta l'algoritmo SHA-256 solo nei casi in cui si utilizzano chiavi simmetriche, ad esempio le chiavi Kerberos, e nei casi in cui i messaggi non vengono firmati tramite un certificato X.509. WCF non supporta le firme RSA (utilizzate nei certificati X. 509) usando l'hash SHA-256, a causa della mancanza di supporto corrente per RSA-SHA256 in WinFX.

### <a name="fips-compliant-sha-256-hashes-not-supported"></a>Hash SHA-256 conformi a FIPS non supportati

WCF non supporta gli hash conformi a FIPS SHA-256, quindi i gruppi di algoritmi che usano SHA-256 non sono supportati da WCF nei sistemi in cui è richiesto l'uso di algoritmi conformi a FIPS.

### <a name="fips-compliant-algorithms-may-fail-if-registry-is-edited"></a>Gli algoritmi conformi a FIPS possono avere esito negativo se il registro è stato modificato

Lo snap-in Impostazioni protezione locale di Microsoft Management Console (MMC) consente di attivare e disattivare gli algoritmi conformi agli standard FIPS. Questa impostazione può inoltre essere eseguita nel Registro di sistema. Si noti, tuttavia, che WCF non supporta l'utilizzo del registro di sistema per reimpostare l'impostazione. Se si esegue questa impostazione utilizzando un valore diverso da 1 oppure 0 è possibile che si verifichino risultati incoerenti tra il runtime CLR e il sistema operativo.

### <a name="fips-compliant-aes-encryption-limitation"></a>Limitazione della crittografia AES conforme a FIPS

La crittografia AES conforme a FIPS non funziona nei callback duplex sotto la rappresentazione del livello di identificazione.

### <a name="cngksp-certificates"></a>Certificati CNG/KSP

*Cryptography API: Next Generation (CNG)* è la sostituzione a lungo termine per CryptoAPI. Questa API è disponibile nel codice non gestito in Windows Vista, Windows Server 2008 e versioni successive di Windows.

 .NET Framework 4.6.1 e versioni precedenti non supportano questi certificati poiché utilizzano la CryptoAPI legacy per gestire i certificati CNG/KSP. L'uso di questi certificati con .NET Framework 4.6.1 e versioni precedenti provocherà un'eccezione.

 Esistono due modi possibili per stabilire se un certificato utilizza KSP:

- Eseguire `p/invoke` di `CertGetCertificateContextProperty` e controllare `dwProvType` sulla proprietà `CertGetCertificateContextProperty` restituita.

- Usare il comando `certutil` dalla riga di comando per eseguire query sui certificati. Per ulteriori informazioni, vedere [attività certutil per la risoluzione dei problemi relativi ai certificati](https://docs.microsoft.com/previous-versions/orphan-topics/ws.10/cc772619(v=ws.10)).

## <a name="message-security-fails-if-using-aspnet-impersonation-and-aspnet-compatibility-is-required"></a>La sicurezza del messaggio ha esito negativo se si usa la rappresentazione ASP.NET e la compatibilità ASP.NET è obbligatoria

WCF non supporta la seguente combinazione di impostazioni perché può impedire che si verifichi l'autenticazione client:

- La rappresentazione ASP.NET è abilitata. Questa operazione viene eseguita nel file Web. config impostando l'attributo `impersonate` della <`identity`elemento > su `true`.

- La modalità di compatibilità ASP.NET è abilitata impostando l'attributo `aspNetCompatibilityEnabled` del [\<ServiceHostingEnvironment](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) su `true`.

- Viene utilizzata la protezione a livello di messaggio.

La soluzione ovvia consiste nel disattivare la modalità di compatibilità ASP.NET. In alternativa, se è richiesta la modalità di compatibilità ASP.NET, disabilitare la funzionalità di rappresentazione ASP.NET e utilizzare invece la rappresentazione fornita da WCF. Per ulteriori informazioni, vedere [delega e rappresentazione](delegation-and-impersonation-with-wcf.md).

## <a name="ipv6-literal-address-failure"></a>Errore di indirizzo letterale IPv6

Le richieste di sicurezza hanno esito negativo quando il client e il servizio si trovano nello stesso computer e gli indirizzi letterali Ipv6 vengono utilizzati per il servizio.

 Gli indirizzi di questo tipo funzionano se il servizio e il client sono sui computer diversi.

## <a name="wsdl-retrieval-failures-with-federated-trust"></a>Errori di recupero WSDL con attendibilità federata

WCF richiede un solo documento WSDL per ogni nodo nella catena di trust federata. È opportuno prestare attenzione a non impostare un ciclo quando si specificano gli endpoint. È possibile che si verifichi un ciclo quando si utilizza un download WSDL di catene di trust federati con due o più collegamenti nello stesso documento WSDL. Uno scenario comune in cui può verificarsi questo problema consiste in un servizio federato in cui il server di token di sicurezza e il servizio sono contenuti nello stesso ServiceHost.

 Un esempio di questa situazione è dato da un servizio con i tre indirizzi endpoint seguenti:

- `http://localhost/CalculatorService/service` (servizio)

- `http://localhost/CalculatorService/issue_ticket` (STS)

- `http://localhost/CalculatorService/mex` (endpoint dei metadati)

 Viene generata un'eccezione.

 È possibile risolvere questo scenario collocando l'endpoint `issue_ticket` in un'altra posizione.

## <a name="wsdl-import-attributes-can-be-lost"></a>Gli attributi di importazione WSDL possono andare perduti

In WCF si perde traccia degli attributi in un elemento `<wst:Claims>`RST in un modello`RST` quando viene eseguita un'importazione WSDL. Questa situazione si verifica durante un'importazione WSDL se si specifica `<Claims>`WSFederationHttpBinding.Security.Message.TokenRequestParameters direttamente in`WSFederationHttpBinding.Security.Message.TokenRequestParameters``IssuedSecurityTokenRequestParameters.AdditionalRequestParameters`IssuedSecurityTokenRequestParameters.AdditionalRequestParameters o in anziché utilizzare direttamente le raccolte dei tipi di attestazione.  Poiché l'importazione perde gli attributi, l'associazione non esegue correttamente una sequenza di andata e ritorno attraverso WSDL e quindi risulta errata sul lato client.

 Per risolvere il problema è necessario modificare l'associazione direttamente nel client dopo aver eseguito l'importazione.

## <a name="see-also"></a>Vedere anche

- [Considerazioni sulla sicurezza](security-considerations-in-wcf.md)
- [Divulgazione di informazioni](information-disclosure.md)
- [Elevazione dei privilegi](elevation-of-privilege.md)
- [Negazione del servizio](denial-of-service.md)
- [Manomissioni](tampering.md)
- [Attacchi di tipo replay](replay-attacks.md)
