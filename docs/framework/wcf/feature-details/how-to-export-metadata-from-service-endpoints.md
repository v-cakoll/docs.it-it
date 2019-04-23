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
# <a name="how-to-export-metadata-from-service-endpoints"></a>Procedura: Esportare metadati da endpoint del servizio
In questo argomento viene illustrato come esportare metadati da endpoint del servizio.  
  
### <a name="to-export-metadata-from-service-endpoints"></a>Per esportare metadati dagli endpoint del servizio  
  
1. Creare un nuovo progetto di applicazione console in Visual Studio. Aggiungere il codice illustrato nei passaggi seguenti al file Program.cs generato all'interno del metodo main().  
  
2. Creare un oggetto <xref:System.ServiceModel.Description.WsdlExporter>.  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3. Impostare la proprietà <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> su uno dei valori dell'enumerazione <xref:System.ServiceModel.Description.PolicyVersion>. In questo esempio il valore viene impostato su <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>, che corrisponde a WS-Policy 1.5.  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4. Creare una matrice di oggetti <xref:System.ServiceModel.Description.ServiceEndpoint>.  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5. Esportare i metadati per ogni endpoint del servizio  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6. Controllare che non si siano verificati errori durante il processo di esportazione e recuperare i metadati.  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7. È ora possibile usare i metadati, ad esempio scrivendoli in un file mediante il metodo <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29>.  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato il codice completo per questo esempio.  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Durante la compilazione di Program.cs fare riferimento a System.ServiceModel.dll.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica dell'architettura dei metadati](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
- [Uso di metadati](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [Endpoint: Gli indirizzi, associazioni e contratti](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
