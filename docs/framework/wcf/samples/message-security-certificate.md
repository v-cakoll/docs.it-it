---
title: Certificato di sicurezza dei messaggi
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
ms.openlocfilehash: 1dec66631368543eecd548ac1ec9bbcda466d746
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584849"
---
# <a name="message-security-certificate"></a><span data-ttu-id="3fd1f-102">Certificato di sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="3fd1f-102">Message Security Certificate</span></span>
<span data-ttu-id="3fd1f-103">In questo esempio viene illustrato come implementare un'applicazione che utilizza WS-Security con l'autenticazione del certificato X.509 v3 per il client e che richiede l'autenticazione del server utilizzando il certificato X.509 v3 del server.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-103">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span> <span data-ttu-id="3fd1f-104">Questo esempio utilizza impostazioni predefinite tali che tutti i messaggi dell'applicazione tra client e server sono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-104">This sample uses default settings such that all application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="3fd1f-105">Questo esempio è basato su [wsHttpBinding](wshttpbinding.md) ed è costituito da un programma di console client e da una libreria di servizi ospitata da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="3fd1f-105">This sample is based on the [WSHttpBinding](wshttpbinding.md) and consists of a client console program and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="3fd1f-106">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-106">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3fd1f-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3fd1f-108">Nell'esempio viene illustrato il controllo dell'autenticazione mediante la configurazione e il modo in cui ottenere l'identità del chiamante dal contesto di sicurezza, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-108">The sample demonstrates controlling authentication by using configuration and how to obtain the caller’s identity from the security context, as shown in the following sample code.</span></span>  

```csharp
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="3fd1f-109">Il servizio espone un endpoint per la comunicazione con il servizio e un endpoint per esporre il documento WSDL del servizio utilizzando il protocollo WS-MetadataExchange, definito utilizzando il file di configurazione (Web.config).</span><span class="sxs-lookup"><span data-stu-id="3fd1f-109">The service exposes one endpoint for communicating with the service and one endpoint for exposing the service's WSDL document using the WS-MetadataExchange protocol, defined by using the configuration file (Web.config).</span></span> <span data-ttu-id="3fd1f-110">L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-110">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="3fd1f-111">L'associazione viene configurata con un [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) elemento standard, che usa per impostazione predefinita la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-111">The binding is configured with a standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) element, which defaults to using message security.</span></span> <span data-ttu-id="3fd1f-112">Questo esempio imposta l'attributo `clientCredentialType` su Certificato per richiedere l'autenticazione del client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-112">This sample sets the `clientCredentialType` attribute to Certificate to require client authentication.</span></span>  
  
```xml  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="3fd1f-113">Il comportamento specifica le credenziali del servizio utilizzate per l'autenticazione del servizio da parte del client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-113">The behavior specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="3fd1f-114">Il nome del soggetto del certificato server è specificato nell' `findValue` attributo dell' [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-114">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="3fd1f-115">La configurazione dell'endpoint client è costituita da un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-115">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="3fd1f-116">L'associazione client viene configurata con modalità di sicurezza e autenticazione appropriate.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-116">The client binding is configured with the appropriate security mode and authentication mode.</span></span> <span data-ttu-id="3fd1f-117">Quando si esegue l'esempio tra più computer, assicurarsi che l'indirizzo dell'endpoint del servizio venga modificato di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-117">When running in a cross-computer scenario, ensure that the service endpoint address is changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="3fd1f-118">L'implementazione client può impostare il certificato tramite il file di configurazione o tramite codice.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-118">The client implementation can set the certificate to use, either through the configuration file or through code.</span></span> <span data-ttu-id="3fd1f-119">Nell'esempio seguente viene illustrato come impostare il certificato in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-119">The following sample shows how to set the certificate to use in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="3fd1f-120">Nell'esempio seguente viene illustrato come chiamare il servizio nel programma.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-120">The following sample shows how to call the service in your program.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```
  
 <span data-ttu-id="3fd1f-121">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="3fd1f-122">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="3fd1f-123">Il file batch Setup.bat incluso negli esempi relativi alla sicurezza dei messaggi consente di configurare client e server con certificati attinenti per eseguire un'applicazione ospitata che richiede sicurezza basata su certificati.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-123">The Setup.bat batch file included with the Message Security samples enables you to configure the client and server with relevant certificates to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="3fd1f-124">Il file batch può essere eseguito in tre modalità.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-124">The batch file can be run in three modes.</span></span> <span data-ttu-id="3fd1f-125">Per l'esecuzione in modalità a computer singolo, digitare **Setup. bat** in una prompt dei comandi per gli sviluppatori per Visual Studio; per la modalità servizio, digitare **Setup. bat service**; e per la modalità client digitare **Setup. bat client**.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-125">To run in single-computer mode type **setup.bat** in a Developer Command Prompt for Visual Studio ; for service mode type **setup.bat service**; and for client mode type **setup.bat client**.</span></span> <span data-ttu-id="3fd1f-126">Utilizzare le modalità client e server quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-126">Use the client and server mode when running the sample across computers.</span></span> <span data-ttu-id="3fd1f-127">Per altre informazioni, vedere la procedura di configurazione alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-127">See the setup procedure at the end of this topic for details.</span></span> <span data-ttu-id="3fd1f-128">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata:</span><span class="sxs-lookup"><span data-stu-id="3fd1f-128">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration:</span></span>  
  
