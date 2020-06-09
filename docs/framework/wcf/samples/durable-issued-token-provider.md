---
title: Provider di token rilasciati in modo durevole
ms.date: 03/30/2017
ms.assetid: 76fb27f5-8787-4b6a-bf4c-99b4be1d2e8b
ms.openlocfilehash: fed5f44e6cc40cfe2ca963077b6371c14b3b086a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600561"
---
# <a name="durable-issued-token-provider"></a>Provider di token rilasciati in modo durevole
Questo esempio illustra come implementare un provider di token rilasciato del client personalizzato.  
  
## <a name="discussion"></a>Discussione  
 Un provider di token in Windows Communication Foundation (WCF) viene utilizzato per fornire le credenziali all'infrastruttura di sicurezza. In generale, il provider di token esamina la destinazione ed emette credenziali adatte in modo che l'infrastruttura di sicurezza possa proteggere il messaggio. WCF viene fornito con un provider di token CardSpace. I provider di token personalizzati sono utili nei casi seguenti:  
  
- Se è disponibile un archivio di credenziali con cui il provider di token incluso non è in grado di operare.  
  
- Se si desidera fornire un meccanismo personalizzato per la trasformazione delle credenziali dal punto in cui l'utente fornisce i dettagli su quando il client WCF usa le credenziali.  
  
- Se si sta compilando un token personalizzato.  
  
 Questo esempio illustra come compilare un provider di token personalizzato che memorizza nella cache token rilasciati da un servizio token di sicurezza (STS, Security Token Service).  
  
 Per riassumere, questo esempio dimostra quanto segue.  
  
- Come è possibile configurare un client con un provider personalizzato.  
  
- Come i token rilasciati possono essere memorizzati nella cache e forniti al client WCF.  
  
- Come viene autenticato il servizio dal client mediante il certificato X.509 del server.  
  
 L'esempio è costituito da un programma console del client (Client.exe), da un programma console del servizio token di sicurezza (Securitytokenservice.exe) e da un programma console del servizio (Service.exe). Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta. Il contratto è definito dall'interfaccia `ICalculator` che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione). Il client riceve un token di sicurezza dal servizio token di sicurezza (STS), esegue richieste sincrone al servizio per un'operazione matematica specificata e il servizio risponde fornendo il risultato. L'attività del client è visibile nella finestra della console.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Questo esempio espone il contratto ICalculator usando [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) . La configurazione di quest'associazione sul client viene illustrata nel codice seguente.  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuer address="http://localhost:8000/sts/windows"
                  binding="wsHttpBinding" />
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 Nell'elemento `security` di `wsFederationHttpBinding`, il valore `mode` configura quale modalità di sicurezza deve essere utilizzata. In questo esempio viene utilizzata la sicurezza dei messaggi; per tale motivo, l'elemento `message` di `wsFederationHttpBinding` viene specificato all'interno dell'elemento `security` di `wsFederationHttpBinding`. L'elemento `issuer` di `wsFederationHttpBinding` all'interno dell'elemento `message` di `wsFederationHttpBinding` specifica l'indirizzo e l'associazione per il servizio token di sicurezza che rilascia un token di sicurezza al client, in modo che quest'ultimo possa autenticarsi presso il servizio di calcolatrice.  
  
 La configurazione di quest'associazione sul servizio viene illustrata nel seguente codice.  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuerMetadata address="http://localhost:8000/sts/mex">
            <identity>
              <certificateReference storeLocation="CurrentUser"
                                    storeName="TrustedPeople"
                                    x509FindType="FindBySubjectDistinguishedName"
                                    findValue="CN=STS" />
            </identity>
          </issuerMetadata>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 Nell'elemento `security` di `wsFederationHttpBinding`, il valore `mode` configura quale modalità di sicurezza deve essere utilizzata. In questo esempio viene utilizzata la sicurezza dei messaggi; per tale motivo, l'elemento `message` di `wsFederationHttpBinding` viene specificato all'interno dell'elemento `security` di `wsFederationHttpBinding`. L'elemento `issuerMetadata` di `wsFederationHttpBinding` all'interno dell'elemento `message` di `wsFederationHttpBinding` specifica l'indirizzo e l'identità di un endpoint che può essere utilizzato per recuperare metadati per il servizio token di sicurezza.  
  
 Il comportamento per il servizio viene illustrato nel codice seguente.  
  
