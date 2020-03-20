---
title: 'Procedura: creare un client federato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 56ece47e-98bf-4346-b92b-fda1fc3b4d9c
ms.openlocfilehash: a9213d8cbbafaaa1fffa3a1db0d6936c2fc6544f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185045"
---
# <a name="how-to-create-a-federated-client"></a>Procedura: creare un client federato
In Windows Communication Foundation (WCF), la creazione di un client per un servizio federato è costituita da tre passaggi principali:In Windows Communication Foundation (WCF), creating a client for a *federated service* consists of three main steps:  
  
1. Configurare un [ \<>wsFederationHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) o un'associazione personalizzata simile. Per ulteriori informazioni sulla creazione di un'associazione appropriata, vedere [Procedura: creare un oggetto WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md). In alternativa, eseguire lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) sull'endpoint dei metadati del servizio federato per generare un file di configurazione per la comunicazione con il servizio federato e uno o più servizi token di sicurezza.  
  
2. Impostare le proprietà di <xref:System.ServiceModel.Security.IssuedTokenClientCredential> che controlla i vari aspetti dell'interazione di un client con un servizio token di sicurezza.  
  
3. Impostare le proprietà di <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>, che consente ai certificati richiesti di comunicare in modo protetto con determinati endpoint, ad esempio servizi token di sicurezza.  
  
> [!NOTE]
> Potrebbe venire generata una <xref:System.Security.Cryptography.CryptographicException> quando un client utilizza credenziali rappresentate, l'associazione <xref:System.ServiceModel.WSFederationHttpBinding> o un token personalizzato e chiavi simmetriche. Chiavi asimmetriche sono utilizzate con l'associazione<xref:System.ServiceModel.WSFederationHttpBinding> e token personalizzati quando le proprietà <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A> e <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> sono impostate rispettivamente su <xref:System.IdentityModel.Tokens.SecurityKeyType.AsymmetricKey>. <xref:System.Security.Cryptography.CryptographicException> viene generato quando il client tenta di inviare un messaggio e non esiste un profilo utente per l'identità che il client sta rappresentando. Per limitare questo problema, accedere al computer client o chiamare `LoadUserProfile` prima di inviare il messaggio.  
  
 In questo argomento vengono fornite informazioni dettagliate su queste procedure. Per ulteriori informazioni sulla creazione di un'associazione appropriata, vedere [Procedura: creare un oggetto WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md). Per ulteriori informazioni sul funzionamento di un servizio federato, vedere [Federazione](../../../../docs/framework/wcf/feature-details/federation.md).  
  
### <a name="to-generate-and-examine-the-configuration-for-a-federated-service"></a>Per generare ed esaminare la configurazione per un servizio federato  
  
1. Eseguire lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con l'indirizzo dell'URL dei metadati del servizio come parametro della riga di comando.  
  
2. Aprire il file di configurazione generato in un editor appropriato.  
  
3. Esaminare gli attributi e il contenuto di qualsiasi [ \<>emittente](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) generato e [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) gli elementi di emittenteMetadata>. Questi si trovano [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) all'interno degli elementi di sicurezza>per il [ \<>wsFederationHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) o gli elementi di associazione personalizzati. Assicurarsi che gli indirizzi contengano i nomi di dominio previsti o altre informazioni sull'indirizzo. È importante controllare queste informazioni perché il client viene autenticato presso questi indirizzi e può fornire informazioni quali coppie di nome utente/password. Se l'indirizzo non è quello previsto, le informazioni potrebbero venire fornite a un destinatario imprevisto.  
  
4. Esaminare eventuali elementi `alternativeIssuedTokenParameters` [ \<aggiuntivi issuedTokenParameters>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md) all'interno dell'elemento> <come commento. Quando viene utilizzato lo strumento Svcutil.exe per generare la configurazione per un servizio federato, se quest'ultimo o qualsiasi servizio token di sicurezza intermedio non specifica l'indirizzo del mittente ma un indirizzo dei metadai per un servizio token di sicurezza che espone più endpoint, il file di configurazione risultante fa riferimento al primo endpoint. Endpoint aggiuntivi sono nel file di configurazione `alternativeIssuedTokenParameters` come commentato <> elementi.  
  
     Determinare se uno `issuedTokenParameters` di questi <> è preferibile a quello già presente nella configurazione. Ad esempio, il client potrebbe preferire l'autenticazione a un servizio token di sicurezza utilizzando un token Windows CardSpace anziché una coppia nome utente/password.  
  
    > [!NOTE]
    > Nel caso in cui sia necessario attraversare più servizi token di sicurezza prima di comunicare con il servizio, un servizio token di sicurezza intermedio potrebbe indirizzare il client a un servizio token di sicurezza errato. Pertanto, assicurarsi che l'endpoint per il servizio token di sicurezza nel [ \<>issuedTokenParameters](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md) sia il servizio token di sicurezza previsto e non un servizio token di sicurezza sconosciuto.  
  
