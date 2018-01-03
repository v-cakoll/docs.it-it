---
title: 'Procedura: restituire rowset'
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
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c5f88ce69239c0ca601344362dc420205291cb74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="c69cf-102">Procedura: restituire rowset</span><span class="sxs-lookup"><span data-stu-id="c69cf-102">How to: Return Rowsets</span></span>
<span data-ttu-id="c69cf-103">In questo esempio viene restituito un rowset dal database e viene incluso un parametro di input per filtrare il risultato.</span><span class="sxs-lookup"><span data-stu-id="c69cf-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="c69cf-104">Quando si esegue una stored procedure che restituisce un set di righe, utilizza un *risultato* classe che archivia i valori restituiti dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c69cf-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="c69cf-105">Per ulteriori informazioni, vedere [l'analisi di codice LINQ to SQL origine](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="c69cf-105">For more information, see [Analyzing LINQ to SQL Source Code](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c69cf-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c69cf-106">Example</span></span>  
 <span data-ttu-id="c69cf-107">Nell'esempio seguente è rappresentata una stored procedure che restituisce righe di clienti e usa un parametro di input per restituire solo le righe in cui è elencata "London" come città del cliente.</span><span class="sxs-lookup"><span data-stu-id="c69cf-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="c69cf-108">In questo esempio si presuppone una classe `CustomersByCityResult` enumerabile.</span><span class="sxs-lookup"><span data-stu-id="c69cf-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c69cf-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c69cf-109">See Also</span></span>  
 [<span data-ttu-id="c69cf-110">stored procedure</span><span class="sxs-lookup"><span data-stu-id="c69cf-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="c69cf-111">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="c69cf-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
