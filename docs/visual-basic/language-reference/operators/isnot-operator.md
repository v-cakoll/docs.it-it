---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966932"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="7cbdb-102">Operatore IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7cbdb-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="7cbdb-103">Confronta due variabili di riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cbdb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7cbdb-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="7cbdb-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7cbdb-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7cbdb-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-106">Required.</span></span> <span data-ttu-id="7cbdb-107">Valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="7cbdb-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-108">Required.</span></span> <span data-ttu-id="7cbdb-109">Qualsiasi `Object` variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="7cbdb-110">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-110">Required.</span></span> <span data-ttu-id="7cbdb-111">Qualsiasi `Object` variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cbdb-112">Note</span><span class="sxs-lookup"><span data-stu-id="7cbdb-112">Remarks</span></span>  
 <span data-ttu-id="7cbdb-113">L' `IsNot` operatore determina se due riferimenti a oggetti si riferiscono a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="7cbdb-114">Tuttavia, non esegue confronti di valori.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="7cbdb-115">Se `object1` ed `False` `result` `result` `True`entrambi fanno riferimento alla stessa istanza dell'oggetto, è; in caso contrario, è. `object2`</span><span class="sxs-lookup"><span data-stu-id="7cbdb-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="7cbdb-116">`IsNot`è l'opposto dell' `Is` operatore.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="7cbdb-117">Il vantaggio di `IsNot` è che è possibile evitare la sintassi scomoda `Not` con `Is`e, che può essere difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="7cbdb-118">È possibile utilizzare gli `Is` operatori `IsNot` e per testare gli oggetti ad associazione anticipata e ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7cbdb-119">Non `IsNot` è possibile usare l'operatore per confrontare le espressioni restituite `TypeOf` dall'operatore.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="7cbdb-120">È invece necessario usare gli `Not` operatori e. `Is`</span><span class="sxs-lookup"><span data-stu-id="7cbdb-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cbdb-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="7cbdb-121">Example</span></span>  
 <span data-ttu-id="7cbdb-122">Nell'esempio di codice seguente vengono usati `Is` sia l'operatore `IsNot` che l'operatore per eseguire lo stesso confronto.</span><span class="sxs-lookup"><span data-stu-id="7cbdb-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="7cbdb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cbdb-123">See also</span></span>

- [<span data-ttu-id="7cbdb-124">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="7cbdb-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="7cbdb-125">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="7cbdb-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="7cbdb-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7cbdb-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7cbdb-127">Procedura: Verificare se due oggetti sono uguali</span><span class="sxs-lookup"><span data-stu-id="7cbdb-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
