---
title: Sicurezza dei messaggi nell'accodamento messaggi
ms.date: 03/30/2017
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
ms.openlocfilehash: 7d483ff8252469e95dfbddedf31d1506848e1b45
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584922"
---
# <a name="message-security-over-message-queuing"></a><span data-ttu-id="1712e-102">Sicurezza dei messaggi nell'accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="1712e-102">Message Security over Message Queuing</span></span>
<span data-ttu-id="1712e-103">In questo esempio viene illustrato come implementare un'applicazione che utilizza WS-Security con l'autenticazione del certificato X.509v3 per il client e che richiede l'autenticazione del server utilizzando il certificato X.509v3 del server su MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1712e-103">This sample demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span> <span data-ttu-id="1712e-104">La sicurezza dei messaggi a volte è più efficace per garantire che i messaggi nell'archivio MSMQ siano crittografati e l'applicazione può eseguire direttamente l'autenticazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1712e-104">Message security is sometimes more desirable to ensure that the messages in the MSMQ store stay encrypted and the application can perform its own authentication of the message.</span></span>

 <span data-ttu-id="1712e-105">Questo esempio è basato sull'esempio di [associazione MSMQ transazionale](transacted-msmq-binding.md) .</span><span class="sxs-lookup"><span data-stu-id="1712e-105">This sample is based on the [Transacted MSMQ Binding](transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="1712e-106">I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="1712e-106">The messages are encrypted and signed.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1712e-107">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1712e-107">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="1712e-108">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1712e-108">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="1712e-109">Se il servizio viene eseguito prima, verificherà la presenza della coda.</span><span class="sxs-lookup"><span data-stu-id="1712e-109">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="1712e-110">Se la coda non è presente, il servizio ne creerà una.</span><span class="sxs-lookup"><span data-stu-id="1712e-110">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="1712e-111">È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1712e-111">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="1712e-112">Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="1712e-112">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="1712e-113">Aprire Server Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="1712e-113">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="1712e-114">Espandere la scheda **funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="1712e-114">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="1712e-115">Fare clic con il pulsante destro del mouse su **code di messaggi private**e selezionare **nuova**, **coda privata**.</span><span class="sxs-lookup"><span data-stu-id="1712e-115">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="1712e-116">Controllare la casella **transazionale** .</span><span class="sxs-lookup"><span data-stu-id="1712e-116">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="1712e-117">Immettere `ServiceModelSamplesTransacted` come nome della nuova coda.</span><span class="sxs-lookup"><span data-stu-id="1712e-117">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="1712e-118">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1712e-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="1712e-119">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="1712e-119">To run the sample on the same computer</span></span>

1. <span data-ttu-id="1712e-120">Assicurarsi che il percorso includa la cartella contenente Makecert.exe e FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="1712e-120">Ensure that the path includes the folder that contains Makecert.exe and FindPrivateKey.exe.</span></span>

2. <span data-ttu-id="1712e-121">Eseguire Setup.bat dalla cartella di installazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="1712e-121">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="1712e-122">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="1712e-122">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1712e-123">Assicurarsi di rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="1712e-123">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="1712e-124">Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.</span><span class="sxs-lookup"><span data-stu-id="1712e-124">Other security samples use the same certificates.</span></span>  
  
3. <span data-ttu-id="1712e-125">Avviare Service.exe da \service\bin.</span><span class="sxs-lookup"><span data-stu-id="1712e-125">Launch Service.exe from \service\bin.</span></span>  
  
4. <span data-ttu-id="1712e-126">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="1712e-126">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="1712e-127">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="1712e-127">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="1712e-128">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1712e-128">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="1712e-129">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="1712e-129">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="1712e-130">Copiare i file Setup.bat, Cleanup.bat e ImportClientCert.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="1712e-130">Copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
2. <span data-ttu-id="1712e-131">Creare una directory sul client del servizio per i file binari del client.</span><span class="sxs-lookup"><span data-stu-id="1712e-131">Create a directory on the client computer for the client binaries.</span></span>  
  
