---
title: Tabella dei valori predefiniti (Riferimenti per C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
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
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: f8cf12317f1f0163028db003ff31604480da5d1c
ms.openlocfilehash: 975d416259778e0741347829d8a9c79aaa6cfc8c
ms.contentlocale: it-it
ms.lasthandoff: 08/12/2017

---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="b4836-102">Tabella dei valori predefiniti (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b4836-102">Default values table (C# Reference)</span></span>
<span data-ttu-id="b4836-103">La tabella seguente mostra i valori predefiniti dei tipi valore restituiti dai costruttori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b4836-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="b4836-104">I costruttori predefiniti vengono richiamati con l'operatore `new`, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="b4836-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="b4836-105">L'istruzione precedente ha lo stesso effetto dell'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="b4836-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="b4836-106">Tenere presente che l'uso di variabili non inizializzate in C# non è consentito.</span><span class="sxs-lookup"><span data-stu-id="b4836-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="b4836-107">Tipo valore</span><span class="sxs-lookup"><span data-stu-id="b4836-107">Value type</span></span>|<span data-ttu-id="b4836-108">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="b4836-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="b4836-109">bool</span><span class="sxs-lookup"><span data-stu-id="b4836-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="b4836-110">byte</span><span class="sxs-lookup"><span data-stu-id="b4836-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="b4836-111">0</span><span class="sxs-lookup"><span data-stu-id="b4836-111">0</span></span>|
|[<span data-ttu-id="b4836-112">char</span><span class="sxs-lookup"><span data-stu-id="b4836-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="b4836-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="b4836-113">'\0'</span></span>|
|[<span data-ttu-id="b4836-114">decimal</span><span class="sxs-lookup"><span data-stu-id="b4836-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="b4836-115">0.0M</span><span class="sxs-lookup"><span data-stu-id="b4836-115">0.0M</span></span>|
|[<span data-ttu-id="b4836-116">double</span><span class="sxs-lookup"><span data-stu-id="b4836-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="b4836-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="b4836-117">0.0D</span></span>|
|[<span data-ttu-id="b4836-118">enum</span><span class="sxs-lookup"><span data-stu-id="b4836-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="b4836-119">Valore prodotto dall'espressione (E)0, dove E è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b4836-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="b4836-120">float</span><span class="sxs-lookup"><span data-stu-id="b4836-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="b4836-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="b4836-121">0.0F</span></span>|
|[<span data-ttu-id="b4836-122">int</span><span class="sxs-lookup"><span data-stu-id="b4836-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="b4836-123">0</span><span class="sxs-lookup"><span data-stu-id="b4836-123">0</span></span>|
|[<span data-ttu-id="b4836-124">long</span><span class="sxs-lookup"><span data-stu-id="b4836-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="b4836-125">0L</span><span class="sxs-lookup"><span data-stu-id="b4836-125">0L</span></span>|
|[<span data-ttu-id="b4836-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="b4836-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="b4836-127">0</span><span class="sxs-lookup"><span data-stu-id="b4836-127">0</span></span>|
|[<span data-ttu-id="b4836-128">short</span><span class="sxs-lookup"><span data-stu-id="b4836-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="b4836-129">0</span><span class="sxs-lookup"><span data-stu-id="b4836-129">0</span></span>|
|[<span data-ttu-id="b4836-130">struct</span><span class="sxs-lookup"><span data-stu-id="b4836-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="b4836-131">Valore prodotto impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="b4836-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="b4836-132">uint</span><span class="sxs-lookup"><span data-stu-id="b4836-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="b4836-133">0</span><span class="sxs-lookup"><span data-stu-id="b4836-133">0</span></span>|
|[<span data-ttu-id="b4836-134">ulong</span><span class="sxs-lookup"><span data-stu-id="b4836-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="b4836-135">0</span><span class="sxs-lookup"><span data-stu-id="b4836-135">0</span></span>|
|[<span data-ttu-id="b4836-136">ushort</span><span class="sxs-lookup"><span data-stu-id="b4836-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="b4836-137">0</span><span class="sxs-lookup"><span data-stu-id="b4836-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="b4836-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4836-138">See also</span></span>
 <span data-ttu-id="b4836-139">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4836-139">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b4836-140">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b4836-140">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b4836-141">[Tabella dei tipi valore](../../../csharp/language-reference/keywords/value-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b4836-141">[Value Types Table](../../../csharp/language-reference/keywords/value-types-table.md) </span></span>  
 <span data-ttu-id="b4836-142">[Tipi di valore](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="b4836-142">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="b4836-143">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b4836-143">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 [<span data-ttu-id="b4836-144">Tabelle di riferimento per i tipi</span><span class="sxs-lookup"><span data-stu-id="b4836-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)

