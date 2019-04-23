---
title: 'Procedura: Determinare se due oggetti sono identici (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: aae053ae0473ed6ced0f28da3d5e5afc0be629df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295036"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="03843-102">Procedura: Determinare se due oggetti sono identici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03843-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="03843-103">In Visual Basic, due riferimenti a variabili sono considerati identici se i relativi puntatori sono gli stessi, vale a dire, se entrambe le variabili puntano alla stessa istanza di classe in memoria.</span><span class="sxs-lookup"><span data-stu-id="03843-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="03843-104">Ad esempio, in un'applicazione Windows Forms, si potrebbe voler eseguire un confronto per determinare se l'istanza corrente (`Me`) è quello utilizzato per una particolare istanza, ad esempio `Form2`.</span><span class="sxs-lookup"><span data-stu-id="03843-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="03843-105">Visual Basic fornisce due operatori per confrontare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="03843-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="03843-106">Il [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) restituisce `True` se gli oggetti sono identici e il [operatore IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) restituisce `True` se non lo sono.</span><span class="sxs-lookup"><span data-stu-id="03843-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="03843-107">Determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="03843-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="03843-108">Per determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="03843-108">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="03843-109">Configurare un `Boolean` espressione da testare i due oggetti.</span><span class="sxs-lookup"><span data-stu-id="03843-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="03843-110">Nell'espressione test, usare il `Is` operatore con i due oggetti come operandi.</span><span class="sxs-lookup"><span data-stu-id="03843-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="03843-111">`Is` Restituisce `True` se gli oggetti puntano alla stessa istanza di classe.</span><span class="sxs-lookup"><span data-stu-id="03843-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="03843-112">Determinare se due oggetti non sono identici</span><span class="sxs-lookup"><span data-stu-id="03843-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="03843-113">Talvolta si desidera eseguire un'azione se i due oggetti non sono identici, ma può essere difficile combinare `Not` e `Is`, ad esempio `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="03843-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="03843-114">In tal caso è possibile usare il `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="03843-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="03843-115">Per determinare se due oggetti non sono identici</span><span class="sxs-lookup"><span data-stu-id="03843-115">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="03843-116">Configurare un `Boolean` espressione da testare i due oggetti.</span><span class="sxs-lookup"><span data-stu-id="03843-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="03843-117">Nell'espressione test, usare il `IsNot` operatore con i due oggetti come operandi.</span><span class="sxs-lookup"><span data-stu-id="03843-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="03843-118">`IsNot` Restituisce `True` se gli oggetti non puntano alla stessa istanza di classe.</span><span class="sxs-lookup"><span data-stu-id="03843-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03843-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="03843-119">Example</span></span>  
 <span data-ttu-id="03843-120">L'esempio seguente verifica coppie di `Object` variabili per vedere se puntano alla stessa istanza di classe.</span><span class="sxs-lookup"><span data-stu-id="03843-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="03843-121">Nell'esempio precedente consente di visualizzare l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="03843-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="03843-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03843-122">See also</span></span>

- [<span data-ttu-id="03843-123">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="03843-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="03843-124">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="03843-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="03843-125">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="03843-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="03843-126">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="03843-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="03843-127">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="03843-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="03843-128">Procedura: Determinare se due oggetti sono correlati</span><span class="sxs-lookup"><span data-stu-id="03843-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="03843-129">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="03843-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
