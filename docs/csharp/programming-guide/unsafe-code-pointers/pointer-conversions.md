---
title: Conversioni di puntatori - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 308d5e0646eeb94012dbe18d46d6d33f67dfeaf5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75698365"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="47d5e-102">Conversioni di puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="47d5e-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="47d5e-103">Nella tabella seguente sono illustrate le conversioni di puntatori implicite predefinite.</span><span class="sxs-lookup"><span data-stu-id="47d5e-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="47d5e-104">Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="47d5e-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="47d5e-105">Conversioni di puntatori implicite</span><span class="sxs-lookup"><span data-stu-id="47d5e-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="47d5e-106">Da</span><span class="sxs-lookup"><span data-stu-id="47d5e-106">From</span></span>|<span data-ttu-id="47d5e-107">Per</span><span class="sxs-lookup"><span data-stu-id="47d5e-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="47d5e-108">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="47d5e-108">Any pointer type</span></span>|<span data-ttu-id="47d5e-109">void\*</span><span class="sxs-lookup"><span data-stu-id="47d5e-109">void\*</span></span>|  
|<span data-ttu-id="47d5e-110">null</span><span class="sxs-lookup"><span data-stu-id="47d5e-110">null</span></span>|<span data-ttu-id="47d5e-111">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="47d5e-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="47d5e-112">La conversione di puntatori esplicita consente di usare un'espressione cast per eseguire conversioni nei casi in cui non è possibile la conversione implicita.</span><span class="sxs-lookup"><span data-stu-id="47d5e-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="47d5e-113">La tabella seguente illustra queste conversioni.</span><span class="sxs-lookup"><span data-stu-id="47d5e-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="47d5e-114">Conversioni di puntatori esplicite</span><span class="sxs-lookup"><span data-stu-id="47d5e-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="47d5e-115">Da</span><span class="sxs-lookup"><span data-stu-id="47d5e-115">From</span></span>|<span data-ttu-id="47d5e-116">Per</span><span class="sxs-lookup"><span data-stu-id="47d5e-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="47d5e-117">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="47d5e-117">Any pointer type</span></span>|<span data-ttu-id="47d5e-118">Qualsiasi altro tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="47d5e-118">Any other pointer type</span></span>|  
|<span data-ttu-id="47d5e-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="47d5e-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="47d5e-120">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="47d5e-120">Any pointer type</span></span>|  
|<span data-ttu-id="47d5e-121">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="47d5e-121">Any pointer type</span></span>|<span data-ttu-id="47d5e-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="47d5e-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="47d5e-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="47d5e-123">Example</span></span>  
 <span data-ttu-id="47d5e-124">Nell'esempio seguente, un puntatore a `int` viene convertito in un puntatore a `byte`.</span><span class="sxs-lookup"><span data-stu-id="47d5e-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="47d5e-125">Osservare come il puntatore punti al byte della variabile con l'indirizzo più basso.</span><span class="sxs-lookup"><span data-stu-id="47d5e-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="47d5e-126">Quando si incrementa successivamente il risultato, fino a raggiungere la dimensione di `int` (4 byte), è possibile visualizzare i byte rimanenti della variabile.</span><span class="sxs-lookup"><span data-stu-id="47d5e-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="47d5e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47d5e-127">See also</span></span>

- [<span data-ttu-id="47d5e-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="47d5e-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="47d5e-129">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="47d5e-129">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="47d5e-130">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="47d5e-130">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="47d5e-131">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="47d5e-131">Value types</span></span>](../../language-reference/keywords/value-types.md)
- [<span data-ttu-id="47d5e-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="47d5e-132">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="47d5e-133">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="47d5e-133">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="47d5e-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="47d5e-134">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
