---
title: Sicurezza delle associazioni personalizzate
ms.date: 03/30/2017
ms.assetid: a6383dff-4308-46d2-bc6d-acd4e18b4b8d
ms.openlocfilehash: eb575594cec9ea714578bc104344acc14b00e9df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592463"
---
# <a name="custom-binding-security"></a><span data-ttu-id="ef87c-102">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ef87c-102">Custom Binding Security</span></span>

<span data-ttu-id="ef87c-103">In questo esempio viene illustrato come configurare la sicurezza mediante un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ef87c-103">This sample demonstrates how to configure security by using a custom binding.</span></span> <span data-ttu-id="ef87c-104">Viene mostrato come usare un'associazione personalizzata per abilitare la sicurezza a livello di messaggio insieme con un trasporto sicuro.</span><span class="sxs-lookup"><span data-stu-id="ef87c-104">It shows how to use a custom binding to enable message-level security together with a secure transport.</span></span> <span data-ttu-id="ef87c-105">Questo è utile quando è necessario un trasporto protetto per trasmettere i messaggi tra client e servizio e simultaneamente i messaggi devono essere protetti a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-105">This is useful when a secure transport is required to transmit the messages between client and service and simultaneously the messages must be secure on the message level.</span></span> <span data-ttu-id="ef87c-106">Questa configurazione non è supportata dalle associazioni fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="ef87c-106">This configuration is not supported by system-provided bindings.</span></span>

<span data-ttu-id="ef87c-107">Questo esempio è costituito da un programma di console client (EXE) e un programma di console del servizio (EXE).</span><span class="sxs-lookup"><span data-stu-id="ef87c-107">This sample consists of a client console program (EXE) and a service console program (EXE).</span></span> <span data-ttu-id="ef87c-108">Il servizio implementa un contratto duplex.</span><span class="sxs-lookup"><span data-stu-id="ef87c-108">The service implements a duplex contract.</span></span> <span data-ttu-id="ef87c-109">Il contratto è definito dall'interfaccia `ICalculatorDuplex`, che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione).</span><span class="sxs-lookup"><span data-stu-id="ef87c-109">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="ef87c-110">L'interfaccia `ICalculatorDuplex` consente al client di eseguire operazioni matematiche, calcolando un risultato in una sessione.</span><span class="sxs-lookup"><span data-stu-id="ef87c-110">The `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over a session.</span></span> <span data-ttu-id="ef87c-111">Il servizio potrebbe restituire risultati sull'interfaccia `ICalculatorDuplexCallback` indipendentemente.</span><span class="sxs-lookup"><span data-stu-id="ef87c-111">Independently, the service may return results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="ef87c-112">Poiché occorre definire un contesto per correlare il set di messaggi scambiati fra il client e il servizio, i contratti duplex richiedono una sessione.</span><span class="sxs-lookup"><span data-stu-id="ef87c-112">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span> <span data-ttu-id="ef87c-113">Viene definita un'associazione personalizzata che supporta la comunicazione duplex ed è protetta.</span><span class="sxs-lookup"><span data-stu-id="ef87c-113">A custom binding is defined that supports duplex communication and is secure.</span></span>

> [!NOTE]
> <span data-ttu-id="ef87c-114">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ef87c-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="ef87c-115">La configurazione del servizio definisce un'associazione personalizzata che supporta i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="ef87c-115">The service configuration defines a custom binding that supports the following:</span></span>

- <span data-ttu-id="ef87c-116">Comunicazione TCP protetta tramite il protocollo TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="ef87c-116">TCP communication protected by using the TLS/SSL protocol.</span></span>

- <span data-ttu-id="ef87c-117">Sicurezza dei messaggi di Windows</span><span class="sxs-lookup"><span data-stu-id="ef87c-117">Windows message security.</span></span>

<span data-ttu-id="ef87c-118">La configurazione dell'associazione personalizzata consente il trasporto protetto abilitando simultaneamente la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-118">The custom binding configuration enables secure transport by simultaneously enabling the message-level security.</span></span> <span data-ttu-id="ef87c-119">L'ordinamento degli elementi di associazione è importante per la definizione di un'associazione personalizzata, perché ogni rappresenta un livello nello stack dei canali (vedere [binding personalizzati](../extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="ef87c-119">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../extending/custom-bindings.md)).</span></span> <span data-ttu-id="ef87c-120">L'associazione personalizzata viene definita nei file di configurazione del servizio e del client, come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="ef87c-120">The custom binding is defined in the service and client configuration files, as shown in the following sample configuration.</span></span>

```xml
<bindings>
  <!-- Configure a custom binding. -->
  <customBinding>
    <binding name="Binding1">
      <security authenticationMode="SecureConversation"
                 requireSecurityContextCancellation="true">
      </security>
      <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>
      <sslStreamSecurity requireClientCertificate="false"/>
      <tcpTransport/>
    </binding>
  </customBinding>
