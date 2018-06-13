---
title: 'Procedura: restituire rowset'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: a2666b752d936e10d377113d5bf18111393df3ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361137"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="d7e70-102">Procedura: restituire rowset</span><span class="sxs-lookup"><span data-stu-id="d7e70-102">How to: Return Rowsets</span></span>
<span data-ttu-id="d7e70-103">In questo esempio viene restituito un rowset dal database e viene incluso un parametro di input per filtrare il risultato.</span><span class="sxs-lookup"><span data-stu-id="d7e70-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="d7e70-104">Quando si esegue una stored procedure che restituisce un set di righe, utilizza un *risultato* classe che archivia i valori restituiti dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d7e70-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="d7e70-105">Per ulteriori informazioni, vedere [l'analisi di codice LINQ to SQL origine](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="d7e70-105">For more information, see [Analyzing LINQ to SQL Source Code](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7e70-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7e70-106">Example</span></span>  
 <span data-ttu-id="d7e70-107">Nell'esempio seguente è rappresentata una stored procedure che restituisce righe di clienti e usa un parametro di input per restituire solo le righe in cui è elencata "London" come città del cliente.</span><span class="sxs-lookup"><span data-stu-id="d7e70-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="d7e70-108">In questo esempio si presuppone una classe `CustomersByCityResult` enumerabile.</span><span class="sxs-lookup"><span data-stu-id="d7e70-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d7e70-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7e70-109">See Also</span></span>  
 [<span data-ttu-id="d7e70-110">stored procedure</span><span class="sxs-lookup"><span data-stu-id="d7e70-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="d7e70-111">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="d7e70-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
