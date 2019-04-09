---
title: 'Procedura: Riutilizzare una connessione tra un comando ADO.NET e un oggetto DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 47e1e45cfe693e3569c343f1058ce2d610af96dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163150"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Procedura: Riutilizzare una connessione tra un comando ADO.NET e un oggetto DataContext
In quanto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fa parte del [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] famiglia di tecnologie e si basa sui servizi forniti dai [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], è possibile riutilizzare una connessione tra un [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] comando e un <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come riutilizzare la stessa connessione tra un comando [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] e <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [ADO.NET e LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [Comunicazione con il database](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
