---
title: Operatori condizionali Null (C# e Visual Basic)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 6118956a5681ddbeb110f6e01f090b85cdd65089
ms.openlocfilehash: 465a395a33c027132b7890e02d540438096e2073
ms.contentlocale: it-it
ms.lasthandoff: 08/23/2017

---
# <a name="null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="ed054-102">Operatori condizionali Null (C# e Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed054-102">Null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="ed054-103">Vengono usati per verificare la presenza di valori Null prima di eseguire un'operazione di accesso ai membri (`?.`) o di indice (`?[`).</span><span class="sxs-lookup"><span data-stu-id="ed054-103">Used to test for null before performing a member access (`?.`) or index (`?[`) operation.</span></span>  <span data-ttu-id="ed054-104">Questi operatori consentono di scrivere meno codice per gestire i controlli null, soprattutto per l'ordinamento decrescente delle strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="ed054-104">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
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
  
 <span data-ttu-id="ed054-105">Nell'ultimo esempio viene dimostrato che gli operatori con condizione Null causano un corto circuito.</span><span class="sxs-lookup"><span data-stu-id="ed054-105">The last example demonstrates that the null-condition operators are short-circuiting.</span></span>  <span data-ttu-id="ed054-106">Se un'operazione in una catena di operazioni condizionali di indice e accesso ai membri restituisce Null, l'esecuzione delle altre operazioni della catena viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="ed054-106">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="ed054-107">L'esecuzione di altre operazioni con precedenza inferiore nell'espressione invece può continuare.</span><span class="sxs-lookup"><span data-stu-id="ed054-107">Other operations with lower precedence in the expression continue.</span></span>  <span data-ttu-id="ed054-108">Ad esempio, nel codice seguente `E` viene eseguita nella seconda riga e le operazioni `??` e `==` vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="ed054-108">For example, `E` in the following executes in the second line, and the `??` and `==` operations execute.</span></span>  <span data-ttu-id="ed054-109">Nella prima riga `??` restituisce un corto circuito e `E` non viene eseguita quando il lato sinistro restituisce un valore non Null.</span><span class="sxs-lookup"><span data-stu-id="ed054-109">In the first line, the `??` short circuits and `E` does not execute when the left side evaluates to non-null.</span></span>
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 <span data-ttu-id="ed054-110">L'accesso ai membri con condizione Null viene usato anche per richiamare delegati in modo thread-safe scrivendo molto meno codice.</span><span class="sxs-lookup"><span data-stu-id="ed054-110">Another use for the null-condition member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="ed054-111">In passato era necessario codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ed054-111">The old way requires code like the following:</span></span>  
  
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
  
 <span data-ttu-id="ed054-112">Ora tutto è molto più semplice:</span><span class="sxs-lookup"><span data-stu-id="ed054-112">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 <span data-ttu-id="ed054-113">Il codice creato in questo modo è thread-safe perché il compilatore genera il codice per valutare `PropertyChanged` una sola volta, mantenendo il risultato in una variabile temporanea.</span><span class="sxs-lookup"><span data-stu-id="ed054-113">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span>  
  
 <span data-ttu-id="ed054-114">È necessario chiamare esplicitamente il metodo `Invoke` perché non esiste una sintassi di chiamata dei delegati con condizione Null `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="ed054-114">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  <span data-ttu-id="ed054-115">In precedenza esistevano troppe situazioni di analisi ambigue che lo consentivano.</span><span class="sxs-lookup"><span data-stu-id="ed054-115">There were too many ambiguous parsing situations to allow it.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="ed054-116">Specifiche del linguaggio</span><span class="sxs-lookup"><span data-stu-id="ed054-116">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="ed054-117">Per altre informazioni, vedere [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="ed054-117">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed054-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed054-118">See Also</span></span>  
 <span data-ttu-id="ed054-119">[?? (null-coalescing operator)](null-conditional-operator.md)  ?? (operatore null-coalescing)</span><span class="sxs-lookup"><span data-stu-id="ed054-119">[?? (null-coalescing operator)](null-conditional-operator.md) </span></span>  
 <span data-ttu-id="ed054-120">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ed054-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ed054-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ed054-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ed054-122">[Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ed054-122">[Visual Basic Language Reference](../../../visual-basic/language-reference/index.md) </span></span>  
 [<span data-ttu-id="ed054-123">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed054-123">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)

