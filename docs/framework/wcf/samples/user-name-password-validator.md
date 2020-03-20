---
title: Validator del nome utente e password
ms.date: 03/30/2017
ms.assetid: 42f03841-286b-42d8-ba58-18c75422bc8e
ms.openlocfilehash: 202c7bfc7f60afbad8220950e46c08c0a71eb001
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183243"
---
# <a name="user-name-password-validator"></a><span data-ttu-id="13cb6-102">Validator del nome utente e password</span><span class="sxs-lookup"><span data-stu-id="13cb6-102">User Name Password Validator</span></span>
<span data-ttu-id="13cb6-103">In questo esempio viene illustrato come implementare un validator di UserNamePassword personalizzato.</span><span class="sxs-lookup"><span data-stu-id="13cb6-103">This sample demonstrates how to implement a custom UserNamePassword Validator.</span></span> <span data-ttu-id="13cb6-104">Questo processo è utile nei casi in cui nessuna delle modalità di convalida UserNamePassword incorporate è appropriata per i requisiti dell'applicazione; ad esempio, quando le coppie di nome utente/password sono archiviate in un archivio esterno, ad esempio un database.</span><span class="sxs-lookup"><span data-stu-id="13cb6-104">This is useful in cases where none of the built-in UserNamePassword Validation modes is appropriate for the requirements of the application; for example, when username/password pairs are stored in some external store, such as a database.</span></span> <span data-ttu-id="13cb6-105">In questo esempio viene illustrato un servizio con un validator personalizzato che verifica due particolari coppie di nome utente/password.</span><span class="sxs-lookup"><span data-stu-id="13cb6-105">This sample shows a service that has a custom validator that checks for two particular username/password pairs.</span></span> <span data-ttu-id="13cb6-106">Il cliente utilizza tale coppia di nome utente/password per l'autenticazione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="13cb6-106">The client uses such a username/password pair to authenticate to the service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13cb6-107">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="13cb6-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="13cb6-108">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="13cb6-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="13cb6-109">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="13cb6-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="13cb6-110">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="13cb6-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\UserNamePasswordValidator`  
  
> [!NOTE]
> <span data-ttu-id="13cb6-111">Poiché chiunque può costruire una credenziale Username che utilizza le coppie di nome utente/password accettate dal validator personalizzato, il servizio è meno affidabile rispetto al comportamento predefinito fornito dal validator UserNamePassword standard.</span><span class="sxs-lookup"><span data-stu-id="13cb6-111">Because anyone can construct a Username credential that uses the username/password pairs that the custom validator accepts, the service is less secure than the default behavior provided by the standard UserNamePassword Validator.</span></span> <span data-ttu-id="13cb6-112">Il validator UserNamePassword standard tenta di eseguire il mapping della coppia di nome utente/password fornita a un account di Windows e se questo mapping non riesce, l'autenticazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="13cb6-112">The standard UserNamePassword Validator attempts to map the provided username/password pair to a Windows account and fails authentication if this mapping fails.</span></span> <span data-ttu-id="13cb6-113">Il validator UserNamePassword personalizzato in questo esempio non deve essere utilizzato nel codice di produzione, poiché è concepito per solo scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="13cb6-113">The custom UserNamePassword Validator in this sample MUST NOT be used in production code, it is for illustration purposes only.</span></span>

 <span data-ttu-id="13cb6-114">In sintesi, nell'esempio viene illustrato in che modo eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13cb6-114">In summary this sample demonstrates how:</span></span>

- <span data-ttu-id="13cb6-115">Il client può essere autenticato utilizzando un token Username.</span><span class="sxs-lookup"><span data-stu-id="13cb6-115">The client can be authenticated using a Username Token.</span></span>

- <span data-ttu-id="13cb6-116">Il server convalida le credenziali client in relazione a un UserNamePasswordValidator personalizzato e il modo in cui vengono propagati gli errori personalizzati dipende dalla logica di convalida del nome utente e della password nel client.</span><span class="sxs-lookup"><span data-stu-id="13cb6-116">The server validates the client credentials against a custom UserNamePasswordValidator and how to propagate custom faults from the username and password validation logic to the client.</span></span>

