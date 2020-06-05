---
title: Impossibile dedurre il tipo di '<variablename>' perché i limiti del ciclo e la clausola STEP non eseguono la conversione nello stesso tipo
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: 74b690ce3dee87e481c629a254e629be4b40f8cd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387010"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="43729-102">Impossibile dedurre il tipo di '\<variablename>' perché i limiti del ciclo e la clausola STEP non eseguono la conversione nello stesso tipo</span><span class="sxs-lookup"><span data-stu-id="43729-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>

<span data-ttu-id="43729-103">È stato scritto un `For...Next` ciclo in cui il compilatore non può dedurre un tipo di dati per la variabile di controllo del ciclo perché sono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43729-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>

- <span data-ttu-id="43729-104">Il tipo di dati della variabile di controllo del ciclo non è specificato con una clausola `As` .</span><span class="sxs-lookup"><span data-stu-id="43729-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>

- <span data-ttu-id="43729-105">I limiti del ciclo e la clausola step contengono almeno due tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="43729-105">The loop bounds and step variable contain at least two data types.</span></span>

- <span data-ttu-id="43729-106">Non esistono conversioni standard tra i tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="43729-106">No standard conversions exist between the data types.</span></span>

 <span data-ttu-id="43729-107">Pertanto, il compilatore non può dedurre il tipo di dati della variabile di controllo di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="43729-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>

 <span data-ttu-id="43729-108">Nell'esempio seguente, la variabile Step è un carattere e i limiti del ciclo sono entrambi numeri interi.</span><span class="sxs-lookup"><span data-stu-id="43729-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="43729-109">Poiché non esiste una conversione standard tra i caratteri e i numeri interi, questo errore viene segnalato.</span><span class="sxs-lookup"><span data-stu-id="43729-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>

```vb
Dim stepVar = "1"c
Dim m = 0
Dim n = 20

' Not valid.
' For i = 1 To 10 Step stepVar
    ' Loop processing
' Next
```

<span data-ttu-id="43729-110">**ID errore:** BC30982</span><span class="sxs-lookup"><span data-stu-id="43729-110">**Error ID:** BC30982</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="43729-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="43729-111">To correct this error</span></span>

- <span data-ttu-id="43729-112">Modificare i tipi di limiti del ciclo e la variabile Step in modo che almeno uno di essi sia un tipo a cui gli altri si ampliano.</span><span class="sxs-lookup"><span data-stu-id="43729-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="43729-113">Nell'esempio precedente, modificare il tipo di `stepVar` in `Integer` .</span><span class="sxs-lookup"><span data-stu-id="43729-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>

  ```vb
  Dim stepVar = 1
  ```

  <span data-ttu-id="43729-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="43729-114">-or-</span></span>

  ```vb
  Dim stepVar As Integer = 1
  ```

- <span data-ttu-id="43729-115">Utilizzare le funzioni di conversione esplicita per convertire i limiti del ciclo e la variabile Step nei tipi appropriati.</span><span class="sxs-lookup"><span data-stu-id="43729-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="43729-116">Nell'esempio precedente, applicare la `Val` funzione a `stepVar` .</span><span class="sxs-lookup"><span data-stu-id="43729-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>

  ```vb
  For i = 1 To 10 Step Val(stepVar)
      ' Loop processing
  Next
  ```

## <a name="see-also"></a><span data-ttu-id="43729-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43729-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="43729-118">Istruzione For...Next</span><span class="sxs-lookup"><span data-stu-id="43729-118">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="43729-119">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="43729-119">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="43729-120">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="43729-120">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="43729-121">Option Infer (istruzione)</span><span class="sxs-lookup"><span data-stu-id="43729-121">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="43729-122">CString</span><span class="sxs-lookup"><span data-stu-id="43729-122">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="43729-123">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="43729-123">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
