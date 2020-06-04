---
title: Operatore Is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 3cc0ae5f04358fbe6b2aabc50498f39ca7225164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370804"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="588bf-102">Operatore Is (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="588bf-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="588bf-103">Confronta due variabili di riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="588bf-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="588bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="588bf-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="588bf-105">Parti</span><span class="sxs-lookup"><span data-stu-id="588bf-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="588bf-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="588bf-106">Required.</span></span> <span data-ttu-id="588bf-107">Qualsiasi `Boolean` valore.</span><span class="sxs-lookup"><span data-stu-id="588bf-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="588bf-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="588bf-108">Required.</span></span> <span data-ttu-id="588bf-109">Qualsiasi `Object` nome.</span><span class="sxs-lookup"><span data-stu-id="588bf-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="588bf-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="588bf-110">Required.</span></span> <span data-ttu-id="588bf-111">Qualsiasi `Object` nome.</span><span class="sxs-lookup"><span data-stu-id="588bf-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="588bf-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="588bf-112">Remarks</span></span>  
 <span data-ttu-id="588bf-113">L' `Is` operatore determina se due riferimenti a oggetti si riferiscono allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="588bf-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="588bf-114">Tuttavia, non esegue confronti di valori.</span><span class="sxs-lookup"><span data-stu-id="588bf-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="588bf-115">Se `object1` ed `object2` entrambi fanno riferimento alla stessa istanza dell'oggetto, `result` è `True` ; in caso contrario, `result` è `False` .</span><span class="sxs-lookup"><span data-stu-id="588bf-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="588bf-116">`Is`può essere usato anche con la `TypeOf` parola chiave per creare un' `TypeOf` espressione... `Is` che verifica se una variabile oggetto è compatibile con un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="588bf-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="588bf-117">La `Is` parola chiave viene inoltre utilizzata nell'oggetto [Select... Istruzione case](../statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="588bf-117">The `Is` keyword is also used in the [Select...Case Statement](../statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="588bf-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="588bf-118">Example</span></span>  
 <span data-ttu-id="588bf-119">Nell'esempio seguente viene usato l' `Is` operatore per confrontare coppie di riferimenti a oggetti.</span><span class="sxs-lookup"><span data-stu-id="588bf-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="588bf-120">I risultati vengono assegnati a un `Boolean` valore che indica se i due oggetti sono identici.</span><span class="sxs-lookup"><span data-stu-id="588bf-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="588bf-121">Come illustrato nell'esempio precedente, è possibile usare l' `Is` operatore per testare gli oggetti ad associazione anticipata e ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="588bf-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="588bf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="588bf-122">See also</span></span>

- [<span data-ttu-id="588bf-123">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="588bf-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="588bf-124">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="588bf-124">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="588bf-125">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="588bf-125">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="588bf-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="588bf-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="588bf-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="588bf-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="588bf-128">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="588bf-128">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
