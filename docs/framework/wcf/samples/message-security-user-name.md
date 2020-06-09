---
title: Sicurezza dei messaggi tramite nome utente
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c63cfc87-6b20-4949-93b3-bcd4b732b0a2
ms.openlocfilehash: 783969342f007895016ed4183257d6b24188d76c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584727"
---
# <a name="message-security-user-name"></a><span data-ttu-id="0c717-102">Sicurezza dei messaggi tramite nome utente</span><span class="sxs-lookup"><span data-stu-id="0c717-102">Message Security User Name</span></span>
<span data-ttu-id="0c717-103">In questo esempio viene illustrato come implementare un'applicazione che usa WS-Security con l'autenticazione del nome utente per il client e richiede l'autenticazione del server tramite il certificato X.509v3 del server.</span><span class="sxs-lookup"><span data-stu-id="0c717-103">This sample demonstrates how to implement an application that uses WS-Security with username authentication for the client and requires server authentication using the server's X.509v3 certificate.</span></span> <span data-ttu-id="0c717-104">Tutti i messaggi dell'applicazione tra il client e il server vengono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="0c717-104">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="0c717-105">Per impostazione predefinita, il nome utente e la password forniti dal client vengono usati per accedere a un account Windows valido.</span><span class="sxs-lookup"><span data-stu-id="0c717-105">By default, the username and password supplied by the client are used to logon to a valid Windows account.</span></span> <span data-ttu-id="0c717-106">Questo esempio è basato su [wsHttpBinding](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="0c717-106">This sample is based on the [WSHttpBinding](wshttpbinding.md).</span></span> <span data-ttu-id="0c717-107">Questo esempio è costituito da un programma di console client (Client.exe) e da una libreria di servizi (Service.dll) ospitati da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="0c717-107">This sample consists of a client console program (Client.exe) and a service library (Service.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="0c717-108">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="0c717-108">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c717-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0c717-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0c717-110">In questo esempio viene inoltre illustrato:</span><span class="sxs-lookup"><span data-stu-id="0c717-110">This sample also demonstrates:</span></span>  
  
- <span data-ttu-id="0c717-111">Il mapping predefinito agli account di Windows per approvare autorizzazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="0c717-111">The default mapping to Windows accounts so that additional authorization can be performed.</span></span>  
  
- <span data-ttu-id="0c717-112">Come accedere alle informazioni di identità del chiamante dal codice del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c717-112">How to access the caller's identity information from the service code.</span></span>  
  
 <span data-ttu-id="0c717-113">Il servizio espone un singolo endpoint per la comunicazione con il servizio, che viene definito utilizzando il file di configurazione Web. config. L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="0c717-113">The service exposes a single endpoint for communicating with the service, which is defined using the configuration file Web.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="0c717-114">L'associazione viene configurata con una classe standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , per impostazione predefinita viene utilizzata la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="0c717-114">The binding is configured with a standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), which defaults to using message security.</span></span> <span data-ttu-id="0c717-115">Questo esempio imposta lo standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) per l'uso dell'autenticazione del nome utente del client.</span><span class="sxs-lookup"><span data-stu-id="0c717-115">This sample sets the standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) to use client username authentication.</span></span> <span data-ttu-id="0c717-116">Il comportamento specifica che le credenziali utente devono essere usate per l'autenticazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c717-116">The behavior specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="0c717-117">Il certificato server deve contenere lo stesso valore per il nome del soggetto dell' `findValue` attributo in [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="0c717-117">The server certificate must contain the same value for the subject name as the `findValue` attribute in the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      By default, Username authentication attempts to authenticate the provided  
      username as a Windows computer or domain account.  
      -->  
      <binding>  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!--   
      The serviceCredentials behavior allows one to define a service certificate.  
      A service certificate is used by the service to authenticate itself to the client and to provide message protection.  
      This configuration references the "localhost" certificate installed during the setup instructions.  
      -->  
        <serviceCredentials>  
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
        </serviceCredentials>  
        <serviceMetadata httpGetEnabled="True"/>  
        <serviceDebug includeExceptionDetailInFaults="False" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="0c717-118">La configurazione dell'endpoint client è costituita da un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto.</span><span class="sxs-lookup"><span data-stu-id="0c717-118">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="0c717-119">L'associazione client viene configurata con la `securityMode` e la `authenticationMode` appropriate.</span><span class="sxs-lookup"><span data-stu-id="0c717-119">The client binding is configured with the appropriate `securityMode` and `authenticationMode`.</span></span> <span data-ttu-id="0c717-120">Quando si esegue l'esempio tra più computer, l'indirizzo dell'endpoint del servizio deve essere modificato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="0c717-120">When running in a cross-computer scenario, the service endpoint address must be changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address="http://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              behaviorConfiguration="ClientCredentialsBehavior"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="ClientCredentialsBehavior">  
        <!--   
      Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
      is in the user's Trusted People store, then it is trusted without performing a  
      validation of the certificate's issuer chain. This setting is used here for convenience so that the   
      sample can be run without having to have certificates issued by a certification authority (CA).  
      This setting is less secure than the default, ChainTrust. The security implications of this   
      setting should be carefully considered before using PeerOrChainTrust in production code.   
      -->  
        <clientCredentials>  
          <serviceCertificate>  
            <authentication certificateValidationMode="PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="0c717-121">L'implementazione del client imposta il nome utente e la password da usare.</span><span class="sxs-lookup"><span data-stu-id="0c717-121">The client implementation sets the user name and password to use.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Configure client with valid computer or domain account (username,password).  
