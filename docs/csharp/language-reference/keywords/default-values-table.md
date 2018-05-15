---
title: Tabella dei valori predefiniti (Riferimenti per C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
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
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e249dd2f352fe6177f3afbfd089fc4dc9b1b7798
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="79742-102">Tabella dei valori predefiniti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="79742-102">Default values table (C# Reference)</span></span>

<span data-ttu-id="79742-103">La tabella seguente mostra i valori predefiniti dei tipi valore restituiti dai costruttori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="79742-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="79742-104">I costruttori predefiniti vengono richiamati con l'operatore `new`, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="79742-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="79742-105">L'istruzione precedente ha lo stesso effetto dell'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="79742-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="79742-106">Tenere presente che l'uso di variabili non inizializzate in C# non è consentito.</span><span class="sxs-lookup"><span data-stu-id="79742-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="79742-107">Tipo valore</span><span class="sxs-lookup"><span data-stu-id="79742-107">Value type</span></span>|<span data-ttu-id="79742-108">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="79742-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="79742-109">bool</span><span class="sxs-lookup"><span data-stu-id="79742-109">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="79742-110">byte</span><span class="sxs-lookup"><span data-stu-id="79742-110">byte</span></span>](byte.md)|<span data-ttu-id="79742-111">0</span><span class="sxs-lookup"><span data-stu-id="79742-111">0</span></span>|
|[<span data-ttu-id="79742-112">char</span><span class="sxs-lookup"><span data-stu-id="79742-112">char</span></span>](char.md)|<span data-ttu-id="79742-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="79742-113">'\0'</span></span>|
|[<span data-ttu-id="79742-114">decimal</span><span class="sxs-lookup"><span data-stu-id="79742-114">decimal</span></span>](decimal.md)|<span data-ttu-id="79742-115">0M</span><span class="sxs-lookup"><span data-stu-id="79742-115">0M</span></span>|
|[<span data-ttu-id="79742-116">double</span><span class="sxs-lookup"><span data-stu-id="79742-116">double</span></span>](double.md)|<span data-ttu-id="79742-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="79742-117">0.0D</span></span>|
|[<span data-ttu-id="79742-118">enum</span><span class="sxs-lookup"><span data-stu-id="79742-118">enum</span></span>](enum.md)|<span data-ttu-id="79742-119">Valore prodotto dall'espressione (E)0, dove E è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="79742-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="79742-120">float</span><span class="sxs-lookup"><span data-stu-id="79742-120">float</span></span>](float.md)|<span data-ttu-id="79742-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="79742-121">0.0F</span></span>|
|[<span data-ttu-id="79742-122">int</span><span class="sxs-lookup"><span data-stu-id="79742-122">int</span></span>](int.md)|<span data-ttu-id="79742-123">0</span><span class="sxs-lookup"><span data-stu-id="79742-123">0</span></span>|
|[<span data-ttu-id="79742-124">long</span><span class="sxs-lookup"><span data-stu-id="79742-124">long</span></span>](long.md)|<span data-ttu-id="79742-125">0L</span><span class="sxs-lookup"><span data-stu-id="79742-125">0L</span></span>|
|[<span data-ttu-id="79742-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="79742-126">sbyte</span></span>](sbyte.md)|<span data-ttu-id="79742-127">0</span><span class="sxs-lookup"><span data-stu-id="79742-127">0</span></span>|
|[<span data-ttu-id="79742-128">short</span><span class="sxs-lookup"><span data-stu-id="79742-128">short</span></span>](short.md)|<span data-ttu-id="79742-129">0</span><span class="sxs-lookup"><span data-stu-id="79742-129">0</span></span>|
|[<span data-ttu-id="79742-130">struct</span><span class="sxs-lookup"><span data-stu-id="79742-130">struct</span></span>](struct.md)|<span data-ttu-id="79742-131">Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="79742-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="79742-132">uint</span><span class="sxs-lookup"><span data-stu-id="79742-132">uint</span></span>](uint.md)|<span data-ttu-id="79742-133">0</span><span class="sxs-lookup"><span data-stu-id="79742-133">0</span></span>|
|[<span data-ttu-id="79742-134">ulong</span><span class="sxs-lookup"><span data-stu-id="79742-134">ulong</span></span>](ulong.md)|<span data-ttu-id="79742-135">0</span><span class="sxs-lookup"><span data-stu-id="79742-135">0</span></span>|
|[<span data-ttu-id="79742-136">ushort</span><span class="sxs-lookup"><span data-stu-id="79742-136">ushort</span></span>](ushort.md)|<span data-ttu-id="79742-137">0</span><span class="sxs-lookup"><span data-stu-id="79742-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="79742-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79742-138">See also</span></span>
 [<span data-ttu-id="79742-139">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="79742-139">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="79742-140">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="79742-140">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="79742-141">Tabella dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="79742-141">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="79742-142">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="79742-142">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="79742-143">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="79742-143">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="79742-144">Tabelle di riferimento per i tipi</span><span class="sxs-lookup"><span data-stu-id="79742-144">Reference Tables for Types</span></span>](reference-tables-for-types.md)
