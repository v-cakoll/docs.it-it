---
title: Provider di token
ms.date: 03/30/2017
ms.assetid: 947986cf-9946-4987-84e5-a14678d96edb
ms.openlocfilehash: acdb820206dee83ff44152a5562642a5c685d648
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584077"
---
# <a name="token-provider"></a><span data-ttu-id="51f0a-102">Provider di token</span><span class="sxs-lookup"><span data-stu-id="51f0a-102">Token Provider</span></span>
<span data-ttu-id="51f0a-103">Questo esempio dimostra come implementare un provider di token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="51f0a-103">This sample demonstrates how to implement a custom token provider.</span></span> <span data-ttu-id="51f0a-104">Un provider di token in Windows Communication Foundation (WCF) viene utilizzato per fornire le credenziali all'infrastruttura di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="51f0a-104">A token provider in Windows Communication Foundation (WCF) is used for supplying credentials to the security infrastructure.</span></span> <span data-ttu-id="51f0a-105">In generale, il provider di token esamina la destinazione ed emette credenziali adatte in modo che l'infrastruttura di sicurezza possa proteggere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-105">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="51f0a-106">WCF viene fornito con il provider di token di gestione credenziali predefinito.</span><span class="sxs-lookup"><span data-stu-id="51f0a-106">WCF ships with the default Credential Manager Token Provider.</span></span> <span data-ttu-id="51f0a-107">WCF viene inoltre fornito con un provider di token CardSpace.</span><span class="sxs-lookup"><span data-stu-id="51f0a-107">WCF also ships with a CardSpace token provider.</span></span> <span data-ttu-id="51f0a-108">I provider di token personalizzati sono utili nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="51f0a-108">Custom token providers are useful in the following cases:</span></span>

- <span data-ttu-id="51f0a-109">Se è disponibile un archivio di credenziali con cui questi provider di token non sono in grado di operare.</span><span class="sxs-lookup"><span data-stu-id="51f0a-109">If you have a credential store that these token providers cannot operate with.</span></span>

- <span data-ttu-id="51f0a-110">Se si desidera fornire un meccanismo personalizzato per la trasformazione delle credenziali dal punto in cui l'utente fornisce i dettagli su quando il framework client WCF usa le credenziali.</span><span class="sxs-lookup"><span data-stu-id="51f0a-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client framework uses the credentials.</span></span>

- <span data-ttu-id="51f0a-111">Se si sta compilando un token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="51f0a-111">If you are building a custom token.</span></span>

 <span data-ttu-id="51f0a-112">Questo esempio illustra come compilare un provider di token personalizzato che trasforma l'input dell'utente in un formato diverso.</span><span class="sxs-lookup"><span data-stu-id="51f0a-112">This sample shows how to build a custom token provider that transforms the input from the user into a different format.</span></span>

 <span data-ttu-id="51f0a-113">Per riassumere, questo esempio dimostra quanto segue.</span><span class="sxs-lookup"><span data-stu-id="51f0a-113">To summarize, this sample demonstrates the following:</span></span>

- <span data-ttu-id="51f0a-114">Come un client può eseguire l'autenticazione utilizzando un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="51f0a-114">How a client can authenticate using a username/password pair.</span></span>

- <span data-ttu-id="51f0a-115">Come è possibile configurare un client con un provider personalizzato.</span><span class="sxs-lookup"><span data-stu-id="51f0a-115">How a client can be configured with a custom token provider.</span></span>

- <span data-ttu-id="51f0a-116">Come il server può convalidare le credenziali client utilizzando una password con una classe personalizzato <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizzata che convalida la corrispondenza tra nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="51f0a-116">How the server can validate the client credentials using a password with a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> that validates that the username and password match.</span></span>

