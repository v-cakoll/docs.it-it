---
title: "Procedura: connettere un'entità esistente a DataServiceContext (WCF Data Services)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 7c8355ea9e9823e7cab6f43c0f3f901948d1d539
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569374"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Procedura: connettere un'entità esistente a DataServiceContext (WCF Data Services)
Quando un'entità esiste già in un servizio dati, la libreria client di WCF Data Services consente di alleghiare un oggetto che rappresenta l'entità direttamente al <xref:System.Data.Services.Client.DataServiceContext> senza prima eseguire una query. Per ulteriori informazioni, vedere [aggiornamento del servizio dati](updating-the-data-service-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono creati al completamento della [WCF Data Services avvio rapido](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare un oggetto `Customer` esistente contenente modifiche da salvare nel servizio dati. oggetto viene collegato al contesto e viene chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> per contrassegnare l'oggetto collegato come <xref:System.Data.Services.Client.EntityStates.Modified> prima della chiamata del metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
