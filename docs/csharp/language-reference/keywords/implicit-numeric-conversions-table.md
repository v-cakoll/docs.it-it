---
title: Tabella delle conversioni numeriche implicite - Riferimenti per C#
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: ab6506e619c675ddd68237c4ddca870e9e14098f
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058464"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="83414-102">Tabella delle conversioni numeriche implicite (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="83414-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="83414-103">Nella tabella che segue sono illustrate le conversioni implicite predefinite tra i tipi numerici .NET.</span><span class="sxs-lookup"><span data-stu-id="83414-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="83414-104">Da</span><span class="sxs-lookup"><span data-stu-id="83414-104">From</span></span>|<span data-ttu-id="83414-105">A</span><span class="sxs-lookup"><span data-stu-id="83414-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="83414-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="83414-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="83414-107">`short`, `int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="83414-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="83414-108">byte</span><span class="sxs-lookup"><span data-stu-id="83414-108">byte</span></span>](byte.md)|<span data-ttu-id="83414-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="83414-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="83414-110">char</span><span class="sxs-lookup"><span data-stu-id="83414-110">char</span></span>](char.md)|<span data-ttu-id="83414-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="83414-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="83414-112">short</span><span class="sxs-lookup"><span data-stu-id="83414-112">short</span></span>](short.md)|<span data-ttu-id="83414-113">`int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="83414-113">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="83414-114">ushort</span><span class="sxs-lookup"><span data-stu-id="83414-114">ushort</span></span>](ushort.md)|<span data-ttu-id="83414-115">`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="83414-115">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="83414-116">int</span><span class="sxs-lookup"><span data-stu-id="83414-116">int</span></span>](int.md)|<span data-ttu-id="83414-117">`long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="83414-117">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="83414-118">uint</span><span class="sxs-lookup"><span data-stu-id="83414-118">uint</span></span>](uint.md)|<span data-ttu-id="83414-119">`long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="83414-119">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="83414-120">long</span><span class="sxs-lookup"><span data-stu-id="83414-120">long</span></span>](long.md)|<span data-ttu-id="83414-121">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="83414-121">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="83414-122">ulong</span><span class="sxs-lookup"><span data-stu-id="83414-122">ulong</span></span>](ulong.md)|<span data-ttu-id="83414-123">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="83414-123">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="83414-124">float</span><span class="sxs-lookup"><span data-stu-id="83414-124">float</span></span>](float.md)|`double`|  
  
## <a name="remarks"></a><span data-ttu-id="83414-125">Note</span><span class="sxs-lookup"><span data-stu-id="83414-125">Remarks</span></span>  

- <span data-ttu-id="83414-126">Qualunque [tipo integrale](integral-types-table.md) è implicitamente convertibile in qualunque [tipo a virgola mobile](floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="83414-126">Any [integral type](integral-types-table.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="83414-127">Nella conversione da `int`, `uint`, `long` o `ulong` a `float` e da `long` o `ulong` a `double` può andare persa la precisione ma non la grandezza.</span><span class="sxs-lookup"><span data-stu-id="83414-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="83414-128">Non esiste alcuna conversione implicita verso i tipi `char`, `byte` e `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="83414-128">There are no implicit conversions to the `char`, `byte` and `sbyte` types.</span></span>  

- <span data-ttu-id="83414-129">Non esiste alcuna conversione implicita dai tipi `char`, `double` e `decimal`.</span><span class="sxs-lookup"><span data-stu-id="83414-129">There are no implicit conversions from the `char`, `double` and `decimal` types.</span></span>
  
- <span data-ttu-id="83414-130">Non esiste alcuna conversione implicita tra il tipo `decimal` e i tipi `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="83414-130">There are no implicit conversions between the `decimal` type and the `float` or `double` types.</span></span>  
  
- <span data-ttu-id="83414-131">Un valore di un'espressione costante di tipo `int` (ad esempio, un valore rappresentato da un valore letterale intero) possono essere convertiti in `sbyte`, `byte`, `short`, `ushort`, `uint`, o `ulong`, purché rientri all'interno dell'intervallo del tipo di destinazione:</span><span class="sxs-lookup"><span data-stu-id="83414-131">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="83414-132">Per altre informazioni sulle conversioni implicite, vedere la sezione [conversioni implicite](~/_csharplang/spec/conversions.md#implicit-conversions) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="83414-132">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="83414-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83414-133">See also</span></span>

- [<span data-ttu-id="83414-134">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="83414-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="83414-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="83414-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="83414-136">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="83414-136">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="83414-137">Tabella dei tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="83414-137">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="83414-138">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="83414-138">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="83414-139">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="83414-139">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="83414-140">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="83414-140">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
