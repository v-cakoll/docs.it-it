---
title: Operatori condizionali Null (C# e Visual Basic)
ms.date: 04/03/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- null-conditional operators [C#]
- null-conditional operators [Visual Basic]
- ?. operator [C#]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 28cf2633d74f047a751ffdad11f1e1db8328cd6f
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="876ea-102">?.</span><span class="sxs-lookup"><span data-stu-id="876ea-102">?.</span></span> <span data-ttu-id="876ea-103">e ?[] - Operatori condizionali Null (C# e Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="876ea-103">and ?[] null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="876ea-104">Testa il valore dell'operando sul lato sinistro per i valori Null prima di eseguire un accesso ai membri (`?.`) o un'operazione (`?[]`) di indicizzazione; restituisce `null` se l'operando sul lato sinistro restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="876ea-104">Tests the value of the left-hand operand for null before performing a member access (`?.`) or index (`?[]`) operation; returns `null` if the left-hand operand evaluates to `null`.</span></span> 

<span data-ttu-id="876ea-105">Questi operatori consentono di scrivere meno codice per gestire i controlli null, soprattutto per l'ordinamento decrescente delle strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="876ea-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="876ea-106">Gli operatori condizionali Null causano corto circuiti.</span><span class="sxs-lookup"><span data-stu-id="876ea-106">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="876ea-107">Se un'operazione in una catena di operazioni condizionali di indice e accesso ai membri restituisce Null, l'esecuzione delle altre operazioni della catena viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="876ea-107">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="876ea-108">Nell'esempio seguente, `E` non viene eseguito se `A`, `B` o `C` restituisce Null.</span><span class="sxs-lookup"><span data-stu-id="876ea-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

```vb
A?.B?.C?.Do(E);
A?.B?.C?(E);
```  
  
 <span data-ttu-id="876ea-109">L'accesso ai membri con condizione Null viene usato anche per chiamare delegati in modo thread-safe scrivendo molto meno codice.</span><span class="sxs-lookup"><span data-stu-id="876ea-109">Another use for the null-conditional member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="876ea-110">In passato era necessario codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="876ea-110">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 <span data-ttu-id="876ea-111">Ora tutto è molto più semplice:</span><span class="sxs-lookup"><span data-stu-id="876ea-111">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

```vb
PropertyChanged?.Invoke(…)
```  
  
 <span data-ttu-id="876ea-112">Il codice creato in questo modo è thread-safe perché il compilatore genera il codice per valutare `PropertyChanged` una sola volta, mantenendo il risultato in una variabile temporanea.</span><span class="sxs-lookup"><span data-stu-id="876ea-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="876ea-113">È necessario chiamare esplicitamente il metodo `Invoke` perché non esiste una sintassi di chiamata dei delegati con condizione Null `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="876ea-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="876ea-114">Specifiche del linguaggio</span><span class="sxs-lookup"><span data-stu-id="876ea-114">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="876ea-115">Per altre informazioni, vedere [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="876ea-115">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="876ea-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="876ea-116">See Also</span></span>  
 [<span data-ttu-id="876ea-117"> ?? (operatore null-coalescing)</span><span class="sxs-lookup"><span data-stu-id="876ea-117">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)  
 [<span data-ttu-id="876ea-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="876ea-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="876ea-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="876ea-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="876ea-120">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="876ea-120">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
