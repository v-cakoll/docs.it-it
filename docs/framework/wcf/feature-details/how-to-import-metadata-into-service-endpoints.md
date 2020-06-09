---
title: 'Procedura: importare metadati negli endpoint del servizio'
ms.date: 03/30/2017
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
ms.openlocfilehash: 1de316b8e91739d5e3e24ff960e2cdfb33cc7fab
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597059"
---
# <a name="how-to-import-metadata-into-service-endpoints"></a><span data-ttu-id="5dec4-102">Procedura: importare metadati negli endpoint del servizio</span><span class="sxs-lookup"><span data-stu-id="5dec4-102">How to: Import Metadata into Service Endpoints</span></span>
<span data-ttu-id="5dec4-103">In questo argomento viene illustrato come importare metadati in una raccolta di endpoint di servizio e utilizzare il servizio definito nella [Introduzione](../samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5dec4-103">This topic explains how to import metadata into a collection of service endpoints and use the service defined in the [Getting Started](../samples/getting-started-sample.md).</span></span> <span data-ttu-id="5dec4-104">In questo argomento viene inoltre illustrato come creare un'applicazione client che importa metadati dal servizio e quindi chiama il metodo `Add` sul servizio.</span><span class="sxs-lookup"><span data-stu-id="5dec4-104">This topic show how to create a client application that imports metadata from the service and then calls the `Add` method on the service.</span></span>  
  
### <a name="to-import-metadata-into-service-endpoints"></a><span data-ttu-id="5dec4-105">Per importare metadati negli endpoint del servizio</span><span class="sxs-lookup"><span data-stu-id="5dec4-105">To import metadata into service endpoints</span></span>  
  
1. <span data-ttu-id="5dec4-106">Dichiarare un oggetto <xref:System.ServiceModel.EndpointAddress> e inizializzarlo con l'URI (Uniform Resource Identifier) per l'indirizzo di scambio dei metadati (MEX, metadata exchange) del servizio.</span><span class="sxs-lookup"><span data-stu-id="5dec4-106">Declare an <xref:System.ServiceModel.EndpointAddress> object and initialize it with the Uniform Resource Identifier (URI) for the metadata exchange (MEX) address of the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2. <span data-ttu-id="5dec4-107">Creare un <xref:System.ServiceModel.Description.MetadataExchangeClient>, passando l'indirizzo MEX, e chiamare <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="5dec4-107">Create a <xref:System.ServiceModel.Description.MetadataExchangeClient>, passing in the MEX address, and call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span></span> <span data-ttu-id="5dec4-108">In questo modo vengono recuperati i metadati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="5dec4-108">This retrieves the metadata from the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3. <span data-ttu-id="5dec4-109">Creare un <xref:System.ServiceModel.Description.WsdlImporter>, passando i metadati precedentemente recuperati, e chiamare <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span><span class="sxs-lookup"><span data-stu-id="5dec4-109">Create a <xref:System.ServiceModel.Description.WsdlImporter>, passing in the metadata previously retrieved, and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span></span> <span data-ttu-id="5dec4-110">In questo modo viene generata una raccolta di oggetti <xref:System.ServiceModel.Description.ContractDescription>.</span><span class="sxs-lookup"><span data-stu-id="5dec4-110">This generates a collection of <xref:System.ServiceModel.Description.ContractDescription> objects.</span></span> <span data-ttu-id="5dec4-111">È anche possibile chiamare <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> o <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5dec4-111">You could also call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> or <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, depending upon your needs.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    > <span data-ttu-id="5dec4-112">Dopo avere importato i metadati, non sarà possibile creare un canale client o esportare i metadati</span><span class="sxs-lookup"><span data-stu-id="5dec4-112">After you have imported the metadata, you will not be able to create a client channel or export the metadata.</span></span> <span data-ttu-id="5dec4-113">poiché in questa fase non è disponibile alcuna informazione sul tipo.</span><span class="sxs-lookup"><span data-stu-id="5dec4-113">This is because no type information is available at this point.</span></span> <span data-ttu-id="5dec4-114">Le informazioni sul tipo sono necessarie per interagire con il servizio o esportare i metadati.</span><span class="sxs-lookup"><span data-stu-id="5dec4-114">Type information is required to actually interact with the service or export metadata.</span></span> <span data-ttu-id="5dec4-115">Per generare informazioni sul tipo, è necessario generare il codice mostrato nei passaggi 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="5dec4-115">To generate the type information, you need to generate code, shown in steps 4 and 5.</span></span> <span data-ttu-id="5dec4-116">In alternativa, è possibile usare la classe di supporto <xref:System.ServiceModel.Description.MetadataResolver>.</span><span class="sxs-lookup"><span data-stu-id="5dec4-116">Alternatively, you could use the <xref:System.ServiceModel.Description.MetadataResolver> helper class.</span></span> <span data-ttu-id="5dec4-117">Per altre informazioni, vedere [procedura: usare classe MetadataResolver per ottenere dinamicamente i metadati di associazione](how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="5dec4-117">For more information, see [How to: Use MetadataResolver to Obtain Binding Metadata Dynamically](how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span></span>  
  
4. <span data-ttu-id="5dec4-118">Generare informazioni sul tipo per ogni contratto.</span><span class="sxs-lookup"><span data-stu-id="5dec4-118">Generate type information for each contract.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5. <span data-ttu-id="5dec4-119">A questo punto è possibile usare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="5dec4-119">Now you can use this information.</span></span> <span data-ttu-id="5dec4-120">Nell'esempio seguente viene generato il codice sorgente C#.</span><span class="sxs-lookup"><span data-stu-id="5dec4-120">The following sample generates C# source code.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5dec4-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dec4-121">See also</span></span>

- [<span data-ttu-id="5dec4-122">Metadati</span><span class="sxs-lookup"><span data-stu-id="5dec4-122">Metadata</span></span>](metadata.md)
- [<span data-ttu-id="5dec4-123">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="5dec4-123">Getting Started</span></span>](../samples/getting-started-sample.md)
