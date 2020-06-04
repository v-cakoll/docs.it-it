---
title: 'Procedura: determinare se due oggetti sono identici'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 67c3af8b7bdac3ad1c7e4908f1ac2684df7a87aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410477"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="bf733-102">Procedura: determinare se due oggetti sono identici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf733-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="bf733-103">In Visual Basic, due riferimenti a variabili sono considerati identici se i relativi puntatori sono gli stessi, ovvero se entrambe le variabili puntano alla stessa istanza della classe in memoria.</span><span class="sxs-lookup"><span data-stu-id="bf733-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="bf733-104">In una Windows Forms Application, ad esempio, può essere necessario eseguire un confronto per determinare se l'istanza corrente ( `Me` ) è uguale a una particolare istanza, ad esempio `Form2` .</span><span class="sxs-lookup"><span data-stu-id="bf733-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="bf733-105">Visual Basic fornisce due operatori per confrontare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="bf733-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="bf733-106">L' [operatore is](../../../language-reference/operators/is-operator.md) restituisce `True` se gli oggetti sono identici e l' [operatore](../../../language-reference/operators/isnot-operator.md) non restituisce `True` se non lo sono.</span><span class="sxs-lookup"><span data-stu-id="bf733-106">The [Is Operator](../../../language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="bf733-107">Determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="bf733-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="bf733-108">Per determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="bf733-108">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="bf733-109">Configurare un' `Boolean` espressione per testare i due oggetti.</span><span class="sxs-lookup"><span data-stu-id="bf733-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="bf733-110">Nell'espressione di test usare l' `Is` operatore con i due oggetti come operandi.</span><span class="sxs-lookup"><span data-stu-id="bf733-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="bf733-111">`Is`restituisce `True` se gli oggetti puntano alla stessa istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="bf733-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="bf733-112">Determinare se due oggetti non sono identici</span><span class="sxs-lookup"><span data-stu-id="bf733-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="bf733-113">In alcuni casi si desidera eseguire un'azione se i due oggetti non sono identici e può essere scomodo combinare `Not` e `Is` , ad esempio `If Not obj1 Is obj2` .</span><span class="sxs-lookup"><span data-stu-id="bf733-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="bf733-114">In tal caso, è possibile usare l' `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="bf733-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="bf733-115">Per determinare se due oggetti non sono identici</span><span class="sxs-lookup"><span data-stu-id="bf733-115">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="bf733-116">Configurare un' `Boolean` espressione per testare i due oggetti.</span><span class="sxs-lookup"><span data-stu-id="bf733-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="bf733-117">Nell'espressione di test usare l' `IsNot` operatore con i due oggetti come operandi.</span><span class="sxs-lookup"><span data-stu-id="bf733-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="bf733-118">`IsNot`restituisce `True` se gli oggetti non puntano alla stessa istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="bf733-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf733-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf733-119">Example</span></span>  
 <span data-ttu-id="bf733-120">Nell'esempio seguente vengono testate coppie di `Object` variabili per verificare se puntano alla stessa istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="bf733-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="bf733-121">Nell'esempio precedente viene visualizzato il seguente output.</span><span class="sxs-lookup"><span data-stu-id="bf733-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="bf733-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf733-122">See also</span></span>

- [<span data-ttu-id="bf733-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="bf733-123">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="bf733-124">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="bf733-124">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="bf733-125">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="bf733-125">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="bf733-126">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="bf733-126">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="bf733-127">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="bf733-127">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="bf733-128">Procedura: determinare se due oggetti sono correlati</span><span class="sxs-lookup"><span data-stu-id="bf733-128">How to: Determine Whether Two Objects Are Related</span></span>](how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="bf733-129">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="bf733-129">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
