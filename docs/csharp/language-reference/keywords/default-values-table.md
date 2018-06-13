---
title: Tabella dei valori predefiniti (Riferimenti per C#)
description: Informazioni sui valori predefiniti dei tipi valore restituiti dai costruttori predefiniti.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218790"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="3ca12-103">Tabella dei valori predefiniti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3ca12-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="3ca12-104">La tabella seguente mostra i valori predefiniti dei tipi valore restituiti dai costruttori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3ca12-104">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="3ca12-105">I costruttori predefiniti vengono richiamati con l'operatore `new`, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="3ca12-105">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="3ca12-106">L'istruzione precedente ha lo stesso effetto dell'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="3ca12-106">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="3ca12-107">Tenere presente che l'uso di variabili non inizializzate in C# non è consentito.</span><span class="sxs-lookup"><span data-stu-id="3ca12-107">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="3ca12-108">Tipo valore</span><span class="sxs-lookup"><span data-stu-id="3ca12-108">Value type</span></span>|<span data-ttu-id="3ca12-109">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="3ca12-109">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="3ca12-110">bool</span><span class="sxs-lookup"><span data-stu-id="3ca12-110">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="3ca12-111">byte</span><span class="sxs-lookup"><span data-stu-id="3ca12-111">byte</span></span>](byte.md)|<span data-ttu-id="3ca12-112">0</span><span class="sxs-lookup"><span data-stu-id="3ca12-112">0</span></span>|
|[<span data-ttu-id="3ca12-113">char</span><span class="sxs-lookup"><span data-stu-id="3ca12-113">char</span></span>](char.md)|<span data-ttu-id="3ca12-114">'\0'</span><span class="sxs-lookup"><span data-stu-id="3ca12-114">'\0'</span></span>|
|[<span data-ttu-id="3ca12-115">decimal</span><span class="sxs-lookup"><span data-stu-id="3ca12-115">decimal</span></span>](decimal.md)|<span data-ttu-id="3ca12-116">0M</span><span class="sxs-lookup"><span data-stu-id="3ca12-116">0M</span></span>|
|[<span data-ttu-id="3ca12-117">double</span><span class="sxs-lookup"><span data-stu-id="3ca12-117">double</span></span>](double.md)|<span data-ttu-id="3ca12-118">0.0D</span><span class="sxs-lookup"><span data-stu-id="3ca12-118">0.0D</span></span>|
|[<span data-ttu-id="3ca12-119">enum</span><span class="sxs-lookup"><span data-stu-id="3ca12-119">enum</span></span>](enum.md)|<span data-ttu-id="3ca12-120">Valore prodotto dall'espressione (E)0, dove E è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3ca12-120">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="3ca12-121">float</span><span class="sxs-lookup"><span data-stu-id="3ca12-121">float</span></span>](float.md)|<span data-ttu-id="3ca12-122">0.0F</span><span class="sxs-lookup"><span data-stu-id="3ca12-122">0.0F</span></span>|
|[<span data-ttu-id="3ca12-123">int</span><span class="sxs-lookup"><span data-stu-id="3ca12-123">int</span></span>](int.md)|<span data-ttu-id="3ca12-124">0</span><span class="sxs-lookup"><span data-stu-id="3ca12-124">0</span></span>|
|[<span data-ttu-id="3ca12-125">long</span><span class="sxs-lookup"><span data-stu-id="3ca12-125">long</span></span>](long.md)|<span data-ttu-id="3ca12-126">0L</span><span class="sxs-lookup"><span data-stu-id="3ca12-126">0L</span></span>|
|[<span data-ttu-id="3ca12-127">sbyte</span><span class="sxs-lookup"><span data-stu-id="3ca12-127">sbyte</span></span>](sbyte.md)|<span data-ttu-id="3ca12-128">0</span><span class="sxs-lookup"><span data-stu-id="3ca12-128">0</span></span>|
|[<span data-ttu-id="3ca12-129">short</span><span class="sxs-lookup"><span data-stu-id="3ca12-129">short</span></span>](short.md)|<span data-ttu-id="3ca12-130">0</span><span class="sxs-lookup"><span data-stu-id="3ca12-130">0</span></span>|
|[<span data-ttu-id="3ca12-131">struct</span><span class="sxs-lookup"><span data-stu-id="3ca12-131">struct</span></span>](struct.md)|<span data-ttu-id="3ca12-132">Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="3ca12-132">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="3ca12-133">uint</span><span class="sxs-lookup"><span data-stu-id="3ca12-133">uint</span></span>](uint.md)|<span data-ttu-id="3ca12-134">0</span><span class="sxs-lookup"><span data-stu-id="3ca12-134">0</span></span>|
|[<span data-ttu-id="3ca12-135">ulong</span><span class="sxs-lookup"><span data-stu-id="3ca12-135">ulong</span></span>](ulong.md)|<span data-ttu-id="3ca12-136">0</span><span class="sxs-lookup"><span data-stu-id="3ca12-136">0</span></span>|
|[<span data-ttu-id="3ca12-137">ushort</span><span class="sxs-lookup"><span data-stu-id="3ca12-137">ushort</span></span>](ushort.md)|<span data-ttu-id="3ca12-138">0</span><span class="sxs-lookup"><span data-stu-id="3ca12-138">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="3ca12-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ca12-139">See also</span></span>
 [<span data-ttu-id="3ca12-140">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3ca12-140">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="3ca12-141">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3ca12-141">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="3ca12-142">Tabella dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="3ca12-142">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="3ca12-143">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="3ca12-143">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="3ca12-144">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="3ca12-144">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="3ca12-145">Tabelle di riferimento per i tipi</span><span class="sxs-lookup"><span data-stu-id="3ca12-145">Reference Tables for Types</span></span>](reference-tables-for-types.md)
