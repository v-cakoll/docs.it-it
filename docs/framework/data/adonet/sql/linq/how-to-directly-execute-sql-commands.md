---
title: 'Procedura: Eseguire direttamente comandi SQL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: eeac6272f176ac8e780b72b0076d032ad9e8f108
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078902"
---
# <a name="how-to-directly-execute-sql-commands"></a>Procedura: Eseguire direttamente comandi SQL
Presupponendo una connessione <xref:System.Data.Linq.DataContext>, è possibile usare <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> per eseguire comandi SQL che non restituiscono oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene imposto a SQL Server di aumentare il valore di UnitPrice di 1,00.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Eseguire direttamente query SQL](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)
- [Comunicazione con il database](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
