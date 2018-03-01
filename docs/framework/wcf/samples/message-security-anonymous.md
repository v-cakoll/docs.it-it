---
title: Sicurezza dei messaggi anonima
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS Security
ms.assetid: c321cbf9-8c05-4cce-b5a5-4bf7b230ee03
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: d6f3ac3ba51939f319d1d0e98265d7867233f2b6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="message-security-anonymous"></a><span data-ttu-id="b3f92-102">Sicurezza dei messaggi anonima</span><span class="sxs-lookup"><span data-stu-id="b3f92-102">Message Security Anonymous</span></span>
<span data-ttu-id="b3f92-103">Nell'esempio relativo alla sicurezza dei messaggi anonima viene illustrato come implementare un'applicazione di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] che usa la sicurezza a livello di messaggi senza autenticazione del client, ma che richiede l'autenticazione del server usando il certificato X.509 del server.</span><span class="sxs-lookup"><span data-stu-id="b3f92-103">The Message Security Anonymous sample demonstrates how to implement a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application that uses message-level security with no client authentication but that requires server authentication using the server's X.509 certificate.</span></span> <span data-ttu-id="b3f92-104">Tutti i messaggi dell'applicazione tra il client e il server vengono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="b3f92-104">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="b3f92-105">Questo esempio è basato sul [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="b3f92-105">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span> <span data-ttu-id="b3f92-106">Questo esempio è costituito da un programma di console client (.exe) e da una libreria di servizi (.dll) ospitati da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b3f92-106">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="b3f92-107">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="b3f92-107">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3f92-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b3f92-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b3f92-109">Questo esempio aggiunge una nuova operazione all'interfaccia della calcolatrice che restituisce `True` se il client non viene autenticato.</span><span class="sxs-lookup"><span data-stu-id="b3f92-109">This sample adds a new operation to the calculator interface that returns `True` if the client was not authenticated.</span></span>  
  