- <span data-ttu-id="13cb6-117">Il server viene autenticato tramite il certificato X.509 del server.</span><span class="sxs-lookup"><span data-stu-id="13cb6-117">The server is authenticated using the server's X.509 certificate.</span></span>

 <span data-ttu-id="13cb6-118">The service exposes a single endpoint for communicating with the service, defined using the configuration file, App.config. L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="13cb6-118">The service exposes a single endpoint for communicating with the service, defined using the configuration file, App.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="13cb6-119">L'associazione è `wsHttpBinding` configurata con uno standard che utilizza per impostazione predefinita l'autenticazione WS-Security e nome utente.</span><span class="sxs-lookup"><span data-stu-id="13cb6-119">The binding is configured with a standard `wsHttpBinding` that defaults to using WS-Security and username authentication.</span></span> <span data-ttu-id="13cb6-120">Il comportamento del servizio specifica la modalità `Custom` per la convalida delle coppie nome utente/password client insieme al tipo di classe del validator.</span><span class="sxs-lookup"><span data-stu-id="13cb6-120">The service behavior specifies the `Custom` mode for validating client username/password pairs along with the type of the validator class.</span></span> <span data-ttu-id="13cb6-121">Il comportamento specifica inoltre il certificato server mediante l'elemento `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="13cb6-121">The behavior also specifies the server certificate using the `serviceCertificate` element.</span></span> <span data-ttu-id="13cb6-122">Il certificato server deve contenere `SubjectName` lo `findValue` stesso valore per il nel nel [ \<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="13cb6-122">The server certificate has to contain the same value for the `SubjectName` as the `findValue` in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <!-- use host/baseAddresses to configure base address provided by host -->
      <host>
        <baseAddresses>
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service" />
        </baseAddresses>
      </host>
      <!-- use base address specified above, provide one endpoint -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- username binding -->
      <binding name="Binding">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceDebug includeExceptionDetailInFaults ="true"/>
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to
          specify a custom validator for username/password
          combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom"
                                  customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to define a service certificate. A service certificate is used by a client to authenticate the service and provide message protection. You must specify a server certificate when passing username/passwords to encrypt the information as it is sent on the wire. Otherwise the username and password information would be sent as clear text. This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

 <span data-ttu-id="13cb6-123">La configurazione dell'endpoint client è costituita da un nome di configurazione, un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto.</span><span class="sxs-lookup"><span data-stu-id="13cb6-123">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="13cb6-124">L'associazione client viene configurata con la modalità e il `clientCredentialType` del messaggio appropriati.</span><span class="sxs-lookup"><span data-stu-id="13cb6-124">The client binding is configured with the appropriate mode and message `clientCredentialType`.</span></span>

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
address="http://localhost:8001/servicemodelsamples/service/username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
        <binding name="Binding">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <clientCredentials>
            <serviceCertificate>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>

  </system.serviceModel>
```

 <span data-ttu-id="13cb6-125">L'implementazione client richiede all'utente di immettere un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="13cb6-125">The client implementation prompts the user to enter a username and password.</span></span>

```csharp
// Get the username and password
Console.WriteLine("Username authentication required.");
Console.WriteLine("Provide a username.");
Console.WriteLine("   Enter username: (test1)");
string username = Console.ReadLine();
Console.WriteLine("   Enter password:");
string password = "";
ConsoleKeyInfo info = Console.ReadKey(true);
while (info.Key != ConsoleKey.Enter)
{
    if (info.Key != ConsoleKey.Backspace)
    {
        if (info.KeyChar != '\0')
        {
            password += info.KeyChar;
        }
        info = Console.ReadKey(true);
    }
    else if (info.Key == ConsoleKey.Backspace)
    {
        if (password != "")
        {
            password = password.Substring(0, password.Length - 1);
        }
        info = Console.ReadKey(true);
    }
}
for (int i = 0; i < password.Length; i++)
{
    Console.Write("*");
}
Console.WriteLine();
// Create a proxy with Certificate endpoint configuration
CalculatorProxy proxy = new CalculatorProxy("Username")
try
{
  proxy.ClientCredentials.Username.Username = username;
  proxy.ClientCredentials.Username.Password = password;
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = proxy.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
  }
  catch (Exception e)
  {
      Console.WriteLine("Call failed:");
      while (e != null)
      {
          Console.WriteLine("\t{0}", e.Message);
          e = e.InnerException;
      }
      proxy.Abort();
  }
}
```

 <span data-ttu-id="13cb6-126">In questo esempio viene utilizzato un UserNamePasswordValidator personalizzato per convalidare le coppie di nome utente/password.</span><span class="sxs-lookup"><span data-stu-id="13cb6-126">This sample uses a custom UserNamePasswordValidator to validate username/password pairs.</span></span> <span data-ttu-id="13cb6-127">Nell'esempio viene implementato `CustomUserNamePasswordValidator`, derivato da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="13cb6-127">The sample implements `CustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="13cb6-128">Per ulteriori informazioni, vedere la documentazione di <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="13cb6-128">See the documentation for <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="13cb6-129">In questo particolare esempio del validator personalizzato viene implementato il metodo `Validate` per accettare due specifiche coppie di nome utente/password, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="13cb6-129">This particular custom validator sample implements the `Validate` method to accept two particular username/password pairs as shown in the following code.</span></span>

