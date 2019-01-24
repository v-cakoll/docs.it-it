---
title: Selezione di un tipo di credenziale
ms.date: 03/30/2017
ms.assetid: bf707063-3f30-4304-ab53-0e63413728a8
ms.openlocfilehash: 27e1bc4b9e4209fafd0e3707ad6674eb5db6e451
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577113"
---
# <a name="selecting-a-credential-type"></a>Selezione di un tipo di credenziale
*Le credenziali* sono i dati di Windows Communication Foundation (WCF) viene utilizzato per stabilire un'identità attestata o funzionalità. Ad esempio, un passaporto è una credenziale rilasciata da un'autorità dello Stato per provare la cittadinanza in un paese o un'area geografica. In WCF, le credenziali possono assumere molte forme, ad esempio token del nome utente e i certificati X.509. In questo argomento illustra come selezionare la credenziale appropriata per l'applicazione, come vengono usati in WCF e le credenziali.  
  
 In molti paesi e aree geografiche, la patente di guida costituisce un esempio di credenziale. Oltre a contenere dati che descrivono l'identità e le capacità di un individuo, una patente contiene una prova di possesso, ovvero la foto del titolare. La patente viene inoltre rilasciata da un'autorità attendibile, in genere un apposito ente governativo e, allo scopo di impedire manomissioni e falsificazioni, viene sigillata ed eventualmente corredata di ologramma.  
  
 Quando si presenta una credenziale, è necessario presentare sia i dati sia la prova di possesso dei dati. WCF supporta un'ampia gamma di tipi di credenziale a livelli di sicurezza di trasporto e messaggio. Ad esempio, prendere in considerazione due tipi di credenziale supportati in WCF: nome utente e certificati (X.509) le credenziali.  
  
 Nel primo tipo di credenziale, il nome utente rappresenta l'attestazione di identità e la password rappresenta la prova di possesso. In questo caso l'autorità attendibile è il sistema che convalida nome utente e password.  
  
 Con una credenziale di certificato X.509, il nome del soggetto, nome alternativo del soggetto o i campi specifici del certificato possono essere utilizzati come attestazioni di identità, mentre gli altri campi, ad esempio la `Valid From` e `Valid To` campi, specificare la validità del certificato.  
  
## <a name="transport-credential-types"></a>Tipi di credenziali a livello di trasporto  
 Nella tabella seguente vengono illustrati i tipi di credenziali client che possono essere usati da un'associazione nella modalità di sicurezza del trasporto. Quando si crea un servizio, impostare la proprietà `ClientCredentialType` su uno di questi valori per specificare il tipo di credenziale che il client deve fornire per comunicare con il servizio. È possibile impostare i tipi nel codice o nei file di configurazione.  
  
|Impostazione|Descrizione|  
|-------------|-----------------|  
|None|Specifica che il client non deve presentare alcuna credenziale. Il client viene pertanto autenticato come anonimo.|  
|Di base|Specifica l'autenticazione di base per il client. Per altre informazioni, vedere il documento RFC2617, ovvero[HTTP Authentication: Basic and Digest Authentication](https://go.microsoft.com/fwlink/?LinkID=88313) (Autenticazione HTTP: autenticazione di base e del digest).|  
|Digest|Specifica l'autenticazione digest per il client. Per altre informazioni, vedere il documento RFC2617, ovvero[HTTP Authentication: Basic and Digest Authentication](https://go.microsoft.com/fwlink/?LinkID=88313) (Autenticazione HTTP: autenticazione di base e del digest).|  
|Ntlm|Specifica l'autenticazione NT LAN Manager (NTLM). Viene usato quando non è possibile usare l'autenticazione Kerberos per qualche motivo. È anche possibile disabilitare l'uso come fallback impostando il <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> proprietà `false`, in modo che WCF rendere un tutti i tentativi possibili per generare un'eccezione se viene usato NTLM. Si noti che l'impostazione di questa proprietà su `false` potrebbe non impedire l'invio di credenziali NTLM nella rete.|  
|Windows|Specifica l'autenticazione Windows. Per specificare solo il protocollo Kerberos in un dominio Windows, impostare la proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> su `false` (l'impostazione predefinita è `true`).|  
|Certificato|Esegue l'autenticazione client mediante un certificato X.509.|  
|Password|L'utente deve specificare un nome utente e una password. Convalidare la coppia di nome utente/password usando l'autenticazione di Windows o un'altra soluzione personalizzata.|  
  