```  
public class CalculatorService : ICalculator  
{  
    public bool IsCallerAnonymous()  
    {  
        // ServiceSecurityContext.IsAnonymous returns true if the caller is not authenticated.  
        return ServiceSecurityContext.Current.IsAnonymous;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="b3f92-110">Il servizio espone un solo endpoint per comunicare con il servizio che viene definito mediante un file di configurazione (Web.config).</span><span class="sxs-lookup"><span data-stu-id="b3f92-110">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="b3f92-111">L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="b3f92-111">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="b3f92-112">L'associazione viene configurata con un'associazione `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="b3f92-112">The binding is configured with a `wsHttpBinding` binding.</span></span> <span data-ttu-id="b3f92-113">La modalità di sicurezza predefinita per l'associazione `wsHttpBinding` è `Message`.</span><span class="sxs-lookup"><span data-stu-id="b3f92-113">The default security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="b3f92-114">L'attributo `clientCredentialType` è impostato su `None`.</span><span class="sxs-lookup"><span data-stu-id="b3f92-114">The `clientCredentialType` attribute is set to `None`.</span></span>  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
     <!--   
     <!--This configuration defines the security mode as Message and-->  
     <!--the clientCredentialType as None. This mode provides -- >  
     <!--server authentication only using the service certificate.-->  
  
     <binding>  
       <security mode="Message">  
         <message clientCredentialType="None" />  
       </security>  
     </binding>  
    </wsHttpBinding>  
  </bindings>  
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="b3f92-115">Le credenziali da utilizzare per l'autenticazione del servizio vengono specificate nel [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md).</span><span class="sxs-lookup"><span data-stu-id="b3f92-115">The credentials to be used for service authentication are specified in the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md).</span></span> <span data-ttu-id="b3f92-116">Il `SubjectName` del certificato server deve contenere lo stesso valore di quello specificato per l'attributo `findValue`, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b3f92-116">The server certificate must contain the same value for the `SubjectName` as the value specified for the `findValue` attribute as shown in the following sample code.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>  
      <!--   
    The serviceCredentials behavior allows you to define a service certificate.  
    A service certificate is used by a client to authenticate the service and provide message protection.  
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
```  
  
 <span data-ttu-id="b3f92-117">La configurazione dell'endpoint client è costituita da un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto.</span><span class="sxs-lookup"><span data-stu-id="b3f92-117">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="b3f92-118">La modalità di sicurezza del client per l'associazione `wsHttpBinding` è `Message`.</span><span class="sxs-lookup"><span data-stu-id="b3f92-118">The client security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="b3f92-119">L'attributo `clientCredentialType` è impostato su `None`.</span><span class="sxs-lookup"><span data-stu-id="b3f92-119">The `clientCredentialType` attribute is set to `None`.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
             address="http://localhost/servicemodelsamples/service.svc"   
             binding="wsHttpBinding"   
             behaviorConfiguration="ClientCredentialsBehavior"  
             bindingConfiguration="Binding1"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--This configuration defines the security mode as -->  
      <!--Message and the clientCredentialType as None. -->  
      <binding name="Binding1">  
        <security mode = "Message">  
          <message clientCredentialType="None"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>   
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="b3f92-120">L'esempio imposta <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> su <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> per l'autenticazione del certificato del servizio.</span><span class="sxs-lookup"><span data-stu-id="b3f92-120">The sample sets the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> to <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> for authenticating the service's certificate.</span></span> <span data-ttu-id="b3f92-121">Questa operazione viene eseguita nel file App.config del client, nella sezione `behaviors`.</span><span class="sxs-lookup"><span data-stu-id="b3f92-121">This is done in the client's App.config file in the `behaviors` section.</span></span> <span data-ttu-id="b3f92-122">Questo significa che se il certificato si trova nell'archivio Persone attendibili, viene considerato attendibili senza eseguire la convalida della catena di emittenti del certificato.</span><span class="sxs-lookup"><span data-stu-id="b3f92-122">This means that if the certificate is in the user's Trusted People store, then it is trusted without performing a validation of the certificate's issuer chain.</span></span> <span data-ttu-id="b3f92-123">Questa impostazione viene usata nell'esempio per comodità, in modo che possa essere eseguito senza richiedere certificati emessi da un'autorità di certificazione (CA).</span><span class="sxs-lookup"><span data-stu-id="b3f92-123">This setting is used here for convenience so that the sample can be run without requiring certificates issued by a certification authority (CA).</span></span> <span data-ttu-id="b3f92-124">Questa impostazione è meno protetta dell'impostazione predefinita, ChainTrust.</span><span class="sxs-lookup"><span data-stu-id="b3f92-124">This setting is less secure than the default, ChainTrust.</span></span> <span data-ttu-id="b3f92-125">Le implicazioni di sicurezza di questa impostazione devono essere considerate attentamente prima di usare `PeerOrChainTrust` nel codice di produzione.</span><span class="sxs-lookup"><span data-stu-id="b3f92-125">The security implications of this setting should be carefully considered before using `PeerOrChainTrust` in production code.</span></span>  
  
 <span data-ttu-id="b3f92-126">L'implementazione del client consente di aggiungere una chiamata al `IsCallerAnonymous` (metodo) e in caso contrario non è diversa dal [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="b3f92-126">The client implementation adds a call to the `IsCallerAnonymous` method and otherwise does not differ from the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span>  
  
```  
// Create a client with a client endpoint configuration.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity operation.  
Console.WriteLine("IsCallerAnonymous returned: {0}", client.IsCallerAnonymous());  
  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
