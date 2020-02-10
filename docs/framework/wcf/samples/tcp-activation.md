---
title: Attivazione TCP
ms.date: 03/30/2017
ms.assetid: bf8c215c-0228-4f4f-85c2-e33794ec09a7
ms.openlocfilehash: 3487d84a63b2838dc1b55fdf3f41b410fcfc2e63
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094878"
---
# <a name="tcp-activation"></a><span data-ttu-id="3686e-102">Attivazione TCP</span><span class="sxs-lookup"><span data-stu-id="3686e-102">TCP Activation</span></span>

<span data-ttu-id="3686e-103">In questo esempio viene illustrato come ospitare un servizio che usa i servizi di attivazione dei processi Windows (WAS) per attivare un servizio che comunica mediante il protocollo net.tcp.</span><span class="sxs-lookup"><span data-stu-id="3686e-103">This sample demonstrates hosting a service that uses Windows Process Activation Services (WAS) to activate a service that communicates over the net.tcp protocol.</span></span> <span data-ttu-id="3686e-104">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="3686e-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3686e-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3686e-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3686e-106">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3686e-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3686e-107">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3686e-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3686e-108">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="3686e-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3686e-109">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3686e-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\TCPActivation`

<span data-ttu-id="3686e-110">L'esempio è costituito da un programma console del client (.exe) e una libreria di servizi (.dll) ospitati in un processo di lavoro attivato dal servizio di attivazione dei processi di Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="3686e-110">The sample consists of a client console program (.exe) and a service library (.dll) hosted in a worker process activated by WAS.</span></span> <span data-ttu-id="3686e-111">L'attività del client è visibile nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="3686e-111">Client activity is visible in the console window.</span></span>

<span data-ttu-id="3686e-112">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="3686e-112">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="3686e-113">Il contratto è definito dall'interfaccia `ICalculator`, che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione), come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3686e-113">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide), as shown in the following sample code:</span></span>

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

<span data-ttu-id="3686e-114">L'implementazione del servizio calcola e restituisce il risultato appropriato:</span><span class="sxs-lookup"><span data-stu-id="3686e-114">The service implementation calculates and returns the appropriate result:</span></span>

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

<span data-ttu-id="3686e-115">L'esempio usa una variante dell'associazione net.tcp con la condivisione delle porte TCP attivata e la sicurezza disattivata.</span><span class="sxs-lookup"><span data-stu-id="3686e-115">The sample uses a variant of the net.tcp binding with TCP port sharing enabled and security turned off.</span></span> <span data-ttu-id="3686e-116">Se si desidera usare un'associazione TCP protetta, impostare la modalità di sicurezza del server sul tipo desiderato ed eseguire di nuovo Svcutil.exe sul client per generare un file di configurazione client aggiornato.</span><span class="sxs-lookup"><span data-stu-id="3686e-116">If you want to use a secured TCP binding, change the server's security mode to the desired setting and re-run Svcutil.exe on the client to generate an update client configuration file.</span></span>

<span data-ttu-id="3686e-117">Nell'esempio seguente viene illustrata la configurazione del servizio:</span><span class="sxs-lookup"><span data-stu-id="3686e-117">The following sample shows the configuration for the service:</span></span>

```xml
<system.serviceModel>

    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: net.tcp://localhost/servicemodelsamples/service.svc  -->
        <endpoint binding="netTcpBinding" bindingConfiguration="PortSharingBinding"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at net.tcp://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexTcpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netTcpBinding>
        <binding name="PortSharingBinding" portSharingEnabled="true">
          <security mode="None" />
        </binding>
      </netTcpBinding>
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

<span data-ttu-id="3686e-118">L'endpoint del client è configurato come illustrato nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3686e-118">The client's endpoint is configured as shown in the following sample code:</span></span>

```xml
<system.serviceModel>
    <bindings>
        <netTcpBinding>
          <binding name="NetTcpBinding_ICalculator">
            <security mode="None"/>
          </binding>
        </netTcpBinding>
    </bindings>
    <client>
        <endpoint address="net.tcp://localhost/servicemodelsamples/service.svc"
            binding="netTcpBinding" bindingConfiguration="NetTcpBinding_ICalculator"
            contract="Microsoft.ServiceModel.Samples.ICalculator" name="NetTcpBinding_ICalculator" />
    </client>
</system.serviceModel>
```

<span data-ttu-id="3686e-119">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="3686e-119">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="3686e-120">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="3686e-120">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3686e-121">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3686e-121">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="3686e-122">Verificare che IIS 7,0 sia installato.</span><span class="sxs-lookup"><span data-stu-id="3686e-122">Ensure that IIS 7.0 is installed.</span></span> <span data-ttu-id="3686e-123">IIS 7,0 è necessario per l'attivazione di WAS.</span><span class="sxs-lookup"><span data-stu-id="3686e-123">IIS 7.0 is required for WAS activation.</span></span>

