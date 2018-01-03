---
title: 'Procedura: utilizzare stored procedure mappate per forme di risultati sequenziali'
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
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 227fe2c777d23172caba5f290d9626552af4747a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a>Procedura: utilizzare stored procedure mappate per forme di risultati sequenziali
Questo tipo di stored procedure può generare più di una forma di risultati, tuttavia si conosce l'ordine in cui tali risultati vengono restituiti. Si consideri questo scenario rispetto allo scenario in cui non si conosca la sequenza dei risultati restituiti. Per ulteriori informazioni, vedere [procedura: utilizzare Stored procedure mappate per più forme di risultati](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato il codice T-SQL di un stored procedure che restituisce più forme di risultati in sequenza:  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a>Esempio  
 Per eseguire questa stored procedure si utilizzerà codice simile al seguente.  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>Vedere anche  
 [stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