...  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="b3f92-127">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="b3f92-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b3f92-128">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="b3f92-128">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
IsCallerAnonymous returned: True  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="b3f92-129">Il file batch Setup.bat incluso nell'esempio relativo alla sicurezza dei messaggi anonima consente di configurare il server con un certificato attinente per eseguire un'applicazione ospitata che richiede sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="b3f92-129">The Setup.bat batch file included with the Message Security Anonymous sample enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="b3f92-130">Il file batch può essere eseguito in due modalità.</span><span class="sxs-lookup"><span data-stu-id="b3f92-130">The batch file can be run in two modes.</span></span> <span data-ttu-id="b3f92-131">Per eseguire il file batch in un solo computer, digitare `setup.bat` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b3f92-131">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="b3f92-132">Per eseguirlo in modalità di servizio, digitare `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="b3f92-132">To run it in service mode, type `setup.bat service`.</span></span> <span data-ttu-id="b3f92-133">Usare questa modalità quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="b3f92-133">Use this mode when running the sample across computers.</span></span> <span data-ttu-id="b3f92-134">Per altre informazioni, vedere la procedura di configurazione alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b3f92-134">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="b3f92-135">Gli elementi seguenti forniscono una breve panoramica delle diverse sezioni dei file batch:</span><span class="sxs-lookup"><span data-stu-id="b3f92-135">The following provides a brief overview of the different sections of the batch files:</span></span>  
  
-   <span data-ttu-id="b3f92-136">Creazione del certificato server.</span><span class="sxs-lookup"><span data-stu-id="b3f92-136">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="b3f92-137">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="b3f92-137">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="b3f92-138">La variabile %SERVER_NAME% specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="b3f92-138">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="b3f92-139">Il certificato viene archiviato nell'archivio LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="b3f92-139">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="b3f92-140">Se il file batch di installazione viene eseguito con un argomento di servizio, ad esempio `setup.bat service`, la variabile %SERVER_NAME% conterrà il nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="b3f92-140">If the setup batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="b3f92-141">In caso contrario, viene usata l'impostazione predefinita localhost.</span><span class="sxs-lookup"><span data-stu-id="b3f92-141">Otherwise it defaults to localhost.</span></span>  
  
