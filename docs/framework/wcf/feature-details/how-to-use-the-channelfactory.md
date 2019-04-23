---
title: 'Procedura: Usare ChannelFactory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7d542a3dcae514e75194b49c23a8dec5dd7e8c3b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773727"
---
# <a name="how-to-use-the-channelfactory"></a>Procedura: Usare ChannelFactory
La classe generica <xref:System.ServiceModel.ChannelFactory%601> viene usata in scenari avanzati che richiedono la creazione di una channel factory utilizzabile per creare più di un canale.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>Per creare e usare la classe ChannelFactory  
  
1. Compilare ed eseguire un servizio Windows Communication Foundation (WCF). Per altre informazioni, vedere [progettazione e implementazione di servizi](../../../../docs/framework/wcf/designing-and-implementing-services.md), [configurazione di servizi](../../../../docs/framework/wcf/configuring-services.md), e [servizi di Hosting](../../../../docs/framework/wcf/hosting-services.md).  
  
2. Usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il contratto (interfaccia) per il client.  
  
3. Nel codice client, usare la classe <xref:System.ServiceModel.ChannelFactory%601> per creare più listener endpoint.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
