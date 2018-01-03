---
title: 'Procedura: caricare risultati di paging (WCF Data Services)'
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
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 405bea18b03ba695dcb952d10a193decc124841d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-paged-results-wcf-data-services"></a>Procedura: caricare risultati di paging (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] consente al servizio dati di limitare il numero di entità restituite in un singolo feed di risposta. In questa situazione, la voce finale nel feed contiene un collegamento alla pagina di dati successiva. L'URI della pagina successiva di dati viene recuperato chiamando il metodo <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> dell'oggetto <xref:System.Data.Services.Client.QueryOperationResponse%601> restituito durante l'esecuzione di <xref:System.Data.Services.Client.DataServiceQuery%601>. L'URI rappresentato da questo oggetto viene quindi utilizzato per caricare la pagina di risultati successiva. Per ulteriori informazioni, vedere [durante il caricamento di contenuto posticipato](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi di dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato un ciclo `do…while` per caricare entità `Customers` dai risultati di paging del servizio dati.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspaged)]  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono restituite entità `Orders` correlate con ogni entità `Customers` e vengono usati un ciclo `do…while` per caricare pagine di entità `Customers` e un ciclo `while` annidato per caricare pagine di entità `Orders` correlate dal servizio dati.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspagednested)]  
  
## <a name="see-also"></a>Vedere anche  
 [Caricamento di contenuto posticipato](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 [Procedura: caricare entità correlate](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)
