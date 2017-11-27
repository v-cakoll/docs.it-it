---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c192cdb4ac43ad614fbfb663079c03ddc6c358c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="byval-visual-basic"></a><span data-ttu-id="fa8d8-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa8d8-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="fa8d8-103">Specifica che un argomento è passato in modo che la routine o proprietà chiamata non è possibile modificare il valore di una variabile sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="fa8d8-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa8d8-104">Note</span><span class="sxs-lookup"><span data-stu-id="fa8d8-104">Remarks</span></span>  
 <span data-ttu-id="fa8d8-105">Il modificatore `ByVal` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa8d8-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="fa8d8-106">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="fa8d8-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="fa8d8-107">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="fa8d8-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="fa8d8-108">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="fa8d8-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="fa8d8-109">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="fa8d8-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="fa8d8-110">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="fa8d8-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="fa8d8-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa8d8-111">Example</span></span>  
 <span data-ttu-id="fa8d8-112">Nell'esempio seguente viene illustrato l'utilizzo del `ByVal` con un argomento di tipo riferimento meccanismo di passaggio dei parametri.</span><span class="sxs-lookup"><span data-stu-id="fa8d8-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="fa8d8-113">Nell'esempio, l'argomento è `c1`, un'istanza della classe `Class1`.</span><span class="sxs-lookup"><span data-stu-id="fa8d8-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="fa8d8-114">`ByVal`impedisce al codice nelle procedure di modifica del valore sottostante dell'argomento di riferimento, `c1`, ma non protegge accessibili campi e proprietà di `c1`.</span><span class="sxs-lookup"><span data-stu-id="fa8d8-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fa8d8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa8d8-115">See Also</span></span>  
 [<span data-ttu-id="fa8d8-116">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fa8d8-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="fa8d8-117">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="fa8d8-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
