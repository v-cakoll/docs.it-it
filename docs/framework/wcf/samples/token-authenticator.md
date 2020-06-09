---
title: Autenticatore token
ms.date: 03/30/2017
ms.assetid: 84382f2c-f6b1-4c32-82fa-aebc8f6064db
ms.openlocfilehash: f4b49edd3b5a2cecd203feed713c7694450f7497
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596552"
---
# <a name="token-authenticator"></a>Autenticatore token
In questo esempio viene illustrato come implementare un autenticatore di token personalizzato. Un autenticatore di token in Windows Communication Foundation (WCF) viene utilizzato per convalidare il token utilizzato con il messaggio, verificarne la coerenza e autenticare l'identità associata al token.

 Gli autenticatori di token personalizzati sono utili in molti casi, ad esempio:

- Quando si vuole eseguire l'override del meccanismo di autenticazione predefinito associato a un token.

- Quando si sta compilando un token personalizzato.

 Questo esempio illustra i seguenti elementi:

- Come un client può eseguire l'autenticazione utilizzando un nome utente e una password.

- Come il server può convalidare le credenziali client utilizzando un autenticatore di token personalizzato.

- Il modo in cui il codice del servizio WCF si collega con l'autenticatore del token personalizzato.

- Come può essere autenticato il servizio dal client mediante il certificato X.509 del server.

 Questo esempio mostra anche come l'identità del chiamante sia accessibile da WCF dopo il processo di autenticazione del token personalizzato.

 Il servizio espone un solo endpoint per comunicare con il servizio che viene definito mediante il file di configurazione App.config. L'endpoint è costituito da un indirizzo, un'associazione e un contratto. L'associazione viene configurata con una classe standard `wsHttpBinding`, con la modalità di sicurezza impostata sul messaggio, modalità predefinita di `wsHttpBinding`. In questo esempio viene impostata la classe `wsHttpBinding` standard per usare l'autenticazione del nome utente del client. Il servizio configura anche il certificato del servizio usando il comportamento `serviceCredentials`. Il comportamento `securityCredentials` consente di specificare un certificato del servizio. Un certificato del servizio viene usato da un client per autenticare il servizio e fornire protezione del messaggio. La configurazione seguente fa riferimento al certificato localhost installato durante l'installazione dell'esempio come descritto nelle istruzioni seguenti.

```xml
<system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- configure base address provided by host -->
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service" />
          </baseAddresses>
        </host>
        <!-- use base address provided by host -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
      </service>
    </services>

    <bindings>
      <wsHttpBinding>
        <binding name="Binding1">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceDebug includeExceptionDetailInFaults="False" />
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
....        -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>
```

 La configurazione dell'endpoint client è costituita da un nome di configurazione, un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto. L'associazione client viene configurata con la `Mode` e la `clientCredentialType` appropriate.

```xml
<system.serviceModel>
    <client>
      <endpoint name=""
                address="http://localhost:8000/servicemodelsamples/service"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <binding name="Binding1">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
```

 L'implementazione del client imposta il nome utente e la password da usare.

```csharp
static void Main()
{
     ...
     client.ClientCredentials.UserNamePassword.UserName = username;
     client.ClientCredentials.UserNamePassword.Password = password;
     ...
}
```

## <a name="custom-token-authenticator"></a>Autenticatore di token personalizzato
 Utilizzare i passaggi seguenti per creare un autenticatore di token personalizzato:

1. Creare un autenticatore di token personalizzato

     L'esempio implementa un autenticatore di token personalizzato che verifica che il nome utente abbia un formato di posta elettronica valido. Deriva la classe <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>. Il metodo più importante di questa classe è <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>. In questo metodo, l'autenticatore convalida il formato del nome utente e verifica anche che il nome host non provenga da un dominio sospetto. Se entrambe le condizioni sono soddisfatte, restituisce una raccolta di sola lettura delle istanze della classe <xref:System.IdentityModel.Policy.IAuthorizationPolicy> che viene quindi utilizzata per fornire attestazioni che rappresentano le informazioni archiviate nel token del nome utente.

    ```csharp
    protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateUserNamePasswordCore(string userName, string password)
    {
        if (!ValidateUserNameFormat(userName))
            throw new SecurityTokenValidationException("Incorrect UserName format");

        ClaimSet claimSet = new DefaultClaimSet(ClaimSet.System, new Claim(ClaimTypes.Name, userName, Rights.PossessProperty));
        List<IIdentity> identities = new List<IIdentity>(1);
        identities.Add(new GenericIdentity(userName));
        List<IAuthorizationPolicy> policies = new List<IAuthorizationPolicy>(1);
        policies.Add(new UnconditionalPolicy(ClaimSet.System, claimSet, DateTime.MaxValue.ToUniversalTime(), identities));
        return policies.AsReadOnly();
    }
    ```

