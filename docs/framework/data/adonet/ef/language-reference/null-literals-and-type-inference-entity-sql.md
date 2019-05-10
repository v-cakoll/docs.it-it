---
title: Valori letterali Null e inferenza dei tipi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 3fea03146549f3d42bf08bbd5e7ce355d25bd4eb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64641818"
---
# <a name="null-literals-and-type-inference-entity-sql"></a><span data-ttu-id="a446a-102">Valori letterali Null e inferenza dei tipi (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a446a-102">Null Literals and Type Inference (Entity SQL)</span></span>
<span data-ttu-id="a446a-103">I valori letterali null sono compatibili con qualsiasi tipo nel sistema di tipi [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a446a-103">Null literals are compatible with any type in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] type system.</span></span> <span data-ttu-id="a446a-104">Tuttavia, per il tipo di valore letterale null corretta, inferenza [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono imposti determinati vincoli su dove può essere utilizzato un valore letterale null.</span><span class="sxs-lookup"><span data-stu-id="a446a-104">However, for the type of a null literal to be inferred correctly, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] imposes certain constraints on where a null literal can be used.</span></span>  
  
## <a name="typed-nulls"></a><span data-ttu-id="a446a-105">Valori null tipizzati</span><span class="sxs-lookup"><span data-stu-id="a446a-105">Typed Nulls</span></span>  
 <span data-ttu-id="a446a-106">I valori null tipizzati possono essere usati in qualsiasi posizione.</span><span class="sxs-lookup"><span data-stu-id="a446a-106">Typed nulls can be used anywhere.</span></span> <span data-ttu-id="a446a-107">L'inferenza dei tipi non è richiesta per i valori null tipizzati in quanto il tipo è noto.</span><span class="sxs-lookup"><span data-stu-id="a446a-107">Type inference is not required for typed nulls because the type is known.</span></span> <span data-ttu-id="a446a-108">È ad esempio possibile costruire un valore null di tipo Int16 con il costrutto [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente:</span><span class="sxs-lookup"><span data-stu-id="a446a-108">For example, you can construct a null of type Int16 with the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construct:</span></span>  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a><span data-ttu-id="a446a-109">Valori letterali null mobili</span><span class="sxs-lookup"><span data-stu-id="a446a-109">Free-Floating Null Literals</span></span>  
 <span data-ttu-id="a446a-110">I valori letterali null mobili possono essere usati nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a446a-110">Free-floating null literals can be used in the following contexts:</span></span>  
  
- <span data-ttu-id="a446a-111">Come argomento di un'espressione CAST o TREAT.</span><span class="sxs-lookup"><span data-stu-id="a446a-111">As an argument to a CAST or TREAT expression.</span></span> <span data-ttu-id="a446a-112">Questa è la modalità consigliata per produrre un'espressione null tipizzata.</span><span class="sxs-lookup"><span data-stu-id="a446a-112">This is the recommended way to produce a typed null expression.</span></span>  
  
- <span data-ttu-id="a446a-113">Come argomento di un metodo o di una funzione.</span><span class="sxs-lookup"><span data-stu-id="a446a-113">As an argument to a method or a function.</span></span> <span data-ttu-id="a446a-114">In questo caso si applicano le regole di overload standard.</span><span class="sxs-lookup"><span data-stu-id="a446a-114">Standard overload rules apply.</span></span>  
  
- <span data-ttu-id="a446a-115">Come uno degli argomenti di un'espressione aritmetica, ad esempio +, - o /.</span><span class="sxs-lookup"><span data-stu-id="a446a-115">As one of the arguments to an arithmetic expression such as +, -, or /.</span></span> <span data-ttu-id="a446a-116">Gli altri argomenti non possono essere valori letterali null. In caso contrario, l'inferenza dei tipi non è possibile.</span><span class="sxs-lookup"><span data-stu-id="a446a-116">The other arguments cannot be null literals, otherwise type inference is not possible.</span></span>  
  
- <span data-ttu-id="a446a-117">Come qualsiasi argomento di un'espressione logica (AND, OR o NOT).</span><span class="sxs-lookup"><span data-stu-id="a446a-117">As any of the arguments to a logical expression (AND, OR, or NOT).</span></span> <span data-ttu-id="a446a-118">Tutti gli argomenti sono noti come tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="a446a-118">All the arguments are known to be of type Boolean.</span></span>  
  
- <span data-ttu-id="a446a-119">Come argomento di un'espressione IS NULL o IS NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="a446a-119">As the argument to an IS NULL or IS NOT NULL expression.</span></span>  
  
- <span data-ttu-id="a446a-120">Come uno o più argomenti di un'espressione LIKE.</span><span class="sxs-lookup"><span data-stu-id="a446a-120">As one or more of the arguments to a LIKE expression.</span></span> <span data-ttu-id="a446a-121">Per tutti gli argomenti è previsto il tipo String.</span><span class="sxs-lookup"><span data-stu-id="a446a-121">All arguments are expected to be strings.</span></span>  
  
- <span data-ttu-id="a446a-122">Come uno o più argomenti di un costruttore di tipo denominato.</span><span class="sxs-lookup"><span data-stu-id="a446a-122">As one or more of the arguments to a named-type constructor.</span></span>  
  
- <span data-ttu-id="a446a-123">Come uno o più argomenti di un costruttore multiset.</span><span class="sxs-lookup"><span data-stu-id="a446a-123">As one or more of the arguments to a multiset constructor.</span></span> <span data-ttu-id="a446a-124">Almeno un argomento del costruttore multiset deve essere un'espressione non costituita da un valore letterale null.</span><span class="sxs-lookup"><span data-stu-id="a446a-124">At least one argument to the multiset constructor must be an expression that is not a null literal.</span></span>  
  
- <span data-ttu-id="a446a-125">Come una o più espressioni THEN o ELSE in un'espressione CASE.</span><span class="sxs-lookup"><span data-stu-id="a446a-125">As one or more of the THEN or ELSE expressions in a CASE expression.</span></span> <span data-ttu-id="a446a-126">Almeno una delle espressioni THEN o ELSE nell'espressione CASE deve essere un'espressione diversa da un valore letterale null.</span><span class="sxs-lookup"><span data-stu-id="a446a-126">At least one of the THEN or ELSE expressions in the CASE expression must be an expression other than a null literal.</span></span>  
  
 <span data-ttu-id="a446a-127">I valori letterali null mobili non possono essere usati in altri scenari.</span><span class="sxs-lookup"><span data-stu-id="a446a-127">Free-floating null literals cannot be used in other scenarios.</span></span> <span data-ttu-id="a446a-128">Non possono ad esempio essere usati come argomenti di un costruttore ROW.</span><span class="sxs-lookup"><span data-stu-id="a446a-128">For example,  they cannot be used as arguments to a row constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a446a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a446a-129">See also</span></span>

- [<span data-ttu-id="a446a-130">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a446a-130">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
