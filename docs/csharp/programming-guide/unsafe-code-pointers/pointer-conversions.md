---
title: Conversioni di puntatori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 872406fdf012ed3b8326789f6664cb3396d59a84
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635178"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="e6f5c-102">Conversioni di puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e6f5c-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="e6f5c-103">Nella tabella seguente sono illustrate le conversioni di puntatori implicite predefinite.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="e6f5c-104">Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="e6f5c-105">Conversioni di puntatori implicite</span><span class="sxs-lookup"><span data-stu-id="e6f5c-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="e6f5c-106">Da</span><span class="sxs-lookup"><span data-stu-id="e6f5c-106">From</span></span>|<span data-ttu-id="e6f5c-107">A</span><span class="sxs-lookup"><span data-stu-id="e6f5c-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="e6f5c-108">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="e6f5c-108">Any pointer type</span></span>|<span data-ttu-id="e6f5c-109">void\*</span><span class="sxs-lookup"><span data-stu-id="e6f5c-109">void\*</span></span>|  
|<span data-ttu-id="e6f5c-110">Null</span><span class="sxs-lookup"><span data-stu-id="e6f5c-110">null</span></span>|<span data-ttu-id="e6f5c-111">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="e6f5c-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="e6f5c-112">La conversione di puntatori esplicita consente di usare un'espressione cast per eseguire conversioni nei casi in cui non è possibile la conversione implicita.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="e6f5c-113">La tabella seguente illustra queste conversioni.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="e6f5c-114">Conversioni di puntatori esplicite</span><span class="sxs-lookup"><span data-stu-id="e6f5c-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="e6f5c-115">Da</span><span class="sxs-lookup"><span data-stu-id="e6f5c-115">From</span></span>|<span data-ttu-id="e6f5c-116">A</span><span class="sxs-lookup"><span data-stu-id="e6f5c-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="e6f5c-117">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="e6f5c-117">Any pointer type</span></span>|<span data-ttu-id="e6f5c-118">Qualsiasi altro tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="e6f5c-118">Any other pointer type</span></span>|  
|<span data-ttu-id="e6f5c-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="e6f5c-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="e6f5c-120">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="e6f5c-120">Any pointer type</span></span>|  
|<span data-ttu-id="e6f5c-121">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="e6f5c-121">Any pointer type</span></span>|<span data-ttu-id="e6f5c-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="e6f5c-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e6f5c-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6f5c-123">Example</span></span>  
 <span data-ttu-id="e6f5c-124">Nell'esempio seguente, un puntatore a `int` viene convertito in un puntatore a `byte`.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="e6f5c-125">Osservare come il puntatore punti al byte della variabile con l'indirizzo più basso.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="e6f5c-126">Quando si incrementa successivamente il risultato, fino a raggiungere la dimensione di `int` (4 byte), è possibile visualizzare i byte rimanenti della variabile.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e6f5c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6f5c-127">See also</span></span>

- [<span data-ttu-id="e6f5c-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e6f5c-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e6f5c-129">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="e6f5c-129">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="e6f5c-130">Tipi</span><span class="sxs-lookup"><span data-stu-id="e6f5c-130">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="e6f5c-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="e6f5c-131">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="e6f5c-132">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="e6f5c-132">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="e6f5c-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="e6f5c-133">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