```csharp
public class CustomUserNameValidator : UserNamePasswordValidator
{
 // This method validates users. It allows in two users,
 // test1 and test2 with passwords 1tset and 2tset respectively.
 // This code is for illustration purposes only and
 // MUST NOT be used in a production environment because it
 // is NOT secure.
 public override void Validate(string userName, string password)
 {
  if (null == userName || null == password)
  {
   throw new ArgumentNullException();
  }

  if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
  {
   throw new FaultException("Unknown Username or Incorrect Password");
   }
  }
 }
```

 <span data-ttu-id="13cb6-130">Quando il validator è stato implementato nel codice del servizio, l'host del servizio deve essere informato dell'istanza del validator da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="13cb6-130">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="13cb6-131">Questa operazione viene eseguita tramite il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="13cb6-131">This is done using the following code.</span></span>

```csharp
serviceHost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials. UserNameAuthentication.CustomUserNamePasswordValidator = new CustomUserNamePasswordValidator();
```

 <span data-ttu-id="13cb6-132">In alternativa, è possibile eseguire la stessa operazione nella configurazione come segue.</span><span class="sxs-lookup"><span data-stu-id="13cb6-132">Or you can do the same thing in configuration as follows.</span></span>

```xml
<behaviors>
 <serviceBehaviors>
  <behavior name="CalculatorServiceBehavior">
  ...
   <serviceCredentials>
    <!--
    The serviceCredentials behavior allows one to specify authentication constraints on username / password combinations.
    -->
    <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+CustomUserNameValidator, service" />
   ...
  </behavior>
 </serviceBehaviors>
</behaviors>
```

 <span data-ttu-id="13cb6-133">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="13cb6-133">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="13cb6-134">Il client deve chiamare correttamente tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="13cb6-134">The client should successfully call all the methods.</span></span> <span data-ttu-id="13cb6-135">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="13cb6-135">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="13cb6-136">File batch di installazione</span><span class="sxs-lookup"><span data-stu-id="13cb6-136">Setup Batch File</span></span>
 <span data-ttu-id="13cb6-137">Il file batch Setup.bat incluso in questo esempio consente di configurare il server con i certificati attinenti per eseguire un'applicazione indipendente che richiede la sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="13cb6-137">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="13cb6-138">Questo file batch deve essere modificato per funzionare su computer diversi o per operare in un contesto non indipendente.</span><span class="sxs-lookup"><span data-stu-id="13cb6-138">This batch file must be modified to work across machines or to work in a non-self-hosted case.</span></span>

 <span data-ttu-id="13cb6-139">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="13cb6-139">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

- <span data-ttu-id="13cb6-140">Creazione del certificato server:</span><span class="sxs-lookup"><span data-stu-id="13cb6-140">Creating the server certificate:</span></span>

     <span data-ttu-id="13cb6-141">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="13cb6-141">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="13cb6-142">La variabile %SERVER_NAME% specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="13cb6-142">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="13cb6-143">Modificare questa variabile per specificare nome del server.</span><span class="sxs-lookup"><span data-stu-id="13cb6-143">Change this variable to specify your own server name.</span></span> <span data-ttu-id="13cb6-144">Il valore predefinito è localhost.</span><span class="sxs-lookup"><span data-stu-id="13cb6-144">The default value is localhost.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="13cb6-145">Installazione del certificato server nell'archivio certificati attendibili del client:</span><span class="sxs-lookup"><span data-stu-id="13cb6-145">Installing the server certificate into client's trusted certificate store:</span></span>

     <span data-ttu-id="13cb6-146">Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client.</span><span class="sxs-lookup"><span data-stu-id="13cb6-146">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="13cb6-147">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="13cb6-147">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="13cb6-148">Se è già disponibile un certificato con radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio del popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="13cb6-148">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="13cb6-149">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="13cb6-149">To set up and build the sample</span></span>

