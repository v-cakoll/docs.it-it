---
title: "Procedura: configurare un'associazione WS-Metadata Exchange personalizzata"
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 6459e3f0cf0ab72af8027bd6802a0e7aa574aece
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635790"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="62469-102">Procedura: configurare un'associazione WS-Metadata Exchange personalizzata</span><span class="sxs-lookup"><span data-stu-id="62469-102">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>

<span data-ttu-id="62469-103">In questo articolo viene illustrato come configurare un'associazione di scambio WS-Metadata personalizzata.</span><span class="sxs-lookup"><span data-stu-id="62469-103">This article explains how to configure a custom WS-Metadata exchange binding.</span></span> <span data-ttu-id="62469-104">Windows Communication Foundation (WCF) include quattro associazioni di metadati definite dal sistema, ma è possibile pubblicare i metadati usando qualsiasi associazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="62469-104">Windows Communication Foundation (WCF) includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="62469-105">In questo articolo viene illustrato `wsHttpBinding`come pubblicare metadati utilizzando il file .</span><span class="sxs-lookup"><span data-stu-id="62469-105">This article shows you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="62469-106">Questa associazione offre la possibilità di esporre i metadati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="62469-106">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="62469-107">Il codice in questo articolo è basato sulla [Guida introduttiva](../samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="62469-107">The code in this article is based on the [Getting Started](../samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="62469-108">Uso di un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="62469-108">Using a configuration file</span></span>  
  
1. <span data-ttu-id="62469-109">Nel file di configurazione del servizio aggiungere un comportamento del servizio che contenga il tag `serviceMetadata`:</span><span class="sxs-lookup"><span data-stu-id="62469-109">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="62469-110">Aggiungere un attributo `behaviorConfiguration` al tag del servizio che fa riferimento a questo nuovo comportamento:</span><span class="sxs-lookup"><span data-stu-id="62469-110">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior" />
    ```  
  
3. <span data-ttu-id="62469-111">Aggiungere un endpoint dei metadati specificando mex come indirizzo, `wsHttpBinding` come associazione e <xref:System.ServiceModel.Description.IMetadataExchange> come contratto:</span><span class="sxs-lookup"><span data-stu-id="62469-111">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. <span data-ttu-id="62469-112">Per verificare che l'endpoint di scambio dei metadati funzioni correttamente, aggiungere un tag endpoint nel file di configurazione client:To verify the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span><span class="sxs-lookup"><span data-stu-id="62469-112">To verify the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. <span data-ttu-id="62469-113">Nel metodo Main() del client creare una nuova istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient>, impostare la proprietà <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> su `true`, chiamare <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> e quindi eseguire un'iterazione nella raccolta di metadati restituita:</span><span class="sxs-lookup"><span data-stu-id="62469-113">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="62469-114">Configurazione mediante codice</span><span class="sxs-lookup"><span data-stu-id="62469-114">Configuring by code</span></span>  
  
1. <span data-ttu-id="62469-115">Creare un'istanza dell'associazione <xref:System.ServiceModel.WSHttpBinding>:</span><span class="sxs-lookup"><span data-stu-id="62469-115">Create a <xref:System.ServiceModel.WSHttpBinding> binding instance:</span></span>  
  
    ```csharp  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. <span data-ttu-id="62469-116">Creare un'istanza di <xref:System.ServiceModel.ServiceHost>:</span><span class="sxs-lookup"><span data-stu-id="62469-116">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```csharp  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. <span data-ttu-id="62469-117">Aggiungere un endpoint di servizio e un'istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior>:</span><span class="sxs-lookup"><span data-stu-id="62469-117">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. <span data-ttu-id="62469-118">Aggiungere un endpoint dello scambio di metadati, specificando la classe <xref:System.ServiceModel.WSHttpBinding> creata in precedenza:</span><span class="sxs-lookup"><span data-stu-id="62469-118">Add a metadata exchange endpoint, specifying the <xref:System.ServiceModel.WSHttpBinding> created earlier:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. <span data-ttu-id="62469-119">Per verificare che l'endpoint dello scambio di metadati stia funzionando correttamente, aggiungere un tag dell'endpoint nel file di configurazione client:</span><span class="sxs-lookup"><span data-stu-id="62469-119">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. <span data-ttu-id="62469-120">Nel metodo Main() del client creare una nuova istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient>, impostare la proprietà <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> su `true`, chiamare <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> e quindi eseguire un'iterazione nella raccolta di metadati restituita:</span><span class="sxs-lookup"><span data-stu-id="62469-120">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="62469-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62469-121">See also</span></span>

- [<span data-ttu-id="62469-122">Comportamento di pubblicazione dei metadati</span><span class="sxs-lookup"><span data-stu-id="62469-122">Metadata Publishing Behavior</span></span>](../samples/metadata-publishing-behavior.md)
- [<span data-ttu-id="62469-123">Recupero di metadati</span><span class="sxs-lookup"><span data-stu-id="62469-123">Retrieve Metadata</span></span>](../samples/retrieve-metadata.md)
- [<span data-ttu-id="62469-124">Metadati</span><span class="sxs-lookup"><span data-stu-id="62469-124">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="62469-125">Pubblicazione di metadati</span><span class="sxs-lookup"><span data-stu-id="62469-125">Publishing Metadata</span></span>](../feature-details/publishing-metadata.md)
- [<span data-ttu-id="62469-126">Pubblicazione di endpoint dei metadati</span><span class="sxs-lookup"><span data-stu-id="62469-126">Publishing Metadata Endpoints</span></span>](../publishing-metadata-endpoints.md)
