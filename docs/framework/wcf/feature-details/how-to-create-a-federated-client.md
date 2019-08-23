---
title: 'Procedura: Creare un client federato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 56ece47e-98bf-4346-b92b-fda1fc3b4d9c
ms.openlocfilehash: 988fc79f71b670f5eaed1a305f54cc90374e4b17
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950621"
---
# <a name="how-to-create-a-federated-client"></a>Procedura: Creare un client federato
In Windows Communication Foundation (WCF) la creazione di un client per un *Servizio federato* è costituita da tre passaggi principali:  
  
1. Configurare un [ \<> WSFederationHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) o un'associazione personalizzata simile. Per ulteriori informazioni sulla creazione di un'associazione appropriata, [vedere Procedura: Creare un'associazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)WSFederationHttpBinding. In alternativa, eseguire lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per l'endpoint dei metadati del servizio federato per generare un file di configurazione per la comunicazione con il servizio federato e uno o più servizi token di sicurezza.  
  
2. Impostare le proprietà di <xref:System.ServiceModel.Security.IssuedTokenClientCredential> che controlla i vari aspetti dell'interazione di un client con un servizio token di sicurezza.  
  
3. Impostare le proprietà di <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>, che consente ai certificati richiesti di comunicare in modo protetto con determinati endpoint, ad esempio servizi token di sicurezza.  
  
> [!NOTE]
> Potrebbe venire generata una <xref:System.Security.Cryptography.CryptographicException> quando un client utilizza credenziali rappresentate, l'associazione <xref:System.ServiceModel.WSFederationHttpBinding> o un token personalizzato e chiavi simmetriche. Chiavi asimmetriche sono utilizzate con l'associazione<xref:System.ServiceModel.WSFederationHttpBinding> e token personalizzati quando le proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A> e <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> sono impostate rispettivamente su <xref:System.IdentityModel.Tokens.SecurityKeyType.AsymmetricKey>. <xref:System.Security.Cryptography.CryptographicException> viene generato quando il client tenta di inviare un messaggio e non esiste un profilo utente per l'identità che il client sta rappresentando. Per limitare questo problema, accedere al computer client o chiamare `LoadUserProfile` prima di inviare il messaggio.  
  
 In questo argomento vengono fornite informazioni dettagliate su queste procedure. Per ulteriori informazioni sulla creazione di un'associazione appropriata, [vedere Procedura: Creare un'associazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)WSFederationHttpBinding. Per ulteriori informazioni sul funzionamento di un servizio federato, vedere [Federazione](../../../../docs/framework/wcf/feature-details/federation.md).  
  
### <a name="to-generate-and-examine-the-configuration-for-a-federated-service"></a>Per generare ed esaminare la configurazione per un servizio federato  
  
1. Eseguire lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con l'indirizzo dell'URL dei metadati del servizio come parametro della riga di comando.  
  
2. Aprire il file di configurazione generato in un editor appropriato.  
  
3. Esaminare gli attributi e il contenuto di tutti gli elementi [ \<Issuer >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) e [ \<IssuerMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) generati. Si trovano negli [ \<elementi > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) per gli [ \<elementi WSFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) o binding personalizzati. Assicurarsi che gli indirizzi contengano i nomi di dominio previsti o altre informazioni sull'indirizzo. È importante controllare queste informazioni perché il client viene autenticato presso questi indirizzi e può fornire informazioni quali coppie di nome utente/password. Se l'indirizzo non è quello previsto, le informazioni potrebbero venire fornite a un destinatario imprevisto.  
  
4. Esaminare gli elementi aggiuntivi [ \<> issuedTokenParameters](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md) all'interno dell'elemento <`alternativeIssuedTokenParameters`> impostato come commento. Quando viene utilizzato lo strumento Svcutil.exe per generare la configurazione per un servizio federato, se quest'ultimo o qualsiasi servizio token di sicurezza intermedio non specifica l'indirizzo del mittente ma un indirizzo dei metadai per un servizio token di sicurezza che espone più endpoint, il file di configurazione risultante fa riferimento al primo endpoint. Gli endpoint aggiuntivi si trovano nel file di configurazione come commento <`alternativeIssuedTokenParameters`> elementi.  
  
     Determinare se una di queste <`issuedTokenParameters`> è preferibile a quella già presente nella configurazione. È ad esempio possibile che il client preferisca eseguire l'autenticazione a un servizio token di sicurezza utilizzando un token Windows CardSpace anziché una coppia nome utente/password.  
  
    > [!NOTE]
    > Nel caso in cui sia necessario attraversare più servizi token di sicurezza prima di comunicare con il servizio, un servizio token di sicurezza intermedio potrebbe indirizzare il client a un servizio token di sicurezza errato. Assicurarsi pertanto che l'endpoint per il servizio token di sicurezza nel [ \<issuedTokenParameters >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md) sia il servizio token di sicurezza previsto e non un servizio token di sicurezza sconosciuto.  
  
