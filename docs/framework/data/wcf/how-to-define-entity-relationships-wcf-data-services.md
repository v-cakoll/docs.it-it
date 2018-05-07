---
title: 'Procedura: definire le relazioni tra entità (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: cc255524-1534-4fae-b83c-250933d5a72b
ms.openlocfilehash: 5658f83eb352327b63bc89db48afcf0f8aae3774
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-entity-relationships-wcf-data-services"></a>Procedura: definire le relazioni tra entità (WCF Data Services)
Quando si aggiunge una nuova entità in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], le relazioni tra la nuova entità e le entità correlate non vengono definite automaticamente. È possibile creare e modificare le relazioni tra istanze di entità e fare in modo che tali modifiche vengano apportate nel servizio dati mediante la libreria client. Per ulteriori informazioni, vedere [l'aggiornamento del servizio dati](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una nuova istanza dell'oggetto e viene quindi chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> sull'oggetto <xref:System.Data.Services.Client.DataServiceContext> per creare l'elemento nel contesto insieme al collegamento all'ordine correlato. Un messaggio POST HTTP viene inviato al servizio dati al momento della chiamata del metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare il metodo <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> per aggiungere un oggetto `Order_Details` a un oggetto `Orders` correlato con un riferimento a un oggetto `Products` specifico. I metodi <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> e <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> definiscono le relazioni. In questo esempio le proprietà di navigazione sull'oggetto `Order_Details` vengono impostate anche in modo esplicito.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorder)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorder)]  
  
## <a name="see-also"></a>Vedere anche  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [Procedura: aggiungere, modificare ed eliminare entità](../../../../docs/framework/data/wcf/how-to-add-modify-and-delete-entities-wcf-data-services.md)