- <span data-ttu-id="51f0a-117">Come viene autenticato il servizio dal client mediante il certificato X.509 del server.</span><span class="sxs-lookup"><span data-stu-id="51f0a-117">How the server is authenticated by the client using the server's X.509 certificate.</span></span>

 <span data-ttu-id="51f0a-118">Questo esempio mostra anche come l'identità del chiamante sia accessibile dopo il processo di autenticazione del token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="51f0a-118">This sample also shows how the caller's identity is accessible after the custom token authentication process.</span></span>

 <span data-ttu-id="51f0a-119">Il servizio espone un solo endpoint per comunicare con il servizio che viene definito mediante il file di configurazione App.config.</span><span class="sxs-lookup"><span data-stu-id="51f0a-119">The service exposes a single endpoint for communicating with the service, defined using the App.config configuration file.</span></span> <span data-ttu-id="51f0a-120">L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="51f0a-120">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="51f0a-121">L'associazione viene configurata con una classe `wsHttpBinding` standard, per la quale è impostata l'autenticazione dei messaggi come predefinita.</span><span class="sxs-lookup"><span data-stu-id="51f0a-121">The binding is configured with a standard `wsHttpBinding`, which uses message security by default.</span></span> <span data-ttu-id="51f0a-122">In questo esempio viene impostata la classe `wsHttpBinding` standard per usare l'autenticazione del nome utente del client.</span><span class="sxs-lookup"><span data-stu-id="51f0a-122">This sample sets the standard `wsHttpBinding` to use client username authentication.</span></span> <span data-ttu-id="51f0a-123">Il servizio configura anche il certificato del servizio utilizzando il comportamento serviceCredentials.</span><span class="sxs-lookup"><span data-stu-id="51f0a-123">The service also configures the service certificate using the serviceCredentials behavior.</span></span> <span data-ttu-id="51f0a-124">Il comportamento serviceCredentials consente di configurare il certificato del servizio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-124">The serviceCredentials behavior allows you to configure a service certificate.</span></span> <span data-ttu-id="51f0a-125">Un certificato del servizio viene usato da un client per autenticare il servizio e fornire protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-125">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="51f0a-126">La configurazione seguente fa riferimento al certificato localhost installato durante l'installazione dell'esempio come descritto nelle istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="51f0a-126">The following configuration references the localhost certificate installed during the sample setup as described in the following setup instructions.</span></span>

```xml
<system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- configure base address provided by host -->
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service"/>
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
        -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
```

 <span data-ttu-id="51f0a-127">La configurazione dell'endpoint client è costituita da un nome di configurazione, un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto.</span><span class="sxs-lookup"><span data-stu-id="51f0a-127">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="51f0a-128">L'associazione client viene configurata con la `Mode` e il `clientCredentialType` del messaggio appropriati.</span><span class="sxs-lookup"><span data-stu-id="51f0a-128">The client binding is configured with the appropriate `Mode` and message `clientCredentialType`.</span></span>

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

 <span data-ttu-id="51f0a-129">Nei passaggi seguenti viene illustrato come sviluppare un provider di token personalizzato e come integrarlo con il Framework di sicurezza di WCF:</span><span class="sxs-lookup"><span data-stu-id="51f0a-129">The following steps show how to develop a custom token provider and integrate it with the WCF security framework:</span></span>

1. <span data-ttu-id="51f0a-130">Scrivere un provider di token personalizzati.</span><span class="sxs-lookup"><span data-stu-id="51f0a-130">Write a custom token provider.</span></span>

     <span data-ttu-id="51f0a-131">L'esempio implementa un provider di token personalizzato che ottiene nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="51f0a-131">The sample implements a custom token provider that obtains the username and password.</span></span> <span data-ttu-id="51f0a-132">La password deve corrispondere al nome utente.</span><span class="sxs-lookup"><span data-stu-id="51f0a-132">The password must match this username.</span></span> <span data-ttu-id="51f0a-133">Questo provider di token personalizzato è a mero scopo esemplificativo e non si consiglia di distribuirlo.</span><span class="sxs-lookup"><span data-stu-id="51f0a-133">This custom token provider is for demonstration purposes only and is not recommended for real world deployment.</span></span>

     <span data-ttu-id="51f0a-134">Per eseguire questa attività il provider di token personalizzato deriva dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenProvider> ed esegue l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>.</span><span class="sxs-lookup"><span data-stu-id="51f0a-134">To perform this task, the custom token provider derives the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="51f0a-135">Questo metodo creare e restituisce un nuovo `UserNameSecurityToken`.</span><span class="sxs-lookup"><span data-stu-id="51f0a-135">This method creates and returns a new `UserNameSecurityToken`.</span></span>

    ```csharp
    protected override SecurityToken GetTokenCore(TimeSpan timeout)
    {
        // obtain username and password from the user using console window
        string username = GetUserName();
        string password = GetPassword();
        Console.WriteLine("username: {0}", username);

        // return new UserNameSecurityToken containing information obtained from user
        return new UserNameSecurityToken(username, password);
    }
    ```

