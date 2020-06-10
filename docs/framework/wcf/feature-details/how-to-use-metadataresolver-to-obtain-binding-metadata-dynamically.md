---
title: 'Procedura: usare la classe MetadataResolver per ottenere dinamicamente i metadati di associazione'
ms.date: 03/30/2017
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
ms.openlocfilehash: 98fe4977f270b008c51039af19261ca86b8d6642
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601127"
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a><span data-ttu-id="53470-102">Procedura: usare la classe MetadataResolver per ottenere dinamicamente i metadati di associazione</span><span class="sxs-lookup"><span data-stu-id="53470-102">How to: Use MetadataResolver to Obtain Binding Metadata Dynamically</span></span>
<span data-ttu-id="53470-103">In questo argomento viene illustrato come utilizzare la classe <xref:System.ServiceModel.Description.MetadataResolver> per ottenere dinamicamente i metadati di associazione.</span><span class="sxs-lookup"><span data-stu-id="53470-103">This topic shows you how to use the <xref:System.ServiceModel.Description.MetadataResolver> class to dynamically obtain binding metadata.</span></span>  
  
### <a name="to-dynamically-obtain-binding-metadata"></a><span data-ttu-id="53470-104">Per ottenere dinamicamente i metadati di associazione</span><span class="sxs-lookup"><span data-stu-id="53470-104">To dynamically obtain binding metadata</span></span>  
  
1. <span data-ttu-id="53470-105">Creare un oggetto <xref:System.ServiceModel.EndpointAddress> con l'indirizzo dell'endpoint dei metadati.</span><span class="sxs-lookup"><span data-stu-id="53470-105">Create an <xref:System.ServiceModel.EndpointAddress> object with the address of the metadata endpoint.</span></span>  
  
    ```csharp
    EndpointAddress metaAddress  
      = new EndpointAddress(new Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2. <span data-ttu-id="53470-106">Chiamare il metodo <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, che accetta come parametro il tipo di servizio e l'indirizzo dell'endpoint dei metadati.</span><span class="sxs-lookup"><span data-stu-id="53470-106">Call <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, which passes in the service type and the metadata endpoint address.</span></span> <span data-ttu-id="53470-107">Questa chiamata restituisce una raccolta di endpoint che implementano il contratto specificato.</span><span class="sxs-lookup"><span data-stu-id="53470-107">This returns a collection of endpoints that implement the specified contract.</span></span> <span data-ttu-id="53470-108">Dai metadati vengono importate solo le informazioni di associazione. Le informazioni relative al contratto non vengono importate.</span><span class="sxs-lookup"><span data-stu-id="53470-108">Only binding information is imported from the metadata; contract information is not imported.</span></span> <span data-ttu-id="53470-109">Al loro posto vengono invece utilizzate le informazioni relative al contratto fornito.</span><span class="sxs-lookup"><span data-stu-id="53470-109">The supplied contract is used instead.</span></span>  
  
    ```csharp  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3. <span data-ttu-id="53470-110">È quindi possibile scorrere la raccolta di endpoint del servizio per estrarre le informazioni di associazione desiderate.</span><span class="sxs-lookup"><span data-stu-id="53470-110">You can then iterate through the collection of service endpoints to extract the binding information you need.</span></span> <span data-ttu-id="53470-111">Il codice seguente scorre gli endpoint, crea un oggetto client del servizio che passa l'associazione e l'indirizzo relativi all'endpoint corrente e quindi chiama un metodo del servizio.</span><span class="sxs-lookup"><span data-stu-id="53470-111">The following code iterates through the endpoints, creates a service client object that passes in the binding and address associated with the current endpoint, and then calls a method on the service.</span></span>  
  
    ```csharp  
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
  
## <a name="see-also"></a><span data-ttu-id="53470-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53470-112">See also</span></span>

- [<span data-ttu-id="53470-113">Metadati</span><span class="sxs-lookup"><span data-stu-id="53470-113">Metadata</span></span>](metadata.md)