```xml  
<behavior name="ServiceBehavior">
  <serviceDebug includeExceptionDetailInFaults="true" />
  <serviceMetadata httpGetEnabled="true" />
  <serviceCredentials>
    <issuedTokenAuthentication>
      <knownCertificates>
        <add storeLocation="LocalMachine"
              storeName="TrustedPeople"
              x509FindType="FindBySubjectDistinguishedName"
              findValue="CN=STS" />
      </knownCertificates>
    </issuedTokenAuthentication>
    <serviceCertificate storeLocation="LocalMachine"
                        storeName="My"
                        x509FindType="FindBySubjectDistinguishedName"
                        findValue="CN=localhost" />
  </serviceCredentials>
</behavior>  
```  
  
 L'elemento `issuedTokenAuthentication` all'interno dell'elemento `serviceCredentials` consente al servizio di specificare i vincoli nei token che i client possono presentare durante l'autenticazione. Questa configurazione specifica che i token firmati da un certificato il cui Nome soggetto è CN=STS possono essere accettati dal servizio.  
  
 Il servizio token di sicurezza espone un solo endpoint utilizzando l'elemento wsHttpBinding standard. Il servizio token di sicurezza risponde alle richieste di token dei client e, se il client si autentica utilizzando un account di Windows, emette un token che contiene il nome utente del client come attestazione nel token emesso. Come parte del processo di creazione del token, il servizio token di protezione firma il token utilizzando la chiave privata associata al certificato CN=STS . Crea, inoltre, una chiave simmetrica e la crittografa utilizzando la chiave pubblica associata al certificato CN=localhost. Nel restituire il token al client, il servizio token di protezione restituisce anche la chiave simmetrica. Il client presenta il token emesso al servizio di calcolatrice e dimostra che conosce la chiave simmetrica firmando il messaggio con quella chiave.  
  
## <a name="custom-client-credentials-and-token-provider"></a>Credenziali client e servizio token di protezione personalizzati  
 Nei passaggi seguenti viene illustrato come sviluppare un provider di token personalizzato che memorizza nella cache i token rilasciati e li integra con WCF: Security.  
  
### <a name="to-develop-a-custom-token-provider"></a>Per sviluppare un provider di token personalizzato  
  
1. Scrivere un provider di token personalizzati.  
  
     L'esempio implementa un provider di token personalizzato che restituisce un token di sicurezza recuperato da una cache.  
  
     Per eseguire questa attività il provider di token personalizzato deriva dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenProvider> ed esegue l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>. Questo metodo tenta di ottenere un token dalla cache o, se non è possibile trovare un token nella cache, recupera un token dal provider sottostante e quindi lo memorizza nella cache. In entrambi i casi, il metodo restituisce `SecurityToken`.  
  
    ```csharp  
    protected override SecurityToken GetTokenCore(TimeSpan timeout)  
    {  
      GenericXmlSecurityToken token;  
      if (!this.cache.TryGetToken(target, issuer, out token))  
      {  
        token = (GenericXmlSecurityToken) this.innerTokenProvider.GetToken(timeout);  
        this.cache.AddToken(token, target, issuer);  
      }  
      return token;  
    }  
    ```  
  
2. Scrivere il gestore di token di sicurezza personalizzato.  
  
     La classe <xref:System.IdentityModel.Selectors.SecurityTokenManager> viene utilizzata per creare un <xref:System.IdentityModel.Selectors.SecurityTokenProvider> per un <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> specifico che viene passato nel metodo `CreateSecurityTokenProvider`. Viene inoltre utilizzato un gestore del token di sicurezza per creare autenticatori del token e serializzatori del token, che però non vengono presi in esame in questo esempio. Nell'esempio, il gestore del token di sicurezza eredita dalla classe <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> ed esegue l'override del metodo `CreateSecurityTokenProvider` per restituire il provider di token personalizzato quando i requisiti del token passati indicano che viene richiesto un token emesso.  
  
    ```csharp
    class DurableIssuedTokenClientCredentialsTokenManager :  
     ClientCredentialsSecurityTokenManager  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentialsTokenManager ( DurableIssuedTokenClientCredentials creds ): base(creds)  
      {  
        this.cache = creds.IssuedTokenCache;  
      }  
  
      public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )  
      {  
        if (IsIssuedSecurityTokenRequirement(tokenRequirement))  
        {  
          return new DurableIssuedSecurityTokenProvider ((IssuedSecurityTokenProvider)base.CreateSecurityTokenProvider( tokenRequirement), this.cache);  
        }  
        else
        {  
          return base.CreateSecurityTokenProvider(tokenRequirement);  
        }  
      }  
    }  
    ```  
  
