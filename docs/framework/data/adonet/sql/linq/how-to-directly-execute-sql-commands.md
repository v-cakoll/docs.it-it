---
title: 'Procedura: Eseguire direttamente comandi SQL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 0ca62c0affc282140eb36979baafb8e3f9c89c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737546"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="d35b6-102">Procedura: Eseguire direttamente comandi SQL</span><span class="sxs-lookup"><span data-stu-id="d35b6-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="d35b6-103">Presupponendo una connessione <xref:System.Data.Linq.DataContext>, è possibile usare <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> per eseguire comandi SQL che non restituiscono oggetti.</span><span class="sxs-lookup"><span data-stu-id="d35b6-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d35b6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d35b6-104">Example</span></span>  
 <span data-ttu-id="d35b6-105">Nell'esempio seguente viene imposto a SQL Server di aumentare il valore di UnitPrice di 1,00.</span><span class="sxs-lookup"><span data-stu-id="d35b6-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d35b6-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d35b6-106">See also</span></span>
- [<span data-ttu-id="d35b6-107">Procedura: Eseguire direttamente query SQL</span><span class="sxs-lookup"><span data-stu-id="d35b6-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="d35b6-108">Comunicazione con il database</span><span class="sxs-lookup"><span data-stu-id="d35b6-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
