---
title: "Procedura: Usare funzioni definite dall'utente con valori scalari"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: eedc2e9b997e91ed9fe0038f260aa475d23a0627
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186833"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="94e3d-102">Procedura: Usare funzioni definite dall'utente con valori scalari</span><span class="sxs-lookup"><span data-stu-id="94e3d-102">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="94e3d-103">Una funzione con valori di tabella restituisce un unico rowset, a differenza delle stored procedure che possono restituire forme di più risultati.</span><span class="sxs-lookup"><span data-stu-id="94e3d-103">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="94e3d-104">Poiché il tipo restituito di una funzione con valori di tabella è `Table`, è possibile usare tale funzione in un punto qualsiasi del codice SQL in cui possa essere usata una tabella.</span><span class="sxs-lookup"><span data-stu-id="94e3d-104">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="94e3d-105">È inoltre possibile gestire la funzione con valori di tabella esattamente come una tabella.</span><span class="sxs-lookup"><span data-stu-id="94e3d-105">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e3d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="94e3d-106">Example</span></span>  
 <span data-ttu-id="94e3d-107">La funzione SQL riportata di seguito dichiara in modo esplicito che verrà restituito `TABLE`.</span><span class="sxs-lookup"><span data-stu-id="94e3d-107">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="94e3d-108">La struttura del rowset restituito è quindi definita in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="94e3d-108">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```  
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="94e3d-109">eseguire il mapping di funzione come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="94e3d-109">maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="94e3d-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="94e3d-110">Example</span></span>  
 <span data-ttu-id="94e3d-111">Il codice SQL seguente mostra come sia possibile creare un join alla tabella restituita dalla funzione e diversamente gestirla come qualsiasi altra tabella:</span><span class="sxs-lookup"><span data-stu-id="94e3d-111">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```  
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="94e3d-112">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] il rendering della query viene eseguito come segue:</span><span class="sxs-lookup"><span data-stu-id="94e3d-112">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="94e3d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94e3d-113">See also</span></span>

- [<span data-ttu-id="94e3d-114">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="94e3d-114">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