3. Scrivere una credenziale client personalizzata.  
  
     La classe delle credenziali di un client viene utilizzata per rappresentare le credenziali configurate per il proxy client e crea il gestore del token di protezione utilizzato per ottenere gli autenticatori del token, i provider di token e i serializzatori di token.  
  
    ```csharp
    public class DurableIssuedTokenClientCredentials : ClientCredentials  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentials() : base()  
      {  
      }  
  
      DurableIssuedTokenClientCredentials ( DurableIssuedTokenClientCredentials other) : base(other)  
      {  
        this.cache = other.cache;  
      }  
  
      public IssuedTokenCache IssuedTokenCache  
      {  
        get  
        {  
          return this.cache;  
        }  
        set  
        {  
          this.cache = value;  
        }  
      }  
  
      protected override ClientCredentials CloneCore()  
      {  
        return new DurableIssuedTokenClientCredentials(this);  
      }  
  
      public override SecurityTokenManager CreateSecurityTokenManager()  
      {  
        return new DurableIssuedTokenClientCredentialsTokenManager ((DurableIssuedTokenClientCredentials)this.Clone());  
      }  
    }  
    ```  
  
4. Implementare la cache del token. L'implementazione di esempio utilizza una classe di base astratta tramite la quale utenti di una cache del token specificata interagiscono con la cache.  
  
    ```csharp
    public abstract class IssuedTokenCache  
    {  
      public abstract void AddToken ( GenericXmlSecurityToken token, EndpointAddress target, EndpointAddress issuer);  
      public abstract bool TryGetToken(EndpointAddress target, EndpointAddress issuer, out GenericXmlSecurityToken cachedToken);  
    }  
    // Configure the client to use the custom client credential.  
    ```  
  
     L'esempio elimina la classe della credenziale client predefinita e fornisce la nuova classe della credenziale client affinché il client possa utilizzare la credenziale client personalizzata.  
  
    ```csharp
    clientFactory.Endpoint.Behaviors.Remove<ClientCredentials>();  
    DurableIssuedTokenClientCredentials durableCreds = new DurableIssuedTokenClientCredentials();  
    durableCreds.IssuedTokenCache = cache;  
    durableCreds.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
    clientFactory.Endpoint.Behaviors.Add(durableCreds);  
    ```  
  
## <a name="running-the-sample"></a>Esecuzione dell'esempio  
 Per eseguire l'esempio seguire le istruzioni riportate qui. Quando si esegue l'esempio, la richiesta per il token di protezione viene visualizzata nella finestra della console del servizio token di protezione. Le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console del client e del servizio. Premere INVIO in una delle finestre della console per arrestare l'applicazione.  
  
## <a name="the-setupcmd-batch-file"></a>File batch Setup.cmd  
 Il file batch Setup.cmd incluso con questo esempio consente di configurare il server e il servizio token di sicurezza con i certificati attinenti per eseguire un'applicazione indipendente. Il file batch crea due certificati, entrambi nell'archivio certificati di CurrentUser/TrustedPeople. Il primo certificato ha un nome soggetto di CN=STS e viene utilizzato dal servizio token di protezione per firmare i token di protezione emessi al client. Il secondo certificato ha un nome soggetto di CN=localhost e viene utilizzato dal servizio token di sicurezza per crittografare un segreto in modo che il servizio non possa decrittografarlo.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Eseguire il file Setup.cmd per creare i certificati richiesti.  
  
2. Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md). Assicurarsi che tutti i progetti nella soluzione siano stati generati  (Shared, RSTRSTR, Service, SecurityTokenService e Client).  
  
3. Assicurarsi che Service.exe e SecurityTokenService.exe siano entrambi in esecuzione con privilegi di amministratore.  
  
4. Eseguire Client.exe.  
  
### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
1. Eseguire Cleanup.cmd nella cartella degli esempi una volta completato l'esempio.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\DurableIssuedTokenProvider`  
