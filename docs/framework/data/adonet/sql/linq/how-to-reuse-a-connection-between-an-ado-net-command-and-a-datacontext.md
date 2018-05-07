---
title: 'Procedura: riutilizzare una connessione tra un comando ADO.NET e un DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 9618ffd3f6b1a050a4c47d1912b4612ce4031cd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Procedura: riutilizzare una connessione tra un comando ADO.NET e un DataContext
Poiché [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fa parte il [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] famiglia di tecnologie e si basa sui servizi forniti da [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], è possibile riutilizzare una connessione tra un [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] comando e un <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come riutilizzare la stessa connessione tra un comando [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] e <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [ADO.NET e LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [Comunicazione con il database](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
