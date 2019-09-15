---
title: 'Procedura: Usare Svcutil.exe per scaricare documenti di metadati'
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 25840247e59b9dd61cadaa2ee94713240d135f88
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991607"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a><span data-ttu-id="c9487-102">Procedura: Usare Svcutil.exe per scaricare documenti di metadati</span><span class="sxs-lookup"><span data-stu-id="c9487-102">How to: Use Svcutil.exe to Download Metadata Documents</span></span>
<span data-ttu-id="c9487-103">È possibile utilizzare Svcutil.exe per scaricare i metadati dai servizi in esecuzione e salvarli in file locali.</span><span class="sxs-lookup"><span data-stu-id="c9487-103">You can use Svcutil.exe to download metadata from running services and to save the metadata to local files.</span></span> <span data-ttu-id="c9487-104">Per gli schemi URL HTTP e HTTPS, Svcutil. exe tenta di recuperare i metadati utilizzando WS-MetadataExchange e l' [individuazione del servizio Web XML](https://go.microsoft.com/fwlink/?LinkId=94950).</span><span class="sxs-lookup"><span data-stu-id="c9487-104">For HTTP and HTTPS URL schemes, Svcutil.exe attempts to retrieve metadata using WS-MetadataExchange and [XML Web Service Discovery](https://go.microsoft.com/fwlink/?LinkId=94950).</span></span> <span data-ttu-id="c9487-105">Per tutti gli altri schemi URL, Svcutil.exe utilizza solo WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="c9487-105">For all other URL schemes, Svcutil.exe uses only WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="c9487-106">Per impostazione predefinita, Svcutil.exe utilizza le associazioni definite nella classe <xref:System.ServiceModel.Description.MetadataExchangeBindings>.</span><span class="sxs-lookup"><span data-stu-id="c9487-106">By default, Svcutil.exe uses the bindings defined in the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class.</span></span> <span data-ttu-id="c9487-107">Per configurare l'associazione utilizzata per WS-MetadataExchange, nel file di configurazione di Svcutil.exe (svcutil.exe.config) è necessario definire un endpoint client che utilizza il contratto `IMetadataExchange` e che ha lo stesso nome dello schema URI (Uniform Resource Identifier) dell'indirizzo dell'endpoint dei metadati.</span><span class="sxs-lookup"><span data-stu-id="c9487-107">To configure the binding used for WS-MetadataExchange, you must define a client endpoint in the configuration file for Svcutil.exe (svcutil.exe.config) that uses the `IMetadataExchange` contract and that has the same name as the Uniform Resource Identifier (URI) scheme of the metadata endpoint address.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="c9487-108">Quando si esegue Svcutil. exe per ottenere i metadati per un servizio che espone due contratti di servizio diversi che contengono ciascuno un'operazione con lo stesso nome, Svcutil. exe Visualizza un errore che informa che "non è possibile ottenere metadati da...". Ad esempio, se si dispone di un servizio che espone un contratto di `ICarService` servizio denominato che dispone `Get(Car c)` di un'operazione e lo stesso servizio espone un `IBookService` contratto di servizio denominato `Get(Book b)`che ha un'operazione.</span><span class="sxs-lookup"><span data-stu-id="c9487-108">When running Svcutil.exe to get metadata for a service that exposes two different service contracts that each contain an operation of the same name, Svcutil.exe displays an error saying, "Cannot obtain Metadata from ...." For example, if you have a service that exposes a service contract called `ICarService` that has an operation `Get(Car c)` and the same service exposes a service contract called `IBookService` that has an operation `Get(Book b)`.</span></span> <span data-ttu-id="c9487-109">Per risolvere il problema, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9487-109">To work around this issue, do one of the following:</span></span>
>
> - <span data-ttu-id="c9487-110">Rinominare una delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="c9487-110">Rename one of the operations.</span></span>
> - <span data-ttu-id="c9487-111">Impostare <xref:System.ServiceModel.OperationContractAttribute.Name%2A> su un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="c9487-111">Set the <xref:System.ServiceModel.OperationContractAttribute.Name%2A> to a different name.</span></span>
> - <span data-ttu-id="c9487-112">Impostare uno degli spazi dei nomi delle operazioni su uno spazio dei nomi diverso, utilizzando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="c9487-112">Set one of the operations' namespaces to a different namespace using the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>
  
## <a name="to-download-metadata-using-svcutilexe"></a><span data-ttu-id="c9487-113">Per scaricare metadati utilizzando Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="c9487-113">To download metadata using Svcutil.exe</span></span>  
  
1. <span data-ttu-id="c9487-114">Individuare lo strumento Svcutil.exe nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="c9487-114">Locate the Svcutil.exe tool at the following location:</span></span>  
  
     <span data-ttu-id="c9487-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span><span class="sxs-lookup"><span data-stu-id="c9487-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span></span>  
  
2. <span data-ttu-id="c9487-116">Al prompt dei comandi, avviare lo strumento utilizzando il formato seguente.</span><span class="sxs-lookup"><span data-stu-id="c9487-116">At the command prompt, launch the tool using the following format.</span></span>  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     <span data-ttu-id="c9487-117">Per scaricare i metadati, è necessario specificare l'opzione `/t:metadata`.</span><span class="sxs-lookup"><span data-stu-id="c9487-117">You must specify the `/t:metadata` option to download metadata.</span></span> <span data-ttu-id="c9487-118">In caso contrario, verranno generati il codice client e la configurazione.</span><span class="sxs-lookup"><span data-stu-id="c9487-118">Otherwise, client code and configuration are generated.</span></span>  
  
3. <span data-ttu-id="c9487-119">L'argomento`url`< > specifica l'URL di un endpoint del servizio che fornisce metadati o a un documento di metadati ospitato online.</span><span class="sxs-lookup"><span data-stu-id="c9487-119">The <`url`>argument specifies the URL to a service endpoint that provides metadata or to a metadata document hosted online.</span></span> <span data-ttu-id="c9487-120">L'argomento`epr`< > specifica il percorso di un file XML contenente un WS-Addressing `EndpointAddress` per un endpoint del servizio che supporta WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="c9487-120">The <`epr`> argument specifies the path to an XML file that contains a WS-Addressing `EndpointAddress` for a service endpoint that supports WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="c9487-121">Per altre opzioni sull'uso di questo strumento per il download dei metadati, vedere [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c9487-121">For more options about using this tool for metadata download, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9487-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9487-122">Example</span></span>  
 <span data-ttu-id="c9487-123">Con il comando seguente vengono scaricati i documenti di metadati da un servizio in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c9487-123">The following command downloads metadata documents from a running service.</span></span>  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9487-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9487-124">See also</span></span>

- [<span data-ttu-id="c9487-125">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="c9487-125">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
