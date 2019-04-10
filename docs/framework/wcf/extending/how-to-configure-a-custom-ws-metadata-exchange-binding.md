---
title: "Procedura: Configurare un'associazione WS-Metadata Exchange personalizzata"
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 51681e258e6a21b3a7ae604d1c0ef65d320bfb4f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311877"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="8afd2-102">Procedura: Configurare un'associazione WS-Metadata Exchange personalizzata</span><span class="sxs-lookup"><span data-stu-id="8afd2-102">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>
<span data-ttu-id="8afd2-103">In questo argomento viene illustrato come configurare un'associazione WS-Metadata Exchange personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8afd2-103">This topic will explain how to configure a custom WS-Metadata exchange binding.</span></span> <span data-ttu-id="8afd2-104">Windows Communication Foundation (WCF) include quattro associazioni di metadati definito dal sistema, ma è possibile pubblicare metadati usando qualsiasi associazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="8afd2-104">Windows Communication Foundation (WCF) includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="8afd2-105">In questo argomento viene illustrato come pubblicare metadati usando `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="8afd2-105">This topic will show you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="8afd2-106">Questa associazione offre la possibilità di esporre i metadati in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="8afd2-106">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="8afd2-107">Il codice in questo articolo si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="8afd2-107">The code in this article is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="8afd2-108">Uso di un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="8afd2-108">Using a configuration file</span></span>  
  
1. <span data-ttu-id="8afd2-109">Nel file di configurazione del servizio aggiungere un comportamento del servizio che contenga il tag `serviceMetadata`:</span><span class="sxs-lookup"><span data-stu-id="8afd2-109">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="8afd2-110">Aggiungere un attributo `behaviorConfiguration` al tag del servizio che fa riferimento a questo nuovo comportamento:</span><span class="sxs-lookup"><span data-stu-id="8afd2-110">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service        name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">   
    ```  
  
3. <span data-ttu-id="8afd2-111">Aggiungere un endpoint dei metadati specificando mex come indirizzo, `wsHttpBinding` come associazione e <xref:System.ServiceModel.Description.IMetadataExchange> come contratto:</span><span class="sxs-lookup"><span data-stu-id="8afd2-111">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. <span data-ttu-id="8afd2-112">Per verificare che l'endpoint dello scambio di metadati stia funzionando correttamente, aggiungere un tag dell'endpoint nel file di configurazione client:</span><span class="sxs-lookup"><span data-stu-id="8afd2-112">To verify the metadata exchange endpoint is working correctly add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. <span data-ttu-id="8afd2-113">Nel metodo Main() del client creare una nuova istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient>, impostare la proprietà <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> su `true`, chiamare <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> e quindi eseguire un'iterazione nella raccolta di metadati restituita:</span><span class="sxs-lookup"><span data-stu-id="8afd2-113">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="8afd2-114">Configurazione mediante codice</span><span class="sxs-lookup"><span data-stu-id="8afd2-114">Configuring by code</span></span>  
  
1. <span data-ttu-id="8afd2-115">Creare un'istanza dell'associazione <xref:System.ServiceModel.WSHttpBinding>:</span><span class="sxs-lookup"><span data-stu-id="8afd2-115">Create a <xref:System.ServiceModel.WSHttpBinding> binding instance:</span></span>  
  
    ```  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. <span data-ttu-id="8afd2-116">Creare un'istanza di <xref:System.ServiceModel.ServiceHost>:</span><span class="sxs-lookup"><span data-stu-id="8afd2-116">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. <span data-ttu-id="8afd2-117">Aggiungere un endpoint di servizio e un'istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior>:</span><span class="sxs-lookup"><span data-stu-id="8afd2-117">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. <span data-ttu-id="8afd2-118">Aggiungere un endpoint dello scambio di metadati, specificando la classe <xref:System.ServiceModel.WSHttpBinding> creata in precedenza:</span><span class="sxs-lookup"><span data-stu-id="8afd2-118">Add a metadata exchange endpoint, specifying the <xref:System.ServiceModel.WSHttpBinding> created earlier:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. <span data-ttu-id="8afd2-119">Per verificare che l'endpoint dello scambio di metadati stia funzionando correttamente, aggiungere un tag dell'endpoint nel file di configurazione client:</span><span class="sxs-lookup"><span data-stu-id="8afd2-119">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. <span data-ttu-id="8afd2-120">Nel metodo Main() del client creare una nuova istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient>, impostare la proprietà <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> su `true`, chiamare <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> e quindi eseguire un'iterazione nella raccolta di metadati restituita:</span><span class="sxs-lookup"><span data-stu-id="8afd2-120">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8afd2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8afd2-121">See also</span></span>

- [<span data-ttu-id="8afd2-122">Comportamento di pubblicazione dei metadati</span><span class="sxs-lookup"><span data-stu-id="8afd2-122">Metadata Publishing Behavior</span></span>](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
- [<span data-ttu-id="8afd2-123">Recupero di metadati</span><span class="sxs-lookup"><span data-stu-id="8afd2-123">Retrieve Metadata</span></span>](../../../../docs/framework/wcf/samples/retrieve-metadata.md)
- [<span data-ttu-id="8afd2-124">Metadati</span><span class="sxs-lookup"><span data-stu-id="8afd2-124">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="8afd2-125">Pubblicazione di metadati</span><span class="sxs-lookup"><span data-stu-id="8afd2-125">Publishing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)
- [<span data-ttu-id="8afd2-126">Pubblicazione di endpoint dei metadati</span><span class="sxs-lookup"><span data-stu-id="8afd2-126">Publishing Metadata Endpoints</span></span>](../../../../docs/framework/wcf/publishing-metadata-endpoints.md)
