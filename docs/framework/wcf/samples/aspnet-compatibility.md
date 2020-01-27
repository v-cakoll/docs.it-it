---
title: Compatibilità con ASP.NET
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: 1f1690cdd1a880c852abc04ea8e4958bae2c5432
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728028"
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="f3526-102">Compatibilità con ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f3526-102">ASP.NET Compatibility</span></span>

<span data-ttu-id="f3526-103">In questo esempio viene illustrato come abilitare la modalità di compatibilità ASP.NET in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f3526-103">This sample demonstrates how to enable ASP.NET Compatibility mode in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="f3526-104">I servizi in esecuzione in modalità di compatibilità ASP.NET partecipano completamente alla pipeline dell'applicazione ASP.NET e possono usare le funzionalità di ASP.NET, ad esempio l'autorizzazione file/URL, lo stato della sessione e la classe <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="f3526-104">Services running in ASP.NET Compatibility mode participate fully in the ASP.NET application pipeline and can make use of ASP.NET features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="f3526-105">La classe <xref:System.Web.HttpContext> consente l'accesso a cookie, sessioni e altre funzionalità ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f3526-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other ASP.NET features.</span></span> <span data-ttu-id="f3526-106">Questa modalità richiede che le associazioni usino il trasporto HTTP e che il servizio stesso debba essere ospitato in IIS.</span><span class="sxs-lookup"><span data-stu-id="f3526-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>

<span data-ttu-id="f3526-107">In questo esempio, il client è un'applicazione console (un file eseguibile) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="f3526-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="f3526-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f3526-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="f3526-109">Per l'esecuzione di questo esempio è necessario un pool di applicazioni .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f3526-109">This sample requires a .NET Framework 4 application pool in order to run.</span></span> <span data-ttu-id="f3526-110">Per creare un nuovo pool di applicazioni o modificare il pool di applicazioni predefinito, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="f3526-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>

1. <span data-ttu-id="f3526-111">Aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="f3526-111">Open **Control Panel**.</span></span>  <span data-ttu-id="f3526-112">Aprire l'applet **strumenti di amministrazione** sotto l'intestazione **sistema e sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="f3526-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="f3526-113">Aprire l'applet **gestione Internet Information Services (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="f3526-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>

2. <span data-ttu-id="f3526-114">Espandere TreeView nel riquadro **connessioni** .</span><span class="sxs-lookup"><span data-stu-id="f3526-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="f3526-115">Selezionare il nodo **pool di applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="f3526-115">Select the **Application Pools** node.</span></span>

3. <span data-ttu-id="f3526-116">Per impostare il pool di applicazioni predefinito per l'utilizzo di .NET Framework 4 (che potrebbe causare problemi di incompatibilità con i siti esistenti), fare clic con il pulsante destro del mouse sull'elemento dell'elenco **DefaultAppPool** e selezionare **impostazioni di base.**</span><span class="sxs-lookup"><span data-stu-id="f3526-116">To set the default application pool to use .NET Framework 4 (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="f3526-117">Impostare il pull della **versione di .NET Framework** su **.NET Framework v 4.0.30128** (o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="f3526-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>

