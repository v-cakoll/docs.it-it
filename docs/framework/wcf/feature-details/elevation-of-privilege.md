---
title: Elevazione dei privilegi
ms.date: 03/30/2017
helpviewer_keywords:
- elevation of privilege [WCF]
- security [WCF], elevation of privilege
ms.assetid: 146e1c66-2a76-4ed3-98a5-fd77851a06d9
ms.openlocfilehash: 823b41f86080d4802f76fe69865279a7c3506238
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597410"
---
# <a name="elevation-of-privilege"></a>Elevazione dei privilegi
L' *elevazione dei privilegi* risulta da concedere a un utente malintenzionato autorizzazioni di autorizzazione oltre a quelle inizialmente concesse. L'autore di un attacco con, ad esempio, un set di privilegi di autorizzazioni "di sola lettura" eleva il set per includere "lettura e scrittura".  
  
## <a name="trusted-sts-should-sign-saml-token-claims"></a>Un servizio token di sicurezza affidabile deve firmare le attestazioni del token SAML  
 Un token SAML (Security Assertions Markup Language) è un token XML generico che è il tipo predefinito per i token emessi. Un token SAML può essere costruito da un servizio token di sicurezza (STS, Security Token Service) ritenuto affidabile dal servizio Web finale in uno scambio tipico. Nelle istruzioni, i token SAML contengono attestazioni. L'autore di un attacco può copiare le attestazioni da un token valido, creare un nuovo token SAML e firmarlo con un emittente diverso. Lo scopo è quello di determinare se il server sta convalidando gli emittenti e, in caso negativo, utilizzare la debolezza per costruire token SAML che consentano privilegi oltre quelli previsti da un servizio token di sicurezza.  
  
 La classe <xref:System.IdentityModel.Tokens.SamlAssertion> verifica la firma digitale contenuta in un token SAML e l'oggetto <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> predefinito richiede che i token SAML siano firmati da un certificato X.509 che sia valido quando l'oggetti <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> della classe <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> è impostata su <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust>. La sola modalità `ChainTrust` non è sufficiente per stabilire se l'emittente del token SAML è affidabile. I servizi che richiedono un modello di affidabilità più granulare possono utilizzare i criteri di autorizzazione e di imposizione per controllare l'emittente dei set di attestazioni prodotti dall'autenticazione del token emesso oppure utilizzare le impostazioni di convalida X.509 in <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> per limitare il set di certificati di firma consentiti. Per ulteriori informazioni, vedere [gestione di attestazioni e autorizzazioni con il modello di identità e la](managing-claims-and-authorization-with-the-identity-model.md) [Federazione e i token emessi](federation-and-issued-tokens.md).  
  
## <a name="switching-identity-without-a-security-context"></a>Cambio di identità senza un contesto di sicurezza  
 Le condizioni seguenti si applicano solo a WinFX.  
  
 Quando viene stabilita una connessione tra un client e un server, l'identità del client non cambia, tranne che in una situazione: dopo l'apertura del client WCF, se vengono soddisfatte tutte le condizioni seguenti:  
  
