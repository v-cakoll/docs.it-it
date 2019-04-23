---
title: 'Procedura: Esportare metadati da endpoint del servizio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b6c4dfd0-f270-43ec-961a-e16eb6af2f2c
ms.openlocfilehash: 6bf2eb3d295f9cbf6a7e13a612d5846ceaa75ab4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59345508"
---
# <a name="how-to-export-metadata-from-service-endpoints"></a><span data-ttu-id="6918c-102">Procedura: Esportare metadati da endpoint del servizio</span><span class="sxs-lookup"><span data-stu-id="6918c-102">How to: Export Metadata from Service Endpoints</span></span>
<span data-ttu-id="6918c-103">In questo argomento viene illustrato come esportare metadati da endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="6918c-103">This topic explains how to export metadata from service endpoints.</span></span>  
  
### <a name="to-export-metadata-from-service-endpoints"></a><span data-ttu-id="6918c-104">Per esportare metadati dagli endpoint del servizio</span><span class="sxs-lookup"><span data-stu-id="6918c-104">To export metadata from service endpoints</span></span>  
  
1. <span data-ttu-id="6918c-105">Creare un nuovo progetto di applicazione console in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6918c-105">Create a new Visual Studio Console App Project.</span></span> <span data-ttu-id="6918c-106">Aggiungere il codice illustrato nei passaggi seguenti al file Program.cs generato all'interno del metodo main().</span><span class="sxs-lookup"><span data-stu-id="6918c-106">Add the code shown in the following steps in the generated Program.cs file within the main() method.</span></span>  
  
2. <span data-ttu-id="6918c-107">Creare un oggetto <xref:System.ServiceModel.Description.WsdlExporter>.</span><span class="sxs-lookup"><span data-stu-id="6918c-107">Create a <xref:System.ServiceModel.Description.WsdlExporter>.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3. <span data-ttu-id="6918c-108">Impostare la proprietà <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> su uno dei valori dell'enumerazione <xref:System.ServiceModel.Description.PolicyVersion>.</span><span class="sxs-lookup"><span data-stu-id="6918c-108">Set the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to one of the values from the <xref:System.ServiceModel.Description.PolicyVersion> enumeration.</span></span> <span data-ttu-id="6918c-109">In questo esempio il valore viene impostato su <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>, che corrisponde a WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="6918c-109">This sample sets the value to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> which corresponds to WS-Policy 1.5.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4. <span data-ttu-id="6918c-110">Creare una matrice di oggetti <xref:System.ServiceModel.Description.ServiceEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="6918c-110">Create an array of <xref:System.ServiceModel.Description.ServiceEndpoint> objects.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5. <span data-ttu-id="6918c-111">Esportare i metadati per ogni endpoint del servizio</span><span class="sxs-lookup"><span data-stu-id="6918c-111">Export metadata for each service endpoint.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6. <span data-ttu-id="6918c-112">Controllare che non si siano verificati errori durante il processo di esportazione e recuperare i metadati.</span><span class="sxs-lookup"><span data-stu-id="6918c-112">Check to make sure no errors occurred during the export process and retrieve the metadata.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7. <span data-ttu-id="6918c-113">È ora possibile usare i metadati, ad esempio scrivendoli in un file mediante il metodo <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29>.</span><span class="sxs-lookup"><span data-stu-id="6918c-113">You can now use the metadata, such as write it to a file by calling the <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6918c-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="6918c-114">Example</span></span>  
 <span data-ttu-id="6918c-115">Di seguito è riportato il codice completo per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="6918c-115">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6918c-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6918c-116">Compiling the Code</span></span>  
 <span data-ttu-id="6918c-117">Durante la compilazione di Program.cs fare riferimento a System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="6918c-117">When compiling Program.cs reference System.ServiceModel.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6918c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6918c-118">See also</span></span>

- [<span data-ttu-id="6918c-119">Panoramica dell'architettura dei metadati</span><span class="sxs-lookup"><span data-stu-id="6918c-119">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
- [<span data-ttu-id="6918c-120">Uso di metadati</span><span class="sxs-lookup"><span data-stu-id="6918c-120">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [<span data-ttu-id="6918c-121">Endpoint: Gli indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="6918c-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