2. <span data-ttu-id="51f0a-136">Scrivere il gestore di token di sicurezza personalizzato.</span><span class="sxs-lookup"><span data-stu-id="51f0a-136">Write custom security token manager.</span></span>

     <span data-ttu-id="51f0a-137">La classe <xref:System.IdentityModel.Selectors.SecurityTokenManager> viene utilizzata per creare <xref:System.IdentityModel.Selectors.SecurityTokenProvider> per il <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> specifico che viene passato nel metodo `CreateSecurityTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="51f0a-137">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="51f0a-138">Viene inoltre utilizzato un gestore del token di sicurezza per creare autenticatori del token e serializzatori del token, che però non sono trattati in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-138">Security token manager is also used to create token authenticators and a token serializer, but those are not covered by this sample.</span></span> <span data-ttu-id="51f0a-139">In questo esempio, il gestore del token di sicurezza personalizzato eredita dalla classe <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> ed esegue l'override del metodo `CreateSecurityTokenProvider` per restituire il provider di token nome utente personalizzato quando i requisiti del token passati indicano che il provider nome utente è richiesto.</span><span class="sxs-lookup"><span data-stu-id="51f0a-139">In this sample, the custom security token manager inherits from <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return custom username token provider when the passed token requirements indicate that username provider is requested.</span></span>

    ```csharp
    public class MyUserNameSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
        MyUserNameClientCredentials myUserNameClientCredentials;

        public MyUserNameSecurityTokenManager(MyUserNameClientCredentials myUserNameClientCredentials)
            : base(myUserNameClientCredentials)
        {
            this.myUserNameClientCredentials = myUserNameClientCredentials;
        }

        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)
        {
            // if token requirement matches username token return custom username token provider
            // otherwise use base implementation
            if (tokenRequirement.TokenType == SecurityTokenTypes.UserName)
            {
                return new MyUserNameTokenProvider();
            }
            else
            {
                return base.CreateSecurityTokenProvider(tokenRequirement);
            }
        }
    }
    ```

3. <span data-ttu-id="51f0a-140">Scrivere una credenziale client personalizzata.</span><span class="sxs-lookup"><span data-stu-id="51f0a-140">Write a custom client credential.</span></span>

     <span data-ttu-id="51f0a-141">La classe delle credenziali client viene utilizzata per rappresentare le credenziali configurate per il proxy client e crea un gestore del token di sicurezza utilizzato per ottenere gli autenticatori del token, i provider di token e il serializzatore di token.</span><span class="sxs-lookup"><span data-stu-id="51f0a-141">Client credentials class is used to represent the credentials that are configured for the client proxy and creates security token manager that is used to obtain token authenticators, token providers and a token serializer.</span></span>

    ```csharp
    public class MyUserNameClientCredentials : ClientCredentials
    {
        public MyUserNameClientCredentials()
            : base()
        {
        }

        protected override ClientCredentials CloneCore()
        {
            return new MyUserNameClientCredentials();
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            // return custom security token manager
            return new MyUserNameSecurityTokenManager(this);
        }
    }
    ```

4. <span data-ttu-id="51f0a-142">Configurare il client per l'uso della credenziale client personalizzata.</span><span class="sxs-lookup"><span data-stu-id="51f0a-142">Configure the client to use the custom client credential.</span></span>

     <span data-ttu-id="51f0a-143">L'esempio elimina la classe della credenziale client predefinita e fornisce la nuova classe della credenziale client affinché il client possa utilizzare la credenziale client personalizzata.</span><span class="sxs-lookup"><span data-stu-id="51f0a-143">In order for the client to use the custom client credential, the sample deletes the default client credential class and supplies the new client credential class.</span></span>

    ```csharp
    static void Main()
    {
        // ...
           // Create a client with given client endpoint configuration
          CalculatorClient client = new CalculatorClient();

          // set new credentials
           client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
         client.ChannelFactory.Endpoint.Behaviors.Add(new MyUserNameClientCredentials());
       // ...
    }
    ```

 <span data-ttu-id="51f0a-144">Nel servizio, per visualizzare le informazioni sul chiamante è possibile utilizzare <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="51f0a-144">On the service, to display the caller's information, use the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> as shown in the following code example.</span></span> <span data-ttu-id="51f0a-145">La classe <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contiene informazioni sulle attestazioni circa il chiamante corrente.</span><span class="sxs-lookup"><span data-stu-id="51f0a-145">The <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contains claims information about the current caller.</span></span>

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
        ServiceSecurityContext.Current.PrimaryIdentity.Name);
}
```

 <span data-ttu-id="51f0a-146">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="51f0a-146">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="51f0a-147">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="51f0a-147">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="51f0a-148">File batch di installazione</span><span class="sxs-lookup"><span data-stu-id="51f0a-148">Setup Batch File</span></span>
 <span data-ttu-id="51f0a-149">Il file batch Setup.bat incluso con questo esempio consente di configurare il server con il certificato attinente per eseguire un'applicazione indipendente che richiede sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="51f0a-149">The Setup.bat batch file included with this sample allows you to configure the server with the relevant certificate to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="51f0a-150">Questo file batch deve essere modificato per funzionare tra computer diversi o nel caso in cui non sia ospitato.</span><span class="sxs-lookup"><span data-stu-id="51f0a-150">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="51f0a-151">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="51f0a-151">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="51f0a-152">Creazione del certificato server.</span><span class="sxs-lookup"><span data-stu-id="51f0a-152">Creating the server certificate.</span></span>

     <span data-ttu-id="51f0a-153">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="51f0a-153">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="51f0a-154">La variabile `%SERVER_NAME%` specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="51f0a-154">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="51f0a-155">Modificare questa variabile per specificare nome del server.</span><span class="sxs-lookup"><span data-stu-id="51f0a-155">Change this variable to specify your own server name.</span></span> <span data-ttu-id="51f0a-156">Il valore predefinito in questo file batch è localhost.</span><span class="sxs-lookup"><span data-stu-id="51f0a-156">The default value in this batch file is localhost.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="51f0a-157">Installazione del certificato server nell'archivio certificati attendibile del client:</span><span class="sxs-lookup"><span data-stu-id="51f0a-157">Installing the server certificate into the client's trusted certificate store:</span></span>

     <span data-ttu-id="51f0a-158">Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client.</span><span class="sxs-lookup"><span data-stu-id="51f0a-158">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="51f0a-159">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="51f0a-159">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="51f0a-160">Se è già disponibile un certificato con radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio del popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="51f0a-160">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

