---
title: Espressioni costanti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: 10c74ede8d490bf96a9d0855889669bdc2628b01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785359"
---
# <a name="constant-expressions"></a><span data-ttu-id="a77bd-102">Espressioni costanti</span><span class="sxs-lookup"><span data-stu-id="a77bd-102">Constant Expressions</span></span>
<span data-ttu-id="a77bd-103">Un'espressione costante è costituita da un valore costante.</span><span class="sxs-lookup"><span data-stu-id="a77bd-103">A constant expression consists of a constant value.</span></span> <span data-ttu-id="a77bd-104">I valori costanti vengono convertiti direttamente in espressioni costanti dell'albero dei comandi, senza conversione nel client.</span><span class="sxs-lookup"><span data-stu-id="a77bd-104">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="a77bd-105">Questo vale anche per le espressioni che hanno come risultato un valore costante.</span><span class="sxs-lookup"><span data-stu-id="a77bd-105">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="a77bd-106">È pertanto possibile prevedere il comportamento dell'origine dati per tutte le espressioni che contengono costanti.</span><span class="sxs-lookup"><span data-stu-id="a77bd-106">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="a77bd-107">Il comportamento risultante può essere diverso da quello in CLR.</span><span class="sxs-lookup"><span data-stu-id="a77bd-107">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="a77bd-108">Nell'esempio seguente è illustrata un'espressione costante valutata nel server.</span><span class="sxs-lookup"><span data-stu-id="a77bd-108">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] <span data-ttu-id="a77bd-109">non supporta l'uso di una classe utente come costante.</span><span class="sxs-lookup"><span data-stu-id="a77bd-109">does not support using a user class as a constant.</span></span> <span data-ttu-id="a77bd-110">Un riferimento a una proprietà in una classe utente è tuttavia considerato una costante e viene convertito in un'espressione costante dell'albero dei comandi ed eseguito nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a77bd-110">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a77bd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a77bd-111">See also</span></span>

- [<span data-ttu-id="a77bd-112">Espressioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="a77bd-112">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