2. Fornisce i criteri di autorizzazione restituiti dall'autenticatore di token personalizzato.

     Questo esempio fornisce un'implementazione di <xref:System.IdentityModel.Policy.IAuthorizationPolicy> chiamata `UnconditionalPolicy` che restituisce set di attestazioni e identità passati a esso nel costruttore.

    ```csharp
    class UnconditionalPolicy : IAuthorizationPolicy
    {
        String id = Guid.NewGuid().ToString();
        ClaimSet issuer;
        ClaimSet issuance;
        DateTime expirationTime;
        IList<IIdentity> identities;

        public UnconditionalPolicy(ClaimSet issuer, ClaimSet issuance, DateTime expirationTime, IList<IIdentity> identities)
        {
            if (issuer == null)
                throw new ArgumentNullException("issuer");
            if (issuance == null)
                throw new ArgumentNullException("issuance");

            this.issuer = issuer;
            this.issuance = issuance;
            this.identities = identities;
            this.expirationTime = expirationTime;
        }

        public string Id
        {
            get { return this.id; }
        }

        public ClaimSet Issuer
        {
            get { return this.issuer; }
        }

        public DateTime ExpirationTime
        {
            get { return this.expirationTime; }
        }

        public bool Evaluate(EvaluationContext evaluationContext, ref object state)
        {
            evaluationContext.AddToTarget(this, this.issuance);

            if (this.identities != null)
            {
                object value;
                IList<IIdentity> contextIdentities;
                if (!evaluationContext.Properties.TryGetValue("Identities", out value))
                {
                    contextIdentities = new List<IIdentity>(this.identities.Count);
                    evaluationContext.Properties.Add("Identities", contextIdentities);
                }
                else
                {
                    contextIdentities = value as IList<IIdentity>;
                }
                foreach (IIdentity identity in this.identities)
                {
                    contextIdentities.Add(identity);
                }
            }

            evaluationContext.RecordExpirationTime(this.expirationTime);
            return true;
        }
    }
    ```

3. Scrivere un gestore di token di sicurezza personalizzato.

     La classe <xref:System.IdentityModel.Selectors.SecurityTokenManager> viene utilizzata per creare una classe <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> per oggetti specifici della classe <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> che vengono passati nel metodo `CreateSecurityTokenAuthenticator`. Viene inoltre utilizzato il gestore del token di sicurezza per creare provider di token e serializzatori di token, che però non sono trattati in questo esempio. In questo esempio, il gestore del token di sicurezza personalizzato eredita dalla classe <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> ed esegue l'override del metodo `CreateSecurityTokenAuthenticator` per restituire un autenticatore di token nome utente personalizzato quando i requisiti del token passati indicano che l'autenticatore nome utente è necessario.

    ```csharp
    public class MySecurityTokenManager : ServiceCredentialsSecurityTokenManager
    {
        MyUserNameCredential myUserNameCredential;

        public MySecurityTokenManager(MyUserNameCredential myUserNameCredential)
            : base(myUserNameCredential)
        {
            this.myUserNameCredential = myUserNameCredential;
        }

        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)
        {
            if (tokenRequirement.TokenType ==  SecurityTokenTypes.UserName)
            {
                outOfBandTokenResolver = null;
                return new MyTokenAuthenticator();
            }
            else
            {
                return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);
            }
        }
    }
    ```

4. Scrivere una credenziale del servizio personalizzata

     La classe delle credenziali del servizio viene utilizzata per rappresentare le credenziali configurate per il servizio e crea un gestore del token di sicurezza utilizzato per ottenere gli autenticatori del token, i provider di token e i serializzatori di token.

    ```csharp
    public class MyUserNameCredential : ServiceCredentials
    {

        public MyUserNameCredential()
            : base()
        {
        }

        protected override ServiceCredentials CloneCore()
        {
            return new MyUserNameCredential();
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new MySecurityTokenManager(this);
        }

    }
    ```

