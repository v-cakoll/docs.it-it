---
title: Conversioni di puntatori (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e415d892d979e2bdcd648256150e2a96b1772ce4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="71b41-102">Conversioni di puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="71b41-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="71b41-103">Nella tabella seguente sono illustrate le conversioni di puntatori implicite predefinite.</span><span class="sxs-lookup"><span data-stu-id="71b41-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="71b41-104">Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="71b41-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="71b41-105">Conversioni di puntatori implicite</span><span class="sxs-lookup"><span data-stu-id="71b41-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="71b41-106">Da</span><span class="sxs-lookup"><span data-stu-id="71b41-106">From</span></span>|<span data-ttu-id="71b41-107">Per</span><span class="sxs-lookup"><span data-stu-id="71b41-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="71b41-108">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="71b41-108">Any pointer type</span></span>|<span data-ttu-id="71b41-109">void*</span><span class="sxs-lookup"><span data-stu-id="71b41-109">void*</span></span>|  
|<span data-ttu-id="71b41-110">Null</span><span class="sxs-lookup"><span data-stu-id="71b41-110">null</span></span>|<span data-ttu-id="71b41-111">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="71b41-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="71b41-112">La conversione di puntatori esplicita consente di usare un'espressione cast per eseguire conversioni nei casi in cui non è possibile la conversione implicita.</span><span class="sxs-lookup"><span data-stu-id="71b41-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="71b41-113">La tabella seguente illustra queste conversioni.</span><span class="sxs-lookup"><span data-stu-id="71b41-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="71b41-114">Conversioni di puntatori esplicite</span><span class="sxs-lookup"><span data-stu-id="71b41-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="71b41-115">Da</span><span class="sxs-lookup"><span data-stu-id="71b41-115">From</span></span>|<span data-ttu-id="71b41-116">Per</span><span class="sxs-lookup"><span data-stu-id="71b41-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="71b41-117">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="71b41-117">Any pointer type</span></span>|<span data-ttu-id="71b41-118">Qualsiasi altro tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="71b41-118">Any other pointer type</span></span>|  
|<span data-ttu-id="71b41-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="71b41-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="71b41-120">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="71b41-120">Any pointer type</span></span>|  
|<span data-ttu-id="71b41-121">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="71b41-121">Any pointer type</span></span>|<span data-ttu-id="71b41-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="71b41-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="71b41-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="71b41-123">Example</span></span>  
 <span data-ttu-id="71b41-124">Nell'esempio seguente, un puntatore a `int` viene convertito in un puntatore a `byte`.</span><span class="sxs-lookup"><span data-stu-id="71b41-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="71b41-125">Osservare come il puntatore punti al byte della variabile con l'indirizzo più basso.</span><span class="sxs-lookup"><span data-stu-id="71b41-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="71b41-126">Quando si incrementa successivamente il risultato, fino a raggiungere la dimensione di `int` (4 byte), è possibile visualizzare i byte rimanenti della variabile.</span><span class="sxs-lookup"><span data-stu-id="71b41-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 <span data-ttu-id="71b41-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="71b41-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span></span>  
  
 <span data-ttu-id="71b41-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="71b41-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b41-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71b41-129">See Also</span></span>  
 <span data-ttu-id="71b41-130">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="71b41-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="71b41-131">[Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="71b41-131">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="71b41-132">[Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="71b41-132">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="71b41-133">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="71b41-133">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="71b41-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="71b41-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="71b41-135">[Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="71b41-135">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="71b41-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="71b41-136">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