2. <span data-ttu-id="3686e-124">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3686e-124">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

    <span data-ttu-id="3686e-125">Inoltre, è necessario installare i componenti di attivazione non HTTP WCF:</span><span class="sxs-lookup"><span data-stu-id="3686e-125">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="3686e-126">Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="3686e-126">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="3686e-127">Selezionare **programmi e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="3686e-127">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="3686e-128">Fare clic **su attivazione o disattivazione dei componenti Windows**.</span><span class="sxs-lookup"><span data-stu-id="3686e-128">Click **Turn Windows Components on or Off**.</span></span>

    4. <span data-ttu-id="3686e-129">Espandere il nodo **Microsoft .NET Framework 3,0** e controllare la funzionalità di **attivazione non http Windows Communication Foundation** .</span><span class="sxs-lookup"><span data-stu-id="3686e-129">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="3686e-130">Configurare WAS per supportare l'attivazione TCP.</span><span class="sxs-lookup"><span data-stu-id="3686e-130">Configure WAS to support TCP activation.</span></span>

    <span data-ttu-id="3686e-131">Per maggiore praticità, i due passaggi seguenti vengono implementati in un file batch di nome AddNetTcpSiteBinding.cmd situato nella directory degli esempi.</span><span class="sxs-lookup"><span data-stu-id="3686e-131">As a convenience, the following two steps are implemented in a batch file called AddNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="3686e-132">Per supportare l'attivazione net.tcp, è prima necessario associare il sito Web predefinito a una porta net.tcp.</span><span class="sxs-lookup"><span data-stu-id="3686e-132">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="3686e-133">A tale fine, usare Appcmd.exe, installato con il set di strumenti di gestione di Internet Information Services 7.0 (IIS).</span><span class="sxs-lookup"><span data-stu-id="3686e-133">This can be done using Appcmd.exe, which is installed with the Internet Information Services 7.0 (IIS) management toolset.</span></span> <span data-ttu-id="3686e-134">Da un prompt dei comandi con privilegi di amministratore, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3686e-134">From an administrator-level command prompt, run the following command:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!TIP]
        > <span data-ttu-id="3686e-135">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="3686e-135">This command is a single line of text.</span></span> <span data-ttu-id="3686e-136">Il comando aggiunge un'associazione del sito net.tcp al sito Web predefinito in ascolto sulla porta TCP 808 con un nome host qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="3686e-136">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any hostname.</span></span>

    2. <span data-ttu-id="3686e-137">Anche se tutte le applicazioni all'interno di un sito condividono un'associazione net.tcp comune, ognuna di esse può attivare il supporto net.tcp individualmente.</span><span class="sxs-lookup"><span data-stu-id="3686e-137">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="3686e-138">Per attivare net.tcp per l'applicazione /servicemodelsamples, eseguire il comando seguente da un prompt dei comandi a livello di amministratore:</span><span class="sxs-lookup"><span data-stu-id="3686e-138">To enable net.tcp for the /servicemodelsamples application, run the following command from an administrator-level command prompt:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.tcp
        ```

        > [!NOTE]
        > <span data-ttu-id="3686e-139">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="3686e-139">This command is a single line of text.</span></span> <span data-ttu-id="3686e-140">Questo comando Abilita l'accesso all'applicazione/servicemodelsamples tramite `http://localhost/servicemodelsamples` e `net.tcp://localhost/servicemodelsamples`.</span><span class="sxs-lookup"><span data-stu-id="3686e-140">This command enables the /servicemodelsamples application to be accessed using both `http://localhost/servicemodelsamples` and `net.tcp://localhost/servicemodelsamples`.</span></span>

4. <span data-ttu-id="3686e-141">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3686e-141">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

5. <span data-ttu-id="3686e-142">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3686e-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

    <span data-ttu-id="3686e-143">Rimuovere l'associazione del sito net.tcp aggiunta per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="3686e-143">Remove the net.tcp site binding you added for this sample.</span></span>

    <span data-ttu-id="3686e-144">Per comodità, i due passaggi seguenti vengono implementati in un file batch chiamato RemoveNetTcpSiteBinding.cmd situato nella directory di esempio.</span><span class="sxs-lookup"><span data-stu-id="3686e-144">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="3686e-145">Rimuovere net.tcp dall'elenco dei protocolli attivati tramite il comando seguente da una finestra del prompt dei comandi a livello di amministratore:</span><span class="sxs-lookup"><span data-stu-id="3686e-145">Remove net.tcp from the list of enabled protocols by running the following command from an administrator-level command prompt:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="3686e-146">Questo comando deve essere immesso come una sola riga del testo.</span><span class="sxs-lookup"><span data-stu-id="3686e-146">This command must be entered as a single line of text.</span></span>

    2. <span data-ttu-id="3686e-147">Rimuovere l'associazione del sito net.tcp eseguendo il comando seguente da una finestra del prompt dei comandi a livello di amministratore:</span><span class="sxs-lookup"><span data-stu-id="3686e-147">Remove the net.tcp site binding by running the following command from an administrator-level command prompt:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="3686e-148">Questo comando deve essere digitato come una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="3686e-148">This command must be typed in as a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="3686e-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3686e-149">See also</span></span>

- <span data-ttu-id="3686e-150">[Esempi di persistenza e hosting di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3686e-150">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
