---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 32e8f9532244679d2994b0e3d98279d75f7e77b4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701042"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="953a7-102">Operatore IsNot (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="953a7-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="953a7-103">Confronta due variabili di riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="953a7-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="953a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="953a7-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="953a7-105">Parti</span><span class="sxs-lookup"><span data-stu-id="953a7-105">Parts</span></span>
 <span data-ttu-id="953a7-106">`result` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="953a7-106">`result` Required.</span></span> <span data-ttu-id="953a7-107">Valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="953a7-107">A `Boolean` value.</span></span>

 <span data-ttu-id="953a7-108">`object1` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="953a7-108">`object1` Required.</span></span> <span data-ttu-id="953a7-109">Qualsiasi variabile o espressione `Object`.</span><span class="sxs-lookup"><span data-stu-id="953a7-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="953a7-110">`object2` Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="953a7-110">`object2` Required.</span></span> <span data-ttu-id="953a7-111">Qualsiasi variabile o espressione `Object`.</span><span class="sxs-lookup"><span data-stu-id="953a7-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="953a7-112">Note</span><span class="sxs-lookup"><span data-stu-id="953a7-112">Remarks</span></span>
 <span data-ttu-id="953a7-113">L'operatore `IsNot` determina se due riferimenti a oggetti si riferiscono a oggetti diversi.</span><span class="sxs-lookup"><span data-stu-id="953a7-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="953a7-114">Tuttavia, non esegue confronti di valori.</span><span class="sxs-lookup"><span data-stu-id="953a7-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="953a7-115">Se `object1` e `object2` fanno entrambi riferimento alla stessa istanza dell'oggetto, `result` è `False`. in caso contrario, `result` è `True`.</span><span class="sxs-lookup"><span data-stu-id="953a7-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="953a7-116">`IsNot` è il contrario dell'operatore `Is`.</span><span class="sxs-lookup"><span data-stu-id="953a7-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="953a7-117">Il vantaggio di `IsNot` è che è possibile evitare la sintassi scomoda con `Not` e `Is`, che può essere difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="953a7-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="953a7-118">È possibile utilizzare gli operatori `Is` e `IsNot` per testare gli oggetti ad associazione anticipata e ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="953a7-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="953a7-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="953a7-119">Example</span></span>
 <span data-ttu-id="953a7-120">Nell'esempio di codice seguente vengono usati sia l'operatore `Is` che l'operatore `IsNot` per eseguire lo stesso confronto.</span><span class="sxs-lookup"><span data-stu-id="953a7-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="953a7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="953a7-121">See also</span></span>

- [<span data-ttu-id="953a7-122">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="953a7-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="953a7-123">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="953a7-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="953a7-124">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="953a7-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- <span data-ttu-id="953a7-125">[Procedura: Verificare se due oggetti sono uguali @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="953a7-125">[How to: Test Whether Two Objects Are the Same](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)</span></span>