### <a name="message-client-credential-types"></a>Tipi di credenziale usati nella sicurezza client a livello di messaggio  
 La tabella seguente mostra i tipi di credenziali usabili quando si crea un'applicazione che usa la sicurezza a livello di messaggio. I valori riportati possono essere usati nel codice o nei file di configurazione.  
  
|Impostazione|Descrizione|  
|-------------|-----------------|  
|None|Specifica che il client non deve presentare una credenziale. Il client viene pertanto autenticato come anonimo.|  
|Windows|Consente lo scambio di messaggi SOAP all'interno di un contesto di sicurezza stabilito mediante una credenziale Windows.|  
|Nome utente|Consente al servizio di richiedere che l'autenticazione del client si basi su una credenziale di tipo nome utente. Si noti che WCF non consente le operazioni di crittografia con i nomi utente, ad esempio la generazione di una firma o la crittografia dei dati. WCF garantisce che il trasporto è protetto quando si usano credenziali nome utente.|  
|Certificato|Consente al servizio di richiedere che il client venga autenticato tramite un certificato X.509.|  
|Token emesso|Un tipo di token personalizzato, configurato in base a un criterio di sicurezza. Il tipo di token predefinito è Security Assertions Markup Language (SAML). Il token viene emesso da un servizio token di sicurezza. Per altre informazioni, vedere [federazione e token emessi](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).|  
  
### <a name="negotiation-model-of-service-credentials"></a>Modello di negoziazione delle credenziali del servizio  
 *La negoziazione* è il processo di definizione di un trust tra un client e un servizio mediante lo scambio di credenziali. Il processo viene eseguito in maniera iterativa tra il client e il servizio in modo da divulgare solo le informazioni necessarie per il passaggio successivo nel processo di negoziazione. In pratica, il risultato finale è il recapito della credenziale di un servizio al client da usare nelle operazioni successive.  
  
 Con un'eccezione, per impostazione predefinita le associazioni fornite dal sistema in WCF negoziano la credenziale del servizio automaticamente quando si utilizza la sicurezza a livello di messaggio. (l'eccezione è <xref:System.ServiceModel.BasicHttpBinding>, che non consente la sicurezza per impostazione predefinita). Per disabilitare questo comportamento, vedere le proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> e <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A>.  
  
> [!NOTE]
>  Quando si usa la sicurezza SSL con .NET Framework 3.5 e versioni successive, un client WCF Usa i certificati intermedi nel proprio archivio certificati sia i certificati intermedi ricevuti durante la negoziazione SSL per eseguire la convalida di catena di certificati del servizio certificato. In .NET Framework 3.0 vengono usati solo i certificati intermedi installati nell'archivio certificati locale.  
  
#### <a name="out-of-band-negotiation"></a>Negoziazione fuori banda  
 Se la negoziazione automatica è disabilitata, la credenziale del servizio deve essere fornita al client prima di inviare qualsiasi messaggio al servizio. È anche noto come un *out-of-band* il provisioning. Ad esempio, se il tipo di credenziale specificato è un certificato e la negoziazione automatica è disabilitata, il client deve contattare il proprietario del servizio per ricevere e installare il certificato nel computer che esegue l'applicazione client. Questa operazione può essere eseguita, ad esempio, quando si desidera controllare accuratamente i client che possono accedere a un servizio in uno scenario business-to-business. Questo timeout-di-negoziazione fuori banda può essere eseguita in messaggio di posta elettronica e il certificato X.509 viene archiviato nell'archivio certificati Windows, utilizzando uno strumento come lo snap-in certificati di Microsoft Management Console (MMC).  
  
> [!NOTE]
>  La proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> viene usata per fornire al servizio un certificato ottenuto tramite la negoziazione fuori banda. Questa proprietà è necessaria quando si usa la classe <xref:System.ServiceModel.BasicHttpBinding> poiché l'associazione non consente la negoziazione automatica. La proprietà viene usata anche in uno scenario duplex non correlato. Si tratta di un scenario in cui un server invia un messaggio al client senza richiedere prima al client l'invio di una richiesta al server. Poiché il server non riceve una richiesta dal client, deve usare il certificato del client per crittografare il messaggio per il client.  
  
## <a name="setting-credential-values"></a>Impostazione dei valori di credenziale  
 Dopo aver selezionato una modalità di sicurezza, è necessario specificare le effettive credenziali. Ad esempio, se il tipo di credenziale è impostato su "certificato", è necessario associare una credenziale specifica (ad esempio un certificato X.509 specifico) al servizio o client.  
  
 Il metodo per l'impostazione del valore della credenziale differisce leggermente se si programma un servizio o un client.  
  
