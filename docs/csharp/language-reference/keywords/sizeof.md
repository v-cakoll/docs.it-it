---
title: sizeof (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: f2507dd8528e2e66016524873ada890227a74ed8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517038"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="b1b5e-102">sizeof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b1b5e-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="b1b5e-103">Usato per ottenere la dimensione in byte per un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="b1b5e-104">I tipi non gestiti includono:</span><span class="sxs-lookup"><span data-stu-id="b1b5e-104">Unmanaged types include:</span></span>

-   <span data-ttu-id="b1b5e-105">I tipi semplici elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="b1b5e-105">The simple types that are listed in the following table:</span></span>
  
   |<span data-ttu-id="b1b5e-106">Espressione</span><span class="sxs-lookup"><span data-stu-id="b1b5e-106">Expression</span></span>|<span data-ttu-id="b1b5e-107">Valore costante</span><span class="sxs-lookup"><span data-stu-id="b1b5e-107">Constant value</span></span>|  
   |----------------|--------------------|  
   |`sizeof(sbyte)`|<span data-ttu-id="b1b5e-108">1</span><span class="sxs-lookup"><span data-stu-id="b1b5e-108">1</span></span>|  
   |`sizeof(byte)`|<span data-ttu-id="b1b5e-109">1</span><span class="sxs-lookup"><span data-stu-id="b1b5e-109">1</span></span>|  
   |`sizeof(short)`|<span data-ttu-id="b1b5e-110">2</span><span class="sxs-lookup"><span data-stu-id="b1b5e-110">2</span></span>|  
   |`sizeof(ushort)`|<span data-ttu-id="b1b5e-111">2</span><span class="sxs-lookup"><span data-stu-id="b1b5e-111">2</span></span>|  
   |`sizeof(int)`|<span data-ttu-id="b1b5e-112">4</span><span class="sxs-lookup"><span data-stu-id="b1b5e-112">4</span></span>|  
   |`sizeof(uint)`|<span data-ttu-id="b1b5e-113">4</span><span class="sxs-lookup"><span data-stu-id="b1b5e-113">4</span></span>|  
   |`sizeof(long)`|<span data-ttu-id="b1b5e-114">8</span><span class="sxs-lookup"><span data-stu-id="b1b5e-114">8</span></span>|  
   |`sizeof(ulong)`|<span data-ttu-id="b1b5e-115">8</span><span class="sxs-lookup"><span data-stu-id="b1b5e-115">8</span></span>|  
   |`sizeof(char)`|<span data-ttu-id="b1b5e-116">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="b1b5e-116">2 (Unicode)</span></span>|  
   |`sizeof(float)`|<span data-ttu-id="b1b5e-117">4</span><span class="sxs-lookup"><span data-stu-id="b1b5e-117">4</span></span>|  
   |`sizeof(double)`|<span data-ttu-id="b1b5e-118">8</span><span class="sxs-lookup"><span data-stu-id="b1b5e-118">8</span></span>|  
   |`sizeof(decimal)`|<span data-ttu-id="b1b5e-119">16</span><span class="sxs-lookup"><span data-stu-id="b1b5e-119">16</span></span>|  
   |`sizeof(bool)`|<span data-ttu-id="b1b5e-120">1</span><span class="sxs-lookup"><span data-stu-id="b1b5e-120">1</span></span>| 
  
-   <span data-ttu-id="b1b5e-121">Tipi enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-121">Enum types.</span></span>
  
-   <span data-ttu-id="b1b5e-122">Tipi puntatore.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-122">Pointer types.</span></span>
  
-   <span data-ttu-id="b1b5e-123">Struct definiti dall'utente che non contengono campi di istanza o proprietà di istanza implementate automaticamente che sono tipi riferimento o tipi costruiti.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>
  
 <span data-ttu-id="b1b5e-124">Nell'esempio seguente viene illustrato come ottenere la dimensione di un `int`:</span><span class="sxs-lookup"><span data-stu-id="b1b5e-124">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="b1b5e-125">Note</span><span class="sxs-lookup"><span data-stu-id="b1b5e-125">Remarks</span></span>  
 <span data-ttu-id="b1b5e-126">A partire dalla versione 2.0 di C#, l'applicazione di `sizeof` a tipi semplici o tipi enumerazione non richiede più che il codice venga compilato in un contesto [non sicuro](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="b1b5e-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>
  
 <span data-ttu-id="b1b5e-127">Non è possibile sottoporre l'operatore `sizeof` a overload.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="b1b5e-128">I valori restituiti dall'operatore `sizeof` sono di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="b1b5e-129">La tabella precedente mostra i valori costanti che vengono sostituiti per le espressioni `sizeof` con determinati tipi predefiniti come operandi.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>  
    
 <span data-ttu-id="b1b5e-130">Per tutti gli altri tipi, inclusi gli struct, l'operatore `sizeof` può essere usato solo nei blocchi di codice unsafe.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="b1b5e-131">Sebbene sia possibile usare il metodo <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, il valore restituito da questo metodo non è sempre uguale al valore restituito da `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="b1b5e-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> restituisce la dimensione dopo il marshalling del tipo, mentre `sizeof` restituisce la dimensione allocata da Common Language Runtime, che include eventuali spaziature interne.</span><span class="sxs-lookup"><span data-stu-id="b1b5e-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1b5e-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1b5e-133">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b1b5e-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b1b5e-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1b5e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1b5e-135">See Also</span></span>

- [<span data-ttu-id="b1b5e-136">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b1b5e-136">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b1b5e-137">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b1b5e-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b1b5e-138">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b1b5e-138">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="b1b5e-139">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="b1b5e-139">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
- [<span data-ttu-id="b1b5e-140">enum</span><span class="sxs-lookup"><span data-stu-id="b1b5e-140">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
- [<span data-ttu-id="b1b5e-141">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="b1b5e-141">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="b1b5e-142">Struct</span><span class="sxs-lookup"><span data-stu-id="b1b5e-142">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
- [<span data-ttu-id="b1b5e-143">Costanti</span><span class="sxs-lookup"><span data-stu-id="b1b5e-143">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)