</bindings>
```

<span data-ttu-id="ef87c-121">L'associazione personalizzata usa un certificato del servizio per autenticare il servizio sul livello del trasporto e proteggere i messaggi durante la trasmissione tra client e servizio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-121">The custom binding uses a service certificate to authenticate the service on the transport level and to protect the messages during the transmission between client and service.</span></span> <span data-ttu-id="ef87c-122">Ciò viene ottenuto dall'elemento di associazione `sslStreamSecurity`.</span><span class="sxs-lookup"><span data-stu-id="ef87c-122">This is accomplished by the `sslStreamSecurity` binding element.</span></span> <span data-ttu-id="ef87c-123">Il certificato del servizio viene configurato utilizzando un comportamento del servizio come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="ef87c-123">The service's certificate is configured using a service behavior as shown in the following sample configuration.</span></span>

```xml
<behaviors>
    <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
        <serviceMetadata />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>
        </serviceCredentials>
    </behavior>
    </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="ef87c-124">L'associazione personalizzata usa inoltre la sicurezza dei messaggi con tipo di credenziale di Windows, che è il tipo di credenziale predefinito.</span><span class="sxs-lookup"><span data-stu-id="ef87c-124">Additionally, the custom binding uses message security with Windows credential type - this is the default credential type.</span></span> <span data-ttu-id="ef87c-125">Ciò viene ottenuto dall'elemento di associazione `security`.</span><span class="sxs-lookup"><span data-stu-id="ef87c-125">This is accomplished by the `security` binding element.</span></span> <span data-ttu-id="ef87c-126">Sia il client che il servizio vengono autenticati mediante la sicurezza a livello di messaggio se è disponibile l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="ef87c-126">Both client and service are authenticated using message-level security if the Kerberos authentication mechanism is available.</span></span> <span data-ttu-id="ef87c-127">Questa situazione si verifica se l'esempio viene eseguito nell'ambiente di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ef87c-127">This happens if the sample is run in the Active Directory environment.</span></span> <span data-ttu-id="ef87c-128">Se il meccanismo di autenticazione Kerberos non è disponibile, viene usata l'autenticazione NTLM.</span><span class="sxs-lookup"><span data-stu-id="ef87c-128">If the Kerberos authentication mechanism is not available, NTLM authentication is used.</span></span> <span data-ttu-id="ef87c-129">Tale autenticazione viene eseguita tra il client e il servizio, ma non tra il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="ef87c-129">NTLM authenticates the client to the service but does not authenticate the service to the client.</span></span> <span data-ttu-id="ef87c-130">L' `security` elemento di associazione è configurato per l'utilizzo di `SecureConversation` `authenticationType` , che comporta la creazione di una sessione di sicurezza nel client e nel servizio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-130">The `security` binding element is configured to use `SecureConversation` `authenticationType`, which results in the creation of a security session on both the client and the service.</span></span> <span data-ttu-id="ef87c-131">Questa operazione è necessaria per consentire il funzionamento del contratto duplex del servizio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-131">This is required to enable the service's duplex contract to work.</span></span>

