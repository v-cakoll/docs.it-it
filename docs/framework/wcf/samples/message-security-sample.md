---
title: Esempio sulla sicurezza dei messaggi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82444166-6288-493a-85d4-85f43f134d19
caps.latest.revision: "33"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: a26356346ca3dfea858f286dd32cb08b0e3b3591
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-sample"></a><span data-ttu-id="f6dea-102">Esempio sulla sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="f6dea-102">Message Security Sample</span></span>
<span data-ttu-id="f6dea-103">In questo esempio viene illustrato come implementare un'applicazione che utilizza `basicHttpBinding` e la sicurezza del messaggio.</span><span class="sxs-lookup"><span data-stu-id="f6dea-103">This sample demonstrates how to implement an application that uses the `basicHttpBinding` and message security.</span></span> <span data-ttu-id="f6dea-104">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="f6dea-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6dea-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f6dea-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="f6dea-106">La modalità di sicurezza di `basicHttpBinding` può essere impostata sui valori seguenti: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` e `None`.</span><span class="sxs-lookup"><span data-stu-id="f6dea-106">The security mode of `basicHttpBinding` can be set to the following values: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` and `None`.</span></span> <span data-ttu-id="f6dea-107">Nell'esempio seguente il file App.config, la definizione dell'endpoint specifica l'`basicHttpBinding` e fa riferimento a una configurazione di associazione denominata `Binding1`, come mostra la configurazione di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f6dea-107">In the following sample service App.config file, the endpoint definition specifies the `basicHttpBinding` and references a binding configuration named `Binding1`, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- This endpoint is exposed at the base address provided by -->  
     <!-- host: http://localhost:8000/ServiceModelSamples/service.-->  
     <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>   …  
