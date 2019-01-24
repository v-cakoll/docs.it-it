---
title: Operatori condizionali null (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: d30d452a7c140a0c56529386b14ef3a3512df490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722153"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="4c4ca-102">?.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-102">?.</span></span> <span data-ttu-id="4c4ca-103">e? operatori condizionali null () (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c4ca-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="4c4ca-104">Testa il valore dell'operando a sinistra i valori null (`Nothing`) prima di eseguire un accesso ai membri (`?.`) o un indice (`?()`) operazione; restituisce `Nothing` se l'operando sinistro `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="4c4ca-105">Si noti che, nelle espressioni di che normalmente restituisce i tipi di valore, l'operatore condizionale null restituisce un <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-105">Note that, in the expressions that would ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="4c4ca-106">Questi operatori consentono di scrivere meno codice per gestire i controlli null, in particolare quando decrescente in strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="4c4ca-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c4ca-107">For example:</span></span>

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

<span data-ttu-id="4c4ca-108">Per il confronto, il codice alternativo per il primo di tali espressioni senza un operatore condizionale null è:</span><span class="sxs-lookup"><span data-stu-id="4c4ca-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="4c4ca-109">Gli operatori condizionali Null causano corto circuiti.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-109">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="4c4ca-110">Se un'operazione in una catena di operazioni di indice e accesso ai membri condizionali non restituisce nulla, il resto dell'esecuzione della catena verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-110">If one operation in a chain of conditional member access and index operations returns Nothing, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="4c4ca-111">Nell'esempio seguente, non viene valutato c (e) se `A`, `B`, o `C` non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-111">In the following example, C(E) isn't evaluated if `A`, `B`, or `C` evaluates to Nothing.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="4c4ca-112">Un altro uso per l'accesso ai membri condizionali null è richiamare delegati in modo thread-safe scrivendo molto meno codice.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-112">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="4c4ca-113">In passato era necessario codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4c4ca-113">The old way requires code like the following:</span></span>  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

<span data-ttu-id="4c4ca-114">Ora tutto è molto più semplice:</span><span class="sxs-lookup"><span data-stu-id="4c4ca-114">The new way is much simpler:</span></span>  

```vb
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="4c4ca-115">Il codice creato in questo modo è thread-safe perché il compilatore genera il codice per valutare `PropertyChanged` una sola volta, mantenendo il risultato in una variabile temporanea.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-115">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="4c4ca-116">È necessario chiamare esplicitamente il metodo `Invoke` perché non esiste una sintassi di chiamata dei delegati con condizione Null `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="4c4ca-116">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4c4ca-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c4ca-117">See also</span></span>

- [<span data-ttu-id="4c4ca-118">Operatori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c4ca-118">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="4c4ca-119">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c4ca-119">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="4c4ca-120">Riferimenti per il linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c4ca-120">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
