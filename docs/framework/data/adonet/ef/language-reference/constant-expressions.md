---
title: Espressioni costanti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: b31cd881f1307ec734c026d3c873d7a650e19a20
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251138"
---
# <a name="constant-expressions"></a><span data-ttu-id="5dfaf-102">Espressioni costanti</span><span class="sxs-lookup"><span data-stu-id="5dfaf-102">Constant Expressions</span></span>
<span data-ttu-id="5dfaf-103">Un'espressione costante è costituita da un valore costante.</span><span class="sxs-lookup"><span data-stu-id="5dfaf-103">A constant expression consists of a constant value.</span></span> <span data-ttu-id="5dfaf-104">I valori costanti vengono convertiti direttamente in espressioni costanti dell'albero dei comandi, senza conversione nel client.</span><span class="sxs-lookup"><span data-stu-id="5dfaf-104">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="5dfaf-105">Questo vale anche per le espressioni che hanno come risultato un valore costante.</span><span class="sxs-lookup"><span data-stu-id="5dfaf-105">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="5dfaf-106">È pertanto possibile prevedere il comportamento dell'origine dati per tutte le espressioni che contengono costanti.</span><span class="sxs-lookup"><span data-stu-id="5dfaf-106">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="5dfaf-107">Il comportamento risultante può essere diverso da quello in CLR.</span><span class="sxs-lookup"><span data-stu-id="5dfaf-107">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="5dfaf-108">Nell'esempio seguente è illustrata un'espressione costante valutata nel server.</span><span class="sxs-lookup"><span data-stu-id="5dfaf-108">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 <span data-ttu-id="5dfaf-109">LINQ to Entities non supporta l'utilizzo di una classe utente come costante.</span><span class="sxs-lookup"><span data-stu-id="5dfaf-109">LINQ to Entities does not support using a user class as a constant.</span></span> <span data-ttu-id="5dfaf-110">Un riferimento a una proprietà in una classe utente è tuttavia considerato una costante e viene convertito in un'espressione costante dell'albero dei comandi ed eseguito nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="5dfaf-110">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dfaf-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dfaf-111">See also</span></span>

- [<span data-ttu-id="5dfaf-112">Espressioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="5dfaf-112">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
