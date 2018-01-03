---
title: "Procedura: aggiungere, modificare ed eliminare entità (Entity Framework)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, changing data
ms.assetid: a00f8933-b232-4445-95ba-adc634f055d8
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0899a179ae51c4884f30fd93fddbcfe289d8d7a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-modify-and-delete-entities-wcf-data-services"></a>Procedura: aggiungere, modificare ed eliminare entità (Entity Framework)
Con il [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] librerie client, è possibile creare, aggiornare ed eliminare dati di entità in un servizio dati eseguendo azioni equivalenti sugli oggetti nel <xref:System.Data.Services.Client.DataServiceContext>. Per ulteriori informazioni, vedere [l'aggiornamento del servizio dati](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato una nuova istanza dell'oggetto e viene quindi chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> sull'oggetto <xref:System.Data.Services.Client.DataServiceContext> per creare l'elemento nel contesto. Un messaggio POST HTTP viene inviato al servizio dati al momento della chiamata del metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AddProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addproduct)]
 [!code-vb[Astoria Northwind Client#AddProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addproduct)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene recuperato e modificato un oggetto esistente e viene quindi chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> sull'oggetto <xref:System.Data.Services.Client.DataServiceContext> per contrassegnare l'elemento come aggiornato. Un messaggio MERGE HTTP viene inviato al servizio dati al momento della chiamata del metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#modifycustomer)]
 [!code-vb[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#modifycustomer)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> sull'oggetto <xref:System.Data.Services.Client.DataServiceContext> per contrassegnare l'elemento nel contesto come eliminato. Un messaggio DELETE HTTP viene inviato al servizio dati al momento della chiamata del metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#deleteproduct)]
 [!code-vb[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#deleteproduct)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una nuova istanza dell'oggetto e viene quindi chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> sull'oggetto <xref:System.Data.Services.Client.DataServiceContext> per creare l'elemento nel contesto insieme al collegamento all'ordine correlato. Un messaggio POST HTTP viene inviato al servizio dati al momento della chiamata del metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="see-also"></a>Vedere anche  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [Procedura: connettere un'entità esistente a DataServiceContext](../../../../docs/framework/data/wcf/attach-an-existing-entity-to-dc-wcf-data.md)  
 [Procedura: definire le relazioni tra entità](../../../../docs/framework/data/wcf/how-to-define-entity-relationships-wcf-data-services.md)  
 [Esecuzione di operazioni in batch](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)
