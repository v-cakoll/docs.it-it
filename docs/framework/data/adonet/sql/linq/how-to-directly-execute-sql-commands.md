---
title: 'Procedura: eseguire direttamente comandi SQL'
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
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9f87572b27cfca7cc1188ab0986dadcba7bb3e29
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="caae2-102">Procedura: eseguire direttamente comandi SQL</span><span class="sxs-lookup"><span data-stu-id="caae2-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="caae2-103">Presupponendo una connessione <xref:System.Data.Linq.DataContext>, è possibile usare <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> per eseguire comandi SQL che non restituiscono oggetti.</span><span class="sxs-lookup"><span data-stu-id="caae2-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caae2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="caae2-104">Example</span></span>  
 <span data-ttu-id="caae2-105">Nell'esempio seguente viene imposto a SQL Server di aumentare il valore di UnitPrice di 1,00.</span><span class="sxs-lookup"><span data-stu-id="caae2-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="caae2-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="caae2-106">See Also</span></span>  
 [<span data-ttu-id="caae2-107">Procedura: eseguire direttamente query SQL</span><span class="sxs-lookup"><span data-stu-id="caae2-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 [<span data-ttu-id="caae2-108">Comunicazione con il database</span><span class="sxs-lookup"><span data-stu-id="caae2-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
