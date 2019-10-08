---
title: 'Procedura: Restituire set di righe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: b853a6f2175009cbcbc01c14a6732b98e37e1a7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003067"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="6b033-102">Procedura: Restituire set di righe</span><span class="sxs-lookup"><span data-stu-id="6b033-102">How to: Return Rowsets</span></span>
<span data-ttu-id="6b033-103">In questo esempio viene restituito un rowset dal database e viene incluso un parametro di input per filtrare il risultato.</span><span class="sxs-lookup"><span data-stu-id="6b033-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="6b033-104">Quando si esegue un stored procedure che restituisce un set di righe, si usa una classe di risultato che archivia i *risultati* restituiti dal stored procedure.</span><span class="sxs-lookup"><span data-stu-id="6b033-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="6b033-105">Per ulteriori informazioni, vedere [analisi LINQ to SQL codice sorgente](analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="6b033-105">For more information, see [Analyzing LINQ to SQL Source Code](analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b033-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b033-106">Example</span></span>  
 <span data-ttu-id="6b033-107">Nell'esempio seguente è rappresentata una stored procedure che restituisce righe di clienti e usa un parametro di input per restituire solo le righe in cui è elencata "London" come città del cliente.</span><span class="sxs-lookup"><span data-stu-id="6b033-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="6b033-108">In questo esempio si presuppone una classe `CustomersByCityResult` enumerabile.</span><span class="sxs-lookup"><span data-stu-id="6b033-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```sql  
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
  
## <a name="see-also"></a><span data-ttu-id="6b033-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b033-109">See also</span></span>

- [<span data-ttu-id="6b033-110">stored procedure</span><span class="sxs-lookup"><span data-stu-id="6b033-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="6b033-111">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="6b033-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
