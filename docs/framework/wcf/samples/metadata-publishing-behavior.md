---
title: Comportamento di pubblicazione dei metadati
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
ms.openlocfilehash: dade6d1a53fd99b994fb3c027db4e51392bfdcda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144396"
---
# <a name="metadata-publishing-behavior"></a><span data-ttu-id="abc3c-102">Comportamento di pubblicazione dei metadati</span><span class="sxs-lookup"><span data-stu-id="abc3c-102">Metadata Publishing Behavior</span></span>
<span data-ttu-id="abc3c-103">L'esempio Comportamento di pubblicazione dei metadati illustra come controllare le caratteristiche di pubblicazione dei metadati di un servizio.</span><span class="sxs-lookup"><span data-stu-id="abc3c-103">The Metadata Publishing Behavior sample demonstrates how to control the metadata publishing features of a service.</span></span> <span data-ttu-id="abc3c-104">Per impedire la divulgazione involontaria di metadati del servizio potenzialmente sensibili, la configurazione predefinita per i servizi Windows Communication Foundation (WCF) disabilita la pubblicazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="abc3c-104">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="abc3c-105">Questo comportamento è protetto per impostazione predefinita, ma significa inoltre che non è possibile usare uno strumento di importazione di metadati (ad esempio Svcutil.exe) per generare il codice client necessario per chiamare il servizio, a meno che il comportamento del servizio di pubblicazione dei metadati non venga abilitato in modo esplicito in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="abc3c-105">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="abc3c-106">Per maggior chiarezza, questo esempio illustra come creare un endpoint non protetto per la configurazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="abc3c-106">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="abc3c-107">Tali endpoint sono potenzialmente disponibili per utenti anonimi non autenticati e bisogna fare attenzione prima di distribuirli per garantire che la pubblicazione dei metadati di un servizio sia appropriata.</span><span class="sxs-lookup"><span data-stu-id="abc3c-107">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> <span data-ttu-id="abc3c-108">Vedere l'esempio [di endpoint di metadati protetti personalizzato](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) per un esempio che protegge un endpoint di metadati.</span><span class="sxs-lookup"><span data-stu-id="abc3c-108">See the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample for a sample that secures a metadata endpoint.</span></span>  
  
 <span data-ttu-id="abc3c-109">L'esempio è [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)basato sul Introduzione `ICalculator` , che implementa il contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="abc3c-109">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="abc3c-110">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="abc3c-110">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="abc3c-111">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="abc3c-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="abc3c-112">Affinché un servizio esponga metadati, la classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior> deve essere configurata nel servizio.</span><span class="sxs-lookup"><span data-stu-id="abc3c-112">For a service to expose metadata, the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> must be configured on the service.</span></span> <span data-ttu-id="abc3c-113">Quando questo comportamento è presente, è possibile pubblicare metadati configurando un endpoint per esporre il contratto <xref:System.ServiceModel.Description.IMetadataExchange> come un'implementazione di un protocollo WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="abc3c-113">When this behavior is present, you can publish metadata by configuring an endpoint to expose the <xref:System.ServiceModel.Description.IMetadataExchange> contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="abc3c-114">Per convenienza, a questo contratto è stato dato il nome di configurazione abbreviato seguente: "IMetadataExchange."</span><span class="sxs-lookup"><span data-stu-id="abc3c-114">As a convenience, this contract has been given the abbreviated configuration name of "IMetadataExchange".</span></span> <span data-ttu-id="abc3c-115">In questo esempio viene utilizzata l'associazione `mexHttpBinding`, ovvero un'utile associazione standard equivalente all'associazione `wsHttpBinding` con la modalità di sicurezza impostata su `None`.</span><span class="sxs-lookup"><span data-stu-id="abc3c-115">This sample uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="abc3c-116">Un indirizzo relativo di "mex" viene utilizzato nell'endpoint, che quando viene `http://localhost/servicemodelsamples/service.svc/mex`risolto rispetto all'indirizzo di base dei servizi restituisce un indirizzo endpoint di .</span><span class="sxs-lookup"><span data-stu-id="abc3c-116">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of `http://localhost/servicemodelsamples/service.svc/mex`.</span></span> <span data-ttu-id="abc3c-117">Di seguito viene illustrata la configurazione del comportamento:</span><span class="sxs-lookup"><span data-stu-id="abc3c-117">The following shows the behavior configuration:</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="abc3c-118">Di seguito viene illustrato l'endpoint MEX.</span><span class="sxs-lookup"><span data-stu-id="abc3c-118">The following shows the MEX endpoint.</span></span>  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="abc3c-119">Questo esempio imposta la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> su `true`, che espone anche i metadati del servizio utilizzando HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="abc3c-119">This sample sets the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, which also exposes the service's metadata using HTTP GET.</span></span> <span data-ttu-id="abc3c-120">Per abilitare un endpoint di metadati HTTP GET, il servizio deve avere un indirizzo di base HTTP.</span><span class="sxs-lookup"><span data-stu-id="abc3c-120">To enable an HTTP GET metadata endpoint, the service must have an HTTP base address.</span></span> <span data-ttu-id="abc3c-121">La stringa di query `?wsdl` viene utilizzata sull'indirizzo di base del servizio per accedere ai metadati.</span><span class="sxs-lookup"><span data-stu-id="abc3c-121">The query string `?wsdl` is used on the base address of the service to access the metadata.</span></span> <span data-ttu-id="abc3c-122">Ad esempio, per visualizzare il file WSDL per il `http://localhost/servicemodelsamples/service.svc?wsdl`servizio in un browser Web è necessario utilizzare l'indirizzo .</span><span class="sxs-lookup"><span data-stu-id="abc3c-122">For example, to see the WSDL for the service in a Web browser you would use the address `http://localhost/servicemodelsamples/service.svc?wsdl`.</span></span> <span data-ttu-id="abc3c-123">In alternativa, è possibile utilizzare questo comportamento per esporre metadati su HTTP impostando <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="abc3c-123">Alternatively, you can use this behavior to expose metadata over HTTPS by setting <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> to `true`.</span></span> <span data-ttu-id="abc3c-124">Ciò richiede un indirizzo di base HTTP.</span><span class="sxs-lookup"><span data-stu-id="abc3c-124">This requires an HTTPS base address.</span></span>  
  
 <span data-ttu-id="abc3c-125">Per accedere all'endpoint MEX del servizio, utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="abc3c-125">To access the service's MEX endpoint use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 <span data-ttu-id="abc3c-126">Ciò genera un client basato sui metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="abc3c-126">This generates a client based on the service's metadata.</span></span>  
  
 <span data-ttu-id="abc3c-127">Per accedere ai metadati del servizio tramite HTTP GET, puntare il browser a `http://localhost/servicemodelsamples/service.svc?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="abc3c-127">To access the service's metadata using HTTP GET, point your browser to `http://localhost/servicemodelsamples/service.svc?wsdl`.</span></span>  
  
 <span data-ttu-id="abc3c-128">Se si rimuove questo comportamento e si tenta di aprire il servizio si otterrà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="abc3c-128">If you remove this behavior and try to open the service you get an exception.</span></span> <span data-ttu-id="abc3c-129">Questo errore si verifica perché senza il comportamento, l'endpoint configurato con il contratto `IMetadataExchange` non viene implementato.</span><span class="sxs-lookup"><span data-stu-id="abc3c-129">This error occurs because without the behavior, the endpoint configured with the `IMetadataExchange` contract has no implementation.</span></span>  
  
 <span data-ttu-id="abc3c-130">Se si imposta `HttpGetEnabled` su `false`, si vede la pagina della Guida di CalculatorService invece dei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="abc3c-130">If you set `HttpGetEnabled` to `false`, you see the CalculatorService help page instead of seeing the service's metadata.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="abc3c-131">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="abc3c-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="abc3c-132">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="abc3c-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="abc3c-133">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="abc3c-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="abc3c-134">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="abc3c-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="abc3c-135">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="abc3c-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="abc3c-136">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="abc3c-136">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="abc3c-137">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="abc3c-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="abc3c-138">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="abc3c-138">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
