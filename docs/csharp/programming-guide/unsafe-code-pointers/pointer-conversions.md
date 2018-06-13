---
title: Conversioni di puntatori (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: e0c3a409d76468a6e214a96e8bb326a9d906fe18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322692"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="0959f-102">Conversioni di puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0959f-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="0959f-103">Nella tabella seguente sono illustrate le conversioni di puntatori implicite predefinite.</span><span class="sxs-lookup"><span data-stu-id="0959f-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="0959f-104">Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="0959f-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="0959f-105">Conversioni di puntatori implicite</span><span class="sxs-lookup"><span data-stu-id="0959f-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="0959f-106">Da</span><span class="sxs-lookup"><span data-stu-id="0959f-106">From</span></span>|<span data-ttu-id="0959f-107">A</span><span class="sxs-lookup"><span data-stu-id="0959f-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="0959f-108">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="0959f-108">Any pointer type</span></span>|<span data-ttu-id="0959f-109">void\*</span><span class="sxs-lookup"><span data-stu-id="0959f-109">void\*</span></span>|  
|<span data-ttu-id="0959f-110">Null</span><span class="sxs-lookup"><span data-stu-id="0959f-110">null</span></span>|<span data-ttu-id="0959f-111">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="0959f-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="0959f-112">La conversione di puntatori esplicita consente di usare un'espressione cast per eseguire conversioni nei casi in cui non è possibile la conversione implicita.</span><span class="sxs-lookup"><span data-stu-id="0959f-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="0959f-113">La tabella seguente illustra queste conversioni.</span><span class="sxs-lookup"><span data-stu-id="0959f-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="0959f-114">Conversioni di puntatori esplicite</span><span class="sxs-lookup"><span data-stu-id="0959f-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="0959f-115">Da</span><span class="sxs-lookup"><span data-stu-id="0959f-115">From</span></span>|<span data-ttu-id="0959f-116">A</span><span class="sxs-lookup"><span data-stu-id="0959f-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="0959f-117">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="0959f-117">Any pointer type</span></span>|<span data-ttu-id="0959f-118">Qualsiasi altro tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="0959f-118">Any other pointer type</span></span>|  
|<span data-ttu-id="0959f-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="0959f-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="0959f-120">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="0959f-120">Any pointer type</span></span>|  
|<span data-ttu-id="0959f-121">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="0959f-121">Any pointer type</span></span>|<span data-ttu-id="0959f-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="0959f-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0959f-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="0959f-123">Example</span></span>  
 <span data-ttu-id="0959f-124">Nell'esempio seguente, un puntatore a `int` viene convertito in un puntatore a `byte`.</span><span class="sxs-lookup"><span data-stu-id="0959f-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="0959f-125">Osservare come il puntatore punti al byte della variabile con l'indirizzo più basso.</span><span class="sxs-lookup"><span data-stu-id="0959f-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="0959f-126">Quando si incrementa successivamente il risultato, fino a raggiungere la dimensione di `int` (4 byte), è possibile visualizzare i byte rimanenti della variabile.</span><span class="sxs-lookup"><span data-stu-id="0959f-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0959f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0959f-127">See Also</span></span>  
 [<span data-ttu-id="0959f-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0959f-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0959f-129">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="0959f-129">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="0959f-130">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="0959f-130">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="0959f-131">Tipi</span><span class="sxs-lookup"><span data-stu-id="0959f-131">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="0959f-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="0959f-132">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="0959f-133">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="0959f-133">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="0959f-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="0959f-134">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
