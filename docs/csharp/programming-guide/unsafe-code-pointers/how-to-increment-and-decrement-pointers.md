---
title: 'Procedura: Incrementare e decrementare i puntatori (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: c75432d88a1e96742573a6e69a4e035066a387c4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128336"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="38a25-102">Procedura: Incrementare e decrementare i puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="38a25-102">How to: increment and decrement pointers (C# Programming Guide)</span></span>

<span data-ttu-id="38a25-103">Gli operatori di incremento e decremento `++` e `--` consentono di modificare la posizione del puntatore in base a `sizeof(pointer-type)` per un puntatore di tipo `pointer-type*`.</span><span class="sxs-lookup"><span data-stu-id="38a25-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by `sizeof(pointer-type)` for a pointer of the type `pointer-type*`.</span></span> <span data-ttu-id="38a25-104">Il formato delle espressioni di incremento e decremento è il seguente:</span><span class="sxs-lookup"><span data-stu-id="38a25-104">The increment and decrement expressions take the following form:</span></span>  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="38a25-105">È possibile applicare gli operatori di incremento e decremento ai puntatori di qualsiasi tipo, ad eccezione del tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="38a25-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="38a25-106">Quando si applica l'operatore di incremento a un puntatore di tipo `pointer-type*`, si aggiunge `sizeof(pointer-type)` all'indirizzo contenuto nella variabile del puntatore.</span><span class="sxs-lookup"><span data-stu-id="38a25-106">The effect of applying the increment operator to a pointer of the type `pointer-type*` is to add `sizeof(pointer-type)` to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="38a25-107">Quando si applica l'operatore di decremento a un puntatore di tipo `pointer-type*`, si sottrae `sizeof(pointer-type)` dall'indirizzo contenuto nella variabile del puntatore.</span><span class="sxs-lookup"><span data-stu-id="38a25-107">The effect of applying the decrement operator to a pointer of the type `pointer-type*` is to subtract `sizeof(pointer-type)` from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="38a25-108">Quando l'operazione causa un overflow del dominio del puntatore, non vengono generate eccezioni e il risultato dipende dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="38a25-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38a25-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="38a25-109">Example</span></span>  
 <span data-ttu-id="38a25-110">Questo esempio mostra come passare da un elemento di una matrice all'altro incrementando il puntatore della dimensione di `int`.</span><span class="sxs-lookup"><span data-stu-id="38a25-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="38a25-111">A ogni passaggio vengono visualizzati l'indirizzo e il contenuto dell'elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="38a25-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
<span data-ttu-id="38a25-112">**Valore:0 @ Address:12860272**
**Valore:1 @ Address:12860276**
**Valore:2 @ Address:12860280**
**Valore:3 @ Address:12860284**
**Valore:4 @ Address:12860288**</span><span class="sxs-lookup"><span data-stu-id="38a25-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span></span>

## <a name="see-also"></a><span data-ttu-id="38a25-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38a25-113">See also</span></span>

- [<span data-ttu-id="38a25-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="38a25-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="38a25-115">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="38a25-115">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="38a25-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="38a25-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="38a25-117">Modifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="38a25-117">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="38a25-118">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="38a25-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="38a25-119">Tipi</span><span class="sxs-lookup"><span data-stu-id="38a25-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="38a25-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="38a25-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="38a25-121">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="38a25-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="38a25-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="38a25-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
- [<span data-ttu-id="38a25-123">sizeof</span><span class="sxs-lookup"><span data-stu-id="38a25-123">sizeof</span></span>](../../../csharp/language-reference/keywords/sizeof.md)
