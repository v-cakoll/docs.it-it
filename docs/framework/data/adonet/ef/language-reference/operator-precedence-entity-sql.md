---
title: Precedenza tra gli operatori (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 2d8c78f410708fd1aa843ee8f14f7243a9f686c0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249777"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="80110-102">Precedenza tra gli operatori (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="80110-102">Operator Precedence (Entity SQL)</span></span>
<span data-ttu-id="80110-103">Quando una [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query ha più operatori, la precedenza degli operatori determina la sequenza in cui vengono eseguite le operazioni.</span><span class="sxs-lookup"><span data-stu-id="80110-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="80110-104">L'ordine di esecuzione può modificare in modo significativo il risultato della query.</span><span class="sxs-lookup"><span data-stu-id="80110-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="80110-105">Nella tabella seguente sono indicati i livelli di precedenza degli operatori.</span><span class="sxs-lookup"><span data-stu-id="80110-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="80110-106">Un operatore con livello di precedenza più alto viene valutato prima di un operatore con livello di precedenza più basso.</span><span class="sxs-lookup"><span data-stu-id="80110-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="80110-107">Level</span><span class="sxs-lookup"><span data-stu-id="80110-107">Level</span></span>|<span data-ttu-id="80110-108">Tipo di operazione</span><span class="sxs-lookup"><span data-stu-id="80110-108">Operation type</span></span>|<span data-ttu-id="80110-109">Operator</span><span class="sxs-lookup"><span data-stu-id="80110-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="80110-110">1</span><span class="sxs-lookup"><span data-stu-id="80110-110">1</span></span>|<span data-ttu-id="80110-111">Primario</span><span class="sxs-lookup"><span data-stu-id="80110-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="80110-112">2</span><span class="sxs-lookup"><span data-stu-id="80110-112">2</span></span>|<span data-ttu-id="80110-113">Unario</span><span class="sxs-lookup"><span data-stu-id="80110-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="80110-114">3</span><span class="sxs-lookup"><span data-stu-id="80110-114">3</span></span>|<span data-ttu-id="80110-115">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="80110-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="80110-116">4</span><span class="sxs-lookup"><span data-stu-id="80110-116">4</span></span>|<span data-ttu-id="80110-117">Addizione</span><span class="sxs-lookup"><span data-stu-id="80110-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="80110-118">5</span><span class="sxs-lookup"><span data-stu-id="80110-118">5</span></span>|<span data-ttu-id="80110-119">Ordering</span><span class="sxs-lookup"><span data-stu-id="80110-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="80110-120">6</span><span class="sxs-lookup"><span data-stu-id="80110-120">6</span></span>|<span data-ttu-id="80110-121">Uguaglianza</span><span class="sxs-lookup"><span data-stu-id="80110-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="80110-122">7</span><span class="sxs-lookup"><span data-stu-id="80110-122">7</span></span>|<span data-ttu-id="80110-123">AND condizionale</span><span class="sxs-lookup"><span data-stu-id="80110-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="80110-124">8</span><span class="sxs-lookup"><span data-stu-id="80110-124">8</span></span>|<span data-ttu-id="80110-125">OR condizionale</span><span class="sxs-lookup"><span data-stu-id="80110-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="80110-126">Se due operatori in un'espressione hanno lo stesso livello di precedenza, vengono valutati da sinistra verso destra in base alla posizione nella query.</span><span class="sxs-lookup"><span data-stu-id="80110-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="80110-127">L'espressione `x+y-z` viene ad esempio valutata come `(x+y)-z`.</span><span class="sxs-lookup"><span data-stu-id="80110-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="80110-128">Per ignorare l'ordine di precedenza predefinito degli operatori in una query, è possibile usare le parentesi.</span><span class="sxs-lookup"><span data-stu-id="80110-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="80110-129">Tutti gli operatori racchiusi tra parentesi vengono valutati per primi in modo da ottenere un singolo risultato, che verrà quindi usato dagli operatori all'esterno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="80110-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="80110-130">Ad esempio, `x+y*z` `y` moltiplica `x` `(x+y)*z` `x` per e quindi aggiunge`z`, ma aggiunge a`y` e quindi moltiplica il risultato per. `z`</span><span class="sxs-lookup"><span data-stu-id="80110-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80110-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80110-131">See also</span></span>

- [<span data-ttu-id="80110-132">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="80110-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