> [!NOTE]
> <span data-ttu-id="51f0a-161">Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="51f0a-161">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="51f0a-162">e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="51f0a-162">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="51f0a-163">Questa variabile di ambiente viene impostata automaticamente all'interno di un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="51f0a-163">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="51f0a-164">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="51f0a-164">To set up and build the sample</span></span>

1. <span data-ttu-id="51f0a-165">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="51f0a-165">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="51f0a-166">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="51f0a-166">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="51f0a-167">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="51f0a-167">To run the sample on the same computer</span></span>

1. <span data-ttu-id="51f0a-168">Eseguire Setup. bat dalla cartella di installazione dell'esempio all'interno di un prompt dei comandi di Visual Studio 2012 aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="51f0a-168">Run Setup.bat from the sample installation folder inside a Visual Studio 2012 command prompt opened with administrator privileges.</span></span> <span data-ttu-id="51f0a-169">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-169">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="51f0a-170">Il file batch Setup. bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="51f0a-170">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="51f0a-171">La variabile di ambiente PATH impostata nel prompt dei comandi di Visual Studio 2012 punta alla directory che contiene i file eseguibili richiesti dallo script Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="51f0a-171">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="51f0a-172">Avviare service.exe da service\bin.</span><span class="sxs-lookup"><span data-stu-id="51f0a-172">Launch service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="51f0a-173">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="51f0a-173">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="51f0a-174">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="51f0a-174">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="51f0a-175">Al prompt del nome utente, digitare un nome utente.</span><span class="sxs-lookup"><span data-stu-id="51f0a-175">At the username prompt, type a user name.</span></span>  
  