- Le procedure per stabilire un contesto di sicurezza (utilizzando una sessione di sicurezza del trasporto o una sessione di sicurezza del messaggio) sono disattivate (la <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> proprietà è impostata su `false` in caso di sicurezza del messaggio o il trasporto che non è in grado di stabilire sessioni di sicurezza viene utilizzato nei casi di sicurezza del trasporto. HTTPS è un esempio di questo tipo di trasporto.  
  
- Viene utilizzata l'autenticazione di Windows.  
  
- La credenziale non è impostata in modo esplicito.  
  
- Il servizio viene chiamato nel contesto di sicurezza rappresentato.  
  
 Se queste condizioni sono vere, l'identità utilizzata per autenticare il client al servizio potrebbe cambiare (potrebbe non essere l'identità rappresentata, ma l'identità del processo) dopo l'apertura del client WCF. Ciò accade perché la credenziale di Windows utilizzata per autenticare il client al servizio viene trasmessa con ogni messaggio e la credenziale utilizzata per l'autenticazione viene ottenuta dall'identità di Windows del thread corrente. Se l'identità di Windows del thread corrente cambia (ad esempio, rappresentando un chiamante diverso), potrebbe cambiare anche la credenziale allegata al messaggio e utilizzata per autenticare il client al servizio.  
  
 Se si desidera ottenere un comportamento deterministico quando si utilizza l'autenticazione di Windows assieme alla rappresentazione, è necessario impostare in modo esplicito la credenziale di Windows oppure stabilire un contesto di sicurezza con il servizio. A tale scopo, utilizzare una sessione di sicurezza del messaggio o una sessione di sicurezza del trasporto. Il trasporto net.tcp, ad esempio, può fornire una sessione di sicurezza del trasporto. Quando si chiama il servizio , è inoltre necessario utilizzare solo una versione sincrona delle operazioni client. Se si stabilisce un contesto di sicurezza del messaggio, non mantenere aperta la connessione al servizio oltre il periodo di rinnovo della sessione configurato, perché l'identità può cambiare anche durante il processo di rinnovo della sessione.  
  
### <a name="credentials-capture"></a>Acquisizione delle credenziali  
 Le condizioni seguenti si applicano a .NET Framework 3,5 e versioni successive.  
  
 Le credenziali utilizzate dal client o dal servizio sono basate sul thread del contesto corrente. Le credenziali vengono ottenute quando si chiama il metodo `Open` (o `BeginOpen`, per le chiamate asincrone) del client o del servizio. Per entrambe le classi <xref:System.ServiceModel.ServiceHost> e <xref:System.ServiceModel.ClientBase%601>, i metodi `Open` e `BeginOpen` ereditano dai metodi <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> e <xref:System.ServiceModel.Channels.CommunicationObject.BeginOpen%2A> della classe <xref:System.ServiceModel.Channels.CommunicationObject>.  
  
> [!NOTE]
> Quando si utilizza il metodo `BeginOpen`, non è possibile garantire che le credenziali acquisite siano quelle del processo che chiama il metodo.  
  
## <a name="token-caches-allow-replay-using-obsolete-data"></a>I token memorizzati nella cache consentono la riproduzione utilizzando dati obsoleti  
 WCF utilizza la funzione autorità di sicurezza locale (LSA) `LogonUser` per autenticare gli utenti in base al nome utente e alla password. Poiché la funzione Logon è un'operazione costosa, WCF consente di memorizzare nella cache i token che rappresentano gli utenti autenticati per migliorare le prestazioni. Il meccanismo di memorizzazione nella cache salva i risultati ottenuti da `LogonUser` per utilizzi successivi. Questo meccanismo è disabilitato per impostazione predefinita. per abilitarla, impostare la <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.CacheLogonTokens%2A> proprietà su `true` oppure utilizzare l' `cacheLogonTokens` attributo dell'oggetto [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) .  
  
 È possibile impostare la durata (TTL) per i token memorizzati nella cache, impostando la proprietà <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.CachedLogonTokenLifetime%2A> su un <xref:System.TimeSpan>, oppure utilizzare l'attributo `cachedLogonTokenLifetime` dell'elemento `userNameAuthentication`. L'impostazione predefinita è 15 minuti. Si noti che quando un token è memorizzato nella cache, può essere utilizzato da qualsiasi client che presenti lo stesso nome utente e la stessa password, anche se l'account utente viene eliminato da Windows o se la sua password è stata modificata. Fino alla scadenza della durata (TTL) e il token viene rimosso dalla cache, WCF consente all'utente (probabilmente dannoso) di eseguire l'autenticazione.  
  
 Per limitare questo problema, ridurre il tempo a disposizione dell'attacco impostando il valore `cachedLogonTokenLifetime` sull'intervallo di tempo più breve necessario per gli utenti.  
  
## <a name="issued-token-authorization-expiration-reset-to-large-value"></a>Autorizzazione del token emesso: scadenza reimpostata su un valore grande  
 In certe condizioni, la proprietà <xref:System.IdentityModel.Policy.AuthorizationContext.ExpirationTime%2A> di <xref:System.IdentityModel.Policy.AuthorizationContext> può essere impostata su un valore inaspettatamente superiore (il valore del campo <xref:System.DateTime.MaxValue> meno un giorno, o 20 dicembre 9999).  
  
 Ciò si verifica quando si utilizza <xref:System.ServiceModel.WSFederationHttpBinding> e una qualsiasi delle associazioni fornite dal sistema che ha un token emesso come tipo di credenziale client.  
  
 Lo stesso accade anche quando si creano associazioni personalizzate utilizzando uno dei metodi seguenti:  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A>  
  
 Per limitare questo problema, i criteri di autorizzazione devono controllare l'azione e la data di scadenza dei singoli criteri di autorizzazione.  
  
## <a name="the-service-uses-a-different-certificate-than-the-client-intended"></a>Il servizio utilizza un certificato diverso da quello previsto dal client  
 In certe condizioni, un client può firmare digitalmente un messaggio con un certificato X.509 e far sì che il servizio recuperi un certificato diverso da quello previsto.  
  
 Ciò può verificarsi nelle circostanze seguenti:  
  
- Il client firma digitalmente un messaggio utilizzando un certificato X.509 e non allega il certificato X.509 al messaggio, ma fa semplicemente riferimento al certificato utilizzando il suo identificatore chiave del soggetto.  
  
- Il computer del servizio contiene due o più certificati con la stessa chiave pubblica, ma tali certificati contengono informazioni diverse.  
  
- Il servizio recupera un certificato che corrisponde all'identificatore chiave del soggetto, ma non è quello che il client doveva utilizzare. Quando WCF riceve il messaggio e verifica la firma, WCF esegue il mapping delle informazioni del certificato X. 509 non intenzionale a un set di attestazioni che sono diverse e potenzialmente elevate rispetto a quelle previste dal client.  
  
 Per limitare questo problema, fare riferimento al certificato X.509 in un altro modo, ad esempio utilizzando <xref:System.ServiceModel.Security.Tokens.X509KeyIdentifierClauseType.IssuerSerial>.  
  
## <a name="see-also"></a>Vedere anche

- [Security Considerations](security-considerations-in-wcf.md)
- [Divulgazione di informazioni](information-disclosure.md)
- [Attacco Denial of Service](denial-of-service.md)
- [Attacchi di tipo replay](replay-attacks.md)
- [Manomissione](tampering.md)
- [Scenari non supportati](unsupported-scenarios.md)
