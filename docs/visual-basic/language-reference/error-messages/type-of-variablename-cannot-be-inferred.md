---
title: "Tipo di &#39; &lt;variablename&gt;&#39; non può essere dedotto perché i limiti del ciclo e la variabile di passaggio si amplia nello stesso tipo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 022e29e38a93d2880bbfa250e65a8b95b39ff140
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="d2b23-102">Tipo di &#39; &lt;variablename&gt;&#39; non può essere dedotto perché i limiti del ciclo e la variabile di passaggio si amplia nello stesso tipo</span><span class="sxs-lookup"><span data-stu-id="d2b23-102">Type of &#39;&lt;variablename&gt;&#39; cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="d2b23-103">È stato scritto un `For...Next` ciclo in cui il compilatore non è possibile dedurre un tipo di dati per la variabile di controllo perché vengono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2b23-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
-   <span data-ttu-id="d2b23-104">Il tipo di dati della variabile di controllo del ciclo non è specificato con una clausola `As` .</span><span class="sxs-lookup"><span data-stu-id="d2b23-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
-   <span data-ttu-id="d2b23-105">I limiti del ciclo e la clausola step contengono almeno due tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="d2b23-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
-   <span data-ttu-id="d2b23-106">Non esiste alcuna conversione standard tra i tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="d2b23-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="d2b23-107">Pertanto, il compilatore non è possibile dedurre il tipo di dati della variabile di controllo di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="d2b23-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="d2b23-108">Nell'esempio seguente, la variabile di passaggio è un carattere e i limiti del ciclo sono entrambe numeri interi.</span><span class="sxs-lookup"><span data-stu-id="d2b23-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="d2b23-109">Poiché non esiste alcuna conversione standard tra i caratteri e numeri interi, viene restituito questo errore.</span><span class="sxs-lookup"><span data-stu-id="d2b23-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="d2b23-110">**ID errore:** BC30982</span><span class="sxs-lookup"><span data-stu-id="d2b23-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2b23-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d2b23-111">To correct this error</span></span>  
  
-   <span data-ttu-id="d2b23-112">Modificare i tipi di limiti del ciclo e passaggio in base alle esigenze in modo che almeno uno di essi è un tipo che gli altri vengono ampliati ai.</span><span class="sxs-lookup"><span data-stu-id="d2b23-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="d2b23-113">Nell'esempio precedente, modificare il tipo di `stepVar` a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="d2b23-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="d2b23-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="d2b23-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   <span data-ttu-id="d2b23-115">Utilizzare le funzioni di conversione esplicita per convertire i limiti del ciclo e passaggio per i tipi appropriati.</span><span class="sxs-lookup"><span data-stu-id="d2b23-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="d2b23-116">Nell'esempio precedente, applicare il `Val` funzione `stepVar`.</span><span class="sxs-lookup"><span data-stu-id="d2b23-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d2b23-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2b23-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="d2b23-118">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="d2b23-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="d2b23-119">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="d2b23-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="d2b23-120">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="d2b23-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="d2b23-121">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="d2b23-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="d2b23-122">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="d2b23-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="d2b23-123">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="d2b23-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