<span data-ttu-id="ef87c-132">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="ef87c-132">When you run the sample, the operation requests and responses are displayed in the client's console window.</span></span> <span data-ttu-id="ef87c-133">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="ef87c-133">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate client.
Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

<span data-ttu-id="ef87c-134">Quando si esegue l'esempio, vengono visualizzati i messaggi restituiti al client sull'interfaccia di callback inviata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-134">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="ef87c-135">Una volta completate tutte le operazioni, vengono visualizzati tutti i risultati intermedi, seguiti dall'intera equazione.</span><span class="sxs-lookup"><span data-stu-id="ef87c-135">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="ef87c-136">Premere INVIO per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="ef87c-136">Press ENTER to shut down the client.</span></span>

<span data-ttu-id="ef87c-137">Il file batch Setup.bat incluso consente di configurare il client e il server con il certificato del servizio attinente per eseguire un'applicazione ospitata che richiede sicurezza basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="ef87c-137">The included Setup.bat file enables you to configure the client and server with the relevant service certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="ef87c-138">Questo file batch deve essere modificato per funzionare tra computer diversi o nel caso in cui non sia ospitato.</span><span class="sxs-lookup"><span data-stu-id="ef87c-138">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

<span data-ttu-id="ef87c-139">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch che si applicano a questo esempio, in modo che possano essere modificate per l'esecuzione nella configurazione appropriata:</span><span class="sxs-lookup"><span data-stu-id="ef87c-139">The following provides a brief overview of the different sections of the batch files that apply to this sample so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="ef87c-140">Creazione del certificato server.</span><span class="sxs-lookup"><span data-stu-id="ef87c-140">Creating the server certificate.</span></span>

  <span data-ttu-id="ef87c-141">Le righe seguenti del file Setup.bat creano il certificato server da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ef87c-141">The following lines from the Setup.bat file create the server certificate to be used.</span></span> <span data-ttu-id="ef87c-142">La variabile `%SERVER_NAME%` specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="ef87c-142">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="ef87c-143">Modificare questa variabile per specificare nome del server.</span><span class="sxs-lookup"><span data-stu-id="ef87c-143">Change this variable to specify your own server name.</span></span> <span data-ttu-id="ef87c-144">Questo file batch imposta localhost come valore predefinito del nome del server.</span><span class="sxs-lookup"><span data-stu-id="ef87c-144">This batch file defaults the server name to localhost.</span></span>

  <span data-ttu-id="ef87c-145">Il certificato viene archiviato in CurrentUser per i servizi ospitati su Web.</span><span class="sxs-lookup"><span data-stu-id="ef87c-145">The certificate is stored in the CurrentUser store for the Web-hosted services.</span></span>

  ```bat
  echo ************
  echo Server cert setup starting
  echo %SERVER_NAME%
  echo ************
  echo making server cert
  echo ************
  makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
  ```

- <span data-ttu-id="ef87c-146">Installazione del certificato server nell'archivio certificati attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="ef87c-146">Installing the server certificate into the client's trusted certificate store.</span></span>

  <span data-ttu-id="ef87c-147">Le righe seguenti nel file Setup.bat copiano il certificato server nell'archivio Persone attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="ef87c-147">The following lines in the Setup.bat file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="ef87c-148">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="ef87c-148">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="ef87c-149">Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="ef87c-149">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

  ```console
  certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
  ```

  > [!NOTE]
  > <span data-ttu-id="ef87c-150">Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="ef87c-150">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="ef87c-151">e richiede che la variabile di ambiente MSSDK punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="ef87c-151">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="ef87c-152">Questa variabile di ambiente viene impostata automaticamente in un prompt dei comandi di Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="ef87c-152">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ef87c-153">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ef87c-153">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="ef87c-154">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ef87c-154">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="ef87c-155">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ef87c-155">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="ef87c-156">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ef87c-156">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="ef87c-157">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="ef87c-157">To run the sample on the same computer</span></span>