3. <span data-ttu-id="1712e-132">Copiare i file di programma del client nella directory del client sul computer relativo</span><span class="sxs-lookup"><span data-stu-id="1712e-132">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="1712e-133">e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.</span><span class="sxs-lookup"><span data-stu-id="1712e-133">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
4. <span data-ttu-id="1712e-134">Eseguire `setup.bat service` sul server.</span><span class="sxs-lookup"><span data-stu-id="1712e-134">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="1712e-135">Quando `setup.bat` si esegue con l' `service` argomento viene creato un certificato del servizio con il nome di dominio completo del computer e il certificato del servizio viene esportato in un file denominato Service. cer.</span><span class="sxs-lookup"><span data-stu-id="1712e-135">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
5. <span data-ttu-id="1712e-136">Modificare Service. exe. config del servizio per riflettere il nuovo nome del certificato (nell' `findValue` attributo in [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ) che corrisponde al nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="1712e-136">Edit service's service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
6. <span data-ttu-id="1712e-137">Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="1712e-137">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
7. <span data-ttu-id="1712e-138">Eseguire `setup.bat client` sul client.</span><span class="sxs-lookup"><span data-stu-id="1712e-138">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="1712e-139">Quando si esegue `setup.bat` con l'argomento `client` viene creato un certificato client denominato client.com che viene esportato in un file denominato Client.cer.</span><span class="sxs-lookup"><span data-stu-id="1712e-139">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
8. <span data-ttu-id="1712e-140">Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="1712e-140">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="1712e-141">Tale operazione viene eseguita sostituendo localhost con il nome di dominio completo del server.</span><span class="sxs-lookup"><span data-stu-id="1712e-141">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  <span data-ttu-id="1712e-142">È inoltre necessario modificare il nome di certificato del servizio in modo che corrisponda al nome di dominio completo del computer del servizio (nell'attributo `findValue` dell'elemento `defaultCertificate` di `serviceCertificate` in `clientCredentials`).</span><span class="sxs-lookup"><span data-stu-id="1712e-142">You must also change the certificate name of the service to be the same as the fully-qualified domain name of the service computer (in the `findValue` attribute in the `defaultCertificate` element of `serviceCertificate` under `clientCredentials`).</span></span>  
  
9. <span data-ttu-id="1712e-143">Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.</span><span class="sxs-lookup"><span data-stu-id="1712e-143">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
10. <span data-ttu-id="1712e-144">Eseguire `ImportServiceCert.bat` sul client.</span><span class="sxs-lookup"><span data-stu-id="1712e-144">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="1712e-145">In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="1712e-145">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
11. <span data-ttu-id="1712e-146">Eseguire `ImportClientCert.bat` sul server. In questo modo il certificato client viene importato dal file Client.cer nell'archivio LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="1712e-146">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="1712e-147">Sul computer del servizio eseguire Service.exe dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="1712e-147">On the service computer, launch Service.exe from the command prompt.</span></span>  
  
13. <span data-ttu-id="1712e-148">Sul computer client avviare Client.exe dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="1712e-148">On the client computer, launch Client.exe from the command prompt.</span></span> <span data-ttu-id="1712e-149">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1712e-149">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="1712e-150">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="1712e-150">To clean up after the sample</span></span>  
  
- <span data-ttu-id="1712e-151">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="1712e-151">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1712e-152">Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="1712e-152">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="1712e-153">Se sono stati eseguiti esempi Windows Communication Foundation (WCF) che usano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="1712e-153">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="1712e-154">Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="1712e-154">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>

## <a name="requirements"></a><span data-ttu-id="1712e-155">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1712e-155">Requirements</span></span>
 <span data-ttu-id="1712e-156">Questo esempio richiede che MSMQ sia installato e in esecuzione,</span><span class="sxs-lookup"><span data-stu-id="1712e-156">This sample requires that MSMQ is installed and running.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1712e-157">Dimostra</span><span class="sxs-lookup"><span data-stu-id="1712e-157">Demonstrates</span></span>
 <span data-ttu-id="1712e-158">Il client crittografa il messaggio con la chiave pubblica del servizio e firma il messaggio utilizzando il relativo certificato.</span><span class="sxs-lookup"><span data-stu-id="1712e-158">The client encrypts the message using the public key of the service and signs the message using its own certificate.</span></span> <span data-ttu-id="1712e-159">Il servizio che legge il messaggio dalla coda autentica il certificato client con il certificato nell'archivio Persone attendibili.</span><span class="sxs-lookup"><span data-stu-id="1712e-159">The service reading the message from the queue authenticates the client certificate with the certificate in its trusted people store.</span></span> <span data-ttu-id="1712e-160">Successivamente decrittografa il messaggio e lo invia all'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="1712e-160">It then decrypts the message and dispatches the message to the service operation.</span></span>

 <span data-ttu-id="1712e-161">Poiché il messaggio di Windows Communication Foundation (WCF) viene portato come payload nel corpo del messaggio MSMQ, il corpo rimane crittografato nell'archivio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1712e-161">Because the Windows Communication Foundation (WCF) message is carried as a payload in the body of the MSMQ message, the body remains encrypted in the MSMQ store.</span></span> <span data-ttu-id="1712e-162">In questo modo il messaggio viene protetto dalla diffusione indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1712e-162">This secures the message from unwanted disclosure of the message.</span></span> <span data-ttu-id="1712e-163">Si noti che il servizio MSMQ non è in grado di identificare se il messaggio trasportato è crittografato.</span><span class="sxs-lookup"><span data-stu-id="1712e-163">Note that MSMQ itself is not aware whether the message it is carrying is encrypted.</span></span>

 <span data-ttu-id="1712e-164">Nell'esempio viene illustrato come l'autenticazione reciproca al livello del messaggio può essere utilizzata con MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1712e-164">The sample demonstrates how mutual authentication at the message level can be used with MSMQ.</span></span> <span data-ttu-id="1712e-165">I certificati vengono scambiati fuori banda.</span><span class="sxs-lookup"><span data-stu-id="1712e-165">The certificates are exchanged out-of-band.</span></span> <span data-ttu-id="1712e-166">Questo comportamento viene applicato sempre nel caso delle applicazioni accodate poiché non è necessario che il client e il servizio siano in esecuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="1712e-166">This is always the case with queued application because the service and the client do not have to be up and running at the same time.</span></span>

## <a name="description"></a><span data-ttu-id="1712e-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1712e-167">Description</span></span>
 <span data-ttu-id="1712e-168">Il codice del client e del servizio di esempio è uguale all'esempio di [associazione MSMQ transazionale](transacted-msmq-binding.md) con una differenza.</span><span class="sxs-lookup"><span data-stu-id="1712e-168">The sample client and service code are the same as the [Transacted MSMQ Binding](transacted-msmq-binding.md) sample with one difference.</span></span> <span data-ttu-id="1712e-169">Il contratto dell'operazione è annotato con il livello di protezione che suggerisce che il messaggio deve essere firmato e crittografato.</span><span class="sxs-lookup"><span data-stu-id="1712e-169">The operation contract is annotated with protection level, which suggests that the message must be signed and encrypted.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="1712e-170">Per assicurare che il messaggio venga protetto utilizzando il token necessario per identificare il servizio e client, il file App.config contiene informazioni sulle credenziali.</span><span class="sxs-lookup"><span data-stu-id="1712e-170">To ensure that the message is secured using the required token to identify the service and client, the App.config contains credential information.</span></span>

 <span data-ttu-id="1712e-171">La configurazione client specifica il certificato del servizio per autenticare il servizio.</span><span class="sxs-lookup"><span data-stu-id="1712e-171">The client configuration specifies the service certificate to authenticate the service.</span></span> <span data-ttu-id="1712e-172">Tale configurazione utilizza l'archivio del computer locale come archivio attendibile per basarsi sulla validità del servizio.</span><span class="sxs-lookup"><span data-stu-id="1712e-172">It uses its LocalMachine store as the trusted store to rely on the validity of the service.</span></span> <span data-ttu-id="1712e-173">Specifica anche il certificato client allegato al messaggio per l'autenticazione del servizio del client.</span><span class="sxs-lookup"><span data-stu-id="1712e-173">It also specifies the client certificate that is attached with the message for service authentication of the client.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <system.serviceModel>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                binding="netMsmqBinding"
                bindingConfiguration="messageSecurityBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"
                behaviorConfiguration="ClientCertificateBehavior" />
    </client>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate"/>
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <!--
        The clientCredentials behavior allows one to define a certificate to present to a service.
        A certificate is used by a client to authenticate itself to the service and provide message integrity.
        This configuration references the "client.com" certificate installed during the setup instructions.
        -->
          <clientCredentials>
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />
            <serviceCertificate>
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
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
</configuration>
```

 <span data-ttu-id="1712e-174">Si noti che la modalità di sicurezza è impostata su Message e ClientCredentialType è impostato su Certificate.</span><span class="sxs-lookup"><span data-stu-id="1712e-174">Note that the security mode is set to Message and the ClientCredentialType is set to Certificate.</span></span>

 <span data-ttu-id="1712e-175">La configurazione del servizio include un comportamento del servizio che specifica le credenziali del servizio che vengono utilizzate quando il client autentica il servizio.</span><span class="sxs-lookup"><span data-stu-id="1712e-175">The service configuration includes a service behavior that specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="1712e-176">Il nome del soggetto del certificato server è specificato nell' `findValue` attributo in [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="1712e-176">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />
  </appSettings>

  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"
          behaviorConfiguration="PurchaseOrderServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
          </baseAddresses>
        </host>
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                  binding="netMsmqBinding"
                  bindingConfiguration="messageSecurityBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="PurchaseOrderServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <!--
               The serviceCredentials behavior allows one to define a service certificate.
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.
               This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
            <clientCertificate>
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
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

</configuration>
```

 <span data-ttu-id="1712e-177">Nell'esempio viene illustrato il controllo dell'autenticazione mediante la configurazione e come ottenere l'identità del chiamante dal contesto di sicurezza, come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1712e-177">The sample demonstrates controlling authentication using configuration, and how to obtain the caller’s identity from the security context, as shown in the following sample code:</span></span>

```csharp
// Service class which implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    private string GetCallerIdentity()
    {
        // The client certificate is not mapped to a Windows identity by default.
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information
        // in the certificate that the client used to authenticate itself to the service.
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }
  //…
}
```

 <span data-ttu-id="1712e-178">Quando viene eseguito, il codice del servizio visualizza l'identificazione client.</span><span class="sxs-lookup"><span data-stu-id="1712e-178">When run, the service code displays the client identification.</span></span> <span data-ttu-id="1712e-179">Di seguito è riportato l'output di esempio del codice del servizio:</span><span class="sxs-lookup"><span data-stu-id="1712e-179">The following is a sample output from the service code:</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

## <a name="comments"></a><span data-ttu-id="1712e-180">Commenti</span><span class="sxs-lookup"><span data-stu-id="1712e-180">Comments</span></span>

- <span data-ttu-id="1712e-181">Creazione del certificato del client.</span><span class="sxs-lookup"><span data-stu-id="1712e-181">Creating the client certificate.</span></span>

     <span data-ttu-id="1712e-182">La riga seguente nel file batch crea il certificato client.</span><span class="sxs-lookup"><span data-stu-id="1712e-182">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="1712e-183">Il nome client specificato viene utilizzato nel nome del soggetto del certificato creato.</span><span class="sxs-lookup"><span data-stu-id="1712e-183">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="1712e-184">Il certificato viene inserito nell'archivio `My` nel percorso `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="1712e-184">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="1712e-185">Installazione del certificato client nell'archivio certificati attendibili del server.</span><span class="sxs-lookup"><span data-stu-id="1712e-185">Installing the client certificate into server’s trusted certificate store.</span></span>

     <span data-ttu-id="1712e-186">La riga seguente nel file batch copia il certificato client nell'archivio TrustedPeople del server in modo che il server possa prendere le decisioni pertinenti in tema di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="1712e-186">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="1712e-187">Affinché un certificato installato nell'archivio TrustedPeople sia considerato attendibile da un servizio Windows Communication Foundation (WCF), è necessario che la modalità di convalida del certificato client sia impostata sul `PeerOrChainTrust` `PeerTrust` valore o.</span><span class="sxs-lookup"><span data-stu-id="1712e-187">For a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust` value.</span></span> <span data-ttu-id="1712e-188">Per informazioni sull'esecuzione di questa operazione mediante un file di configurazione, vedere l'esempio di configurazione del servizio precedente.</span><span class="sxs-lookup"><span data-stu-id="1712e-188">See the previous service configuration sample to learn how this can be done using a configuration file.</span></span>

    ```bat
    echo ************
    echo copying client cert to server's LocalMachine store
    echo ************
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

- <span data-ttu-id="1712e-189">Creazione del certificato server.</span><span class="sxs-lookup"><span data-stu-id="1712e-189">Creating the server certificate.</span></span>

     <span data-ttu-id="1712e-190">Le righe seguenti del file batch Setup.bat creano il certificato server da utilizzare:</span><span class="sxs-lookup"><span data-stu-id="1712e-190">The following lines from the Setup.bat batch file create the server certificate to be used:</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     <span data-ttu-id="1712e-191">La variabile %SERVER_NAME% specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="1712e-191">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="1712e-192">Il certificato viene archiviato nell'archivio LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="1712e-192">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="1712e-193">Se il file batch di installazione viene eseguito con un argomento di servizio (ad esempio, `setup.bat service` ),% server_name% contiene il nome di dominio completo del computer. In caso contrario, il valore predefinito è localhost</span><span class="sxs-lookup"><span data-stu-id="1712e-193">If the setup batch file is run with an argument of service (such as, `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.Otherwise it defaults to localhost</span></span>

- <span data-ttu-id="1712e-194">Installazione del certificato server nell'archivio certificati attendibili del client</span><span class="sxs-lookup"><span data-stu-id="1712e-194">Installing server certificate into the client’s trusted certificate store.</span></span>

     <span data-ttu-id="1712e-195">La riga seguente copia il certificato server nell'archivio Persone attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="1712e-195">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="1712e-196">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="1712e-196">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="1712e-197">Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="1712e-197">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > <span data-ttu-id="1712e-198">Se si usa un'edizione non in lingua inglese di Microsoft Windows, è necessario modificare il file Setup. bat e sostituire il nome dell'account "NT AUTHORITY\NETWORK SERVICE" con l'equivalente regionale.</span><span class="sxs-lookup"><span data-stu-id="1712e-198">If you are using a non-U.S. English edition of Microsoft Windows you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1712e-199">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1712e-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1712e-200">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1712e-200">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1712e-201">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="1712e-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1712e-202">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1712e-202">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`  