### <a name="setting-service-credentials"></a>Impostazione delle credenziali del servizio  
 Se si sta usando la modalità di trasporto e si usa HTTP come trasporto, è necessario usare Internet Information Services (IIS) o configurare la porta con un certificato. Per altre informazioni, vedere [Cenni preliminari sulla sicurezza di trasporto](../../../../docs/framework/wcf/feature-details/transport-security-overview.md) e [sicurezza del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Per fornire le credenziali a un servizio tramite il codice, creare un'istanza della classe <xref:System.ServiceModel.ServiceHost> e specificare la credenziale appropriata usando la classe <xref:System.ServiceModel.Description.ServiceCredentials>, a cui si accede tramite la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.  
  
#### <a name="setting-a-certificate"></a>Impostazione di un certificato  
 Per fornire a un servizio un certificato X.509 da usare per autenticare il servizio nei client, usare il metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>.  
  
 Per fornire a un servizio un certificato client, usare il metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>.  
  
#### <a name="setting-windows-credentials"></a>Impostazione delle credenziali di Windows  
 Se il client specifica un nome utente e una password validi, tali credenziali vengono usate per autenticare client. In caso contrario, vengono usate le credenziali dell'utente connesso.  
  
### <a name="setting-client-credentials"></a>Impostazione delle credenziali del client  
 In WCF, le applicazioni client usano un client WCF per connettersi ai servizi. Ogni client deriva dalla classe <xref:System.ServiceModel.ClientBase%601> e la proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> sul client consente alla specifica di vari valori delle credenziali client.  
  
#### <a name="setting-a-certificate"></a>Impostazione di un certificato  
 Per fornire a un servizio un certificato X.509 usato per autenticare il client per un servizio, usare il metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
## <a name="how-client-credentials-are-used-to-authenticate-a-client-to-the-service"></a>Come usare le credenziali client per autenticare il client per il servizio  
 Le informazioni sulla credenziale client richieste per comunicare con un servizio vengono fornite mediante la proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> o la proprietà <xref:System.ServiceModel.ChannelFactory.Credentials%2A>. Il canale di sicurezza usa queste informazioni per autenticare il client per il servizio. L'autenticazione viene eseguita tramite una delle due modalità seguenti:  
  
-   Le credenziali client vengono usate una sola volta prima che il primo messaggio venga inviato, usando l'istanza del client WCF per stabilire un contesto di sicurezza. Tutti i messaggi dell'applicazione vengono quindi protetti tramite il contesto di sicurezza.  
  
-   Le credenziali client vengono usate per autenticare ogni messaggio dell'applicazione inviato al servizio. In questo caso, nessun contesto viene stabilito tra il client e il servizio.  
  
### <a name="established-identities-cannot-be-changed"></a>Non è possibile modificare le identità stabilite  
 Quando si usa il primo metodo, il contesto stabilito viene associato permanentemente all'identità del client. Pertanto, quando il contesto di sicurezza è stato stabilito, l'identità associata al client non può essere modificata.  
  
> [!IMPORTANT]
>  È necessario tenere presente un aspetto legato all'impossibilità di cambiare identità (quando viene stabilito il contesto di sicurezza, ovvero il comportamento predefinito). Se si crea un servizio che comunica con un secondo servizio, l'identità usata per aprire il client WCF per il secondo servizio non può essere modificato. Questo diventa un problema se più client possono usare il primo servizio e il servizio rappresenta i client nell'accesso al secondo servizio. Se il servizio riusa lo stesso client per tutti i chiamanti, tutte le chiamate al secondo servizio vengono eseguite con l'identità del primo chiamante usato per aprire il client al secondo servizio. In altre parole, il servizio usa l'identità del primo client per tutti i client che vogliono comunicare con il secondo servizio. Ciò può causare un'elevazione di privilegi. Se questo non è il comportamento desiderato del servizio, è necessario registrare ogni chiamante e creare un nuovo client per il secondo servizio per ogni singolo chiamante e verificare che il servizio usi solo il client corretto per consentire ai diversi chiamanti la comunicazione con il secondo servizio.  
  
 Per altre informazioni sulle credenziali e le sessioni protette, vedere [considerazioni sulla sicurezza per le sessioni protette](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageSecurity.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverMsmq.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A?displayProperty=nameWithType>
- [Concetti relativi alla sicurezza](../../../../docs/framework/wcf/feature-details/security-concepts.md)
- [Protezione di servizi e client](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Programmazione delle funzionalità di sicurezza di WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
- [Sicurezza del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
