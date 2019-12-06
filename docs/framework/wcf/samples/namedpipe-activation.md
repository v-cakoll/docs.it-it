---
title: Attivazione di NamedPipe
ms.date: 03/30/2017
ms.assetid: f3c0437d-006c-442e-bfb0-6b29216e4e29
ms.openlocfilehash: a562ec51d35af08f49e89b652670e9a57b0f00c2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837857"
---
# <a name="namedpipe-activation"></a><span data-ttu-id="55a21-102">Attivazione di NamedPipe</span><span class="sxs-lookup"><span data-stu-id="55a21-102">NamedPipe Activation</span></span>

<span data-ttu-id="55a21-103">In questo esempio viene dimostrato l'hosting di un servizio che usa WAS (Windows Process Activation Service) per attivare un servizio che comunica su named pipe.</span><span class="sxs-lookup"><span data-stu-id="55a21-103">This sample demonstrates hosting a service that uses Windows Process Activation Service (WAS) to activate a service that communicates over names pipes.</span></span> <span data-ttu-id="55a21-104">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) e richiede l'esecuzione di Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="55a21-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and requires Windows Vista to run.</span></span>

> [!NOTE]
> <span data-ttu-id="55a21-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="55a21-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55a21-106">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="55a21-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="55a21-107">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="55a21-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="55a21-108">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="55a21-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="55a21-109">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="55a21-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\NamedPipeActivation`

## <a name="sample-details"></a><span data-ttu-id="55a21-110">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="55a21-110">Sample Details</span></span>

<span data-ttu-id="55a21-111">L'esempio è costituito da un programma console client (.exe) e una libreria di servizi (.dll) ospitati in un processo di lavoro attivato dal servizio di attivazione dei processi di Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="55a21-111">The sample consists of a client console program (.exe) and a service library (.dll) hosted in a worker process activated by the Windows Process Activation Services (WAS).</span></span> <span data-ttu-id="55a21-112">L'attività del client è visibile nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="55a21-112">Client activity is visible in the console window.</span></span>

<span data-ttu-id="55a21-113">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="55a21-113">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="55a21-114">Il contratto è definito dall'interfaccia `ICalculator`, che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione), come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="55a21-114">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide), as shown in the following sample code.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="55a21-115">Il client esegue richieste sincrone a una determinata operazione matematica e l'implementazione del servizio calcola e restituisce il risultato appropriato.</span><span class="sxs-lookup"><span data-stu-id="55a21-115">The client makes synchronous requests to a given math operation and the service implementation calculates and returns the appropriate result.</span></span>

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="55a21-116">L'esempio usa un'associazione `netNamedPipeBinding` modificata senza sicurezza.</span><span class="sxs-lookup"><span data-stu-id="55a21-116">The sample uses a modified `netNamedPipeBinding` binding with no security.</span></span> <span data-ttu-id="55a21-117">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="55a21-117">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="55a21-118">Il tipo di associazione per il servizio è specificato nell'attributo `binding` dell'elemento endpoint come mostrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="55a21-118">The binding type for the service is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>

<span data-ttu-id="55a21-119">Se si desidera usare un'associazione named pipe protetta, impostare la modalità di sicurezza del server sul tipo desiderato ed eseguire di nuovo svcutil.exe sul client per ottenere un file di configurazione client aggiornato.</span><span class="sxs-lookup"><span data-stu-id="55a21-119">If you want use a secured named pipe binding, change the server's security mode to the desired security setting and run svcutil.exe again on the client to obtain an updated client configuration file.</span></span>

```xml
<system.serviceModel>
        <services>
            <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">

        <!-- This endpoint is exposed at the base address provided by host: net.pipe://localhost/servicemodelsamples/service.svc  -->
        <endpoint address=""
                  binding="netNamedPipeBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at net.pipe://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexNamedPipeBinding"
                  contract="IMetadataExchange" />
      </service>
        </services>
        <bindings>
            <netNamedPipeBinding>
                <binding name="Binding1" >
                    <security mode = "None">
                    </security>
                </binding >
            </netNamedPipeBinding>
        </bindings>

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>
```

<span data-ttu-id="55a21-120">Le informazioni endpoint del client sono configurate come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="55a21-120">The client’s endpoint information is configured as shown in the following sample code.</span></span>

```xml
<system.serviceModel>

    <client>
      <endpoint name=""
                          address="net.pipe://localhost/servicemodelsamples/service.svc"
                          binding="netNamedPipeBinding"
                          bindingConfiguration="Binding1"
                          contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </client>

    <bindings>

      <!--  Following is the expanded configuration section for a NetNamedPipeBinding.
            Each property is configured with the default value. -->

      <netNamedPipeBinding>
        <binding name="Binding1"
                         maxBufferSize="65536"
                         maxConnections="10">
          <security mode = "None">
          </security>
        </binding >

      </netNamedPipeBinding>
    </bindings>

  </system.serviceModel>
```

<span data-ttu-id="55a21-121">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="55a21-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="55a21-122">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="55a21-122">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="55a21-123">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="55a21-123">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="55a21-124">Verificare che IIS 7,0 sia installato.</span><span class="sxs-lookup"><span data-stu-id="55a21-124">Ensure that IIS 7.0 is installed.</span></span> <span data-ttu-id="55a21-125">IIS 7,0 è necessario per l'attivazione di WAS.</span><span class="sxs-lookup"><span data-stu-id="55a21-125">IIS 7.0 is required for WAS activation.</span></span>

