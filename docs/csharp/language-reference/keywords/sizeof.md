---
title: sizeof (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
dev_langs:
- CSharp
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 15d11071c369fad398d40cfef301e462c006d5e4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="sizeof-c-reference"></a><span data-ttu-id="7a6a2-102">sizeof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7a6a2-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="7a6a2-103">Usato per ottenere la dimensione in byte per un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="7a6a2-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="7a6a2-104">I tipi non gestiti includono i tipi predefiniti che sono elencati nella tabella riportata di seguito, nonché quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7a6a2-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="7a6a2-105">Tipi enum</span><span class="sxs-lookup"><span data-stu-id="7a6a2-105">Enum types</span></span>  
  
-   <span data-ttu-id="7a6a2-106">Tipi puntatore</span><span class="sxs-lookup"><span data-stu-id="7a6a2-106">Pointer types</span></span>  
  
-   <span data-ttu-id="7a6a2-107">Struct definiti dall'utente che non contengono campi o proprietà che sono tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="7a6a2-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="7a6a2-108">Nell'esempio seguente viene illustrato come ottenere la dimensione di un `int`:</span><span class="sxs-lookup"><span data-stu-id="7a6a2-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="7a6a2-109">Note</span><span class="sxs-lookup"><span data-stu-id="7a6a2-109">Remarks</span></span>  
 <span data-ttu-id="7a6a2-110">A partire dalla versione 2.0 di C#, l'applicazione di `sizeof` ai tipi predefiniti non richiede più l'uso della modalità [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="7a6a2-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="7a6a2-111">Non è possibile eseguire l'overload dell'operatore `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="7a6a2-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="7a6a2-112">I valori restituiti dall'operatore `sizeof` sono di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="7a6a2-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="7a6a2-113">Nella tabella seguente vengono illustrati i valori costanti che vengono sostituiti con espressioni `sizeof` che dispongono di determinati tipi predefiniti come operandi.</span><span class="sxs-lookup"><span data-stu-id="7a6a2-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="7a6a2-114">Espressione</span><span class="sxs-lookup"><span data-stu-id="7a6a2-114">Expression</span></span>|<span data-ttu-id="7a6a2-115">Valore costante</span><span class="sxs-lookup"><span data-stu-id="7a6a2-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="7a6a2-116">1</span><span class="sxs-lookup"><span data-stu-id="7a6a2-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="7a6a2-117">1</span><span class="sxs-lookup"><span data-stu-id="7a6a2-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="7a6a2-118">2</span><span class="sxs-lookup"><span data-stu-id="7a6a2-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="7a6a2-119">2</span><span class="sxs-lookup"><span data-stu-id="7a6a2-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="7a6a2-120">4</span><span class="sxs-lookup"><span data-stu-id="7a6a2-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="7a6a2-121">4</span><span class="sxs-lookup"><span data-stu-id="7a6a2-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="7a6a2-122">8</span><span class="sxs-lookup"><span data-stu-id="7a6a2-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="7a6a2-123">8</span><span class="sxs-lookup"><span data-stu-id="7a6a2-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="7a6a2-124">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="7a6a2-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="7a6a2-125">4</span><span class="sxs-lookup"><span data-stu-id="7a6a2-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="7a6a2-126">8</span><span class="sxs-lookup"><span data-stu-id="7a6a2-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="7a6a2-127">16</span><span class="sxs-lookup"><span data-stu-id="7a6a2-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="7a6a2-128">1</span><span class="sxs-lookup"><span data-stu-id="7a6a2-128">1</span></span>|  
  
 <span data-ttu-id="7a6a2-129">Per tutti gli altri tipi, inclusi gli struct, l'operatore `sizeof` può essere usato solo nei blocchi di codice unsafe.</span><span class="sxs-lookup"><span data-stu-id="7a6a2-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="7a6a2-130">Sebbene sia possibile usare il metodo <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName>, il valore restituito da questo metodo non è sempre uguale al valore restituito da `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="7a6a2-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="7a6a2-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> restituisce la dimensione dopo il marshalling del tipo, mentre `sizeof` restituisce la dimensione allocata da Common Language Runtime, che include eventuali spaziature interne.</span><span class="sxs-lookup"><span data-stu-id="7a6a2-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a6a2-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a6a2-132">Example</span></span>  
 <span data-ttu-id="7a6a2-133">[!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7a6a2-133">[!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7a6a2-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7a6a2-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7a6a2-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a6a2-135">See Also</span></span>  
 <span data-ttu-id="7a6a2-136">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7a6a2-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7a6a2-137">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7a6a2-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7a6a2-138">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="7a6a2-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="7a6a2-139">[Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="7a6a2-139">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="7a6a2-140">[enum](../../../csharp/language-reference/keywords/enum.md) </span><span class="sxs-lookup"><span data-stu-id="7a6a2-140">[enum](../../../csharp/language-reference/keywords/enum.md) </span></span>  
 <span data-ttu-id="7a6a2-141">[Codice di tipo unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="7a6a2-141">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="7a6a2-142">[Struct](../../../csharp/programming-guide/classes-and-structs/structs.md) </span><span class="sxs-lookup"><span data-stu-id="7a6a2-142">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span></span>  
 [<span data-ttu-id="7a6a2-143">Costanti</span><span class="sxs-lookup"><span data-stu-id="7a6a2-143">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

