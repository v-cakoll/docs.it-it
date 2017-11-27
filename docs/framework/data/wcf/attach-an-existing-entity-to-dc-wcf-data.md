---
title: "Procedura: connettere un'entità esistente a DataServiceContext (WCF Data Services)"
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
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e389e0ff274b0b4c256bbd9764cd72805b09fcc2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Procedura: connettere un'entità esistente a DataServiceContext (WCF Data Services)
Quando un'entità già esistente in un servizio dati, il [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] libreria client consente di connettere un oggetto che rappresenta l'entità direttamente il <xref:System.Data.Services.Client.DataServiceContext> senza prima eseguire una query. Per ulteriori informazioni, vedere [l'aggiornamento del servizio dati](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare un oggetto `Customer` esistente contenente modifiche da salvare nel servizio dati. oggetto viene collegato al contesto e viene chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> per contrassegnare l'oggetto collegato come <xref:System.Data.Services.Client.EntityStates.Modified> prima della chiamata del metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>Vedere anche  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
