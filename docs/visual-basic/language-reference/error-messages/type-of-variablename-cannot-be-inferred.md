---
title: Impossibile dedurre il tipo di '<variablename>' perché i limiti del ciclo e la clausola STEP non eseguono la conversione nello stesso tipo
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: c3086f79fb71693810bc8f14e8c0f493aa1e6515
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512713"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="f199a-102">Non è possibile\<dedurre il tipo di ' variablename >' perché i limiti del ciclo e la variabile Step non si ampliano allo stesso tipo</span><span class="sxs-lookup"><span data-stu-id="f199a-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>

<span data-ttu-id="f199a-103">È stato scritto un `For...Next` ciclo in cui il compilatore non può dedurre un tipo di dati per la variabile di controllo del ciclo perché sono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f199a-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>

- <span data-ttu-id="f199a-104">Il tipo di dati della variabile di controllo del ciclo non è specificato con una clausola `As` .</span><span class="sxs-lookup"><span data-stu-id="f199a-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>

- <span data-ttu-id="f199a-105">I limiti del ciclo e la clausola step contengono almeno due tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="f199a-105">The loop bounds and step variable contain at least two data types.</span></span>

- <span data-ttu-id="f199a-106">Non esistono conversioni standard tra i tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="f199a-106">No standard conversions exist between the data types.</span></span>

 <span data-ttu-id="f199a-107">Pertanto, il compilatore non può dedurre il tipo di dati della variabile di controllo di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="f199a-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>

 <span data-ttu-id="f199a-108">Nell'esempio seguente, la variabile Step è un carattere e i limiti del ciclo sono entrambi numeri interi.</span><span class="sxs-lookup"><span data-stu-id="f199a-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="f199a-109">Poiché non esiste una conversione standard tra i caratteri e i numeri interi, questo errore viene segnalato.</span><span class="sxs-lookup"><span data-stu-id="f199a-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

<span data-ttu-id="f199a-110">**ID errore:** BC30982</span><span class="sxs-lookup"><span data-stu-id="f199a-110">**Error ID:** BC30982</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f199a-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f199a-111">To correct this error</span></span>

- <span data-ttu-id="f199a-112">Modificare i tipi di limiti del ciclo e la variabile Step in modo che almeno uno di essi sia un tipo a cui gli altri si ampliano.</span><span class="sxs-lookup"><span data-stu-id="f199a-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="f199a-113">Nell'esempio precedente, modificare il tipo di `stepVar` in. `Integer`</span><span class="sxs-lookup"><span data-stu-id="f199a-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>

  ```vb
  Dim stepVar = 1
  ```

  <span data-ttu-id="f199a-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="f199a-114">-or-</span></span>

  ```vb
  Dim stepVar As Integer = 1
  ```

- <span data-ttu-id="f199a-115">Utilizzare le funzioni di conversione esplicita per convertire i limiti del ciclo e la variabile Step nei tipi appropriati.</span><span class="sxs-lookup"><span data-stu-id="f199a-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="f199a-116">Nell'esempio precedente, applicare la `Val` funzione a. `stepVar`</span><span class="sxs-lookup"><span data-stu-id="f199a-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a><span data-ttu-id="f199a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f199a-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="f199a-118">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="f199a-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="f199a-119">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="f199a-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="f199a-120">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="f199a-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="f199a-121">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="f199a-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="f199a-122">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="f199a-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="f199a-123">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="f199a-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
