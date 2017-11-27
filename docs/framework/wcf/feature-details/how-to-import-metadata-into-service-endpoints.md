---
title: 'Procedura: importare metadati negli endpoint del servizio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca59de38ddb37260de5106a65419ebdc46f73151
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-import-metadata-into-service-endpoints"></a><span data-ttu-id="dba75-102">Procedura: importare metadati negli endpoint del servizio</span><span class="sxs-lookup"><span data-stu-id="dba75-102">How to: Import Metadata into Service Endpoints</span></span>
<span data-ttu-id="dba75-103">In questo argomento viene descritto come importare i metadati in una raccolta di endpoint del servizio e utilizzare il servizio definito nel [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="dba75-103">This topic explains how to import metadata into a collection of service endpoints and use the service defined in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="dba75-104">In questo argomento viene inoltre illustrato come creare un'applicazione client che importa metadati dal servizio e quindi chiama il metodo `Add` sul servizio.</span><span class="sxs-lookup"><span data-stu-id="dba75-104">This topic show how to create a client application that imports metadata from the service and then calls the `Add` method on the service.</span></span>  
  
### <a name="to-import-metadata-into-service-endpoints"></a><span data-ttu-id="dba75-105">Per importare metadati negli endpoint del servizio</span><span class="sxs-lookup"><span data-stu-id="dba75-105">To import metadata into service endpoints</span></span>  
  
1.  <span data-ttu-id="dba75-106">Dichiarare un oggetto <xref:System.ServiceModel.EndpointAddress> e inizializzarlo con l'URI (Uniform Resource Identifier) per l'indirizzo di scambio dei metadati (MEX, metadata exchange) del servizio.</span><span class="sxs-lookup"><span data-stu-id="dba75-106">Declare an <xref:System.ServiceModel.EndpointAddress> object and initialize it with the Uniform Resource Identifier (URI) for the metadata exchange (MEX) address of the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2.  <span data-ttu-id="dba75-107">Creare un <xref:System.ServiceModel.Description.MetadataExchangeClient>, passando l'indirizzo MEX, e chiamare <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="dba75-107">Create a <xref:System.ServiceModel.Description.MetadataExchangeClient>, passing in the MEX address, and call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span></span> <span data-ttu-id="dba75-108">In questo modo vengono recuperati i metadati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="dba75-108">This retrieves the metadata from the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3.  <span data-ttu-id="dba75-109">Creare un <xref:System.ServiceModel.Description.WsdlImporter>, passando i metadati precedentemente recuperati, e chiamare <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span><span class="sxs-lookup"><span data-stu-id="dba75-109">Create a <xref:System.ServiceModel.Description.WsdlImporter>, passing in the metadata previously retrieved, and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span></span> <span data-ttu-id="dba75-110">In questo modo viene generata una raccolta di oggetti <xref:System.ServiceModel.Description.ContractDescription>.</span><span class="sxs-lookup"><span data-stu-id="dba75-110">This generates a collection of <xref:System.ServiceModel.Description.ContractDescription> objects.</span></span> <span data-ttu-id="dba75-111">È anche possibile chiamare <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> o <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="dba75-111">You could also call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> or <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, depending upon your needs.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    >  <span data-ttu-id="dba75-112">Dopo avere importato i metadati, non sarà possibile creare un canale client o esportare i metadati</span><span class="sxs-lookup"><span data-stu-id="dba75-112">After you have imported the metadata, you will not be able to create a client channel or export the metadata.</span></span> <span data-ttu-id="dba75-113">poiché in questa fase non è disponibile alcuna informazione sul tipo.</span><span class="sxs-lookup"><span data-stu-id="dba75-113">This is because no type information is available at this point.</span></span> <span data-ttu-id="dba75-114">Le informazioni sul tipo sono necessarie per interagire con il servizio o esportare i metadati.</span><span class="sxs-lookup"><span data-stu-id="dba75-114">Type information is required to actually interact with the service or export metadata.</span></span> <span data-ttu-id="dba75-115">Per generare informazioni sul tipo, è necessario generare il codice mostrato nei passaggi 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="dba75-115">To generate the type information, you need to generate code, shown in steps 4 and 5.</span></span> <span data-ttu-id="dba75-116">In alternativa, è possibile usare la classe di supporto <xref:System.ServiceModel.Description.MetadataResolver>.</span><span class="sxs-lookup"><span data-stu-id="dba75-116">Alternatively, you could use the <xref:System.ServiceModel.Description.MetadataResolver> helper class.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="dba75-117">[Procedura: usare la classe MetadataResolver per ottenere dinamicamente i metadati di associazione](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="dba75-117"> [How to: Use MetadataResolver to Obtain Binding Metadata Dynamically](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span></span>  
  
4.  <span data-ttu-id="dba75-118">Generare informazioni sul tipo per ogni contratto.</span><span class="sxs-lookup"><span data-stu-id="dba75-118">Generate type information for each contract.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5.  <span data-ttu-id="dba75-119">A questo punto è possibile usare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="dba75-119">Now you can use this information.</span></span> <span data-ttu-id="dba75-120">Nell'esempio seguente viene generato il codice sorgente C#.</span><span class="sxs-lookup"><span data-stu-id="dba75-120">The following sample generates C# source code.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="dba75-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dba75-121">See Also</span></span>  
 [<span data-ttu-id="dba75-122">Metadati</span><span class="sxs-lookup"><span data-stu-id="dba75-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="dba75-123">Introduzione</span><span class="sxs-lookup"><span data-stu-id="dba75-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
