---
title: 'Procedura: recuperare informazioni in sola lettura'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e7144863e43ec816ad2359c6c48f6d38babb3b46
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-retrieve-information-as-read-only"></a>Procedura: recuperare informazioni in sola lettura
Quando non si prevede di modificare i dati, è possibile migliorare le prestazione delle query effettuando la ricerca di risultati di sola lettura.  
  
 Per implementare l'elaborazione di sola lettura, impostare <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> su `false`.  
  
> [!NOTE]
>  Quando <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> è impostato su `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> viene impostato in modo implicito su `false`.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene recuperato una raccolta di date di assunzione dei dipendenti di sola lettura.  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Esecuzione di query sul database](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [Caricamento posticipato e immediato](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
