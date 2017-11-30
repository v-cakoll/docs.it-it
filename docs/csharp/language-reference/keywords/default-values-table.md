---
title: Tabella dei valori predefiniti (Riferimenti per C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d034c1daf495c50e299fec4c5bf399652dad08ce
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2017
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="afe9d-102">Tabella dei valori predefiniti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="afe9d-102">Default values table (C# Reference)</span></span>
<span data-ttu-id="afe9d-103">La tabella seguente mostra i valori predefiniti dei tipi valore restituiti dai costruttori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="afe9d-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="afe9d-104">I costruttori predefiniti vengono richiamati con l'operatore `new`, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="afe9d-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="afe9d-105">L'istruzione precedente ha lo stesso effetto dell'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="afe9d-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="afe9d-106">Tenere presente che l'uso di variabili non inizializzate in C# non è consentito.</span><span class="sxs-lookup"><span data-stu-id="afe9d-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="afe9d-107">Tipo valore</span><span class="sxs-lookup"><span data-stu-id="afe9d-107">Value type</span></span>|<span data-ttu-id="afe9d-108">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="afe9d-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="afe9d-109">bool</span><span class="sxs-lookup"><span data-stu-id="afe9d-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="afe9d-110">byte</span><span class="sxs-lookup"><span data-stu-id="afe9d-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="afe9d-111">0</span><span class="sxs-lookup"><span data-stu-id="afe9d-111">0</span></span>|
|[<span data-ttu-id="afe9d-112">char</span><span class="sxs-lookup"><span data-stu-id="afe9d-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="afe9d-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="afe9d-113">'\0'</span></span>|
|[<span data-ttu-id="afe9d-114">decimal</span><span class="sxs-lookup"><span data-stu-id="afe9d-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="afe9d-115">M 0</span><span class="sxs-lookup"><span data-stu-id="afe9d-115">0M</span></span>|
|[<span data-ttu-id="afe9d-116">double</span><span class="sxs-lookup"><span data-stu-id="afe9d-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="afe9d-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="afe9d-117">0.0D</span></span>|
|[<span data-ttu-id="afe9d-118">enum</span><span class="sxs-lookup"><span data-stu-id="afe9d-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="afe9d-119">Valore prodotto dall'espressione (E)0, dove E è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="afe9d-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="afe9d-120">float</span><span class="sxs-lookup"><span data-stu-id="afe9d-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="afe9d-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="afe9d-121">0.0F</span></span>|
|[<span data-ttu-id="afe9d-122">int</span><span class="sxs-lookup"><span data-stu-id="afe9d-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="afe9d-123">0</span><span class="sxs-lookup"><span data-stu-id="afe9d-123">0</span></span>|
|[<span data-ttu-id="afe9d-124">long</span><span class="sxs-lookup"><span data-stu-id="afe9d-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="afe9d-125">0L</span><span class="sxs-lookup"><span data-stu-id="afe9d-125">0L</span></span>|
|[<span data-ttu-id="afe9d-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="afe9d-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="afe9d-127">0</span><span class="sxs-lookup"><span data-stu-id="afe9d-127">0</span></span>|
|[<span data-ttu-id="afe9d-128">short</span><span class="sxs-lookup"><span data-stu-id="afe9d-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="afe9d-129">0</span><span class="sxs-lookup"><span data-stu-id="afe9d-129">0</span></span>|
|[<span data-ttu-id="afe9d-130">struct</span><span class="sxs-lookup"><span data-stu-id="afe9d-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="afe9d-131">Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="afe9d-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="afe9d-132">uint</span><span class="sxs-lookup"><span data-stu-id="afe9d-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="afe9d-133">0</span><span class="sxs-lookup"><span data-stu-id="afe9d-133">0</span></span>|
|[<span data-ttu-id="afe9d-134">ulong</span><span class="sxs-lookup"><span data-stu-id="afe9d-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="afe9d-135">0</span><span class="sxs-lookup"><span data-stu-id="afe9d-135">0</span></span>|
|[<span data-ttu-id="afe9d-136">ushort</span><span class="sxs-lookup"><span data-stu-id="afe9d-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="afe9d-137">0</span><span class="sxs-lookup"><span data-stu-id="afe9d-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="afe9d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afe9d-138">See also</span></span>
 [<span data-ttu-id="afe9d-139">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="afe9d-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="afe9d-140">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="afe9d-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="afe9d-141">Tabella dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="afe9d-141">Value Types Table</span></span>](../../../csharp/language-reference/keywords/value-types-table.md)  
 [<span data-ttu-id="afe9d-142">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="afe9d-142">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="afe9d-143">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="afe9d-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="afe9d-144">Tabelle di riferimento per i tipi</span><span class="sxs-lookup"><span data-stu-id="afe9d-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