5. Configurare il servizio per l'utilizzo della credenziale del servizio personalizzata.

     Affinché il servizio utilizzi la credenziale del servizio personalizzata, si elimina la classe della credenziale di servizio predefinita dopo avere acquisito il certificato del servizio già preconfigurato nella credenziale del servizio predefinita, si configura la nuova istanza della credenziale del servizio per utilizzare i certificati del servizio preconfigurati e si aggiunge questa nuova istanza della credenziale del servizio nuova ai comportamenti del servizio.

    ```csharp
    ServiceCredentials sc = serviceHost.Credentials;
    X509Certificate2 cert = sc.ServiceCertificate.Certificate;
    MyUserNameCredential serviceCredential = new MyUserNameCredential();
    serviceCredential.ServiceCertificate.Certificate = cert;
    serviceHost.Description.Behaviors.Remove((typeof(ServiceCredentials)));
    serviceHost.Description.Behaviors.Add(serviceCredential);
    ```

 Per visualizzare le informazioni sul chiamante è possibile utilizzare <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> come mostra il codice seguente. La classe <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contiene informazioni sulle attestazioni circa il chiamante corrente.

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
            ServiceSecurityContext.Current.PrimaryIdentity.Name);
     return;
}
```

 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.

## <a name="setup-batch-file"></a>File batch di installazione
 Il file batch Setup.bat incluso con questo esempio consente di configurare il server con i certificati attinenti per eseguire un'applicazione indipendente che richiede la sicurezza server basata su certificato. Questo file batch deve essere modificato per funzionare tra computer diversi o nel caso in cui non sia ospitato.

 Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.

- Creazione del certificato server.

     Le righe seguenti del file batch Setup.bat creano il certificato server da usare. La variabile `%SERVER_NAME%` specifica il nome del server. Modificare questa variabile per specificare nome del server. Il valore predefinito in questo file batch è localhost.

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Installazione del certificato server nell'archivio certificati attendibili del client

     Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client. Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client. Se è già disponibile un certificato con radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio del popolamento dell'archivio certificati client con il certificato server non è necessario.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > Il file batch di configurazione è progettato per essere eseguito da un prompt dei comandi di Windows SDK. e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK. Questa variabile di ambiente viene impostata automaticamente all'interno di un prompt dei comandi di SDK di Windows.

#### <a name="to-set-up-and-build-the-sample"></a>Per impostare e compilare l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).

#### <a name="to-run-the-sample-on-the-same-computer"></a>Per eseguire l'esempio nello stesso computer

1. Eseguire Setup. bat dalla cartella di installazione dell'esempio all'interno di un prompt dei comandi di Visual Studio 2012 aperto con privilegi di amministratore. In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.

    > [!NOTE]
    > Il file batch Setup. bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2012. La variabile di ambiente PATH impostata nel prompt dei comandi di Visual Studio 2012 punta alla directory che contiene i file eseguibili richiesti dallo script Setup. bat.  
  
2. Avviare service.exe da service\bin.  
  
3. Avviare client.exe da \client\bin. L'attività del client viene visualizzata nella finestra dell'applicazione console.  
  
4. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer  
  
1. Creare una directory sul computer del servizio per i file binari del servizio.  
  
2. Copiare i file di programma del servizio nella directory del servizio sul computer relativo. Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.  
  
3. È necessario disporre di un certificato server con il nome del soggetto che contiene il nome di dominio completo del computer. Il file service.App.config deve essere aggiornato per riflettere il nome del nuovo certificato. È possibile crearne uno utilizzando Setup.bat se si imposta la variabile `%SERVER_NAME%` sul nome host completo del computer sul quale il servizio sarà eseguito. Si noti che il file Setup. bat deve essere eseguito da un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.  
  
4. Copiare il certificato server nell'archivio CurrentUser-TrustedPeople del client. Questo passaggio è necessario solo quando il certificato server è emesso da un'autorità emittente client attendibile.  
  
5. Nel file App.exe.config sul computer del servizio modificare il valore dell'indirizzo di base per specificare un nome del computer completo anziché localhost.  
  
6. Sul computer del servizio eseguire service.exe da un prompt dei comandi.  
  
7. Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.  
  
8. Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.  
  
9. Sul computer client avviare Client.exe da un prompt dei comandi.  
  
10. Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
1. Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.  
