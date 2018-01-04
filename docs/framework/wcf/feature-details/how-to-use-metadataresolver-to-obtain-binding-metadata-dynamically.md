---
title: 'Procedura: usare la classe MetadataResolver per ottenere dinamicamente i metadati di associazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 640d053e0186766e5acdbef692f4e7fae59337b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a><span data-ttu-id="abefc-102">Procedura: usare la classe MetadataResolver per ottenere dinamicamente i metadati di associazione</span><span class="sxs-lookup"><span data-stu-id="abefc-102">How to: Use MetadataResolver to Obtain Binding Metadata Dynamically</span></span>
<span data-ttu-id="abefc-103">In questo argomento viene illustrato come utilizzare la classe <xref:System.ServiceModel.Description.MetadataResolver> per ottenere dinamicamente i metadati di associazione.</span><span class="sxs-lookup"><span data-stu-id="abefc-103">This topic shows you how to use the <xref:System.ServiceModel.Description.MetadataResolver> class to dynamically obtain binding metadata.</span></span>  
  
### <a name="to-dynamically-obtain-binding-metadata"></a><span data-ttu-id="abefc-104">Per ottenere dinamicamente i metadati di associazione</span><span class="sxs-lookup"><span data-stu-id="abefc-104">To dynamically obtain binding metadata</span></span>  
  
1.  <span data-ttu-id="abefc-105">Creare un oggetto <xref:System.ServiceModel.EndpointAddress> con l'indirizzo dell'endpoint dei metadati.</span><span class="sxs-lookup"><span data-stu-id="abefc-105">Create an <xref:System.ServiceModel.EndpointAddress> object with the address of the metadata endpoint.</span></span>  
  
    ```  
    EndpointAddress metaAddress  
      = new EndpointAddress(new   Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2.  <span data-ttu-id="abefc-106">Chiamare il metodo <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, che accetta come parametro il tipo di servizio e l'indirizzo dell'endpoint dei metadati.</span><span class="sxs-lookup"><span data-stu-id="abefc-106">Call <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, which passes in the service type and the metadata endpoint address.</span></span> <span data-ttu-id="abefc-107">Questa chiamata restituisce una raccolta di endpoint che implementano il contratto specificato.</span><span class="sxs-lookup"><span data-stu-id="abefc-107">This returns a collection of endpoints that implement the specified contract.</span></span> <span data-ttu-id="abefc-108">Dai metadati vengono importate solo le informazioni di associazione. Le informazioni relative al contratto non vengono importate.</span><span class="sxs-lookup"><span data-stu-id="abefc-108">Only binding information is imported from the metadata; contract information is not imported.</span></span> <span data-ttu-id="abefc-109">Al loro posto vengono invece utilizzate le informazioni relative al contratto fornito.</span><span class="sxs-lookup"><span data-stu-id="abefc-109">The supplied contract is used instead.</span></span>  
  
    ```  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3.  <span data-ttu-id="abefc-110">È quindi possibile scorrere la raccolta di endpoint del servizio per estrarre le informazioni di associazione desiderate.</span><span class="sxs-lookup"><span data-stu-id="abefc-110">You can then iterate through the collection of service endpoints to extract the binding information you need.</span></span> <span data-ttu-id="abefc-111">Il codice seguente scorre gli endpoint, crea un oggetto client del servizio che passa l'associazione e l'indirizzo relativi all'endpoint corrente e quindi chiama un metodo del servizio.</span><span class="sxs-lookup"><span data-stu-id="abefc-111">The following code iterates through the endpoints, creates a service client object that passes in the binding and address associated with the current endpoint, and then calls a method on the service.</span></span>  
  
    ```  
    foreach (ServiceEndpoint point in endpoints)  
    {  
       if (point != null)  
       {  
          // Create a new wcfClient using retrieved endpoints.  
          using (wcfClient = new SampleServiceClient(point.Binding, point.Address))  
          {  
             Console.WriteLine(  
               wcfClient.SampleMethod("Client used the "  
               + point.Address.ToString() + " address."));  
          }  
      }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="abefc-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abefc-112">See Also</span></span>  
 [<span data-ttu-id="abefc-113">Metadati</span><span class="sxs-lookup"><span data-stu-id="abefc-113">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