4. <span data-ttu-id="f3526-118">Per creare un nuovo pool di applicazioni che usi .NET Framework 4 (per mantenere la compatibilità per altre applicazioni), fare clic con il pulsante destro del mouse sul nodo **pool di applicazioni** e scegliere **Aggiungi pool di applicazioni.**</span><span class="sxs-lookup"><span data-stu-id="f3526-118">To create a new application pool that uses .NET Framework 4 (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="f3526-119">Assegnare un nome al nuovo pool di applicazioni e impostare il pull della **versione di .NET Framework** su **.NET Framework v 4.0.30128** (o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="f3526-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="f3526-120">Dopo aver eseguito la procedura di installazione riportata di seguito, fare clic con il pulsante destro del mouse sull'applicazione **servicemodelsamples** e scegliere **Gestisci applicazione**, **Impostazioni avanzate.**</span><span class="sxs-lookup"><span data-stu-id="f3526-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="f3526-121">Impostare il **pool di applicazioni** sul nuovo pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f3526-121">Set the **Application Pool** to the new application pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3526-122">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="f3526-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f3526-123">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="f3526-123">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f3526-124">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="f3526-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f3526-125">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="f3526-125">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`

<span data-ttu-id="f3526-126">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md), che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="f3526-126">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="f3526-127">Il contratto `ICalculator` è stato modificato al contratto `ICalculatorSession` per consentire l'esecuzione di un set di operazioni mantenendo il risultato della sessione.</span><span class="sxs-lookup"><span data-stu-id="f3526-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculatorSession
{
    [OperationContract]
    void Clear();
    [OperationContract]
    void AddTo(double n);
    [OperationContract]
    void SubtractFrom(double n);
    [OperationContract]
    void MultiplyBy(double n);
    [OperationContract]
    void DivideBy(double n);
    [OperationContract]
    double Result();
}
```

<span data-ttu-id="f3526-128">Usando questa funzionalità il servizio mantiene lo stato di ogni client, mentre vengono chiamate più operazioni del servizio per eseguire un calcolo.</span><span class="sxs-lookup"><span data-stu-id="f3526-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="f3526-129">Il client può recuperare il risultato corrente chiamando `Result` e può azzerare il risultato chiamando `Clear`.</span><span class="sxs-lookup"><span data-stu-id="f3526-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>

<span data-ttu-id="f3526-130">Il servizio usa la sessione ASP.NET per archiviare il risultato per ogni sessione client.</span><span class="sxs-lookup"><span data-stu-id="f3526-130">The service uses the ASP.NET session to store the result for each client session.</span></span> <span data-ttu-id="f3526-131">Questo consente al servizio di mantenere il risultato della sessione per ogni client, su più chiamate al servizio.</span><span class="sxs-lookup"><span data-stu-id="f3526-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>

> [!NOTE]
> <span data-ttu-id="f3526-132">Lo stato della sessione ASP.NET e le sessioni WCF sono molto diversi.</span><span class="sxs-lookup"><span data-stu-id="f3526-132">ASP.NET session state and WCF sessions are very different things.</span></span> <span data-ttu-id="f3526-133">Per informazioni dettagliate sulle sessioni WCF, vedere la [sessione](../../../../docs/framework/wcf/samples/session.md) .</span><span class="sxs-lookup"><span data-stu-id="f3526-133">See [Session](../../../../docs/framework/wcf/samples/session.md) for details on WCF sessions.</span></span>

<span data-ttu-id="f3526-134">Il servizio ha una dipendenza intima dallo stato della sessione ASP.NET e richiede la modalità di compatibilità ASP.NET per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="f3526-134">The service has an intimate dependency on ASP.NET session state and requires ASP.NET compatibility mode to function correctly.</span></span> <span data-ttu-id="f3526-135">Questi requisiti vengono espressi in modo dichiarativo applicando l'attributo `AspNetCompatibilityRequirements`.</span><span class="sxs-lookup"><span data-stu-id="f3526-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>

```csharp
[AspNetCompatibilityRequirements(RequirementsMode =
                       AspNetCompatibilityRequirementsMode.Required)]
public class CalculatorService : ICalculatorSession
{
    double Result
    {  // store result in AspNet Session
       get {
          if (HttpContext.Current.Session["Result"] != null)
             return (double)HttpContext.Current.Session["Result"];
          return 0.0D;
       }
       set
       {
          HttpContext.Current.Session["Result"] = value;
       }
    }
    public void Clear()
    {
        Result = 0.0D;
    }
    public void AddTo(double n)
    {
        Result += n;
    }
    public void SubtractFrom(double n)
    {
        Result -= n;
    }
    public void MultiplyBy(double n)
    {
        Result *= n;
    }
    public void DivideBy(double n)
    {
        Result /= n;
    }
    public double Result()
    {
        return Result;
    }
}
```

<span data-ttu-id="f3526-136">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="f3526-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="f3526-137">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="f3526-137">Press ENTER in the client window to shut down the client.</span></span>

```console
0, + 100, - 50, * 17.65, / 2 = 441.25
Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f3526-138">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="f3526-138">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="f3526-139">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f3526-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="f3526-140">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f3526-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="f3526-141">Una volta compilata la soluzione, eseguire Setup. bat per configurare l'applicazione ServiceModelSamples in IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="f3526-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="f3526-142">La directory ServiceModelSamples dovrebbe ora essere visualizzata come applicazione IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="f3526-142">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="f3526-143">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f3526-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3526-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3526-144">See also</span></span>

- <span data-ttu-id="f3526-145">[Esempi di persistenza e hosting di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="f3526-145">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
