---
title: Operatore IsNot
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336068"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="67553-102">Operatore IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67553-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="67553-103">Confronta due variabili di riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="67553-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="67553-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67553-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="67553-105">Parti</span><span class="sxs-lookup"><span data-stu-id="67553-105">Parts</span></span>
 <span data-ttu-id="67553-106">`result` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="67553-106">`result` Required.</span></span> <span data-ttu-id="67553-107">Valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="67553-107">A `Boolean` value.</span></span>

 <span data-ttu-id="67553-108">`object1` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="67553-108">`object1` Required.</span></span> <span data-ttu-id="67553-109">Qualsiasi `Object` variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="67553-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="67553-110">`object2` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="67553-110">`object2` Required.</span></span> <span data-ttu-id="67553-111">Qualsiasi `Object` variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="67553-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="67553-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="67553-112">Remarks</span></span>
 <span data-ttu-id="67553-113">L'operatore `IsNot` determina se due riferimenti a oggetti si riferiscono a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="67553-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="67553-114">Tuttavia, non esegue confronti di valori.</span><span class="sxs-lookup"><span data-stu-id="67553-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="67553-115">Se `object1` e `object2` entrambi fanno riferimento alla stessa istanza dell'oggetto, `result` è `False`; in caso contrario, `result` viene `True`.</span><span class="sxs-lookup"><span data-stu-id="67553-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="67553-116">`IsNot` è l'opposto dell'operatore `Is`.</span><span class="sxs-lookup"><span data-stu-id="67553-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="67553-117">Il vantaggio di `IsNot` è che è possibile evitare la sintassi scomoda con `Not` e `Is`, che può essere difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="67553-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="67553-118">È possibile utilizzare gli operatori `Is` e `IsNot` per testare gli oggetti ad associazione anticipata e ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="67553-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="67553-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="67553-119">Example</span></span>
 <span data-ttu-id="67553-120">Nell'esempio di codice seguente vengono usati sia l'operatore `Is` che l'operatore `IsNot` per eseguire lo stesso confronto.</span><span class="sxs-lookup"><span data-stu-id="67553-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="67553-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67553-121">See also</span></span>

- [<span data-ttu-id="67553-122">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="67553-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="67553-123">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="67553-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="67553-124">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67553-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="67553-125">Procedura: Determinare se due oggetti sono uguali</span><span class="sxs-lookup"><span data-stu-id="67553-125">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
