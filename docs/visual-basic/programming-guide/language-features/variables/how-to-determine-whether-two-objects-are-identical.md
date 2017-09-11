---
title: 'Procedura: determinare se due oggetti sono identici (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- testing, objects
- objects [Visual Basic], comparing
- object variables, determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c9621412eb1429ed07d8861114a67a67b6c1d58c
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="6a057-102">Procedura: determinare se due oggetti sono identici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a057-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="6a057-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], due riferimenti a variabili vengono considerati identici se i relativi puntatori sono uguali, vale a dire se entrambe le variabili puntano alla stessa istanza di classe nella memoria.</span><span class="sxs-lookup"><span data-stu-id="6a057-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="6a057-104">Ad esempio, in un'applicazione Windows Form, è per un confronto per determinare se l'istanza corrente (`Me`) è uguale a un'istanza specifica, ad esempio `Form2`.</span><span class="sxs-lookup"><span data-stu-id="6a057-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="6a057-105">sono disponibili due operatori per confrontare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="6a057-105"> provides two operators to compare pointers.</span></span> <span data-ttu-id="6a057-106">Il [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) restituisce `True` se gli oggetti sono identici e [IsNot (operatore)](../../../../visual-basic/language-reference/operators/isnot-operator.md) restituisce `True` se non lo sono.</span><span class="sxs-lookup"><span data-stu-id="6a057-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="6a057-107">Determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="6a057-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="6a057-108">Per determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="6a057-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="6a057-109">Impostare un `Boolean` espressione da testare i due oggetti.</span><span class="sxs-lookup"><span data-stu-id="6a057-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="6a057-110">Un'espressione di test, utilizzare il `Is` operatore con i due oggetti come operandi.</span><span class="sxs-lookup"><span data-stu-id="6a057-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="6a057-111">`Is`Restituisce `True` se gli oggetti puntano alla stessa istanza di classe.</span><span class="sxs-lookup"><span data-stu-id="6a057-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="6a057-112">Determinare se due oggetti non sono identici</span><span class="sxs-lookup"><span data-stu-id="6a057-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="6a057-113">A volte si desidera eseguire un'azione se i due oggetti non sono identici, ma può essere difficile combinare `Not` e `Is`, ad esempio `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="6a057-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="6a057-114">In questo caso è possibile utilizzare il `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="6a057-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="6a057-115">Per determinare se due oggetti non sono identici</span><span class="sxs-lookup"><span data-stu-id="6a057-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="6a057-116">Impostare un `Boolean` espressione da testare i due oggetti.</span><span class="sxs-lookup"><span data-stu-id="6a057-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="6a057-117">Un'espressione di test, utilizzare il `IsNot` operatore con i due oggetti come operandi.</span><span class="sxs-lookup"><span data-stu-id="6a057-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="6a057-118">`IsNot`Restituisce `True` se gli oggetti non puntano alla stessa istanza di classe.</span><span class="sxs-lookup"><span data-stu-id="6a057-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a057-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a057-119">Example</span></span>  
 <span data-ttu-id="6a057-120">Nell'esempio seguente verifica coppie di `Object` variabili per stabilire se puntano alla stessa istanza di classe.</span><span class="sxs-lookup"><span data-stu-id="6a057-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 <span data-ttu-id="6a057-121">[!code-vb[VbVbalrKeywords&#14;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="6a057-121">[!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span></span>  
  
 <span data-ttu-id="6a057-122">Nell'esempio precedente viene visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="6a057-122">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="6a057-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a057-123">See Also</span></span>  
 <span data-ttu-id="6a057-124">[Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="6a057-124">[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="6a057-125"> [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6a057-125"> [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="6a057-126"> [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span><span class="sxs-lookup"><span data-stu-id="6a057-126"> [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span></span>  
<span data-ttu-id="6a057-127"> [Is (operatore)](../../../../visual-basic/language-reference/operators/is-operator.md) </span><span class="sxs-lookup"><span data-stu-id="6a057-127"> [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) </span></span>  
<span data-ttu-id="6a057-128"> [IsNot (operatore)](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span><span class="sxs-lookup"><span data-stu-id="6a057-128"> [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span></span>  
<span data-ttu-id="6a057-129"> [Procedura: determinare se due oggetti sono correlati](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="6a057-129"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="6a057-130"> [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="6a057-130"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>