</system.serviceModel>  
```  
  
 <span data-ttu-id="f6dea-108">I set di configurazione di associazione di `mode` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) a `Message` e imposta il `clientCredentialType` attributo del [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)per `Certificate` come illustrato nell'esempio di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="f6dea-108">The binding configuration sets the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message` and sets the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md) to `Certificate` as shown in the following sample configuration:</span></span>  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
    <binding name="Binding1" >  
      <security mode = "Message">  
        <message clientCredentialType="Certificate"/>  
      </security>  
    </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="f6dea-109">Il certificato utilizzato dal servizio per l'autenticazione con il client è impostato nella sezione comportamenti del file di configurazione sotto l'elemento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="f6dea-109">The certificate that the service uses to authenticate itself to the client is set in the behaviors section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="f6dea-110">Anche la modalità di convalida applicata al certificato utilizzato dal servizio per l'autenticazione con il client è impostata nella sezione comportamenti del file di configurazione sotto l'elemento `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="f6dea-110">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the behaviors section under the `clientCertificate` element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <!--The serviceCredentials behavior allows one to define a -->  
      <!--service certificate. A service certificate is used by a -->  
      <!--client to authenticate the service and provide message -->  
      <!-- protection. This configuration references the "localhost"-->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost"  
               storeLocation="LocalMachine"   
               storeName="My" x509FindType="FindBySubjectName" />  
        <clientCertificate>  
          <!-- Setting the certificateValidationMode to -->  
          <!-- PeerOrChainTrust means that if the certificate -->  
          <!--is in the user's Trusted People store, then it is -->  
          <!-- trusted without performing a validation of the -->  
          <!-- certificate's issuer chain. This setting is used -->  
          <!-- here for convenience so that the sample can be run -->  
          <!-- without having to have certificates issued by a -->  
          <!-- certification authority (CA). -->  
          <!-- This setting is less secure than the default, -->  
          <!-- ChainTrust. The security implications of this -->  
          <!-- setting should be carefully considered before using -->  
          <!-- PeerOrChainTrust in production code. -->  
          <authentication   
                       certificateValidationMode="PeerOrChainTrust" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="f6dea-111">Gli stessi dettagli sull'associazione e la sicurezza sono specificati nel file di configurazione del client.</span><span class="sxs-lookup"><span data-stu-id="f6dea-111">The same binding and security details are specified in the client configuration file.</span></span>  
  
 <span data-ttu-id="f6dea-112">L'identità del chiamante viene visualizzata nella finestra della console del servizio utilizzando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f6dea-112">The identity of the caller is displayed in the service console window by using the following code:</span></span>  
  
```  
Console.WriteLine("Called by {0}", ServiceSecurityContext.Current.PrimaryIdentity.Name);  
```  
  
 <span data-ttu-id="f6dea-113">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="f6dea-113">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="f6dea-114">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="f6dea-114">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="f6dea-115">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="f6dea-115">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="f6dea-116">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f6dea-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f6dea-117">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f6dea-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="f6dea-118">Per eseguire l'esempio sullo stesso computer</span><span class="sxs-lookup"><span data-stu-id="f6dea-118">To run the sample on the same machine</span></span>  
  
1.  <span data-ttu-id="f6dea-119">Eseguire Setup.bat dalla cartella di installazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="f6dea-119">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="f6dea-120">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="f6dea-120">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6dea-121">Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="f6dea-121">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="f6dea-122">e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="f6dea-122">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="f6dea-123">Questa variabile di ambiente viene impostata automaticamente all'interno di un prompt dei comandi di SDK di Windows.</span><span class="sxs-lookup"><span data-stu-id="f6dea-123">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>  
  
2.  <span data-ttu-id="f6dea-124">Eseguire l'applicazione di servizio da \service\bin.</span><span class="sxs-lookup"><span data-stu-id="f6dea-124">Run the service application from \service\bin.</span></span>  
  
3.  <span data-ttu-id="f6dea-125">Eseguire l'applicazione client da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="f6dea-125">Run the client application from \client\bin.</span></span> <span data-ttu-id="f6dea-126">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f6dea-126">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="f6dea-127">Se il client e il servizio non possono comunicare, vedere [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="f6dea-127">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
5.  <span data-ttu-id="f6dea-128">Rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="f6dea-128">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="f6dea-129">Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.</span><span class="sxs-lookup"><span data-stu-id="f6dea-129">Other security samples use the same certificates.</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="f6dea-130">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="f6dea-130">To run the sample across machines</span></span>  
  
1.  <span data-ttu-id="f6dea-131">Creare una directory sul computer del servizio per i file binari del servizio.</span><span class="sxs-lookup"><span data-stu-id="f6dea-131">Create a directory on the service machine for the service binaries.</span></span>  
  
2.  <span data-ttu-id="f6dea-132">Copiare i file di programma del servizio nella directory del server.</span><span class="sxs-lookup"><span data-stu-id="f6dea-132">Copy the service program files to the service directory on the server.</span></span> <span data-ttu-id="f6dea-133">Copiare anche i file Setup.bat, Cleanup.bat e ImportClientCert.bat nel server.</span><span class="sxs-lookup"><span data-stu-id="f6dea-133">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the server.</span></span>  
  
3.  <span data-ttu-id="f6dea-134">Creare una directory sul client del servizio per i file binari del client.</span><span class="sxs-lookup"><span data-stu-id="f6dea-134">Create a directory on the client machine for the client binaries.</span></span>  
  
4.  <span data-ttu-id="f6dea-135">Copiare i file di programma del client nella directory del client sul computer del client</span><span class="sxs-lookup"><span data-stu-id="f6dea-135">Copy the client program files to the client directory on the client machine.</span></span> <span data-ttu-id="f6dea-136">e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.</span><span class="sxs-lookup"><span data-stu-id="f6dea-136">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5.  <span data-ttu-id="f6dea-137">Eseguire `setup.bat service` sul server.</span><span class="sxs-lookup"><span data-stu-id="f6dea-137">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="f6dea-138">Esecuzione `setup.bat` con il `service` argomento crea un certificato di servizio con il nome di dominio completo del computer e il certificato di servizio viene esportato in un file denominato Service.cer.</span><span class="sxs-lookup"><span data-stu-id="f6dea-138">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
6.  <span data-ttu-id="f6dea-139">Modifica Service.exe per riflettere il nuovo nome del certificato (nel `findValue` attributo la [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) elemento) che corrisponde al nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="f6dea-139">Edit Service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) element) which is the same as the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="f6dea-140">Modificare anche il valore dell'indirizzo di base e specificare un nome di computer completo anziché localhost`.`</span><span class="sxs-lookup"><span data-stu-id="f6dea-140">Also change the value of the base address to specify a fully-qualified machine name instead of localhost`.`</span></span>  
  
7.  <span data-ttu-id="f6dea-141">Copiare il file Service.cer dalla directory del servizio alla directory del client sul computer client.</span><span class="sxs-lookup"><span data-stu-id="f6dea-141">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
8.  <span data-ttu-id="f6dea-142">Eseguire `setup.bat client` sul client.</span><span class="sxs-lookup"><span data-stu-id="f6dea-142">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="f6dea-143">Quando si esegue `setup.bat` con l'argomento `client` viene creato un certificato client denominato client.com che viene esportato in un file denominato Client.cer.</span><span class="sxs-lookup"><span data-stu-id="f6dea-143">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="f6dea-144">Nel file Client.exe.config nel computer client, modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="f6dea-144">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="f6dea-145">Tale operazione viene eseguita sostituendo localhost con il nome di dominio completo del server.</span><span class="sxs-lookup"><span data-stu-id="f6dea-145">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="f6dea-146">Modificare inoltre il `findValue` attributo del [ \<defaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) per il nuovo nome di certificato di servizio che è il nome di dominio completo del server.</span><span class="sxs-lookup"><span data-stu-id="f6dea-146">Also change the `findValue` attribute of the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) to the new service certificate name which is the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="f6dea-147">Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.</span><span class="sxs-lookup"><span data-stu-id="f6dea-147">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="f6dea-148">Nel client, eseguire ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="f6dea-148">On the client, run ImportServiceCert.bat.</span></span> <span data-ttu-id="f6dea-149">In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="f6dea-149">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="f6dea-150">Eseguire sul server ImportClientCert.bat. In questo modo il certificato client viene importato dal file Client.cer nell'archivio LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="f6dea-150">On the server, run ImportClientCert.bat, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="f6dea-151">Sul computer del servizio, eseguire Service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f6dea-151">On the service machine, run Service.exe from a command prompt.</span></span>  
  
14. <span data-ttu-id="f6dea-152">Sul computer client, avviare Client.exe da una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f6dea-152">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
    1.  <span data-ttu-id="f6dea-153">Se il client e il servizio non possono comunicare, vedere [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="f6dea-153">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="f6dea-154">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="f6dea-154">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="f6dea-155">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="f6dea-155">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6dea-156">Questo script non rimuove i certificati del servizio su un client quando si esegue questo esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="f6dea-156">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="f6dea-157">Se sono stati eseguiti esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] che utilizzano certificati in più computer, verificare di cancellare i certificati del servizio installati nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="f6dea-157">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="f6dea-158">Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f6dea-158">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f6dea-159">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="f6dea-159">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f6dea-160">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="f6dea-160">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f6dea-161">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6dea-161">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f6dea-162">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="f6dea-162">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\MessageSecurity`  
  
## <a name="see-also"></a><span data-ttu-id="f6dea-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6dea-163">See Also</span></span>