client.ClientCredentials.UserName.UserName = username;  
client.ClientCredentials.UserName.Password = password.ToString();  
  
// Call GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```

 <span data-ttu-id="0c717-122">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="0c717-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0c717-123">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="0c717-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
MyMachine\TestAccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="0c717-124">Il file batch Setup.bat incluso negli esempi relativi alla sicurezza dei messaggi consente di configurare il server con un certificato attinente per eseguire un'applicazione ospitata che richiede sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="0c717-124">The Setup.bat batch file included with the MessageSecurity samples enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="0c717-125">Il file batch può essere eseguito in due modalità.</span><span class="sxs-lookup"><span data-stu-id="0c717-125">The batch file can be run in two modes.</span></span> <span data-ttu-id="0c717-126">Per eseguire il file batch in un solo computer, digitare `setup.bat` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0c717-126">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="0c717-127">Per eseguirlo in modalità di servizio, digitare `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="0c717-127">To run it in service mode type `setup.bat service`.</span></span> <span data-ttu-id="0c717-128">Usare questa modalità quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="0c717-128">You use this mode when running the sample across computers.</span></span> <span data-ttu-id="0c717-129">Per altre informazioni, vedere la procedura di configurazione alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0c717-129">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="0c717-130">Di seguito viene presentata una breve panoramica delle diverse sezioni dei file batch.</span><span class="sxs-lookup"><span data-stu-id="0c717-130">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
- <span data-ttu-id="0c717-131">Creazione del certificato server</span><span class="sxs-lookup"><span data-stu-id="0c717-131">Creating the server certificate</span></span>  
  
     <span data-ttu-id="0c717-132">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="0c717-132">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="0c717-133">La variabile %SERVER_NAME% specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="0c717-133">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="0c717-134">Il certificato viene archiviato nell'archivio LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0c717-134">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="0c717-135">Se il file batch Setup.bat viene eseguito con un argomento di servizio (ad esempio `setup.bat service`) il %NOME_SERVER% contiene il nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="0c717-135">If the Setup.bat batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span>  <span data-ttu-id="0c717-136">In caso contrario, viene usata l'impostazione predefinita localhost.</span><span class="sxs-lookup"><span data-stu-id="0c717-136">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="0c717-137">Installazione del certificato server nell'archivio certificati attendibili del client</span><span class="sxs-lookup"><span data-stu-id="0c717-137">Installing the server certificate into the client's trusted certificate store</span></span>  
  
     <span data-ttu-id="0c717-138">La riga seguente copia il certificato server nell'archivio Persone attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="0c717-138">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="0c717-139">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="0c717-139">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="0c717-140">Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="0c717-140">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="0c717-141">Concessione delle autorizzazioni sulla chiave privata del certificato</span><span class="sxs-lookup"><span data-stu-id="0c717-141">Granting permissions on the certificate's private key</span></span>  
  
     <span data-ttu-id="0c717-142">Le righe seguenti del file batch Setup. bat rendono il certificato server archiviato nell'archivio LocalMachine accessibile all'account del processo di lavoro di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0c717-142">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>  
  
    ```bat
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="0c717-143">Se si usa un'edizione non in lingua inglese di Windows, è necessario modificare il file Setup. bat e sostituire il `NT AUTHORITY\NETWORK SERVICE` nome dell'account con l'equivalente regionale.</span><span class="sxs-lookup"><span data-stu-id="0c717-143">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0c717-144">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0c717-144">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0c717-145">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c717-145">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0c717-146">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c717-146">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="0c717-147">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="0c717-147">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="0c717-148">Assicurarsi che il percorso includa la cartella in cui sono situati Makecert.exe e FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="0c717-148">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>  
  
2. <span data-ttu-id="0c717-149">Eseguire Setup. bat dalla cartella di installazione dell'esempio in un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0c717-149">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="0c717-150">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="0c717-150">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0c717-151">Il file batch Setup. bat è progettato per essere eseguito da un Prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c717-151">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="0c717-152">e richiede che la variabile di ambiente PATH punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="0c717-152">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="0c717-153">Questa variabile di ambiente viene impostata automaticamente in un Prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c717-153">This environment variable is automatically set within a Developer Command Prompt for Visual Studio.</span></span>  
  
3. <span data-ttu-id="0c717-154">Verificare l'accesso al servizio usando un browser immettendo l'indirizzo `http://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="0c717-154">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>
  
