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
# <a name="token-authenticator"></a><span data-ttu-id="28d11-102">Autenticatore token</span><span class="sxs-lookup"><span data-stu-id="28d11-102">Token Authenticator</span></span>
<span data-ttu-id="28d11-103">In questo esempio viene illustrato come implementare un autenticatore di token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28d11-103">This sample demonstrates how to implement a custom token authenticator.</span></span> <span data-ttu-id="28d11-104">Un autenticatore di token in Windows Communication Foundation (WCF) viene utilizzato per convalidare il token utilizzato con il messaggio, verificarne la coerenza e autenticare l'identità associata al token.</span><span class="sxs-lookup"><span data-stu-id="28d11-104">A token authenticator in Windows Communication Foundation (WCF) is used for validating the token used with the message, verifying that it is self-consistent, and authenticating the identity associated with the token.</span></span>

 <span data-ttu-id="28d11-105">Gli autenticatori di token personalizzati sono utili in molti casi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="28d11-105">Custom token authenticators are useful in a variety of cases, such as:</span></span>

- <span data-ttu-id="28d11-106">Quando si vuole eseguire l'override del meccanismo di autenticazione predefinito associato a un token.</span><span class="sxs-lookup"><span data-stu-id="28d11-106">When you want to override the default authentication mechanism associated with a token.</span></span>

- <span data-ttu-id="28d11-107">Quando si sta compilando un token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28d11-107">When you are building a custom token.</span></span>

 <span data-ttu-id="28d11-108">Questo esempio illustra i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="28d11-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="28d11-109">Come un client può eseguire l'autenticazione utilizzando un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="28d11-109">How a client can authenticate using a username/password pair.</span></span>

- <span data-ttu-id="28d11-110">Come il server può convalidare le credenziali client utilizzando un autenticatore di token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28d11-110">How the server can validate the client credentials using a custom token authenticator.</span></span>

- <span data-ttu-id="28d11-111">Il modo in cui il codice del servizio WCF si collega con l'autenticatore del token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28d11-111">How the WCF service code ties in with the custom token authenticator.</span></span>

- <span data-ttu-id="28d11-112">Come può essere autenticato il servizio dal client mediante il certificato X.509 del server.</span><span class="sxs-lookup"><span data-stu-id="28d11-112">How the server can be authenticated using the server's X.509 certificate.</span></span>

 <span data-ttu-id="28d11-113">Questo esempio mostra anche come l'identità del chiamante sia accessibile da WCF dopo il processo di autenticazione del token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28d11-113">This sample also shows how the caller's identity is accessible from WCF after the custom token authentication process.</span></span>

 <span data-ttu-id="28d11-114">Il servizio espone un solo endpoint per comunicare con il servizio che viene definito mediante il file di configurazione App.config.</span><span class="sxs-lookup"><span data-stu-id="28d11-114">The service exposes a single endpoint for communicating with the service, defined using the App.config configuration file.</span></span> <span data-ttu-id="28d11-115">L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="28d11-115">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="28d11-116">L'associazione viene configurata con una classe standard `wsHttpBinding`, con la modalità di sicurezza impostata sul messaggio, modalità predefinita di `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="28d11-116">The binding is configured with a standard `wsHttpBinding`, with the security mode set to message - the default mode of the `wsHttpBinding`.</span></span> <span data-ttu-id="28d11-117">In questo esempio viene impostata la classe `wsHttpBinding` standard per usare l'autenticazione del nome utente del client.</span><span class="sxs-lookup"><span data-stu-id="28d11-117">This sample sets the standard `wsHttpBinding` to use client username authentication.</span></span> <span data-ttu-id="28d11-118">Il servizio configura anche il certificato del servizio usando il comportamento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="28d11-118">The service also configures the service certificate using `serviceCredentials` behavior.</span></span> <span data-ttu-id="28d11-119">Il comportamento `securityCredentials` consente di specificare un certificato del servizio.</span><span class="sxs-lookup"><span data-stu-id="28d11-119">The `securityCredentials` behavior allows you to specify a service certificate.</span></span> <span data-ttu-id="28d11-120">Un certificato del servizio viene usato da un client per autenticare il servizio e fornire protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="28d11-120">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="28d11-121">La configurazione seguente fa riferimento al certificato localhost installato durante l'installazione dell'esempio come descritto nelle istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="28d11-121">The following configuration references the localhost certificate installed during the sample setup as described in the following setup instructions.</span></span>

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

 <span data-ttu-id="28d11-122">La configurazione dell'endpoint client è costituita da un nome di configurazione, un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto.</span><span class="sxs-lookup"><span data-stu-id="28d11-122">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="28d11-123">L'associazione client viene configurata con la `Mode` e la `clientCredentialType` appropriate.</span><span class="sxs-lookup"><span data-stu-id="28d11-123">The client binding is configured with the appropriate `Mode` and `clientCredentialType`.</span></span>

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

 <span data-ttu-id="28d11-124">L'implementazione del client imposta il nome utente e la password da usare.</span><span class="sxs-lookup"><span data-stu-id="28d11-124">The client implementation sets the user name and password to use.</span></span>