### <a name="to-configure-an-issuedtokenclientcredential-in-code"></a>Per configurare un IssuedTokenClientCredential nel codice  
  
1. Accedere a <xref:System.ServiceModel.Security.IssuedTokenClientCredential> tramite la proprietà <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> della classe <xref:System.ServiceModel.Description.ClientCredentials> (restituita dalla proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601> o tramite la classe <xref:System.ServiceModel.ChannelFactory>), come illustrato nell'esempio di codice seguente.  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
2. Se non è richiesta la memorizzazione del token nella cache, impostare la proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.CacheIssuedTokens%2A> su `false`. La proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.CacheIssuedTokens%2A> controlla se tali token da un servizio token di sicurezza sono memorizzati nella cache. Se questa proprietà è impostata su `false`, il client richiede un nuovo token al servizio token di sicurezza ogni volta che deve autenticarsi di nuovo al servizio federato, a prescindere dal fatto che un token precedente sia ancora valido. Se questa proprietà è impostata su `true`, il client riutilizza un token esistente ogni volta che deve autenticarsi di nuovo al servizio federato (a condizione che il token non sia scaduto). Il valore predefinito è `true`.  
  
3. Se è richiesto un tempo massimo sui token memorizzati nella cache, impostare la proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.MaxIssuedTokenCachingTime%2A> su un valore <xref:System.TimeSpan>. La proprietà specifica quanto tempo un token può essere memorizzato nella cache. Allo scadere del periodo di tempo specificato, il token viene rimosso dalla cache del client. Per impostazione predefinita, i token sono memorizzati nella cache per una durata illimitata. Nell'esempio seguente, l'intervallo di tempo viene impostato su 10 minuti.  
  
     [!code-csharp[c_CreateSTS#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#15)]
     [!code-vb[c_CreateSTS#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#15)]  
  
4. Facoltativa. Impostare <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuedTokenRenewalThresholdPercentage%2A> su una percentuale. Il valore predefinito è 60 (percento). La proprietà specifica una percentuale del periodo di validità del token. Se il token emesso è valido, ad esempio, per 10 ore e <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuedTokenRenewalThresholdPercentage%2A> è impostato su 80, il token verrà rinnovato dopo otto ore. Nell'esempio seguente il valore viene impostato su 80 percento.  
  
     [!code-csharp[c_CreateSTS#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#16)]
     [!code-vb[c_CreateSTS#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#16)]  
  
     L'intervallo di rinnovo determinato dal periodo di validità del token e il valore `IssuedTokenRenewalThresholdPercentage` vengono sottoposti a override da parte del valore `MaxIssuedTokenCachingTime` nei casi in cui il tempo di memorizzazione nella cache sia inferiore al tempo soglia di rinnovo. Se, ad esempio, il prodotto di `IssuedTokenRenewalThresholdPercentage` e la durata del token è otto ore e il valore `MaxIssuedTokenCachingTime` è 10 minuti, il client contatta il servizio token di sicurezza per un token aggiornato ogni 10 minuti.  
  
5. Se è richiesta una modalità di entropia di chiavi diversa da <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.CombinedEntropy> su un'associazione che non utilizza la sicurezza del messaggio o quella del trasporto con le credenziali del messaggio (ad esempio, l'associazione non ha un oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement>), impostare la proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> su un valore appropriato. La modalità *di entropia* determina <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> se le chiavi simmetriche possono essere controllate utilizzando la proprietà . Questa impostazione predefinita è <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.CombinedEntropy>, dove sia il client che l'emittente del token, forniscono dati combinati per produrre la chiave effettiva. Gli altri valori sono <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.ClientEntropy> e <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.ServerEntropy>, il che indica che la chiave intera è specificata rispettivamente dal client o dal server. Nell'esempio seguente viene impostata la proprietà per utilizzare solo i dati del server per la chiave.  
  
     [!code-csharp[c_CreateSTS#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#17)]
     [!code-vb[c_CreateSTS#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#17)]  
  
    > [!NOTE]
    > Se in un servizio token di sicurezza o in un'associazione del servizio è presente un elemento <xref:System.ServiceModel.Channels.SecurityBindingElement>, <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> impostata su <xref:System.ServiceModel.Security.IssuedTokenClientCredential> viene sottoposta a override da parte della proprietà <xref:System.ServiceModel.Channels.SecurityBindingElement.KeyEntropyMode%2A> di `SecurityBindingElement`.  
  
6. Configurare qualsiasi comportamento dell'endopoint specifico per l'emittente aggiungendolo alla raccolta restituita dalla proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>.  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-issuedtokenclientcredential-in-configuration"></a>Per configurare IssuedTokenClientCredential nella configurazione  
  
1. Creare un [ \<elemento di>issuedToken](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) come figlio dell'elemento [ \<>di emissione](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) in un endpoint.  
  
2. Se la memorizzazione nella cache `cacheIssuedTokens` dei token `issuedToken` non è `false`necessaria, impostare l'attributo (dell'elemento <>) su .  
  
3. Se è necessario un limite di tempo `maxIssuedTokenCachingTime` per i `issuedToken` token memorizzati nella cache, impostare l'attributo sull'elemento <> su un valore appropriato. Ad esempio:  
    `<issuedToken maxIssuedTokenCachingTime='00:10:00' />`  
  
4. Se si preferisce un valore diverso `issuedTokenRenewalThresholdPercentage` da quello `issuedToken` predefinito, impostare l'attributo sul <>elemento su un valore appropriato, ad esempio:  
  
    ```xml  
    <issuedToken issuedTokenRenewalThresholdPercentage = "80" />  
    ```  
  
5. Se una modalità entropia chiave diversa da `CombinedEntropy` è su un'associazione che non utilizza la protezione del messaggio o la protezione del trasporto con le credenziali del messaggio (ad esempio, l'associazione non ha un `SecurityBindingElement`), impostare l'attributo `defaultKeyEntropyMode` nell'elemento `<issuedToken>``ServerEntropy`, come richiesto.  
  
    ```xml  
    <issuedToken defaultKeyEntropyMode = "ServerEntropy" />  
    ```  
  
6. Facoltativa. Configurare qualsiasi comportamento dell'endpoint personalizzato `issuerChannelBehaviors` specifico dell'autorità emittente `issuedToken` creando un elemento <> come elemento figlio dell'elemento <>. Per ogni comportamento, `add` creare un elemento> `issuerChannelBehaviors` <come elemento figlio dell'elemento> <. Specificare l'indirizzo dell'autorità `issuerAddress` emittente del `add` comportamento impostando l'attributo sull'elemento <>. Specificare il comportamento `behaviorConfiguration` stesso impostando `add` l'attributo sull'elemento <>.  
  
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
  
1. Creare un [ \<elemento scopedCertificates>](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md) come figlio dell'elemento [ \<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) che è a sua volta figlio dell'elemento [ \<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) in un comportamento dell'endpoint.  
  
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
  
 Per ulteriori informazioni <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A>sull'impostazione delle proprietà <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A>, e <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> della <xref:System.ServiceModel.Security.IssuedTokenClientCredential> classe , vedere [Procedura: configurare un'autorità emittente locale](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
## <a name="scoped-certificates"></a>Certificati con ambito  
 Se è necessario specificare certificati del servizio per comunicare con qualsiasi servizio token di sicurezza, in genere perché la negoziazione del certificato non è utilizzata, utilizzare la proprietà <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>. Il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetDefaultCertificate%2A> prende <xref:System.Uri> e <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> come parametri. Il certificato specificato viene utilizzato quando si comunica con gli endpoint nell'URI specificato. In alternativa, è possibile utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetScopedCertificate%2A> per aggiungere un certificato alla raccolta restituita dalla proprietà <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>.  
  
> [!NOTE]
> L'idea client di certificati definiti con ambito per uno specifico URI si applica solo alle applicazioni che stanno effettuando chiamate in uscita a servizi che espongono endpoint a tali URI. Non si applica ai certificati utilizzati per firmare i token rilasciati, ad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A> esempio <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> quelli configurati nel server nella raccolta restituita dalla classe . Per ulteriori informazioni, vedere [Procedura: configurare le credenziali in un servizio federativo](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di federazione](../../../../docs/framework/wcf/samples/federation-sample.md)
- [Procedura: disattivare sessioni protette in un'associazione WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Procedura: Creare una classe WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [Procedura: configurare le credenziali in un servizio federativo](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Procedura: configurare un emittente locale](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Considerazioni sulla sicurezza con metadati](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)
- [Procedura: proteggere endpoint dei metadati](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md)
