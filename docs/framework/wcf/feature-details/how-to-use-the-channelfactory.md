---
title: 'Procedura: usare ChannelFactory'
description: Informazioni su come creare una channel factory per creare più di un canale per accedere ai servizi tramite un client WCF.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7c87026ca4cf7c739f4615da9bc7f0272a382392
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246662"
---
# <a name="how-to-use-the-channelfactory"></a>Procedura: usare ChannelFactory
La classe generica <xref:System.ServiceModel.ChannelFactory%601> viene usata in scenari avanzati che richiedono la creazione di una channel factory utilizzabile per creare più di un canale.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>Per creare e usare la classe ChannelFactory  
  
1. Compilazione ed esecuzione di un servizio Windows Communication Foundation (WCF). Per ulteriori informazioni, vedere [progettazione e implementazione di servizi](../designing-and-implementing-services.md), [configurazione di servizi](../configuring-services.md)e [hosting di servizi](../hosting-services.md).  
  
2. Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il contratto (interfaccia) per il client.  
  
3. Nel codice client, usare la classe <xref:System.ServiceModel.ChannelFactory%601> per creare più listener endpoint.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