### <a name="to-configure-an-issuedtokenclientcredential-in-code"></a>Per configurare un IssuedTokenClientCredential nel codice  
  
1. Accedere a <xref:System.ServiceModel.Security.IssuedTokenClientCredential> tramite la proprietà <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> della classe <xref:System.ServiceModel.Description.ClientCredentials> (restituita dalla proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601> o tramite la classe <xref:System.ServiceModel.ChannelFactory>), come illustrato nell'esempio di codice seguente.  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
2. Se non è richiesta la memorizzazione del token nella cache, impostare la proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.CacheIssuedTokens%2A> su `false`. La proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.CacheIssuedTokens%2A> controlla se tali token da un servizio token di sicurezza sono memorizzati nella cache. Se questa proprietà è impostata su `false`, il client richiede un nuovo token al servizio token di sicurezza ogni volta che deve autenticarsi di nuovo al servizio federato, a prescindere dal fatto che un token precedente sia ancora valido. Se questa proprietà è impostata su `true`, il client riutilizza un token esistente ogni volta che deve autenticarsi di nuovo al servizio federato (a condizione che il token non sia scaduto). Il valore predefinito è `true`.  
  
3. Se è richiesto un tempo massimo sui token memorizzati nella cache, impostare la proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.MaxIssuedTokenCachingTime%2A> su un valore <xref:System.TimeSpan>. La proprietà specifica quanto tempo un token può essere memorizzato nella cache. Allo scadere del periodo di tempo specificato, il token viene rimosso dalla cache del client. Per impostazione predefinita, i token sono memorizzati nella cache per una durata illimitata. Nell'esempio seguente, l'intervallo di tempo viene impostato su 10 minuti.  
  
     [!code-csharp[c_CreateSTS#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#15)]
     [!code-vb[c_CreateSTS#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#15)]  
  
4. facoltativo. Impostare <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuedTokenRenewalThresholdPercentage%2A> su una percentuale. Il valore predefinito è 60 (percento). La proprietà specifica una percentuale del periodo di validità del token. Se il token emesso è valido, ad esempio, per 10 ore e <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuedTokenRenewalThresholdPercentage%2A> è impostato su 80, il token verrà rinnovato dopo otto ore. Nell'esempio seguente il valore viene impostato su 80 percento.  
  
     [!code-csharp[c_CreateSTS#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#16)]
     [!code-vb[c_CreateSTS#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#16)]  
  
     L'intervallo di rinnovo determinato dal periodo di validità del token e il valore `IssuedTokenRenewalThresholdPercentage` vengono sottoposti a override da parte del valore `MaxIssuedTokenCachingTime` nei casi in cui il tempo di memorizzazione nella cache sia inferiore al tempo soglia di rinnovo. Se, ad esempio, il prodotto di `IssuedTokenRenewalThresholdPercentage` e la durata del token è otto ore e il valore `MaxIssuedTokenCachingTime` è 10 minuti, il client contatta il servizio token di sicurezza per un token aggiornato ogni 10 minuti.  
  
5. Se è richiesta una modalità di entropia di chiavi diversa da <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.CombinedEntropy> su un'associazione che non utilizza la sicurezza del messaggio o quella del trasporto con le credenziali del messaggio (ad esempio, l'associazione non ha un oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement>), impostare la proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> su un valore appropriato. La modalità *entropia* determina se è possibile controllare le chiavi simmetriche utilizzando <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> la proprietà. Questa impostazione predefinita è <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.CombinedEntropy>, dove sia il client che l'emittente del token, forniscono dati combinati per produrre la chiave effettiva. Gli altri valori sono <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.ClientEntropy> e <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.ServerEntropy>, il che indica che la chiave intera è specificata rispettivamente dal client o dal server. Nell'esempio seguente viene impostata la proprietà per utilizzare solo i dati del server per la chiave.  
  
     [!code-csharp[c_CreateSTS#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#17)]
     [!code-vb[c_CreateSTS#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#17)]  
  
    > [!NOTE]
    > Se in un servizio token di sicurezza o in un'associazione del servizio è presente un elemento <xref:System.ServiceModel.Channels.SecurityBindingElement>, <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> impostata su <xref:System.ServiceModel.Security.IssuedTokenClientCredential> viene sottoposta a override da parte della proprietà <xref:System.ServiceModel.Channels.SecurityBindingElement.KeyEntropyMode%2A> di `SecurityBindingElement`.  
  
6. Configurare qualsiasi comportamento dell'endopoint specifico per l'emittente aggiungendolo alla raccolta restituita dalla proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>.  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-issuedtokenclientcredential-in-configuration"></a>Per configurare IssuedTokenClientCredential nella configurazione  
  
1. Creare un [ \<elemento > IssuedToken](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) come figlio dell' [ \<elemento IssuedToken >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) in un comportamento dell'endpoint.  
  
2. Se non è necessaria la memorizzazione dei token nella cache `cacheIssuedTokens` , impostare l'attributo (`issuedToken`del < elemento > `false`) su.  
  
3. Se è necessario un limite di tempo per i token memorizzati nella cache `maxIssuedTokenCachingTime` , impostare l'attributo`issuedToken`sull'elemento < > su un valore appropriato. Ad esempio:  
    `<issuedToken maxIssuedTokenCachingTime='00:10:00' />`  
  
4. Se è preferibile un valore diverso da quello predefinito, `issuedTokenRenewalThresholdPercentage` impostare l'attributo nell'`issuedToken`elemento < > su un valore appropriato, ad esempio:  
  
    ```xml  
    <issuedToken issuedTokenRenewalThresholdPercentage = "80" />  
    ```  
  
5. Se una modalità di entropia di chiavi diversa da `CombinedEntropy` si trova in un'associazione di sicurezza di non utilizzare la sicurezza dei messaggi o di trasporto con credenziali messaggio (ad esempio, l'associazione non ha un `SecurityBindingElement`), impostare il `defaultKeyEntropyMode` attributo la `<issuedToken>` elemento da un oggetto `ServerEntropy` o `ClientEntropy` come richiesto.  
  
    ```xml  
    <issuedToken defaultKeyEntropyMode = "ServerEntropy" />  
    ```  
  
6. facoltativo. Configurare qualsiasi comportamento dell'endpoint personalizzato specifico dell'autorità emittente creando un <`issuerChannelBehaviors`elemento > come figlio dell'elemento <`issuedToken`>. Per ogni comportamento, creare un elemento`add`< > come figlio dell'elemento <`issuerChannelBehaviors`>. Specificare l'indirizzo dell'autorità emittente del comportamento impostando l' `issuerAddress` attributo sull'elemento <`add`>. Specificare il comportamento stesso impostando l' `behaviorConfiguration` attributo sull'elemento <`add`>.  
  
    ```xml  
    <issuerChannelBehaviors>  
    <add issuerAddress="http://fabrikam.org/sts" behaviorConfiguration="FabrikamSTS" />  
    </issuerChannelBehaviors>  
    ```  
  
### <a name="to-configure-an-x509certificaterecipientclientcredential-in-code"></a>Per configurare un X509CertificateRecipientClientCredential nel codice  
  
1. Accedere a <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential> tramite la proprietà <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A> della proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601> o la proprietà <xref:System.ServiceModel.ChannelFactory>.  
  
     [!code-csharp[c_CreateSTS#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#18)]
     [!code-vb[c_CreateSTS#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#18)]  
  
2. Se è disponibile un'istanza di <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> per il certificato per un determinato endpoint, utilizzare il metodo <xref:System.Collections.Generic.ICollection%601.Add%2A> della raccolta restituita dalla proprietà <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>.  
  
     [!code-csharp[c_CreateSTS#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#19)]
     [!code-vb[c_CreateSTS#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#19)]  
  
3. Se non è disponibile un'istanza di <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>, utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetScopedCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential> come illustrato nell'esempio seguente.  
  
     [!code-csharp[c_CreateSTS#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#20)]
     [!code-vb[c_CreateSTS#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#20)]  
  
### <a name="to-configure-an-x509certificaterecipientclientcredential-in-configuration"></a>Per configurare un X509CertificateRecipientClientCredential nella configurazione  
  
1. Creare un [ \<elemento > scopedCertificates](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md) come figlio dell' [ \<elemento > ServiceCertificate](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) che è figlio dell' [ \<elemento ClientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) in un comportamento dell'endpoint.  
  
2. Creare un elemento `<add>` come figlio dell'elemento `<scopedCertificates>`. Specificare i valori per gli attributi `storeLocation`, `storeName`, `x509FindType` e `findValue` per fare riferimento al certificato appropriato. Impostare l'attributo `targetUri` su un valore che fornisce l'indirizzo dell'endpoint per il quale deve essere utilizzato il certificato, come illustrato nell'esempio seguente.  
  
    ```xml  
    <scopedCertificates>  
     <add targetUri="http://fabrikam.com/sts"   
          storeLocation="CurrentUser"  
          storeName="TrustedPeople"  
          x509FindType="FindBySubjectName"  
          findValue="FabrikamSTS" />  
    </scopedCertificates>  
    ```  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene configurata un'istanza della classe <xref:System.ServiceModel.Security.IssuedTokenClientCredential> nel codice.  
  
 [!code-csharp[c_FederatedClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federatedclient/cs/source.cs#2)]
 [!code-vb[c_FederatedClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federatedclient/vb/source.vb#2)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Per impedire che vengano divulgate determinate informazioni, i client che stanno eseguendo lo strumento Svcutil.exe per elaborare i metadati dagli endpoint federati devono assicurarsi che gli indirizzi del servizio token di sicurezza risultanti siano quelli previsti. Ciò è particolarmente importante quando un servizio token di sicurezza espone più endpoint, perché lo strumento Svcutil.exe genera il file di configurazione risultante per utilizzare il primo di questi endpoint che potrebbe non essere quello che il client deve utilizzare.  
  
## <a name="localissuer-required"></a>LocalIssuer Required  
 Se si prevede che i client utilizzino sempre un emittente locale, tenere presente quanto segue: per impostazione predefinita, lo strumento Svcutil.exe fa sì che l'emittente locale non venga utilizzato nel caso in cui il penultimo servizio token di sicurezza nella catena specifichi un indirizzo dell'emittente o un indirizzo dei metadati dell'emittente.  
  
 Per ulteriori informazioni sull' <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A>impostazione delle proprietà, <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A>e <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> della <xref:System.ServiceModel.Security.IssuedTokenClientCredential> classe, vedere [procedura: Configurare un'autorità emittente](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)locale.  
  
## <a name="scoped-certificates"></a>Certificati con ambito  
 Se è necessario specificare certificati del servizio per comunicare con qualsiasi servizio token di sicurezza, in genere perché la negoziazione del certificato non è utilizzata, utilizzare la proprietà <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>. Il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetDefaultCertificate%2A> prende <xref:System.Uri> e <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> come parametri. Il certificato specificato viene utilizzato quando si comunica con gli endpoint nell'URI specificato. In alternativa, è possibile utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetScopedCertificate%2A> per aggiungere un certificato alla raccolta restituita dalla proprietà <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>.  
  
> [!NOTE]
> L'idea client di certificati definiti con ambito per uno specifico URI si applica solo alle applicazioni che stanno effettuando chiamate in uscita a servizi che espongono endpoint a tali URI. Non si applica ai certificati utilizzati per firmare i token emessi, ad esempio quelli configurati nel server nella raccolta restituita da <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A> <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> della classe. Per altre informazioni, vedere [Procedura: Configurare le credenziali in un](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)servizio federativo.  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di federazione](../../../../docs/framework/wcf/samples/federation-sample.md)
- [Procedura: Disabilitare le sessioni protette in un'associazione WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Procedura: Creare un'associazione WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [Procedura: Configurare le credenziali in un Servizio federativo](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Procedura: Configurare un'autorità emittente locale](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Considerazioni sulla sicurezza con i metadati](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)
- [Procedura: Proteggere gli endpoint dei metadati](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md)