1. <span data-ttu-id="ef87c-158">Aprire una finestra di Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire Setup. bat dalla cartella di installazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-158">Open a Developer Command Prompt for Visual Studio window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="ef87c-159">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-159">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef87c-160">Il file batch Setup. bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="ef87c-160">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="ef87c-161">La variabile di ambiente PATH impostata nel prompt dei comandi di Visual Studio 2012 punta alla directory che contiene i file eseguibili richiesti dallo script Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="ef87c-161">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

2. <span data-ttu-id="ef87c-162">Avviare Service.exe da \service\bin.</span><span class="sxs-lookup"><span data-stu-id="ef87c-162">Launch Service.exe from \service\bin.</span></span>

3. <span data-ttu-id="ef87c-163">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="ef87c-163">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="ef87c-164">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="ef87c-164">Client activity is displayed on the client console application.</span></span>

4. <span data-ttu-id="ef87c-165">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="ef87c-165">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="ef87c-166">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="ef87c-166">To run the sample across computers</span></span>

1. <span data-ttu-id="ef87c-167">Sul computer del servizio:</span><span class="sxs-lookup"><span data-stu-id="ef87c-167">On the service computer:</span></span>

    1. <span data-ttu-id="ef87c-168">Creare una directory virtuale denominata ServiceModelSamples sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-168">Create a virtual directory named servicemodelsamples on the service computer.</span></span>

    2. <span data-ttu-id="ef87c-169">Copiare i file del programma del servizio da \inetpub\wwwroot\servicemodelsamples nella directory virtuale sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-169">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="ef87c-170">Assicurarsi di copiare i file nella sottodirectory \bin</span><span class="sxs-lookup"><span data-stu-id="ef87c-170">Ensure that you copy the files in the \bin subdirectory.</span></span>

    3. <span data-ttu-id="ef87c-171">Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-171">Copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>

    4. <span data-ttu-id="ef87c-172">Eseguire il comando seguente in un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore: `Setup.bat service` .</span><span class="sxs-lookup"><span data-stu-id="ef87c-172">Run the following command in a Developer Command Prompt for Visual Studio opened with administrator privileges: `Setup.bat service`.</span></span> <span data-ttu-id="ef87c-173">In questo modo verrà creato il certificato del servizio con il nome dell'oggetto che corrisponde al nome del computer in cui viene eseguito il file batch.</span><span class="sxs-lookup"><span data-stu-id="ef87c-173">This creates the service certificate with the subject name matching the name of the computer the batch file was run on.</span></span>

        > [!NOTE]
        > <span data-ttu-id="ef87c-174">Il file batch Setup.bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="ef87c-174">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="ef87c-175">e richiede che la variabile di ambiente PATH punti alla directory in cui è installato SDK.</span><span class="sxs-lookup"><span data-stu-id="ef87c-175">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="ef87c-176">Questa variabile di ambiente viene impostata automaticamente in un prompt dei comandi di Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="ef87c-176">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>

    5. <span data-ttu-id="ef87c-177">Modificare all' [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) interno del file Service. exe. config in modo che corrisponda al nome del soggetto del certificato generato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="ef87c-177">Change the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) inside the Service.exe.config file to reflect the subject name of the certificate generated in the previous step.</span></span>

    6. <span data-ttu-id="ef87c-178">Eseguire Service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ef87c-178">Run Service.exe from a command prompt.</span></span>

