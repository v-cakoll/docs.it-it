---
title: 'Procedura: Ottenere il valore di una variabile puntatore - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 288d8cb2d286f55cc9a162614d45ef7b298f79f1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974484"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="06a8a-102">Procedura: Ottenere il valore di una variabile puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="06a8a-102">How to: obtain the value of a pointer variable (C# Programming Guide)</span></span>

<span data-ttu-id="06a8a-103">L'operatore di riferimento indiretto a puntatore consente di ottenere la variabile nella posizione indicata da un puntatore.</span><span class="sxs-lookup"><span data-stu-id="06a8a-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="06a8a-104">L'espressione ha il seguente formato, dove `p` è un tipo di puntatore:</span><span class="sxs-lookup"><span data-stu-id="06a8a-104">The expression takes the following form, where `p` is a pointer type:</span></span>  

```csharp
*p;  
```

<span data-ttu-id="06a8a-105">Non è possibile usare l'operatore di riferimento indiretto unario o un'espressione di qualsiasi altro tipo diverso dal tipo puntatore.</span><span class="sxs-lookup"><span data-stu-id="06a8a-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="06a8a-106">Non è inoltre possibile applicarlo a un puntatore [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="06a8a-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  

<span data-ttu-id="06a8a-107">Quando si applica l'operatore di riferimento indiretto a un puntatore [Null](../../../csharp/language-reference/keywords/null.md), il risultato dipende dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="06a8a-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  

## <a name="example"></a><span data-ttu-id="06a8a-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="06a8a-108">Example</span></span>

<span data-ttu-id="06a8a-109">Nell'esempio seguente si accede a una variabile di tipo `char` usando puntatori di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="06a8a-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="06a8a-110">Si noti che l'indirizzo di `theChar` varia da un'esecuzione all'altra, perché l'indirizzo fisico allocato a una variabile può cambiare.</span><span class="sxs-lookup"><span data-stu-id="06a8a-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  

 [!code-csharp[csProgGuidePointers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#5)]  

 [!code-csharp[csProgGuidePointers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#6)]  
  
<span data-ttu-id="06a8a-111">**Valore di theChar = Z**</span><span class="sxs-lookup"><span data-stu-id="06a8a-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="06a8a-112">**Indirizzo di theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="06a8a-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="06a8a-113">**Valore di pChar = Z**</span><span class="sxs-lookup"><span data-stu-id="06a8a-113">**Value of pChar = Z**</span></span>  
<span data-ttu-id="06a8a-114">**Valore di pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="06a8a-114">**Value of pInt = 90**</span></span>  

## <a name="see-also"></a><span data-ttu-id="06a8a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06a8a-115">See also</span></span>

- [<span data-ttu-id="06a8a-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="06a8a-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="06a8a-117">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="06a8a-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="06a8a-118">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="06a8a-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="06a8a-119">Tipi</span><span class="sxs-lookup"><span data-stu-id="06a8a-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="06a8a-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="06a8a-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="06a8a-121">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="06a8a-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="06a8a-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="06a8a-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