4. <span data-ttu-id="0c717-155">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="0c717-155">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="0c717-156">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="0c717-156">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="0c717-157">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0c717-157">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="0c717-158">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="0c717-158">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="0c717-159">Creare una directory sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c717-159">Create a directory on the service computer.</span></span> <span data-ttu-id="0c717-160">Creare un'applicazione virtuale denominata servicemodelsamples per questa directory usando lo strumento di gestione di Internet Information Services.</span><span class="sxs-lookup"><span data-stu-id="0c717-160">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services management tool.</span></span>  
  
2. <span data-ttu-id="0c717-161">Copiare i file del programma del servizio da \inetpub\wwwroot\servicemodelsamples nella directory virtuale sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c717-161">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="0c717-162">Assicurarsi di copiare i file nella sottodirectory \bin</span><span class="sxs-lookup"><span data-stu-id="0c717-162">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="0c717-163">Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c717-163">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="0c717-164">Creare una directory sul client del servizio per i file binari del client.</span><span class="sxs-lookup"><span data-stu-id="0c717-164">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="0c717-165">Copiare i file di programma del client nella directory del client sul computer relativo</span><span class="sxs-lookup"><span data-stu-id="0c717-165">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="0c717-166">e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.</span><span class="sxs-lookup"><span data-stu-id="0c717-166">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="0c717-167">Sul server, eseguire `setup.bat service` in un prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0c717-167">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="0c717-168">Quando `setup.bat` si esegue con l' `service` argomento viene creato un certificato del servizio con il nome di dominio completo del computer e il certificato del servizio viene esportato in un file denominato Service. cer.</span><span class="sxs-lookup"><span data-stu-id="0c717-168">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="0c717-169">Modificare Web.config per riflettere il nuovo nome del certificato (nell'attributo findValue dell'elemento serviceCertificate) che corrisponde al nome di dominio completo del computer`.`</span><span class="sxs-lookup"><span data-stu-id="0c717-169">Edit Web.config to reflect the new certificate name (in the findValue attribute in the serviceCertificate element) which is the same as the fully-qualified domain name of the computer`.`</span></span>  
  
7. <span data-ttu-id="0c717-170">Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="0c717-170">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="0c717-171">Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c717-171">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="0c717-172">Sul client, eseguire ImportServiceCert. bat in un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0c717-172">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="0c717-173">In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="0c717-173">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="0c717-174">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0c717-174">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="0c717-175">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0c717-175">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="0c717-176">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="0c717-176">To clean up after the sample</span></span>  
  
- <span data-ttu-id="0c717-177">Eseguire Cleanup.bat nella cartella degli esempi dopo che l'esempio è stato completato.</span><span class="sxs-lookup"><span data-stu-id="0c717-177">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0c717-178">Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="0c717-178">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="0c717-179">Se sono stati eseguiti esempi Windows Communication Foundation (WCF) che usano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="0c717-179">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="0c717-180">Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="0c717-180">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