- <span data-ttu-id="3fd1f-129">Creazione del certificato del client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-129">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="3fd1f-130">La riga seguente nel file batch crea il certificato client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-130">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="3fd1f-131">Il nome client specificato viene utilizzato nel nome del soggetto del certificato creato.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-131">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="3fd1f-132">Il certificato viene inserito nell'archivio `My` nel percorso `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-132">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```bat
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
- <span data-ttu-id="3fd1f-133">Installazione del certificato client nell'archivio certificati attendibili del server.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-133">Installing the client certificate into the server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="3fd1f-134">La riga seguente nel file batch copia il certificato client nell'archivio TrustedPeople del server in modo che il server possa prendere le decisioni pertinenti in tema di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-134">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="3fd1f-135">Affinché un certificato installato nell'archivio TrustedPeople sia considerato attendibile da un servizio Windows Communication Foundation (WCF), la modalità di convalida del certificato client deve essere impostata su `PeerOrChainTrust` o `PeerTrust` .</span><span class="sxs-lookup"><span data-stu-id="3fd1f-135">In order for a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust`.</span></span> <span data-ttu-id="3fd1f-136">Per informazioni sull'esecuzione di questa operazione mediante un file di configurazione, vedere l'esempio di configurazione del servizio precedente.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-136">See the previous service configuration sample to learn how this can be done by using a configuration file.</span></span>  
  
    ```bat
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```  
  
- <span data-ttu-id="3fd1f-137">Creazione del certificato server.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-137">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="3fd1f-138">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-138">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="3fd1f-139">La variabile %SERVER_NAME% specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-139">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="3fd1f-140">Il certificato viene archiviato nell'archivio LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-140">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="3fd1f-141">Se il file batch Setup. bat viene eseguito con un argomento di servizio (ad esempio, **Setup. bat service**), il% server_name% contiene il nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-141">If the Setup.bat batch file is run with an argument of service (such as, **setup.bat service**) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="3fd1f-142">In caso contrario, viene usata l'impostazione predefinita localhost.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-142">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="3fd1f-143">Installazione del certificato server nell'archivio certificati attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-143">Installing the server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="3fd1f-144">La riga seguente copia il certificato server nell'archivio Persone attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-144">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="3fd1f-145">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-145">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="3fd1f-146">Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-146">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="3fd1f-147">Concessione delle autorizzazioni sulla chiave privata del certificato.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-147">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="3fd1f-148">Le righe seguenti del file Setup. bat rendono il certificato server archiviato nell'archivio LocalMachine accessibile all'account del processo di lavoro di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-148">The following lines in the Setup.bat file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>  
  
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
    > <span data-ttu-id="3fd1f-149">Se si usa una versione non in lingua inglese di Windows, è necessario modificare il file Setup. bat e sostituire il nome dell'account "NT AUTHORITY\NETWORK SERVICE" con l'equivalente regionale.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-149">If you are using a non-U.S. English edition of Windows, you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3fd1f-150">Gli strumenti utilizzati in questo file batch si trovano in C:\Program Files\Microsoft Visual Studio 8\Common7\tools o C:\Program Files\Microsoft SDKs\Windows\v6 .0 \bin.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-150">The tools used in this batch file are located in either C:\Program Files\Microsoft Visual Studio 8\Common7\tools or C:\Program Files\Microsoft SDKs\Windows\v6.0\bin.</span></span> <span data-ttu-id="3fd1f-151">Una di queste directory deve essere nel percorso di sistema.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-151">One of these directories must be in your system path.</span></span> <span data-ttu-id="3fd1f-152">Se Visual Studio è installato, il modo più semplice per ottenere questa directory nel percorso è aprire il Prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-152">If you have Visual Studio installed, the easiest way to get this directory in your path is to open the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="3fd1f-153">Fare clic su **Start**, quindi selezionare **tutti i programmi**, **Visual Studio 2012**, **strumenti**.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-153">Click **Start**, and then select **All Programs**, **Visual Studio 2012**, **Tools**.</span></span> <span data-ttu-id="3fd1f-154">In questo prompt dei comandi i percorsi adatti sono già configurati.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-154">This command prompt has the appropriate paths already configured.</span></span> <span data-ttu-id="3fd1f-155">In caso contrario, sarà necessario aggiungere manualmente la directory appropriata al percorso.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-155">Otherwise you must add the appropriate directory to your path manually.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3fd1f-156">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-156">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3fd1f-157">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-157">Check for the following (default) directory before continuing:</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3fd1f-158">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-158">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3fd1f-159">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-159">This sample is located in the following directory:</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3fd1f-160">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3fd1f-160">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3fd1f-161">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3fd1f-161">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="3fd1f-162">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3fd1f-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="3fd1f-163">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="3fd1f-163">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="3fd1f-164">Aprire un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire Setup. bat dalla cartella di installazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-164">Open a Developer Command Prompt for Visual Studio  with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="3fd1f-165">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-165">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3fd1f-166">Il file batch Setup. bat è progettato per essere eseguito da un Prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-166">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="3fd1f-167">e richiede che la variabile di ambiente PATH punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-167">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="3fd1f-168">Questa variabile di ambiente viene impostata automaticamente in un Prompt dei comandi per gli sviluppatori per Visual Studio (2010).</span><span class="sxs-lookup"><span data-stu-id="3fd1f-168">This environment variable is automatically set within a Developer Command Prompt for Visual Studio (2010).</span></span>  
  
