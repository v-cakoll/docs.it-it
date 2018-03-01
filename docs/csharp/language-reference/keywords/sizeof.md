---
title: sizeof (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0148ae8381804ca9286315251582c8ab40778369
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="2b576-102">sizeof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2b576-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="2b576-103">Usato per ottenere la dimensione in byte per un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="2b576-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="2b576-104">I tipi non gestiti includono i tipi predefiniti che sono elencati nella tabella riportata di seguito, nonché quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2b576-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="2b576-105">Tipi enum</span><span class="sxs-lookup"><span data-stu-id="2b576-105">Enum types</span></span>  
  
-   <span data-ttu-id="2b576-106">Tipi puntatore</span><span class="sxs-lookup"><span data-stu-id="2b576-106">Pointer types</span></span>  
  
-   <span data-ttu-id="2b576-107">Struct definiti dall'utente che non contengono campi o proprietà che sono tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="2b576-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="2b576-108">Nell'esempio seguente viene illustrato come ottenere la dimensione di un `int`:</span><span class="sxs-lookup"><span data-stu-id="2b576-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="2b576-109">Note</span><span class="sxs-lookup"><span data-stu-id="2b576-109">Remarks</span></span>  
 <span data-ttu-id="2b576-110">A partire dalla versione 2.0 di C#, l'applicazione di `sizeof` ai tipi predefiniti non richiede più l'uso della modalità [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="2b576-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="2b576-111">Non è possibile eseguire l'overload dell'operatore `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="2b576-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="2b576-112">I valori restituiti dall'operatore `sizeof` sono di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="2b576-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="2b576-113">Nella tabella seguente vengono illustrati i valori costanti che vengono sostituiti con espressioni `sizeof` che dispongono di determinati tipi predefiniti come operandi.</span><span class="sxs-lookup"><span data-stu-id="2b576-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="2b576-114">Espressione</span><span class="sxs-lookup"><span data-stu-id="2b576-114">Expression</span></span>|<span data-ttu-id="2b576-115">Valore costante</span><span class="sxs-lookup"><span data-stu-id="2b576-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="2b576-116">1</span><span class="sxs-lookup"><span data-stu-id="2b576-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="2b576-117">1</span><span class="sxs-lookup"><span data-stu-id="2b576-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="2b576-118">2</span><span class="sxs-lookup"><span data-stu-id="2b576-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="2b576-119">2</span><span class="sxs-lookup"><span data-stu-id="2b576-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="2b576-120">4</span><span class="sxs-lookup"><span data-stu-id="2b576-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="2b576-121">4</span><span class="sxs-lookup"><span data-stu-id="2b576-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="2b576-122">8</span><span class="sxs-lookup"><span data-stu-id="2b576-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="2b576-123">8</span><span class="sxs-lookup"><span data-stu-id="2b576-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="2b576-124">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="2b576-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="2b576-125">4</span><span class="sxs-lookup"><span data-stu-id="2b576-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="2b576-126">8</span><span class="sxs-lookup"><span data-stu-id="2b576-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="2b576-127">16</span><span class="sxs-lookup"><span data-stu-id="2b576-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="2b576-128">1</span><span class="sxs-lookup"><span data-stu-id="2b576-128">1</span></span>|  
  
 <span data-ttu-id="2b576-129">Per tutti gli altri tipi, inclusi gli struct, l'operatore `sizeof` può essere usato solo nei blocchi di codice unsafe.</span><span class="sxs-lookup"><span data-stu-id="2b576-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="2b576-130">Sebbene sia possibile usare il metodo <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, il valore restituito da questo metodo non è sempre uguale al valore restituito da `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="2b576-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="2b576-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> restituisce la dimensione dopo il marshalling del tipo, mentre `sizeof` restituisce la dimensione allocata da Common Language Runtime, che include eventuali spaziature interne.</span><span class="sxs-lookup"><span data-stu-id="2b576-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b576-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b576-132">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="2b576-133">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2b576-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b576-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b576-134">See Also</span></span>  
 [<span data-ttu-id="2b576-135">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2b576-135">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2b576-136">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2b576-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2b576-137">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="2b576-137">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="2b576-138">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="2b576-138">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="2b576-139">enum</span><span class="sxs-lookup"><span data-stu-id="2b576-139">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
 [<span data-ttu-id="2b576-140">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="2b576-140">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="2b576-141">Struct</span><span class="sxs-lookup"><span data-stu-id="2b576-141">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [<span data-ttu-id="2b576-142">Costanti</span><span class="sxs-lookup"><span data-stu-id="2b576-142">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)