```csharp
static void Main()
{
     ...
     client.ClientCredentials.UserNamePassword.UserName = username;
     client.ClientCredentials.UserNamePassword.Password = password;
     ...
}
```

## <a name="custom-token-authenticator"></a><span data-ttu-id="28d11-125">Autenticatore di token personalizzato</span><span class="sxs-lookup"><span data-stu-id="28d11-125">Custom Token Authenticator</span></span>
 <span data-ttu-id="28d11-126">Utilizzare i passaggi seguenti per creare un autenticatore di token personalizzato:</span><span class="sxs-lookup"><span data-stu-id="28d11-126">Use the following steps to create a custom token authenticator:</span></span>

1. <span data-ttu-id="28d11-127">Creare un autenticatore di token personalizzato</span><span class="sxs-lookup"><span data-stu-id="28d11-127">Write a custom token authenticator.</span></span>

     <span data-ttu-id="28d11-128">L'esempio implementa un autenticatore di token personalizzato che verifica che il nome utente abbia un formato di posta elettronica valido.</span><span class="sxs-lookup"><span data-stu-id="28d11-128">The sample implements a custom token authenticator that validates that the username has a valid email format.</span></span> <span data-ttu-id="28d11-129">Deriva la classe <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="28d11-129">It derives the <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>.</span></span> <span data-ttu-id="28d11-130">Il metodo più importante di questa classe è <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="28d11-130">The most important method in this class is <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>.</span></span> <span data-ttu-id="28d11-131">In questo metodo, l'autenticatore convalida il formato del nome utente e verifica anche che il nome host non provenga da un dominio sospetto.</span><span class="sxs-lookup"><span data-stu-id="28d11-131">In this method, the authenticator validates the format of the username and also that the host name is not from a rogue domain.</span></span> <span data-ttu-id="28d11-132">Se entrambe le condizioni sono soddisfatte, restituisce una raccolta di sola lettura delle istanze della classe <xref:System.IdentityModel.Policy.IAuthorizationPolicy> che viene quindi utilizzata per fornire attestazioni che rappresentano le informazioni archiviate nel token del nome utente.</span><span class="sxs-lookup"><span data-stu-id="28d11-132">If both conditions are met, then it returns a read-only collection of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> instances that is then used to provide claims that represent the information stored inside the username token.</span></span>

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

2. <span data-ttu-id="28d11-133">Fornisce i criteri di autorizzazione restituiti dall'autenticatore di token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28d11-133">Provide an authorization policy that is returned by custom token authenticator.</span></span>

     <span data-ttu-id="28d11-134">Questo esempio fornisce un'implementazione di <xref:System.IdentityModel.Policy.IAuthorizationPolicy> chiamata `UnconditionalPolicy` che restituisce set di attestazioni e identità passati a esso nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="28d11-134">This sample provides its own implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> called `UnconditionalPolicy` that returns set of claims and identities that were passed to it in its constructor.</span></span>

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