5. <span data-ttu-id="51f0a-176">Al prompt della password, utilizzare la stessa stringa digitata per il prompt del nome utente.</span><span class="sxs-lookup"><span data-stu-id="51f0a-176">At the password prompt, use the same string that was typed for the username prompt.</span></span>  
  
6. <span data-ttu-id="51f0a-177">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="51f0a-177">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="51f0a-178">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="51f0a-178">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="51f0a-179">Creare una directory sul computer del servizio per i file binari del servizio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-179">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="51f0a-180">Copiare i file di programma del servizio nella directory del servizio sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="51f0a-180">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="51f0a-181">Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-181">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="51f0a-182">È necessario disporre di un certificato server con il nome del soggetto che contiene il nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="51f0a-182">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="51f0a-183">Il file Service.exe.config deve essere aggiornato per riflettere il nome del nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="51f0a-183">The Service.exe.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="51f0a-184">È possibile creare il certificato server modificando il file batch Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="51f0a-184">You can create server certificate by modifying the Setup.bat batch file.</span></span> <span data-ttu-id="51f0a-185">Si noti che il file Setup. bat deve essere eseguito da un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="51f0a-185">Note that the setup.bat file must be run from a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="51f0a-186">È necessario impostare la variabile `%SERVER_NAME%` sul nome host completo del computer utilizzato per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-186">You must set `%SERVER_NAME%` variable to fully-qualified host name of the computer that is used to host the service.</span></span>  
  
4. <span data-ttu-id="51f0a-187">Copiare il certificato server nell'archivio CurrentUser-TrustedPeople del client.</span><span class="sxs-lookup"><span data-stu-id="51f0a-187">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="51f0a-188">Questo passaggio non è necessario quando il certificato server è emesso da un'autorità emittente client attendibile.</span><span class="sxs-lookup"><span data-stu-id="51f0a-188">You do not need to do this when the server certificate is issued by a client trusted issuer.</span></span>  
  
5. <span data-ttu-id="51f0a-189">Nel file Service.exe.config sul computer del servizio modificare il valore dell'indirizzo di base per specificare un nome del computer completo anziché localhost.</span><span class="sxs-lookup"><span data-stu-id="51f0a-189">In the Service.exe.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="51f0a-190">Sul computer del servizio eseguire service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="51f0a-190">On the service computer, run service.exe from a command prompt.</span></span>  
  
7. <span data-ttu-id="51f0a-191">Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.</span><span class="sxs-lookup"><span data-stu-id="51f0a-191">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8. <span data-ttu-id="51f0a-192">Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-192">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="51f0a-193">Sul computer client avviare `Client.exe` da una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="51f0a-193">On the client computer, launch `Client.exe` from a command prompt window.</span></span>  
  
10. <span data-ttu-id="51f0a-194">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="51f0a-194">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="51f0a-195">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="51f0a-195">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="51f0a-196">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="51f0a-196">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