2. <span data-ttu-id="ef87c-179">Nel computer client:</span><span class="sxs-lookup"><span data-stu-id="ef87c-179">On the client computer:</span></span>

    1. <span data-ttu-id="ef87c-180">Copiare i file del programma client dalla cartella \client\bin\ sul computer client.</span><span class="sxs-lookup"><span data-stu-id="ef87c-180">Copy the client program files from the \client\bin\ folder to the client computer.</span></span> <span data-ttu-id="ef87c-181">Copiare inoltre il file Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="ef87c-181">Also copy the Cleanup.bat file.</span></span>

    2. <span data-ttu-id="ef87c-182">Eseguire Cleanup.bat per rimuovere i certificati obsoleti dagli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="ef87c-182">Run Cleanup.bat to remove any old certificates from previous samples.</span></span>

    3. <span data-ttu-id="ef87c-183">Esportare il certificato del servizio aprendo un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi amministrativi ed eseguendo il comando seguente sul computer del servizio (sostituire `%SERVER_NAME%` con il nome completo del computer in cui è in esecuzione il servizio):</span><span class="sxs-lookup"><span data-stu-id="ef87c-183">Export the service's certificate by opening a Developer Command Prompt for Visual Studio with administrative privileges, and running the following command on the service computer (substitute `%SERVER_NAME%` with the fully-qualified name of the computer where the service is running):</span></span>

        ```console
        certmgr -put -r LocalMachine -s My -c -n %SERVER_NAME% %SERVER_NAME%.cer
        ```

    4. <span data-ttu-id="ef87c-184">Copiare %NOME_SERVER%.cer sul computer client (sostituire %NOME_SERVER% con il nome completo del computer in cui viene eseguito il servizio).</span><span class="sxs-lookup"><span data-stu-id="ef87c-184">Copy %SERVER_NAME%.cer to the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running).</span></span>

    5. <span data-ttu-id="ef87c-185">Importare il certificato del servizio aprendo un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi amministrativi ed eseguendo il comando seguente nel computer client (sostituire% SERVER_NAME% con il nome completo del computer in cui è in esecuzione il servizio):</span><span class="sxs-lookup"><span data-stu-id="ef87c-185">Import the service's certificate by opening a Developer Command Prompt for Visual Studio with administrative privileges, and running the following command on the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running):</span></span>

        ```console
        certmgr.exe -add -c %SERVER_NAME%.cer -s -r CurrentUser TrustedPeople
        ```

        <span data-ttu-id="ef87c-186">I passaggi c, d ed e non sono necessari se il certificato viene emesso da un'autorità emittente attendibile.</span><span class="sxs-lookup"><span data-stu-id="ef87c-186">Steps c, d, and e are not necessary if the certificate is issued by a Trusted Issuer.</span></span>

    6. <span data-ttu-id="ef87c-187">Modificare il file App.config del client come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ef87c-187">Modify the client’s App.config file as follows:</span></span>

        ```xml
        <client>
            <endpoint name="default"
                address="net.tcp://ReplaceThisWithServiceMachineName:8000/ServiceModelSamples/Service"
                binding="customBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex"
                behaviorConfiguration="CalculatorClientBehavior" />
        </client>
        ```

    7. <span data-ttu-id="ef87c-188">Se il servizio viene eseguito in un account diverso da NetworkService o LocalSystem in un ambiente del dominio, potrebbe essere necessario modificare l'identità dell'endpoint del servizio nel file App.config del client per impostare il nome UPN o SPN appropriato basato sull'account utilizzato per eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="ef87c-188">If the service is running under an account other than the NetworkService or LocalSystem account in a domain environment, you might need to modify the endpoint identity for the service endpoint inside the client's App.config file to set the appropriate UPN or SPN based on the account that is used to run the service.</span></span> <span data-ttu-id="ef87c-189">Per ulteriori informazioni sull'identità dell'endpoint, vedere l'argomento relativo a [identità e autenticazione del servizio](../feature-details/service-identity-and-authentication.md) .</span><span class="sxs-lookup"><span data-stu-id="ef87c-189">For more information about endpoint identity, see the [Service Identity and Authentication](../feature-details/service-identity-and-authentication.md) topic.</span></span>

    8. <span data-ttu-id="ef87c-190">Eseguire Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ef87c-190">Run Client.exe from a command prompt.</span></span>

### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="ef87c-191">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="ef87c-191">To clean up after the sample</span></span>

- <span data-ttu-id="ef87c-192">Eseguire Cleanup.bat nella cartella degli esempi dopo che l'esempio è stato completato.</span><span class="sxs-lookup"><span data-stu-id="ef87c-192">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>
