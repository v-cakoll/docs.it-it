---
title: Tabella delle conversioni numeriche implicite (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 4bbc6086dc5fd3838ef9361762c3068ca44efd0e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43417596"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="94394-102">Tabella delle conversioni numeriche implicite (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="94394-102">Implicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="94394-103">Nella tabella che segue sono illustrate le conversioni numeriche implicite predefinite.</span><span class="sxs-lookup"><span data-stu-id="94394-103">The following table shows the predefined implicit numeric conversions.</span></span> <span data-ttu-id="94394-104">Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="94394-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
|<span data-ttu-id="94394-105">Da</span><span class="sxs-lookup"><span data-stu-id="94394-105">From</span></span>|<span data-ttu-id="94394-106">A</span><span class="sxs-lookup"><span data-stu-id="94394-106">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="94394-107">sbyte</span><span class="sxs-lookup"><span data-stu-id="94394-107">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="94394-108">`short`, `int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="94394-108">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="94394-109">byte</span><span class="sxs-lookup"><span data-stu-id="94394-109">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="94394-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="94394-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="94394-111">short</span><span class="sxs-lookup"><span data-stu-id="94394-111">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="94394-112">`int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="94394-112">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="94394-113">ushort</span><span class="sxs-lookup"><span data-stu-id="94394-113">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="94394-114">`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="94394-114">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="94394-115">int</span><span class="sxs-lookup"><span data-stu-id="94394-115">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="94394-116">`long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="94394-116">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="94394-117">uint</span><span class="sxs-lookup"><span data-stu-id="94394-117">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="94394-118">`long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="94394-118">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="94394-119">long</span><span class="sxs-lookup"><span data-stu-id="94394-119">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="94394-120">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="94394-120">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="94394-121">char</span><span class="sxs-lookup"><span data-stu-id="94394-121">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="94394-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="94394-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="94394-123">float</span><span class="sxs-lookup"><span data-stu-id="94394-123">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[<span data-ttu-id="94394-124">ulong</span><span class="sxs-lookup"><span data-stu-id="94394-124">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="94394-125">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="94394-125">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94394-126">Note</span><span class="sxs-lookup"><span data-stu-id="94394-126">Remarks</span></span>  
  
-   <span data-ttu-id="94394-127">Nella conversione da `int`, `uint`, `long` o `ulong` a `float` e da `long` o `ulong` a `double` può andare persa la precisione ma non la grandezza.</span><span class="sxs-lookup"><span data-stu-id="94394-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`,  `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
-   <span data-ttu-id="94394-128">Non esiste alcuna conversione implicita verso il tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="94394-128">There are no implicit conversions to the `char` type.</span></span>  
  
-   <span data-ttu-id="94394-129">Non esiste alcuna conversione implicita tra tipi a virgola mobile e il tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="94394-129">There are no implicit conversions between floating-point types and the `decimal` type.</span></span>  
  
-   <span data-ttu-id="94394-130">Un'espressione costante di tipo `int` può essere convertita in `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, a condizione che il valore di tale espressione sia compreso nell'intervallo del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="94394-130">A constant expression of type `int` can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided the value of the constant expression is within the range of the destination type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="94394-131">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="94394-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="94394-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94394-132">See Also</span></span>  

- [<span data-ttu-id="94394-133">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="94394-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="94394-134">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="94394-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="94394-135">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="94394-135">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="94394-136">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="94394-136">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="94394-137">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="94394-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [<span data-ttu-id="94394-138">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="94394-138">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
