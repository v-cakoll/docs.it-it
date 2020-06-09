---
title: 'Procedura: usare Svcutil.exe per scaricare documenti di metadati'
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: c04b63fa4963a5df0f910da8702643a6484a4edd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596929"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a><span data-ttu-id="79adc-102">Procedura: usare Svcutil.exe per scaricare documenti di metadati</span><span class="sxs-lookup"><span data-stu-id="79adc-102">How to: Use Svcutil.exe to Download Metadata Documents</span></span>
<span data-ttu-id="79adc-103">È possibile utilizzare Svcutil.exe per scaricare i metadati dai servizi in esecuzione e salvarli in file locali.</span><span class="sxs-lookup"><span data-stu-id="79adc-103">You can use Svcutil.exe to download metadata from running services and to save the metadata to local files.</span></span> <span data-ttu-id="79adc-104">Per gli schemi URL HTTP e HTTPS, Svcutil. exe tenta di recuperare i metadati utilizzando WS-MetadataExchange e l' [individuazione del servizio Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="79adc-104">For HTTP and HTTPS URL schemes, Svcutil.exe attempts to retrieve metadata using WS-MetadataExchange and [XML Web Service Discovery](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)).</span></span> <span data-ttu-id="79adc-105">Per tutti gli altri schemi URL, Svcutil.exe utilizza solo WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="79adc-105">For all other URL schemes, Svcutil.exe uses only WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="79adc-106">Per impostazione predefinita, Svcutil.exe utilizza le associazioni definite nella classe <xref:System.ServiceModel.Description.MetadataExchangeBindings>.</span><span class="sxs-lookup"><span data-stu-id="79adc-106">By default, Svcutil.exe uses the bindings defined in the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class.</span></span> <span data-ttu-id="79adc-107">Per configurare l'associazione utilizzata per WS-MetadataExchange, nel file di configurazione di Svcutil.exe (svcutil.exe.config) è necessario definire un endpoint client che utilizza il contratto `IMetadataExchange` e che ha lo stesso nome dello schema URI (Uniform Resource Identifier) dell'indirizzo dell'endpoint dei metadati.</span><span class="sxs-lookup"><span data-stu-id="79adc-107">To configure the binding used for WS-MetadataExchange, you must define a client endpoint in the configuration file for Svcutil.exe (svcutil.exe.config) that uses the `IMetadataExchange` contract and that has the same name as the Uniform Resource Identifier (URI) scheme of the metadata endpoint address.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="79adc-108">Quando si esegue Svcutil. exe per ottenere i metadati per un servizio che espone due contratti di servizio diversi che contengono ciascuno un'operazione con lo stesso nome, Svcutil. exe Visualizza un errore che informa che "non è possibile ottenere metadati da...". Ad esempio, se si dispone di un servizio che espone un contratto di servizio denominato `ICarService` che dispone di un'operazione `Get(Car c)` e lo stesso servizio espone un contratto di servizio denominato `IBookService` che ha un'operazione `Get(Book b)` .</span><span class="sxs-lookup"><span data-stu-id="79adc-108">When running Svcutil.exe to get metadata for a service that exposes two different service contracts that each contain an operation of the same name, Svcutil.exe displays an error saying, "Cannot obtain Metadata from ...." For example, if you have a service that exposes a service contract called `ICarService` that has an operation `Get(Car c)` and the same service exposes a service contract called `IBookService` that has an operation `Get(Book b)`.</span></span> <span data-ttu-id="79adc-109">Per ovviare al problema, effettuare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="79adc-109">To work around this issue, do one of the following:</span></span>
>
> - <span data-ttu-id="79adc-110">Rinominare una delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="79adc-110">Rename one of the operations.</span></span>
> - <span data-ttu-id="79adc-111">Impostare <xref:System.ServiceModel.OperationContractAttribute.Name%2A> su un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="79adc-111">Set the <xref:System.ServiceModel.OperationContractAttribute.Name%2A> to a different name.</span></span>
> - <span data-ttu-id="79adc-112">Impostare uno degli spazi dei nomi delle operazioni su uno spazio dei nomi diverso, utilizzando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="79adc-112">Set one of the operations' namespaces to a different namespace using the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>
  
## <a name="to-download-metadata-using-svcutilexe"></a><span data-ttu-id="79adc-113">Per scaricare metadati utilizzando Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="79adc-113">To download metadata using Svcutil.exe</span></span>  
  
1. <span data-ttu-id="79adc-114">Individuare lo strumento Svcutil.exe nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="79adc-114">Locate the Svcutil.exe tool at the following location:</span></span>  
  
     <span data-ttu-id="79adc-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span><span class="sxs-lookup"><span data-stu-id="79adc-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span></span>  
  
2. <span data-ttu-id="79adc-116">Al prompt dei comandi, avviare lo strumento utilizzando il formato seguente.</span><span class="sxs-lookup"><span data-stu-id="79adc-116">At the command prompt, launch the tool using the following format.</span></span>  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     <span data-ttu-id="79adc-117">Per scaricare i metadati, è necessario specificare l'opzione `/t:metadata`.</span><span class="sxs-lookup"><span data-stu-id="79adc-117">You must specify the `/t:metadata` option to download metadata.</span></span> <span data-ttu-id="79adc-118">In caso contrario, verranno generati il codice client e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="79adc-118">Otherwise, client code and configuration are generated.</span></span>  
  
3. <span data-ttu-id="79adc-119">L' `url` argomento <>specifica l'URL di un endpoint del servizio che fornisce metadati o a un documento di metadati ospitato online.</span><span class="sxs-lookup"><span data-stu-id="79adc-119">The <`url`>argument specifies the URL to a service endpoint that provides metadata or to a metadata document hosted online.</span></span> <span data-ttu-id="79adc-120">L' `epr` argomento <> specifica il percorso di un file XML contenente un WS-Addressing `EndpointAddress` per un endpoint del servizio che supporta WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="79adc-120">The <`epr`> argument specifies the path to an XML file that contains a WS-Addressing `EndpointAddress` for a service endpoint that supports WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="79adc-121">Per altre opzioni sull'uso di questo strumento per il download dei metadati, vedere [ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="79adc-121">For more options about using this tool for metadata download, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79adc-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="79adc-122">Example</span></span>  
 <span data-ttu-id="79adc-123">Con il comando seguente vengono scaricati i documenti di metadati da un servizio in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="79adc-123">The following command downloads metadata documents from a running service.</span></span>  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a><span data-ttu-id="79adc-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79adc-124">See also</span></span>

- [<span data-ttu-id="79adc-125">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="79adc-125">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
