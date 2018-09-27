---
title: Tabella delle conversioni numeriche implicite (Riferimenti per C#)
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: e46816fc8f3a6ff71dcba3561098d3cfce1e1054
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44213264"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="e1e27-102">Tabella delle conversioni numeriche implicite (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e1e27-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="e1e27-103">Nella tabella che segue sono illustrate le conversioni implicite predefinite tra i tipi numerici .NET.</span><span class="sxs-lookup"><span data-stu-id="e1e27-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="e1e27-104">Da</span><span class="sxs-lookup"><span data-stu-id="e1e27-104">From</span></span>|<span data-ttu-id="e1e27-105">A</span><span class="sxs-lookup"><span data-stu-id="e1e27-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="e1e27-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="e1e27-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="e1e27-107">`short`, `int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="e1e27-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e1e27-108">byte</span><span class="sxs-lookup"><span data-stu-id="e1e27-108">byte</span></span>](byte.md)|<span data-ttu-id="e1e27-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="e1e27-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e1e27-110">short</span><span class="sxs-lookup"><span data-stu-id="e1e27-110">short</span></span>](short.md)|<span data-ttu-id="e1e27-111">`int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="e1e27-111">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e1e27-112">ushort</span><span class="sxs-lookup"><span data-stu-id="e1e27-112">ushort</span></span>](ushort.md)|<span data-ttu-id="e1e27-113">`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="e1e27-113">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e1e27-114">int</span><span class="sxs-lookup"><span data-stu-id="e1e27-114">int</span></span>](int.md)|<span data-ttu-id="e1e27-115">`long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="e1e27-115">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e1e27-116">uint</span><span class="sxs-lookup"><span data-stu-id="e1e27-116">uint</span></span>](uint.md)|<span data-ttu-id="e1e27-117">`long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="e1e27-117">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e1e27-118">long</span><span class="sxs-lookup"><span data-stu-id="e1e27-118">long</span></span>](long.md)|<span data-ttu-id="e1e27-119">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="e1e27-119">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e1e27-120">char</span><span class="sxs-lookup"><span data-stu-id="e1e27-120">char</span></span>](char.md)|<span data-ttu-id="e1e27-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="e1e27-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e1e27-122">float</span><span class="sxs-lookup"><span data-stu-id="e1e27-122">float</span></span>](float.md)|`double`|  
|[<span data-ttu-id="e1e27-123">ulong</span><span class="sxs-lookup"><span data-stu-id="e1e27-123">ulong</span></span>](ulong.md)|<span data-ttu-id="e1e27-124">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="e1e27-124">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1e27-125">Note</span><span class="sxs-lookup"><span data-stu-id="e1e27-125">Remarks</span></span>  

- <span data-ttu-id="e1e27-126">Qualunque [tipo integrale](integral-types-table.md) è implicitamente convertibile in qualunque [tipo a virgola mobile](floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="e1e27-126">Any [integral type](integral-types-table.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="e1e27-127">Nella conversione da `int`, `uint`, `long` o `ulong` a `float` e da `long` o `ulong` a `double` può andare persa la precisione ma non la grandezza.</span><span class="sxs-lookup"><span data-stu-id="e1e27-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="e1e27-128">Non esiste alcuna conversione implicita verso il tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="e1e27-128">There are no implicit conversions to the `char` type.</span></span>  
  
- <span data-ttu-id="e1e27-129">Non esiste alcuna conversione implicita tra tipi `float` e `double` e il tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="e1e27-129">There are no implicit conversions between the `float` and `double` types and the `decimal` type.</span></span>  
  
- <span data-ttu-id="e1e27-130">Un valore di un'espressione costante di tipo `int` (ad esempio, un valore rappresentato da un valore letterale intero) possono essere convertiti in `sbyte`, `byte`, `short`, `ushort`, `uint`, o `ulong`, purché rientri all'interno dell'intervallo del tipo di destinazione:</span><span class="sxs-lookup"><span data-stu-id="e1e27-130">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="e1e27-131">Per altre informazioni sulle conversioni implicite, vedere la sezione [conversioni implicite](/dotnet/csharp/language-reference/language-specification/conversions#implicit-conversions) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="e1e27-131">For more information about implicit conversions, see the [Implicit conversions](/dotnet/csharp/language-reference/language-specification/conversions#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1e27-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1e27-132">See also</span></span>

- [<span data-ttu-id="e1e27-133">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e1e27-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e1e27-134">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e1e27-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e1e27-135">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="e1e27-135">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="e1e27-136">Tabella dei tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="e1e27-136">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="e1e27-137">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="e1e27-137">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="e1e27-138">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="e1e27-138">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="e1e27-139">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="e1e27-139">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
