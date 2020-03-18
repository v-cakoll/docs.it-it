---
title: Conversioni di puntatori - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 517166331d2bcf73132269ce2adcf68d5f60b4fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76745359"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="1c0e0-102">Conversioni di puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1c0e0-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="1c0e0-103">Nella tabella seguente sono illustrate le conversioni di puntatori implicite predefinite.</span><span class="sxs-lookup"><span data-stu-id="1c0e0-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="1c0e0-104">Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="1c0e0-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="1c0e0-105">Conversioni di puntatori implicite</span><span class="sxs-lookup"><span data-stu-id="1c0e0-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="1c0e0-106">From</span><span class="sxs-lookup"><span data-stu-id="1c0e0-106">From</span></span>|<span data-ttu-id="1c0e0-107">A</span><span class="sxs-lookup"><span data-stu-id="1c0e0-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="1c0e0-108">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="1c0e0-108">Any pointer type</span></span>|<span data-ttu-id="1c0e0-109">void\*</span><span class="sxs-lookup"><span data-stu-id="1c0e0-109">void\*</span></span>|  
|<span data-ttu-id="1c0e0-110">Null</span><span class="sxs-lookup"><span data-stu-id="1c0e0-110">null</span></span>|<span data-ttu-id="1c0e0-111">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="1c0e0-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="1c0e0-112">La conversione di puntatori esplicita consente di usare un'espressione cast per eseguire conversioni nei casi in cui non è possibile la conversione implicita.</span><span class="sxs-lookup"><span data-stu-id="1c0e0-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="1c0e0-113">La tabella seguente illustra queste conversioni.</span><span class="sxs-lookup"><span data-stu-id="1c0e0-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="1c0e0-114">Conversioni di puntatori esplicite</span><span class="sxs-lookup"><span data-stu-id="1c0e0-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="1c0e0-115">From</span><span class="sxs-lookup"><span data-stu-id="1c0e0-115">From</span></span>|<span data-ttu-id="1c0e0-116">A</span><span class="sxs-lookup"><span data-stu-id="1c0e0-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="1c0e0-117">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="1c0e0-117">Any pointer type</span></span>|<span data-ttu-id="1c0e0-118">Qualsiasi altro tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="1c0e0-118">Any other pointer type</span></span>|  
|<span data-ttu-id="1c0e0-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="1c0e0-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="1c0e0-120">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="1c0e0-120">Any pointer type</span></span>|  
|<span data-ttu-id="1c0e0-121">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="1c0e0-121">Any pointer type</span></span>|<span data-ttu-id="1c0e0-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="1c0e0-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1c0e0-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c0e0-123">Example</span></span>  
 <span data-ttu-id="1c0e0-124">Nell'esempio seguente, un puntatore a `int` viene convertito in un puntatore a `byte`.</span><span class="sxs-lookup"><span data-stu-id="1c0e0-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="1c0e0-125">Osservare come il puntatore punti al byte della variabile con l'indirizzo più basso.</span><span class="sxs-lookup"><span data-stu-id="1c0e0-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="1c0e0-126">Quando si incrementa successivamente il risultato, fino a raggiungere la dimensione di `int` (4 byte), è possibile visualizzare i byte rimanenti della variabile.</span><span class="sxs-lookup"><span data-stu-id="1c0e0-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1c0e0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c0e0-127">See also</span></span>

- [<span data-ttu-id="1c0e0-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1c0e0-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1c0e0-129">Tipi di puntatore</span><span class="sxs-lookup"><span data-stu-id="1c0e0-129">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="1c0e0-130">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="1c0e0-130">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="1c0e0-131">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="1c0e0-131">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="1c0e0-132">Pericoloso</span><span class="sxs-lookup"><span data-stu-id="1c0e0-132">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="1c0e0-133">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="1c0e0-133">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="1c0e0-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="1c0e0-134">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