3. <span data-ttu-id="28d11-135">Scrivere un gestore di token di sicurezza personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28d11-135">Write a custom security token manager.</span></span>

     <span data-ttu-id="28d11-136">La classe <xref:System.IdentityModel.Selectors.SecurityTokenManager> viene utilizzata per creare una classe <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> per oggetti specifici della classe <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> che vengono passati nel metodo `CreateSecurityTokenAuthenticator`.</span><span class="sxs-lookup"><span data-stu-id="28d11-136">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create a <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> objects that are passed to it in the `CreateSecurityTokenAuthenticator` method.</span></span> <span data-ttu-id="28d11-137">Viene inoltre utilizzato il gestore del token di sicurezza per creare provider di token e serializzatori di token, che però non sono trattati in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="28d11-137">The security token manager is also used to create token providers and token serializers, but those are not covered by this sample.</span></span> <span data-ttu-id="28d11-138">In questo esempio, il gestore del token di sicurezza personalizzato eredita dalla classe <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> ed esegue l'override del metodo `CreateSecurityTokenAuthenticator` per restituire un autenticatore di token nome utente personalizzato quando i requisiti del token passati indicano che l'autenticatore nome utente è necessario.</span><span class="sxs-lookup"><span data-stu-id="28d11-138">In this sample, the custom security token manager inherits from <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenAuthenticator` method to return custom username token authenticator when the passed token requirements indicate that username authenticator is requested.</span></span>

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

4. <span data-ttu-id="28d11-139">Scrivere una credenziale del servizio personalizzata</span><span class="sxs-lookup"><span data-stu-id="28d11-139">Write a custom service credential.</span></span>

     <span data-ttu-id="28d11-140">La classe delle credenziali del servizio viene utilizzata per rappresentare le credenziali configurate per il servizio e crea un gestore del token di sicurezza utilizzato per ottenere gli autenticatori del token, i provider di token e i serializzatori di token.</span><span class="sxs-lookup"><span data-stu-id="28d11-140">The service credentials class is used to represent the credentials that are configured for the service and creates a security token manager that is used to obtain token authenticators, token providers and token serializers.</span></span>

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

5. <span data-ttu-id="28d11-141">Configurare il servizio per l'utilizzo della credenziale del servizio personalizzata.</span><span class="sxs-lookup"><span data-stu-id="28d11-141">Configure the service to use the custom service credential.</span></span>

     <span data-ttu-id="28d11-142">Affinché il servizio utilizzi la credenziale del servizio personalizzata, si elimina la classe della credenziale di servizio predefinita dopo avere acquisito il certificato del servizio già preconfigurato nella credenziale del servizio predefinita, si configura la nuova istanza della credenziale del servizio per utilizzare i certificati del servizio preconfigurati e si aggiunge questa nuova istanza della credenziale del servizio nuova ai comportamenti del servizio.</span><span class="sxs-lookup"><span data-stu-id="28d11-142">In order for the service to use the custom service credential, we delete the default service credential class after capturing the service certificate that is already preconfigured in the default service credential, and configure the new service credential instance to use the preconfigured service certificates and add this new service credential instance to service behaviors.</span></span>

    ```csharp
    ServiceCredentials sc = serviceHost.Credentials;
    X509Certificate2 cert = sc.ServiceCertificate.Certificate;
    MyUserNameCredential serviceCredential = new MyUserNameCredential();
    serviceCredential.ServiceCertificate.Certificate = cert;
    serviceHost.Description.Behaviors.Remove((typeof(ServiceCredentials)));
    serviceHost.Description.Behaviors.Add(serviceCredential);
    ```

 <span data-ttu-id="28d11-143">Per visualizzare le informazioni sul chiamante è possibile utilizzare <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> come mostra il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="28d11-143">To display the caller's information, you can use the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> as shown in the following code.</span></span> <span data-ttu-id="28d11-144">La classe <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contiene informazioni sulle attestazioni circa il chiamante corrente.</span><span class="sxs-lookup"><span data-stu-id="28d11-144">The <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contains claims information about the current caller.</span></span>

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
            ServiceSecurityContext.Current.PrimaryIdentity.Name);
     return;
}
```

 <span data-ttu-id="28d11-145">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="28d11-145">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="28d11-146">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="28d11-146">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="28d11-147">File batch di installazione</span><span class="sxs-lookup"><span data-stu-id="28d11-147">Setup Batch File</span></span>
 <span data-ttu-id="28d11-148">Il file batch Setup.bat incluso con questo esempio consente di configurare il server con i certificati attinenti per eseguire un'applicazione indipendente che richiede la sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="28d11-148">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate based security.</span></span> <span data-ttu-id="28d11-149">Questo file batch deve essere modificato per funzionare tra computer diversi o nel caso in cui non sia ospitato.</span><span class="sxs-lookup"><span data-stu-id="28d11-149">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="28d11-150">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="28d11-150">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration.</span></span>

