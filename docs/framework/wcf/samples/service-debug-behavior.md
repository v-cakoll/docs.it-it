---
title: Comportamento di debug del servizio
ms.date: 03/30/2017
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
ms.openlocfilehash: 53f21129860c644d09d1a2eb9cb956aecf8ab0ad
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596643"
---
# <a name="service-debug-behavior"></a><span data-ttu-id="803be-102">Comportamento di debug del servizio</span><span class="sxs-lookup"><span data-stu-id="803be-102">Service Debug Behavior</span></span>

<span data-ttu-id="803be-103">In questo esempio viene illustrato come configurare le impostazioni del comportamento di debug.</span><span class="sxs-lookup"><span data-stu-id="803be-103">This sample demonstrates how service debug behavior settings can be configured.</span></span> <span data-ttu-id="803be-104">L'esempio è basato sulla [Introduzione](getting-started-sample.md), che implementa il `ICalculator` contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="803be-104">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="803be-105">Questo esempio definisce in modo esplicito il comportamento di debug del servizio nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="803be-105">This sample explicitly defines service debug behavior in the configuration file.</span></span> <span data-ttu-id="803be-106">Questa operazione può essere eseguita anche nel codice in modo imperativo.</span><span class="sxs-lookup"><span data-stu-id="803be-106">It can also be done imperatively in code.</span></span>

<span data-ttu-id="803be-107">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="803be-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="803be-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="803be-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="803be-109">Il file Web.config per il server definisce il comportamento di debug del servizio per attivare la pagina della Guida e la gestione delle eccezioni come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="803be-109">The Web.config file for the server defines the service debug behavior to enable the help page and exception handling as shown in the following sample.</span></span>

```xml
<behaviors>
     <serviceBehaviors>
         <behavior name="CalculatorServiceBehavior">
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->
         <!-- Please set this to false when deploying -->
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>
         </behavior>
     </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="803be-110">[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md)è l'elemento di configurazione che consente di modificare le proprietà del comportamento di debug del servizio.</span><span class="sxs-lookup"><span data-stu-id="803be-110">[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) is the configuration element that allows changing the service debug behavior properties.</span></span> <span data-ttu-id="803be-111">L'utente può modificare questo comportamento per raggiungere i seguenti obiettivi:</span><span class="sxs-lookup"><span data-stu-id="803be-111">The user can modify this behavior to achieve the following:</span></span>

- <span data-ttu-id="803be-112">Questo consente al servizio di restituire qualsiasi eccezione che viene generata dal codice dell'applicazione anche se l'eccezione non è dichiarata mediante <xref:System.ServiceModel.FaultContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="803be-112">This allows the service to return any exception that is thrown by the application code even if the exception is not declared using the <xref:System.ServiceModel.FaultContractAttribute>.</span></span> <span data-ttu-id="803be-113">Per eseguire questa operazione si imposta `includeExceptionDetailInFaults` su `true`.</span><span class="sxs-lookup"><span data-stu-id="803be-113">It is done by setting `includeExceptionDetailInFaults` to `true`.</span></span> <span data-ttu-id="803be-114">Questa impostazione è utile in caso dell'esecuzione il debug di casi dove il server sta generando un'eccezione imprevista.</span><span class="sxs-lookup"><span data-stu-id="803be-114">This setting is useful when debugging cases where the server is throwing an unexpected exception.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="803be-115">Attivare questa impostazione in un ambiente di produzione può comportare dei rischi.</span><span class="sxs-lookup"><span data-stu-id="803be-115">It is not secure to turn this setting on in a production environment.</span></span> <span data-ttu-id="803be-116">Un'eccezione del server imprevista può avere alcune informazioni che non sono destinate al client, quindi impostare `includeExceptionDetailsInFaults` su `true` potrebbe comportare una perdita di informazioni.</span><span class="sxs-lookup"><span data-stu-id="803be-116">An unexpected server exception may have some information that is not intended for the client and so setting `includeExceptionDetailsInFaults` to `true` might result in an information leak.</span></span>

- <span data-ttu-id="803be-117">[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md)Consente inoltre all'utente di abilitare o disabilitare la pagina della guida.</span><span class="sxs-lookup"><span data-stu-id="803be-117">The [\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) also allows a user to enable or disable the help page.</span></span> <span data-ttu-id="803be-118">Ogni servizio può esporre facoltativamente una pagina della Guida che contiene informazioni sul servizio incluso l'endpoint ottenere WSDL per il servizio.</span><span class="sxs-lookup"><span data-stu-id="803be-118">Each service can optionally expose a help page that contains information about the service including the endpoint to get WSDL for the service.</span></span> <span data-ttu-id="803be-119">A tale fine, impostare `httpHelpPageEnabled` su `true`.</span><span class="sxs-lookup"><span data-stu-id="803be-119">This can be enabled by setting `httpHelpPageEnabled` to `true`.</span></span> <span data-ttu-id="803be-120">Consente di restituire la pagina della Guida a una richiesta GET all'indirizzo di base del servizio.</span><span class="sxs-lookup"><span data-stu-id="803be-120">This enables the help page to be returned to a GET request to the base address of the service.</span></span> <span data-ttu-id="803be-121">È possibile modificare questo indirizzo impostando un altro attributo `httpHelpPageUrl`.</span><span class="sxs-lookup"><span data-stu-id="803be-121">You can change this address by setting another attribute `httpHelpPageUrl`.</span></span> <span data-ttu-id="803be-122">L'operazione può essere protetta utilizzando HTTPS anziché HTTP.</span><span class="sxs-lookup"><span data-stu-id="803be-122">You can make this secure by using HTTPS instead of HTTP.</span></span> <span data-ttu-id="803be-123">A tale fine, impostare `httpsHelpPageEnabled` e `httpsHelpPageUrl`.</span><span class="sxs-lookup"><span data-stu-id="803be-123">This can be done by setting `httpsHelpPageEnabled` and `httpsHelpPageUrl`.</span></span>

<span data-ttu-id="803be-124">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="803be-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="803be-125">Le prime tre operazioni (di addizione, sottrazione e moltiplicazione) devono essere completate.</span><span class="sxs-lookup"><span data-stu-id="803be-125">The first three operations (Add, Subtract and Multiply) must succeed.</span></span> <span data-ttu-id="803be-126">L'ultima operazione (di divisione) ha esito negativo con un'eccezione di divisione per zero.</span><span class="sxs-lookup"><span data-stu-id="803be-126">The last operation ("divide") fails with a division by zero exception.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="803be-127">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="803be-127">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="803be-128">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="803be-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="803be-129">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="803be-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="803be-130">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="803be-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="803be-131">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="803be-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="803be-132">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="803be-132">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="803be-133">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="803be-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="803be-134">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="803be-134">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`
