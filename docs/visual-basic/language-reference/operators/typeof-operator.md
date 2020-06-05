---
title: Operatore TypeOf
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 0cce36073b53442bce63f966f3bd94bd5d70d2a8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406327"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="b91eb-102">Operatore TypeOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b91eb-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="b91eb-103">Verifica se il tipo di runtime del risultato di un'espressione è compatibile con il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="b91eb-103">Checks whether the runtime type of an expression's result is type-compatible with the specified type.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="b91eb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b91eb-104">Syntax</span></span>  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="b91eb-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b91eb-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b91eb-106">Restituita.</span><span class="sxs-lookup"><span data-stu-id="b91eb-106">Returned.</span></span> <span data-ttu-id="b91eb-107">Valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b91eb-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="b91eb-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b91eb-108">Required.</span></span> <span data-ttu-id="b91eb-109">Qualsiasi espressione che restituisce un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="b91eb-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="b91eb-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b91eb-110">Required.</span></span> <span data-ttu-id="b91eb-111">Qualsiasi nome di un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="b91eb-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b91eb-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="b91eb-112">Remarks</span></span>  
 <span data-ttu-id="b91eb-113">L'operatore `TypeOf` determina se il tipo di `objectexpression` in fase di esecuzione è compatibile con `typename`.</span><span class="sxs-lookup"><span data-stu-id="b91eb-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="b91eb-114">La compatibilità dipende dalla categoria del tipo di `typename`.</span><span class="sxs-lookup"><span data-stu-id="b91eb-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="b91eb-115">La tabella seguente illustra come viene determinata la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="b91eb-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="b91eb-116">Categoria del tipo di `typename`</span><span class="sxs-lookup"><span data-stu-id="b91eb-116">Type category of `typename`</span></span>|<span data-ttu-id="b91eb-117">Criterio di compatibilità</span><span class="sxs-lookup"><span data-stu-id="b91eb-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="b91eb-118">Class</span><span class="sxs-lookup"><span data-stu-id="b91eb-118">Class</span></span>|<span data-ttu-id="b91eb-119">`objectexpression` è del tipo `typename` o eredita da `typename`</span><span class="sxs-lookup"><span data-stu-id="b91eb-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="b91eb-120">Struttura</span><span class="sxs-lookup"><span data-stu-id="b91eb-120">Structure</span></span>|<span data-ttu-id="b91eb-121">`objectexpression` è del tipo `typename`</span><span class="sxs-lookup"><span data-stu-id="b91eb-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="b91eb-122">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="b91eb-122">Interface</span></span>|<span data-ttu-id="b91eb-123">`objectexpression` implementa `typename` o eredita da una classe che implementa `typename`</span><span class="sxs-lookup"><span data-stu-id="b91eb-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="b91eb-124">Se il tipo di `objectexpression` in fase di esecuzione soddisfa il criterio di compatibilità, `result` sarà `True`.</span><span class="sxs-lookup"><span data-stu-id="b91eb-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="b91eb-125">In caso contrario, `result` sarà `False`.</span><span class="sxs-lookup"><span data-stu-id="b91eb-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="b91eb-126">Se `objectexpression` è null, `TypeOf`...`Is` restituisce `False` e ...`IsNot` restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="b91eb-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="b91eb-127">`TypeOf` viene sempre usato con la parola chiave `Is` per costruire un'espressione `TypeOf`...`Is` oppure con la parola chiave `IsNot` per costruire un'espressione `TypeOf`...`IsNot`.</span><span class="sxs-lookup"><span data-stu-id="b91eb-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b91eb-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="b91eb-128">Example</span></span>  
 <span data-ttu-id="b91eb-129">Nell'esempio seguente le espressioni `TypeOf`...`Is` vengono usate per verificare la compatibilità dei tipi di due variabili di riferimento a un oggetto con diversi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="b91eb-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 <span data-ttu-id="b91eb-130">La variabile `refInteger` presenta un tipo in fase di esecuzione `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b91eb-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="b91eb-131">È compatibile con `Integer`, ma non con `Double`.</span><span class="sxs-lookup"><span data-stu-id="b91eb-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="b91eb-132">La variabile `refForm` presenta un tipo in fase di esecuzione <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="b91eb-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="b91eb-133">È compatibile con <xref:System.Windows.Forms.Form> perché si tratta del relativo tipo, con <xref:System.Windows.Forms.Control> perché <xref:System.Windows.Forms.Form> eredita da <xref:System.Windows.Forms.Control> e con <xref:System.ComponentModel.IComponent> perché <xref:System.Windows.Forms.Form> eredita da <xref:System.ComponentModel.Component>, che implementa <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="b91eb-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="b91eb-134">`refForm` non è invece compatibile con <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="b91eb-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91eb-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b91eb-135">See also</span></span>

- [<span data-ttu-id="b91eb-136">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="b91eb-136">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="b91eb-137">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="b91eb-137">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="b91eb-138">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b91eb-138">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="b91eb-139">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b91eb-139">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="b91eb-140">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="b91eb-140">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="b91eb-141">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="b91eb-141">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