1. <span data-ttu-id="13cb6-150">Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="13cb6-150">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

2. <span data-ttu-id="13cb6-151">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="13cb6-151">To run the sample in a single- or cross-machine configuration, use the following instructions.</span></span>

#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="13cb6-152">Per eseguire l'esempio sullo stesso computer</span><span class="sxs-lookup"><span data-stu-id="13cb6-152">To run the sample on the same machine</span></span>

1. <span data-ttu-id="13cb6-153">Eseguire Setup.bat dalla cartella di installazione di esempio all'interno di un prompt dei comandi di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="13cb6-153">Run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt.</span></span> <span data-ttu-id="13cb6-154">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="13cb6-154">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="13cb6-155">Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="13cb6-155">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="13cb6-156">La variabile di ambiente PATH impostata all'interno del prompt dei comandi di Visual Studio 2012 punta alla directory che contiene gli eseguibili richiesti dallo script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="13cb6-156">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="13cb6-157">Avviare Service.exe da service\bin.</span><span class="sxs-lookup"><span data-stu-id="13cb6-157">Launch Service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="13cb6-158">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="13cb6-158">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="13cb6-159">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="13cb6-159">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="13cb6-160">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="13cb6-160">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="13cb6-161">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="13cb6-161">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="13cb6-162">Creare una directory sul computer del servizio per i file binari del servizio.</span><span class="sxs-lookup"><span data-stu-id="13cb6-162">Create a directory on the service machine for the service binaries.</span></span>  
  
2. <span data-ttu-id="13cb6-163">Copiare i file di programma del servizio nella directory del servizio all'interno del computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="13cb6-163">Copy the service program files the service directory on the service machine.</span></span> <span data-ttu-id="13cb6-164">Copiare anche i file Setup.bat e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="13cb6-164">Also copy the Setup.bat and Cleanup.bat files to the service machine.</span></span>  
  
3. <span data-ttu-id="13cb6-165">È necessario disporre di un certificato server con il nome del soggetto che contiene il nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="13cb6-165">You need a server certificate with the subject name that contains the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="13cb6-166">Il file di configurazione per il server deve essere aggiornato per riflettere il nome del nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="13cb6-166">The configuration file for the server must be updated to reflect this new certificate name.</span></span>  
  
4. <span data-ttu-id="13cb6-167">Copiare il certificato server nell'archivio CurrentUser-TrustedPeople del client.</span><span class="sxs-lookup"><span data-stu-id="13cb6-167">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="13cb6-168">Questo passaggio è necessario solo se il certificato server non è emesso da un'autorità emittente attendibile.</span><span class="sxs-lookup"><span data-stu-id="13cb6-168">You need to do this only if the server certificate is not issued by a trusted issuer.</span></span>  
  
5. <span data-ttu-id="13cb6-169">Nel file App.config sul computer del servizio, modificare il valore dell'indirizzo di base per specificare un nome del computer completo anziché localhost.</span><span class="sxs-lookup"><span data-stu-id="13cb6-169">In the App.config file on the service machine, change the value of the base address to specify a fully-qualified machine name instead of localhost.</span></span>  
  
6. <span data-ttu-id="13cb6-170">Nel computer del servizio, avviare Service.exe da una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="13cb6-170">On the service machine, launch Service.exe from a command prompt window.</span></span>  
  
7. <span data-ttu-id="13cb6-171">Copiare i file del programma client dalla cartella \client\bin\, nella cartella specifica del linguaggio, al computer client.</span><span class="sxs-lookup"><span data-stu-id="13cb6-171">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machine.</span></span>  
  
8. <span data-ttu-id="13cb6-172">Nel file Client.exe.config nel computer client, modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="13cb6-172">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="13cb6-173">Sul computer client, avviare Client.exe da una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="13cb6-173">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
10. <span data-ttu-id="13cb6-174">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="13cb6-174">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="13cb6-175">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="13cb6-175">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="13cb6-176">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="13cb6-176">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span> <span data-ttu-id="13cb6-177">In questo modo il certificato del server viene rimosso dall'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="13cb6-177">This removes the server certificate from the certificate store.</span></span>  
