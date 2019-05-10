---
title: Operatori condizionali null (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 4815fe7ad337634cfb56127fbd24a47a37fdd74b
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65062939"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="827a4-102">?.</span><span class="sxs-lookup"><span data-stu-id="827a4-102">?.</span></span> <span data-ttu-id="827a4-103">e? operatori condizionali null () (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="827a4-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="827a4-104">Testa il valore dell'operando a sinistra i valori null (`Nothing`) prima di eseguire un accesso ai membri (`?.`) o un indice (`?()`) operazione; restituisce `Nothing` se l'operando sinistro `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="827a4-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="827a4-105">Si noti che nelle espressioni che restituiscono in genere i tipi di valore, l'operatore condizionale null restituisce un <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="827a4-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="827a4-106">Questi operatori consentono di scrivere meno codice per gestire i controlli null, in particolare quando decrescente in strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="827a4-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="827a4-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="827a4-107">For example:</span></span>

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

<span data-ttu-id="827a4-108">Per il confronto, il codice alternativo per il primo di tali espressioni senza un operatore condizionale null è:</span><span class="sxs-lookup"><span data-stu-id="827a4-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="827a4-109">In alcuni casi è necessario eseguire un'azione su un oggetto che può essere null, in base al valore di un membro booleano su tale oggetto (ad esempio la proprietà booleana `IsAllowedFreeShipping` nell'esempio seguente):</span><span class="sxs-lookup"><span data-stu-id="827a4-109">Sometimes you need to take an action on an object that may be null, based on the value of a Boolean member on that object (like the Boolean property `IsAllowedFreeShipping` in the following example):</span></span>

```vb
  Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
  
  If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
   ApplyFreeShippingToOrders(customer)
  End If
```

<span data-ttu-id="827a4-110">È possibile abbreviare il codice ed evitare controllare manualmente i valori null usando l'operatore condizionale null come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="827a4-110">You can shorten your code and avoid manually checking for null by using the null-conditional operator as follows:</span></span>

```vb
 Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
 
 If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

<span data-ttu-id="827a4-111">Gli operatori condizionali Null causano corto circuiti.</span><span class="sxs-lookup"><span data-stu-id="827a4-111">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="827a4-112">Se un'operazione in una catena di operazioni di indice e accesso ai membri condizionali restituisce `Nothing`, il resto del viene arrestata l'esecuzione della catena.</span><span class="sxs-lookup"><span data-stu-id="827a4-112">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="827a4-113">Nell'esempio riportato di seguito `C(E)` non viene valutato se `A`, `B`, o `C` restituisce `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="827a4-113">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="827a4-114">Un altro uso per l'accesso ai membri condizionali null è richiamare delegati in modo thread-safe scrivendo molto meno codice.</span><span class="sxs-lookup"><span data-stu-id="827a4-114">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="827a4-115">L'esempio seguente definisce due tipi, una `NewsBroadcaster` e un `NewsReceiver`.</span><span class="sxs-lookup"><span data-stu-id="827a4-115">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="827a4-116">Nuovi elementi vengono inviati al ricevitore per il `NewsBroadcaster.SendNews` delegare.</span><span class="sxs-lookup"><span data-stu-id="827a4-116">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String) 

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

<span data-ttu-id="827a4-117">Se non esistono elementi nel `SendNews` elenco di chiamate, il `SendNews` delegare genera un <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="827a4-117">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="827a4-118">Prima di operatori condizionali null, di codice come il seguente garantito che l'elenco di chiamate del delegato non è stato `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="827a4-118">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb  
SendNews = SendNews.Combine({SendNews, client})  
If SendNews IsNot Nothing Then 
   SendNews("Just in...")
End If
```

<span data-ttu-id="827a4-119">Ora tutto è molto più semplice:</span><span class="sxs-lookup"><span data-stu-id="827a4-119">The new way is much simpler:</span></span>  

```vb
SendNews = SendNews.Combine({SendNews, client})  
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="827a4-120">Il codice creato in questo modo è thread-safe perché il compilatore genera il codice per valutare `SendNews` una sola volta, mantenendo il risultato in una variabile temporanea.</span><span class="sxs-lookup"><span data-stu-id="827a4-120">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="827a4-121">È necessario chiamare esplicitamente il metodo `Invoke` perché non esiste una sintassi di chiamata dei delegati con condizione Null `SendNews?(String)`.</span><span class="sxs-lookup"><span data-stu-id="827a4-121">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="827a4-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="827a4-122">See also</span></span>

- [<span data-ttu-id="827a4-123">Operatori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="827a4-123">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="827a4-124">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="827a4-124">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="827a4-125">Riferimenti per il linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="827a4-125">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
