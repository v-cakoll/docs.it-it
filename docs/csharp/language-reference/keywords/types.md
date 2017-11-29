---
title: Tipi (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2c7285e237b04c1290391c4bba3e62886dceb83c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="types-c-reference"></a><span data-ttu-id="f2ed7-102">Tipi (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f2ed7-102">Types (C# Reference)</span></span>
<span data-ttu-id="f2ed7-103">Il sistema di tipizzazione di C# contiene le categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2ed7-103">The C# typing system contains the following categories:</span></span>  
  
-   [<span data-ttu-id="f2ed7-104">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="f2ed7-104">Value types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [<span data-ttu-id="f2ed7-105">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="f2ed7-105">Reference types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="f2ed7-106">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="f2ed7-106">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
 <span data-ttu-id="f2ed7-107">Le variabili che sono tipi valore archiviano dati, mentre quelle che sono tipi riferimento archiviano riferimenti ai dati effettivi.</span><span class="sxs-lookup"><span data-stu-id="f2ed7-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="f2ed7-108">I tipi riferimento vengono anche denominati oggetti.</span><span class="sxs-lookup"><span data-stu-id="f2ed7-108">Reference types are also referred to as objects.</span></span> <span data-ttu-id="f2ed7-109">I tipi puntatore possono essere usati solo nella modalità [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="f2ed7-109">Pointer types can be used only in [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode.</span></span>  
  
 <span data-ttu-id="f2ed7-110">È possibile convertire un tipo valore in un tipo riferimento, e quindi nuovamente in un tipo valore, usando [boxing e unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="f2ed7-110">It is possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="f2ed7-111">Fatta eccezione per un tipo valore boxed, è possibile convertire un tipo riferimento in un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="f2ed7-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>  
  
 <span data-ttu-id="f2ed7-112">In questa sezione viene presentato anche [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="f2ed7-112">This section also introduces [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
 <span data-ttu-id="f2ed7-113">I tipi valore sono inoltre nullable, il che significa che possono archiviare uno stato aggiuntivo diverso da un valore.</span><span class="sxs-lookup"><span data-stu-id="f2ed7-113">Value types are also nullable, which means they can store an additional non-value state.</span></span> <span data-ttu-id="f2ed7-114">Per altre informazioni, vedere [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="f2ed7-114">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ed7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2ed7-115">See Also</span></span>  
 [<span data-ttu-id="f2ed7-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f2ed7-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f2ed7-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f2ed7-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f2ed7-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="f2ed7-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f2ed7-119">Tabelle di riferimento per i tipi</span><span class="sxs-lookup"><span data-stu-id="f2ed7-119">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [<span data-ttu-id="f2ed7-120">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="f2ed7-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [<span data-ttu-id="f2ed7-121">Tipi</span><span class="sxs-lookup"><span data-stu-id="f2ed7-121">Types</span></span>](../../../csharp/programming-guide/types/index.md)
