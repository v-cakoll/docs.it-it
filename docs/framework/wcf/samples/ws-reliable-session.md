---
title: Sessioni affidabili WS
ms.date: 03/30/2017
helpviewer_keywords:
- Reliable session
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
ms.openlocfilehash: 8898dfedc6ba7deceb5a6e6856b7c7e6ad79d047
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143499"
---
# <a name="ws-reliable-session"></a><span data-ttu-id="2526f-102">Sessioni affidabili WS</span><span class="sxs-lookup"><span data-stu-id="2526f-102">WS Reliable Session</span></span>
<span data-ttu-id="2526f-103">Nell'esempio viene illustrato l'utilizzo delle sessioni affidabili.</span><span class="sxs-lookup"><span data-stu-id="2526f-103">This sample demonstrates the use of reliable sessions.</span></span> <span data-ttu-id="2526f-104">Le sessioni affidabili forniscono supporto per la messaggistica affidabile e le sessioni.</span><span class="sxs-lookup"><span data-stu-id="2526f-104">Reliable sessions provide support for reliable messaging and sessions.</span></span> <span data-ttu-id="2526f-105">La messaggistica affidabile ritenta la comunicazione in caso di errore e consente di specificare assicurazioni del recapito quali l'arrivo nell'ordine di invio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="2526f-105">Reliable messaging retries communication on failure and allows delivery assurances to be specified, such as in-order arrival of messages.</span></span> <span data-ttu-id="2526f-106">Le sessioni gestiscono lo stato per i client tra le chiamate.</span><span class="sxs-lookup"><span data-stu-id="2526f-106">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="2526f-107">L'esempio implementa le sessioni per mantenere lo stato del client e specifica assicurazioni di recapito nell'ordine.</span><span class="sxs-lookup"><span data-stu-id="2526f-107">The sample implements sessions for maintaining client state and specifies in-order delivery assurances.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2526f-108">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2526f-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2526f-109">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2526f-109">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="2526f-110">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2526f-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2526f-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2526f-111">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 <span data-ttu-id="2526f-112">Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="2526f-112">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="2526f-113">Le funzionalità di sessioni affidabili vengono abilitate e configurate nei file di configurazione dell'applicazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="2526f-113">The reliable session features are enabled and configured in the application configuration files for the client and service.</span></span>  
  
 <span data-ttu-id="2526f-114">In questo esempio, il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (.exe).</span><span class="sxs-lookup"><span data-stu-id="2526f-114">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2526f-115">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2526f-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2526f-116">Nell'esempio viene utilizzato il file `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2526f-116">The sample uses the `wsHttpBinding`.</span></span> <span data-ttu-id="2526f-117">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="2526f-117">The binding is specified in the configuration files for both the client and service.</span></span> <span data-ttu-id="2526f-118">Il tipo di associazione è specificato nell'attributo `binding` dell'elemento endpoint, come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="2526f-118">The binding type is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="2526f-119">L'endpoint contiene l'attributo `bindingConfiguration` che fa riferimento a una configurazione di associazione denominata "Binding1".</span><span class="sxs-lookup"><span data-stu-id="2526f-119">The endpoint contains a `bindingConfiguration` attribute that references a binding configuration named "Binding1."</span></span> <span data-ttu-id="2526f-120">La configurazione di binding consente `enabled` sessioni affidabili impostando `true`l'attributo dell'>[ \<reliableSession su](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) .</span><span class="sxs-lookup"><span data-stu-id="2526f-120">The binding configuration enables reliable sessions by setting the `enabled` attribute of the [\<reliableSession>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) to `true`.</span></span> <span data-ttu-id="2526f-121">Le garanzie di recapito per le sessioni ordinate possono essere controllate impostando l'attributo ordinato su `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="2526f-121">Delivery assurances for ordered sessions are controlled by setting the ordered attribute to `true` or `false`.</span></span> <span data-ttu-id="2526f-122">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="2526f-122">The default is `true`.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="2526f-123">La classe dell'implementazione del servizio implementa l'istanza <xref:System.ServiceModel.InstanceContextMode.PerSession> per gestire un'istanza della classe separata per ciascun client, come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2526f-123">The service implementation class implements <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing to maintain a separate class instance for each client, as shown in the following sample code.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
```
  
 <span data-ttu-id="2526f-124">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="2526f-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="2526f-125">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="2526f-125">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2526f-126">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="2526f-126">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2526f-127">Installare ASP.NET 4.0 utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="2526f-127">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="2526f-128">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2526f-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="2526f-129">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2526f-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="2526f-130">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2526f-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
