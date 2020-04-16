---
title: Comportamenti di sicurezza in WCF
ms.date: 03/30/2017
ms.assetid: 513232c0-39fd-4409-bda6-5ebd5e0ea7b0
ms.openlocfilehash: 9f96abac0f5f32279c5579dd01c3dd7f2dc1786c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464053"
---
# <a name="security-behaviors-in-wcf"></a>Comportamenti di sicurezza in WCF
In Windows Communication Foundation (WCF), i comportamenti modificano il comportamento in fase di esecuzione a livello di servizio o a livello di endpoint. Per ulteriori informazioni sui comportamenti in generale, vedere Specifica del comportamento in fase di [esecuzione del servizio.](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md) *I comportamenti di sicurezza* consentono di controllare le credenziali, l'autenticazione, l'autorizzazione e i registri di controllo. I comportamenti possono essere utilizzati tramite programmazione o mediante configurazione. In questo argomento viene descritto come configurare i comportamenti relativi alle funzioni di sicurezza elencati di seguito:  
  
- serviceCredentials>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)  
  
- clientCredentials>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)  
  
- >serviceAuthorization . [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)  
  
- serviceSecurityAudit>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)  
  
- serviceMetadata>, che consente inoltre di specificare un endpoint sicuro a cui i client possono accedere per i metadati. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)  
  
## <a name="setting-credentials-with-behaviors"></a>Impostazione delle credenziali tramite i comportamenti  
 Usare il [ \<>serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) e [ \<clientCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) per impostare i valori delle credenziali per un servizio o un client. La configurazione dell'associazione sottostante determina se occorre impostare una credenziale. Ad esempio, se la modalità di sicurezza è impostata su `None`, né i client né i servizi si autenticano reciprocamente o richiedono alcun tipo di credenziale.  
  
 Se invece l'associazione del servizio richiede un tipo di credenziale client, è possibile che occorra utilizzare un comportamento per impostare i valori delle credenziali. Per ulteriori informazioni sui possibili tipi di credenziali, vedere Selezione di un tipo di [credenziali.](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md) In alcuni casi, ad esempio quando le credenziali di Windows vengono utilizzate per l'autenticazione, l'ambiente stabilisce automaticamente il valore effettivo delle credenziali e non è necessario impostare in modo esplicito il valore delle credenziali (a meno che non si desideri specificare un set di credenziali diverso).  
  
 Tutte le credenziali del servizio vengono trovate come elementi figlio del [ \<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md). L'esempio seguente illustra un certificato utilizzato come credenziale di servizio.  
  