- <span data-ttu-id="28d11-151">Creazione del certificato server.</span><span class="sxs-lookup"><span data-stu-id="28d11-151">Creating the server certificate.</span></span>

     <span data-ttu-id="28d11-152">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="28d11-152">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="28d11-153">La variabile `%SERVER_NAME%` specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="28d11-153">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="28d11-154">Modificare questa variabile per specificare nome del server.</span><span class="sxs-lookup"><span data-stu-id="28d11-154">Change this variable to specify your own server name.</span></span> <span data-ttu-id="28d11-155">Il valore predefinito in questo file batch è localhost.</span><span class="sxs-lookup"><span data-stu-id="28d11-155">The default in this batch file is localhost.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="28d11-156">Installazione del certificato server nell'archivio certificati attendibili del client</span><span class="sxs-lookup"><span data-stu-id="28d11-156">Installing the server certificate into client's trusted certificate store.</span></span>

     <span data-ttu-id="28d11-157">Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client.</span><span class="sxs-lookup"><span data-stu-id="28d11-157">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="28d11-158">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="28d11-158">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="28d11-159">Se è già disponibile un certificato con radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio del popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="28d11-159">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > <span data-ttu-id="28d11-160">Il file batch di configurazione è progettato per essere eseguito da un prompt dei comandi di Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="28d11-160">The setup batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="28d11-161">e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="28d11-161">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="28d11-162">Questa variabile di ambiente viene impostata automaticamente all'interno di un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="28d11-162">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="28d11-163">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="28d11-163">To set up and build the sample</span></span>

1. <span data-ttu-id="28d11-164">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="28d11-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="28d11-165">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="28d11-165">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="28d11-166">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="28d11-166">To run the sample on the same computer</span></span>

1. <span data-ttu-id="28d11-167">Eseguire Setup. bat dalla cartella di installazione dell'esempio all'interno di un prompt dei comandi di Visual Studio 2012 aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="28d11-167">Run Setup.bat from the sample installation folder inside a Visual Studio 2012 command prompt opened with administrator privileges.</span></span> <span data-ttu-id="28d11-168">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="28d11-168">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28d11-169">Il file batch Setup. bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="28d11-169">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="28d11-170">La variabile di ambiente PATH impostata nel prompt dei comandi di Visual Studio 2012 punta alla directory che contiene i file eseguibili richiesti dallo script Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="28d11-170">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="28d11-171">Avviare service.exe da service\bin.</span><span class="sxs-lookup"><span data-stu-id="28d11-171">Launch service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="28d11-172">Avviare client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="28d11-172">Launch client.exe from \client\bin.</span></span> <span data-ttu-id="28d11-173">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="28d11-173">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="28d11-174">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="28d11-174">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="28d11-175">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="28d11-175">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="28d11-176">Creare una directory sul computer del servizio per i file binari del servizio.</span><span class="sxs-lookup"><span data-stu-id="28d11-176">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="28d11-177">Copiare i file di programma del servizio nella directory del servizio sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="28d11-177">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="28d11-178">Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="28d11-178">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="28d11-179">È necessario disporre di un certificato server con il nome del soggetto che contiene il nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="28d11-179">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="28d11-180">Il file service.App.config deve essere aggiornato per riflettere il nome del nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="28d11-180">The service App.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="28d11-181">È possibile crearne uno utilizzando Setup.bat se si imposta la variabile `%SERVER_NAME%` sul nome host completo del computer sul quale il servizio sarà eseguito.</span><span class="sxs-lookup"><span data-stu-id="28d11-181">You can create one by using the Setup.bat if you set the `%SERVER_NAME%` variable to fully-qualified host name of the computer on which the service will run.</span></span> <span data-ttu-id="28d11-182">Si noti che il file Setup. bat deve essere eseguito da un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="28d11-182">Note that the setup.bat file must be run from a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>  
  
4. <span data-ttu-id="28d11-183">Copiare il certificato server nell'archivio CurrentUser-TrustedPeople del client.</span><span class="sxs-lookup"><span data-stu-id="28d11-183">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="28d11-184">Questo passaggio è necessario solo quando il certificato server è emesso da un'autorità emittente client attendibile.</span><span class="sxs-lookup"><span data-stu-id="28d11-184">You do not need to do this except when the server certificate is issued by a client trusted issuer.</span></span>  
  
5. <span data-ttu-id="28d11-185">Nel file App.exe.config sul computer del servizio modificare il valore dell'indirizzo di base per specificare un nome del computer completo anziché localhost.</span><span class="sxs-lookup"><span data-stu-id="28d11-185">In the App.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="28d11-186">Sul computer del servizio eseguire service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="28d11-186">On the service computer, run service.exe from a command prompt.</span></span>  
  
7. <span data-ttu-id="28d11-187">Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.</span><span class="sxs-lookup"><span data-stu-id="28d11-187">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8. <span data-ttu-id="28d11-188">Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="28d11-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="28d11-189">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="28d11-189">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
10. <span data-ttu-id="28d11-190">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="28d11-190">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="28d11-191">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="28d11-191">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="28d11-192">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="28d11-192">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
