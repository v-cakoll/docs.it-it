---
title: "Procedura: utilizzare funzioni definite dall'utente con valori di tabella"
description: Utilizzare questi esempi per apprendere come creare una funzione con valori di tabella, che restituisce un singolo set di righe. Utilizzare una funzione con valori di tabella analoga a una tabella.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: 44866367393e321d7dd2db965e2fad8a2e6b63e9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286326"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="e820f-104">Procedura: utilizzare funzioni definite dall'utente con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="e820f-104">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="e820f-105">Una funzione con valori di tabella restituisce un unico rowset, a differenza delle stored procedure che possono restituire forme di più risultati.</span><span class="sxs-lookup"><span data-stu-id="e820f-105">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="e820f-106">Poiché il tipo restituito di una funzione con valori di tabella è `Table`, è possibile usare tale funzione in un punto qualsiasi del codice SQL in cui possa essere usata una tabella.</span><span class="sxs-lookup"><span data-stu-id="e820f-106">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="e820f-107">È inoltre possibile gestire la funzione con valori di tabella esattamente come una tabella.</span><span class="sxs-lookup"><span data-stu-id="e820f-107">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e820f-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e820f-108">Example</span></span>  
 <span data-ttu-id="e820f-109">La funzione SQL riportata di seguito dichiara in modo esplicito che verrà restituito `TABLE`.</span><span class="sxs-lookup"><span data-stu-id="e820f-109">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="e820f-110">La struttura del rowset restituito è quindi definita in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="e820f-110">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```sql
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="e820f-111">esegue il mapping della funzione come segue:</span><span class="sxs-lookup"><span data-stu-id="e820f-111">maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="e820f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="e820f-112">Example</span></span>  
 <span data-ttu-id="e820f-113">Il codice SQL seguente mostra come sia possibile creare un join alla tabella restituita dalla funzione e diversamente gestirla come qualsiasi altra tabella:</span><span class="sxs-lookup"><span data-stu-id="e820f-113">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```sql
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="e820f-114">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] il rendering della query viene eseguito come segue:</span><span class="sxs-lookup"><span data-stu-id="e820f-114">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e820f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e820f-115">See also</span></span>

- [<span data-ttu-id="e820f-116">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="e820f-116">User-Defined Functions</span></span>](user-defined-functions.md)