```xml  
<configuration>  
 <system.serviceModel>  
  <behaviors>  
   <serviceBehaviors>  
    <behavior name="ServiceBehavior1">  
     <serviceCredentials>  
      <serviceCertificate findValue="000000000000000000000000000"
                          storeLocation="CurrentUser"  
      storeName="Root" x509FindType="FindByThumbprint" />  
     </serviceCredentials>  
    </behavior>  
   </serviceBehaviors>  
  </behaviors>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="service-credentials"></a>Credenziali di servizio  
 Il [ \<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) contiene quattro elementi figlio. Questi elementi e le relative modalità di utilizzo vengono descritti nelle sezioni seguenti.  
  
### <a name="servicecertificate-element"></a>\<Elemento> serviceCertificate  
 Questo elemento consente di specificare il certificato X.509 utilizzato dai client per autenticare il servizio tramite la modalità di sicurezza Messaggio. L'identificazione digitale di un certificato rinnovato periodicamente viene aggiornata di conseguenza. In questo caso, poiché il certificato può essere rilasciato nuovamente con lo stesso nome del soggetto, usare quest'ultimo come tipo `X509FindType`.  
  
 Per ulteriori informazioni sull'utilizzo dell'elemento, vedere [Procedura: specificare i valori delle credenziali client](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
### <a name="certificate-of-clientcertificate-element"></a>\<> di \<certificato dell'elemento> clientCertificate  
 Utilizzare [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md) l'elemento>del certificato quando il servizio deve disporre in anticipo del certificato del client per comunicare in modo sicuro con il client. Questa esigenza si presenta quando si usa il modello di comunicazione duplex. Nel modello più comune di comunicazione richiesta-risposta, il client include il proprio certificato nella richiesta e il servizio usa tale certificato per proteggere la risposta che invia al client. Il modello di comunicazione duplex, invece, non prevede né richieste né risposte e pertanto il servizio non può ricavare il certificato del client dalla comunicazione. Di conseguenza, per proteggere i messaggi inviati al client, il servizio deve disporre in anticipo del certificato del client. Il certificato del client deve essere ottenuto fuori banda e deve essere specificato tramite questo elemento. Per ulteriori informazioni sui servizi duplex, vedere [Procedura: creare un contratto duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
### <a name="authentication-of-clientcertificate-element"></a>\<> di \<autenticazione dell'elemento> clientCertificate  
 [ \<L'elemento>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) di autenticazione consente di personalizzare la modalità di autenticazione dei client. A tale scopo, l'attributo `CertificateValidationMode` può essere impostato su `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` o `Custom`. Per impostazione predefinita, `ChainTrust`il livello è impostato su , che specifica che ogni certificato deve trovarsi in una gerarchia di certificati che termina con *un'autorità radice* nella parte superiore della catena. Si tratta della modalità più protetta. Il livello può inoltre essere impostato su `PeerOrChainTrust`, a indicare che sia i certificati autocertificati (trust peer) sia i certificati appartenenti a una catena di trust sono ritenuti attendibili. Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi. Quando si distribuisce un client è invece opportuno usare il livello `ChainTrust`. Un altro livello disponibile è `Custom`. Quando si imposta il livello `Custom` è necessario impostare anche l'attributo `CustomCertificateValidatorType` sull'assembly e sul tipo usati per convalidare il certificato. Per creare un validator personalizzato è necessario ereditare una classe dalla classe astratta <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
### <a name="issuedtokenauthentication-element"></a>\<elemento> issuedTokenAuthentication  
 L'emissione di un token di autenticazione prevede tre fasi. Nella prima fase, un client che tenta di accedere a un servizio viene fatto riferimento a un *servizio token di sicurezza.* Nella seconda fase, il servizio token di sicurezza autentica il client, quindi rilascia a quest'ultimo un token, in genere un token SAML (Security Assertions Markup Language), che il client restituisce in seguito al servizio. Nella terza fase, il servizio ricerca nel token appena ricevuto i dati da usare per autenticare il token stesso e, pertanto, il client. Affinché il token venga autenticato è necessario che il servizio riconosca il certificato utilizzato dal servizio token di sicurezza. Il [ \<>issuedTokenAuthentication](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) è l'archivio per tali certificati del servizio token di sicurezza. Per aggiungere certificati, utilizzare il [ \<>knownCertificates ](../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). Inserire [ \<un>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) aggiuntivo per ogni certificato, come illustrato nell'esempio seguente.  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"
           storeLocation="LocalMachine" storeName="My"
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 Per impostazione predefinita, i certificati devono essere ottenuti da un servizio token di sicurezza. Questi certificati "riconosciuti" garantiscono che solo i client autorizzati siano in grado di accedere a un determinato servizio.  
  
 È necessario usare la `SamlSecurityToken` *secure token service* [ \<raccolta di>allowedAudienceUris](../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md) in un'applicazione federata che utilizza un servizio token di sicurezza che emette token di sicurezza. Quando emette il token di sicurezza, il servizio STS può specificare l'URI dei servizi Web per cui si desidera usare il token di sicurezza tramite l'aggiunta di una condizione `SamlAudienceRestrictionCondition` al token di sicurezza. Ciò consente all'autenticatore `SamlSecurityTokenAuthenticator` del servizio Web di destinazione di verificare che il token di sicurezza emesso sia associato a questo servizio Web specificando che questo controllo deve essere svolto mediante l'esecuzione delle operazioni seguenti:  
  
- Impostare `audienceUriMode` l'attributo [ \<di issuedTokenAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) su `Always` o `BearerKeyOnly`.  
  
- Specificare il set di URI validi, aggiungendo gli URI a questa raccolta. A tale scopo, inserire [ \<un'aggiunta di elementi per](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md) ogni URITo do this, insert an add>for each URI  
  
 Per altre informazioni, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 Per ulteriori informazioni sull'utilizzo di questo elemento di configurazione, vedere [Procedura: configurare le credenziali in un servizio federativo](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
#### <a name="allowing-anonymous-cardspace-users"></a>Autenticazione degli utenti anonimi di CardSpace  
 Se si imposta in modo esplicito l'attributo `AllowUntrustedRsaIssuers` dell'elemento `<IssuedTokenAuthentication>` su `true`, qualsiasi client è in grado di presentare un token autocertificato firmato con una coppia di chiavi RSA arbitraria. L'autorità emittente non è *attendibile* perché alla chiave non sono associati dati dell'autorità emittente. Un utente CardSpace può creare una carta auto-emessa che include attestazioni di identità auto-fornite. Questa funzionalità deve essere utilizzata con cautela. Per utilizzare questa funzionalità, considerare la chiave RSA pubblica come una password dotata di un maggior livello di sicurezza da memorizzare in un database insieme a un nome utente. Prima di consentire a un client di accedere al servizio, verificare la chiave pubblica RSA presentata dal client confrontandola con la chiave pubblica memorizzata associata al nome utente presentato. Ciò presuppone l'implementazione di un processo di registrazione in base al quale un utente può registrare il proprio nome utente e associarlo alla chiave pubblica RSA autocertificata.  
  
## <a name="client-credentials"></a>Client Credentials  
 Le credenziali client sono usate per autenticare i client presso i servizi nei casi in cui non è richiesta l'autenticazione reciproca. È possibile utilizzare questa sezione per specificare i certificati di servizio negli scenari in cui il client deve utilizzare il certificato di un servizio per proteggere i messaggi inviati a quest'ultimo.  
  
 È inoltre possibile configurare un client come parte di uno scenario federato in modo che utilizzi i token emessi da un servizio token di sicurezza o da un'autorità emittente locale di token. Per ulteriori informazioni sugli scenari [federati, vedere Federazione e token rilasciati](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md). Tutte le credenziali client si trovano in [ \<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md), come illustrato nel codice seguente.  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="EndpointBehavior1">  
   <clientCredentials>  
    <clientCertificate findValue="cn=www.contoso.com"
        storeLocation="LocalMachine"  
        storeName="AuthRoot" x509FindType="FindBySubjectName" />  
    <serviceCertificate>  
     <defaultCertificate findValue="www.cohowinery.com"
                    storeLocation="LocalMachine"  
                    storeName="Root" x509FindType="FindByIssuerName" />  
    <authentication revocationMode="Online"  
                    trustedStoreLocation="LocalMachine" />  
    </serviceCertificate>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
</behaviors>  
```  
  