2. <span data-ttu-id="55a21-126">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55a21-126">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

    <span data-ttu-id="55a21-127">Inoltre, è necessario installare i componenti di attivazione non HTTP WCF:</span><span class="sxs-lookup"><span data-stu-id="55a21-127">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="55a21-128">Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="55a21-128">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="55a21-129">Selezionare **programmi e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="55a21-129">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="55a21-130">Fare clic **su attivazione o disattivazione dei componenti Windows**.</span><span class="sxs-lookup"><span data-stu-id="55a21-130">Click **Turn Windows Components on or Off**.</span></span>

    4. <span data-ttu-id="55a21-131">Espandere il nodo **Microsoft .NET Framework 3,0** e controllare la funzionalità di **attivazione non http Windows Communication Foundation** .</span><span class="sxs-lookup"><span data-stu-id="55a21-131">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="55a21-132">Configurare il servizio WAS (Windows Process Activation Service) per supportare l'attivazione di named pipe.</span><span class="sxs-lookup"><span data-stu-id="55a21-132">Configure the Windows Process Activation Service (WAS) to support named pipe activation.</span></span>

    <span data-ttu-id="55a21-133">Per maggiore praticità, i due passaggi seguenti vengono implementati in un file batch di nome AddNetPipeSiteBinding.cmd situato nella directory degli esempi.</span><span class="sxs-lookup"><span data-stu-id="55a21-133">As a convenience, the following two steps are implemented in a batch file called AddNetPipeSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="55a21-134">Per supportare l'attivazione net.pipe, è innanzitutto necessario associare il sito Web predefinito al protocollo net.pipe.</span><span class="sxs-lookup"><span data-stu-id="55a21-134">To support net.pipe activation, the default Web site must first be bound to the net.pipe protocol.</span></span> <span data-ttu-id="55a21-135">A tale fine, usare appcmd.exe, installato con il set di strumenti di gestione di IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="55a21-135">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="55a21-136">Da un prompt dei comandi con privilegi elevati (amministratore), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="55a21-136">From an elevated (administrator) command prompt, run the following command.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.pipe',bindingInformation='*']
        ```

        > [!NOTE]
        > <span data-ttu-id="55a21-137">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="55a21-137">This command is a single line of text.</span></span>

        <span data-ttu-id="55a21-138">Questo comando aggiunge un'associazione di sito net.pipe al sito Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="55a21-138">This command adds a net.pipe site binding to the default Web site.</span></span>

    2. <span data-ttu-id="55a21-139">Anche se tutte le applicazioni all'interno di un sito condividono un'associazione net.pipe comune, ciascuna di esse può abilitare il supporto net.pipe individualmente.</span><span class="sxs-lookup"><span data-stu-id="55a21-139">Although all applications within a site share a common net.pipe binding, each application can enable net.pipe support individually.</span></span> <span data-ttu-id="55a21-140">Per abilitare net.pipe per l'applicazione /servicemodelsamples, eseguire il comando seguente da un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="55a21-140">To enable net.pipe for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.pipe
        ```

        > [!NOTE]
        > <span data-ttu-id="55a21-141">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="55a21-141">This command is a single line of text.</span></span>

        <span data-ttu-id="55a21-142">Questo comando Abilita l'accesso all'applicazione/servicemodelsamples tramite `http://localhost/servicemodelsamples` e `net.tcp://localhost/servicemodelsamples`.</span><span class="sxs-lookup"><span data-stu-id="55a21-142">This command enables the /servicemodelsamples application to be accessed using both `http://localhost/servicemodelsamples` and `net.tcp://localhost/servicemodelsamples`.</span></span>

4. <span data-ttu-id="55a21-143">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55a21-143">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

5. <span data-ttu-id="55a21-144">Rimuovere l'associazione del sito net.pipe aggiunta per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="55a21-144">Remove the net.pipe site binding you added for this sample.</span></span>

    <span data-ttu-id="55a21-145">Per maggiore praticità, i due passaggi seguenti vengono implementati in un file batch denominato RemoveNetPipeSiteBinding.cmd posto nella directory degli esempi:</span><span class="sxs-lookup"><span data-stu-id="55a21-145">As a convenience, the following two steps are implemented in a batch file called RemoveNetPipeSiteBinding.cmd located in the sample directory:</span></span>

    1. <span data-ttu-id="55a21-146">Rimuovere net.tcp dall'elenco dei protocolli abilitati eseguendo il comando seguente da una finestra del prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="55a21-146">Remove net.tcp from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="55a21-147">Questo comando deve essere immesso come una sola riga del testo.</span><span class="sxs-lookup"><span data-stu-id="55a21-147">This command must be entered as a single line of text.</span></span>

    2. <span data-ttu-id="55a21-148">Rimuovere l'associazione del sito net.tcp eseguendo il comando seguente da un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="55a21-148">Remove the net.tcp site binding by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.pipe',bindingInformation='*']
        ```

        > [!NOTE]
        > <span data-ttu-id="55a21-149">Questo comando deve essere digitato come una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="55a21-149">This command must be typed in as a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="55a21-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55a21-150">See also</span></span>

- <span data-ttu-id="55a21-151">[Esempi di persistenza e hosting di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="55a21-151">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
