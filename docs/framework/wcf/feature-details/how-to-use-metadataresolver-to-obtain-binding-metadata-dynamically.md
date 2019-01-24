---
title: 'Procedura: Usare la classe MetadataResolver per ottenere dinamicamente i metadati di associazione'
ms.date: 03/30/2017
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
ms.openlocfilehash: 9887f74902a1f324f57e39a61a48b5826127cba9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735974"
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a>Procedura: Usare la classe MetadataResolver per ottenere dinamicamente i metadati di associazione
In questo argomento viene illustrato come utilizzare la classe <xref:System.ServiceModel.Description.MetadataResolver> per ottenere dinamicamente i metadati di associazione.  
  
### <a name="to-dynamically-obtain-binding-metadata"></a>Per ottenere dinamicamente i metadati di associazione  
  
1.  Creare un oggetto <xref:System.ServiceModel.EndpointAddress> con l'indirizzo dell'endpoint dei metadati.  
  
    ```  
    EndpointAddress metaAddress  
      = new EndpointAddress(new   Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2.  Chiamare il metodo <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, che accetta come parametro il tipo di servizio e l'indirizzo dell'endpoint dei metadati. Questa chiamata restituisce una raccolta di endpoint che implementano il contratto specificato. Dai metadati vengono importate solo le informazioni di associazione. Le informazioni relative al contratto non vengono importate. Al loro posto vengono invece utilizzate le informazioni relative al contratto fornito.  
  
    ```  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3.  È quindi possibile scorrere la raccolta di endpoint del servizio per estrarre le informazioni di associazione desiderate. Il codice seguente scorre gli endpoint, crea un oggetto client del servizio che passa l'associazione e l'indirizzo relativi all'endpoint corrente e quindi chiama un metodo del servizio.  
  
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
  
## <a name="see-also"></a>Vedere anche
- [Metadati](../../../../docs/framework/wcf/feature-details/metadata.md)
