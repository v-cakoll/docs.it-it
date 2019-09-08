---
title: 'Procedura: Riutilizzare una connessione tra un comando ADO.NET e un oggetto DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: f1ee7726042327eae88e69e9e6d062909c5bc74e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793284"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Procedura: Riutilizzare una connessione tra un comando ADO.NET e un oggetto DataContext
Poiché [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fa parte della famiglia di tecnologie ADO.NET e si basa sui servizi forniti da ADO.NET, è possibile riutilizzare una connessione tra un comando ADO.NET e un <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come riutilizzare la stessa connessione tra un comando ADO.NET e <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di base](background-information.md)
- [ADO.NET e LINQ to SQL](ado-net-and-linq-to-sql.md)
- [Comunicazione con il database](communicating-with-the-database.md)