2. <span data-ttu-id="3fd1f-169">Verificare l'accesso al servizio usando un browser immettendo l'indirizzo `http://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="3fd1f-169">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
3. <span data-ttu-id="3fd1f-170">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-170">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="3fd1f-171">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-171">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="3fd1f-172">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="3fd1f-172">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="3fd1f-173">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="3fd1f-173">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="3fd1f-174">Creare una directory sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-174">Create a directory on the service computer.</span></span> <span data-ttu-id="3fd1f-175">Creare un'applicazione virtuale denominata servicemodelsamples per questa directory usando lo strumento di gestione di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="3fd1f-175">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="3fd1f-176">Copiare i file del programma del servizio da \inetpub\wwwroot\servicemodelsamples nella directory virtuale sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-176">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="3fd1f-177">Assicurarsi di copiare i file nella sottodirectory \bin</span><span class="sxs-lookup"><span data-stu-id="3fd1f-177">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="3fd1f-178">e copiare inoltre i file Setup.bat, Cleanup.bat e ImportClientCert.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-178">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="3fd1f-179">Creare una directory sul client del servizio per i file binari del client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-179">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="3fd1f-180">Copiare i file di programma del client nella directory del client sul computer relativo</span><span class="sxs-lookup"><span data-stu-id="3fd1f-180">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="3fd1f-181">e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-181">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="3fd1f-182">Sul server, eseguire il **servizio Setup. bat** in un prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-182">On the server, run **setup.bat service** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="3fd1f-183">Quando si esegue **Setup. bat** con l'argomento **Service** viene creato un certificato di servizio con il nome di dominio completo del computer e il certificato del servizio viene esportato in un file denominato Service. cer.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-183">Running **setup.bat** with the **service** argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="3fd1f-184">Modificare Web. config per riflettere il nuovo nome del certificato (nell' `findValue` attributo in [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ) che corrisponde al nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-184">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="3fd1f-185">Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-185">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="3fd1f-186">Sul client, eseguire **Setup. bat client** in una prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-186">On the client, run **setup.bat client** in a Developer Command Prompt for Visual Studio with administrator privileges.</span></span> <span data-ttu-id="3fd1f-187">Quando si esegue **Setup. bat** con l'argomento **client** viene creato un certificato client denominato client.com e il certificato client viene esportato in un file denominato client. cer.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-187">Running **setup.bat** with the **client** argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="3fd1f-188">Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="3fd1f-189">Tale operazione viene eseguita sostituendo localhost con il nome di dominio completo del server.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-189">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="3fd1f-190">Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-190">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="3fd1f-191">Sul client, eseguire ImportServiceCert. bat in una Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-191">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="3fd1f-192">In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-192">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="3fd1f-193">Sul server, eseguire ImportClientCert. bat in una Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-193">On the server, run ImportClientCert.bat in a Developer Command Prompt for Visual Studio with administrative privileges.</span></span> <span data-ttu-id="3fd1f-194">In questo modo viene importato il certificato del client dal file Client.cer nell'archivio LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-194">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="3fd1f-195">Sul computer client avviare Client.exe da una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-195">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="3fd1f-196">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="3fd1f-196">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="3fd1f-197">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="3fd1f-197">To clean up after the sample</span></span>  
  
- <span data-ttu-id="3fd1f-198">Eseguire Cleanup.bat nella cartella degli esempi dopo che l'esempio è stato completato.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-198">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3fd1f-199">Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-199">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="3fd1f-200">Se sono stati eseguiti esempi Windows Communication Foundation (WCF) che usano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-200">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="3fd1f-201">Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="3fd1f-201">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