#### <a name="clientcertificate-element"></a>\<Elemento> clientCertificate  
 Questo elemento consente di impostare il certificato utilizzato per autenticare il client. Per ulteriori informazioni, vedere [Procedura: specificare](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)i valori delle credenziali client .  
  
#### <a name="httpdigest"></a>\<> httpDigest  
 Questa funzionalità deve essere abilitata con Active Directory in Windows e Internet Information Services (IIS). Per ulteriori informazioni, vedere [Autenticazione del digest in IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).  
  
#### <a name="issuedtoken-element"></a>\<elemento> issuedToken  
 Il [ \<>issuedToken](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) contiene gli elementi utilizzati per configurare un'autorità emittente locale di token o comportamenti utilizzati con un servizio token di sicurezza. Per istruzioni sulla configurazione di un client per l'utilizzo di un'autorità emittente locale, vedere [Procedura: Configurare un'autorità emittente locale](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
#### <a name="localissueraddress"></a>\<> localIssuerAddress  
 Specifica l'indirizzo predefinito di un servizio token di sicurezza. Viene utilizzato quando <xref:System.ServiceModel.WSFederationHttpBinding> l'oggetto non fornisce un URL per il servizio token di `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` sicurezza `null`o quando l'indirizzo dell'autorità emittente di un'associazione federata è o . In questi casi le credenziali <xref:System.ServiceModel.Description.ClientCredentials> devono essere configurate con l'indirizzo dell'autorità emittente locale e con l'associazione da utilizzare per comunicare con tale autorità emittente.  
  
#### <a name="issuerchannelbehaviors"></a>\<issuerChannelBehaviors>  
 Utilizzare il [ \<>issuerChannelBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md) per aggiungere i comportamenti client WCF utilizzati durante la comunicazione con un servizio token di sicurezza. Definire i comportamenti client nella sezione [ \<endpointBehaviors.Define](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) client behaviors in the endpointBehaviors>section. Per utilizzare un comportamento definito, aggiungere un <`add`> elemento all'elemento `<issuerChannelBehaviors>` con due attributi. Impostare l'indirizzo `issuerAddress` sull'URL del servizio token di sicurezza, quindi impostare l'attributo `behaviorConfiguration` sul nome del comportamento di endpoint definito, come mostrato nell'esempio seguente.  
  
```xml  
<clientCredentials>  
   <issuedToken>  
      <issuerChannelBehaviors>  
         <add issuerAddress="http://www.contoso.com"  
               behaviorConfiguration="clientBehavior1" />
      </issuerChannelBehaviors>  
   </issuedToken>  
</clientCredentials>
```  
  
#### <a name="servicecertificate-element"></a>\<Elemento> serviceCertificate  
 Utilizzare questo elemento per controllare l'autenticazione dei certificati di servizio.  
  
 L'elemento [ \<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) può archiviare un singolo certificato utilizzato quando il servizio non specifica alcun certificato.  
  
 Utilizzare [ \<l'ambitoCertificati>](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md) e [ \<aggiungere>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md) per impostare i certificati di servizio associati a servizi specifici. L'elemento `<add>` contiene l'attributo `targetUri` utilizzato per associare il certificato al servizio.  
  
 [ \<L'elemento>di autenticazione](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) specifica il livello di attendibilità utilizzato per autenticare i certificati. Per impostazione predefinita, il livello è impostato su "ChainTrust". Tale impostazione prevede che ogni certificato appartenga a una gerarchia di certificati che termina in un'autorità di certificazione attendibile situata all'inizio della catena. Si tratta della modalità più protetta. Il livello può inoltre essere impostato su "PeerOrChainTrust" per indicare che sia i certificati autocertificati (trust peer) che quelli appartenenti a una catena di trust sono ritenuti attendibili. Poiché i certificati autocertificati non devono essere acquistati da un'autorità attendibile, questo livello viene usato in fase di sviluppo e di debug dei client e dei servizi. Quando si distribuisce un client è invece opportuno utilizzare il livello "ChainTrust". Il livello può inoltre essere impostato su "Custom" o "None". Quando si imposta il livello "Custom" è necessario impostare anche l'attributo `CustomCertificateValidatorType` sull'assembly e sul tipo utilizzati per convalidare il certificato. Per creare un validator personalizzato è necessario ereditare una classe dalla classe astratta <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Per ulteriori informazioni, vedere [Procedura: creare un servizio che utilizza una convalida del certificato personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 L'elemento [ \<>di autenticazione](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) include un `RevocationMode` attributo che specifica come i certificati vengono controllati per la revoca. L'impostazione predefinita è "online" e indica che i certificati vengono contrassegnati automaticamente per la revoca. Per ulteriori informazioni, vedere [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="serviceauthorization"></a>ServiceAuthorization  
 L'elemento [ \<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) contiene elementi che influiscono sull'autorizzazione, sui provider di ruoli personalizzati e sulla rappresentazione.  
  
 La classe <xref:System.Security.Permissions.PrincipalPermissionAttribute> viene applicata a un metodo di servizio. Questo attributo specifica i gruppi di utenti da utilizzare quando si autorizza l'utilizzo di un metodo protetto. Il valore predefinito è "UseWindowsGroups" e specifica che la ricerca degli ID che tentano di accedere a una determinata risorsa viene eseguita nei gruppi di Windows, ad esempio "Administrators" o "Users". È inoltre possibile specificare "UseAspNetRoles" per utilizzare un `system.web` provider di ruoli personalizzato configurato nell'elemento > <, come illustrato nel codice seguente.  
  
```xml  
<system.web>  
  <membership defaultProvider="SqlProvider"
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add
          name="SqlProvider"
          type="System.Web.Security.SqlMembershipProvider"
          connectionStringName="SqlConn"  
          applicationName="MembershipProvider"  
          enablePasswordRetrieval="false"  
          enablePasswordReset="false"  
          requiresQuestionAndAnswer="false"  
          requiresUniqueEmail="true"  
          passwordFormat="Hashed" />  
     </providers>  
   </membership>  
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 Nell'esempio di codice seguente viene illustrato l'uso di un elemento `roleProviderName` con l'attributo `principalPermissionMode`.  
  
```xml  
<behaviors>  
 <behavior name="ServiceBehaviour">
  <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                        roleProviderName ="SqlProvider" />  
</behavior>
   <!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
## <a name="configuring-security-audits"></a>Configurazione dei controlli di sicurezza  
 Utilizzare il [ \<>serviceSecurityAudit](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) per specificare il log scritto e i tipi di eventi da registrare. Per ulteriori informazioni, vedere [Controllo](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
```xml  
<behaviors>
 <serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceSecurityAudit auditLogLocation="Application"
             suppressAuditFailure="true"  
             serviceAuthorizationAuditLevel="Success"
             messageAuthenticationAuditLevel="Success" />  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="secure-metadata-exchange"></a>Scambio protetto di metadati  
 L'esportazione e l'invio di metadati ai client risulta particolarmente utile per gli sviluppatori di servizi e client, in quanto consente il download di codice client e di configurazione. Per ridurre l'esposizione di un servizio agli utenti malintenzionati, questo trasferimento può essere protetto mediante il meccanismo HTTPS (ovvero SSL su HTTP). A tale scopo, è anzitutto necessario associare un certificato X.509 adatto a una porta specifica del computer che ospita il servizio. Per ulteriori informazioni, vedere [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). In secondo luogo, aggiungere un `HttpsGetEnabled` `true` [ \<>serviceMetadata](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) alla configurazione del servizio e impostare l'attributo su . Impostare infine l'attributo `HttpsGetUrl` sull'URL dell'endpoint dei metadati del servizio, come illustrato nell'esempio seguente.  
  
```xml  
<behaviors>  
 <serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceMetadata httpsGetEnabled="true"
     httpsGetUrl="https://myComputerName/myEndpoint" />  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Controllo](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