-   <span data-ttu-id="b3f92-142">Installazione del certificato server nell'archivio certificati attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="b3f92-142">Installing the server certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="b3f92-143">La riga seguente copia il certificato server nell'archivio Persone attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="b3f92-143">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="b3f92-144">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="b3f92-144">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="b3f92-145">Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="b3f92-145">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="b3f92-146">Concessione delle autorizzazioni sulla chiave privata del certificato.</span><span class="sxs-lookup"><span data-stu-id="b3f92-146">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="b3f92-147">Le righe seguenti de file batch Setup.bat rendono il certificato server archiviato nell'archivio LocalMachine accessibile all'account del processo di lavoro [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3f92-147">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] worker process account.</span></span>  
  
    ```  
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%MSSDK%\bin\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr "5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="b3f92-148">Se si usa una versione in lingua diversa dall'inglese (Stati Uniti) di Windows, è necessario modificare il file Setup.bat e sostituire il nome dell'account `NT AUTHORITY\NETWORK SERVICE` con l'equivalente locale.</span><span class="sxs-lookup"><span data-stu-id="b3f92-148">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b3f92-149">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b3f92-149">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b3f92-150">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b3f92-150">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b3f92-151">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b3f92-151">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="b3f92-152">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="b3f92-152">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="b3f92-153">Assicurarsi che il percorso includa la cartella in cui sono situati Makecert.exe e FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="b3f92-153">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>  
  
2.  <span data-ttu-id="b3f92-154">Aprire un prompt dei comandi di Visual Studio con privilegi di amministratore ed eseguire Setup.bat dalla cartella di installazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="b3f92-154">Run Setup.bat from the sample install folder in a Visual Studio command prompt run with administrator privileges.</span></span> <span data-ttu-id="b3f92-155">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="b3f92-155">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3f92-156">Il file batch di installazione è progettato per essere eseguito da un prompt dei comandi di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3f92-156">The setup batch file is designed to be run from a  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]Command Prompt.</span></span> <span data-ttu-id="b3f92-157">e richiede che la variabile di ambiente PATH punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="b3f92-157">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="b3f92-158">Questa variabile di ambiente viene impostata automaticamente in un prompt dei comandi di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3f92-158">This environment variable is automatically set within a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]Command Prompt.</span></span>  
  
3.  <span data-ttu-id="b3f92-159">Verificare l'accesso al servizio immettendo l'indirizzo http://localhost/servicemodelsamples/service.svc in un browser.</span><span class="sxs-lookup"><span data-stu-id="b3f92-159">Verify access to the service using a browser by entering the address http://localhost/servicemodelsamples/service.svc.</span></span>  
  
4.  <span data-ttu-id="b3f92-160">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="b3f92-160">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="b3f92-161">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="b3f92-161">Client activity is displayed on the client console application.</span></span>  
  
5.  <span data-ttu-id="b3f92-162">Se il client e il servizio non sono in grado di comunicare, vedere [suggerimenti per la risoluzione dei problemi](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="b3f92-162">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="b3f92-163">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="b3f92-163">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="b3f92-164">Creare una directory sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="b3f92-164">Create a directory on the service computer.</span></span> <span data-ttu-id="b3f92-165">Creare un'applicazione virtuale denominata servicemodelsamples per questa directory usando lo strumento di gestione di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b3f92-165">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2.  <span data-ttu-id="b3f92-166">Copiare i file del programma del servizio da \inetpub\wwwroot\servicemodelsamples nella directory virtuale sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="b3f92-166">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="b3f92-167">Assicurarsi di copiare i file nella sottodirectory \bin</span><span class="sxs-lookup"><span data-stu-id="b3f92-167">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="b3f92-168">Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="b3f92-168">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="b3f92-169">Creare una directory sul client del servizio per i file binari del client.</span><span class="sxs-lookup"><span data-stu-id="b3f92-169">Create a directory on the client computer for the client binaries.</span></span>  
  
4.  <span data-ttu-id="b3f92-170">Copiare i file di programma del client nella directory del client sul computer relativo</span><span class="sxs-lookup"><span data-stu-id="b3f92-170">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="b3f92-171">e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.</span><span class="sxs-lookup"><span data-stu-id="b3f92-171">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5.  <span data-ttu-id="b3f92-172">Sul server aprire un prompt dei comandi di Visual Studio con privilegi di amministratore ed eseguire `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="b3f92-172">On the server, run `setup.bat service` in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="b3f92-173">Esecuzione `setup.bat` con il `service` argomento crea un certificato di servizio con il nome di dominio completo del computer e il certificato di servizio viene esportato in un file denominato Service.cer.</span><span class="sxs-lookup"><span data-stu-id="b3f92-173">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6.  <span data-ttu-id="b3f92-174">Modificare Web. config per riflettere il nuovo nome del certificato (nel `findValue` attributo la [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), ovvero lo stesso nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="b3f92-174">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7.  <span data-ttu-id="b3f92-175">Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="b3f92-175">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8.  <span data-ttu-id="b3f92-176">Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="b3f92-176">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="b3f92-177">Sul client aprire un prompt dei comandi di Visual Studio con privilegi di amministratore ed eseguire ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="b3f92-177">On the client, run ImportServiceCert.bat in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="b3f92-178">In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="b3f92-178">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="b3f92-179">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b3f92-179">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="b3f92-180">Se il client e il servizio non sono in grado di comunicare, vedere [suggerimenti per la risoluzione dei problemi](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="b3f92-180">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="b3f92-181">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="b3f92-181">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="b3f92-182">Eseguire Cleanup.bat nella cartella degli esempi dopo che l'esempio è stato completato.</span><span class="sxs-lookup"><span data-stu-id="b3f92-182">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3f92-183">Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="b3f92-183">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="b3f92-184">Se sono stati eseguiti esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] che usano certificati tra più computer, verificare di cancellare i certificati del servizio installati nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="b3f92-184">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="b3f92-185">Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`</span><span class="sxs-lookup"><span data-stu-id="b3f92-185">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f92-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3f92-186">See Also</span></span>
