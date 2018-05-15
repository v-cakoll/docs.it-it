---
title: Tipi nullable (Guida per programmatori C#)
ms.date: 05/15/2017
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: 10a2d4ab248276d9fdbe9d2bba40ccdd02a77408
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="e9c9c-102">Tipi nullable (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e9c9c-102">Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="e9c9c-103">I tipi nullable sono istanze dello struct <xref:System.Nullable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-103">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=nameWithType> struct.</span></span> <span data-ttu-id="e9c9c-104">Un tipo nullable può rappresentare l'intervallo di valori corretto del tipo valore sottostante, più un valore `null` aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-104">A nullable type can represent the correct range of values for its underlying value type, plus an additional `null` value.</span></span> <span data-ttu-id="e9c9c-105">Ad esempio, a un tipo `Nullable<Int32>`, detto anche "Nullable of Int32", può essere assegnato qualsiasi valore compreso tra -2147483648 e 2147483647. In alternativa, può essere assegnato il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-105">For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from -2147483648 to 2147483647, or it can be assigned the `null` value.</span></span> <span data-ttu-id="e9c9c-106">A un tipo `Nullable<bool>` può essere assegnato il valore [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) o [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="e9c9c-106">A `Nullable<bool>` can be assigned the values [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), or [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="e9c9c-107">La possibilità di assegnare il valore `null` a tipi numerici e booleani è particolarmente utile quando si gestiscono database e altri tipi di dati contenenti elementi a cui non è possibile assegnare un valore.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-107">The ability to assign `null` to numeric and Boolean types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value.</span></span> <span data-ttu-id="e9c9c-108">Ad esempio, un campo booleano di un database può archiviare i valori `true` o `false` oppure può essere non definito.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-108">For example, a Boolean field in a database can store the values `true` or `false`, or it may be undefined.</span></span> 
  
[!code-csharp[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
<span data-ttu-id="e9c9c-109">Per altri esempi, vedere [Uso dei tipi nullable](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span><span class="sxs-lookup"><span data-stu-id="e9c9c-109">For more examples, see [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span></span>  
  
## <a name="nullable-types-overview"></a><span data-ttu-id="e9c9c-110">Panoramica dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="e9c9c-110">Nullable Types Overview</span></span>  
 <span data-ttu-id="e9c9c-111">I tipi nullable hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9c9c-111">Nullable types have the following characteristics:</span></span>  
  
-   <span data-ttu-id="e9c9c-112">I tipi nullable rappresentano variabili di tipo valore a cui può essere assegnato il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-112">Nullable types represent value-type variables that can be assigned the value of `null`.</span></span> <span data-ttu-id="e9c9c-113">Non è possibile creare un tipi nullable sulla base di un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-113">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="e9c9c-114">I tipi riferimento supportano già il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-114">(Reference types already support the `null` value.)</span></span>  
  
-   <span data-ttu-id="e9c9c-115">La sintassi `T?` è l'abbreviazione di <xref:System.Nullable%601>, dove `T` è un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-115">The syntax `T?` is shorthand for <xref:System.Nullable%601>, where `T` is a value type.</span></span> <span data-ttu-id="e9c9c-116">Le due forme sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-116">The two forms are interchangeable.</span></span>  
  
-   <span data-ttu-id="e9c9c-117">Per assegnare un valore a un tipo nullable è possibile procedere come per un comune tipo valore, ad esempio `int? x = 10;` o `double? d = 4.108`.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-117">Assign a value to a nullable type just as you would for an ordinary value type, for example `int? x = 10;` or `double? d = 4.108`.</span></span> <span data-ttu-id="e9c9c-118">A un tipo nullable può essere assegnato anche il valore `null`: `int? x = null.`</span><span class="sxs-lookup"><span data-stu-id="e9c9c-118">A nullable type can also be assigned the value `null`: `int? x = null.`</span></span>  
  
-   <span data-ttu-id="e9c9c-119">Usare il metodo <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> per restituire il valore assegnato oppure il valore predefinito del tipo sottostante se il valore è `null`, ad esempio `int j = x.GetValueOrDefault();`</span><span class="sxs-lookup"><span data-stu-id="e9c9c-119">Use the <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> method to return either the assigned value, or the default value for the underlying type if the value is `null`, for example `int j = x.GetValueOrDefault();`</span></span>  
  
-   <span data-ttu-id="e9c9c-120">Usare le proprietà di sola lettura <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> per verificare la presenza di valori null e recuperare il valore, come illustrato nell'esempio seguente: `if(x.HasValue) j = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="e9c9c-120">Use the <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> read-only properties to test for null and retrieve the value, as shown in the following example: `if(x.HasValue) j = x.Value;`</span></span>  
  
    -   <span data-ttu-id="e9c9c-121">La proprietà `HasValue` restituisce `true` se la variabile contiene un valore o `false` se è `null`.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-121">The `HasValue` property returns `true` if the variable contains a value, or `false` if it is `null`.</span></span>  
  
    -   <span data-ttu-id="e9c9c-122">La proprietà `Value` restituisce un valore se ne è stato assegnato uno.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-122">The `Value` property returns a value if one is assigned.</span></span> <span data-ttu-id="e9c9c-123">In caso contrario viene generata un'eccezione <xref:System.InvalidOperationException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-123">Otherwise, a <xref:System.InvalidOperationException?displayProperty=nameWithType> is thrown.</span></span>  
  
    -   <span data-ttu-id="e9c9c-124">Il valore predefinito per la proprietà `HasValue` è `false`.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-124">The default value for `HasValue` is `false`.</span></span> <span data-ttu-id="e9c9c-125">La proprietà `Value` non ha alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-125">The `Value` property has no default value.</span></span>  
  
    -   <span data-ttu-id="e9c9c-126">Con un tipo nullable è anche possibile usare gli operatori `==` e `!=`, come mostrato nell'esempio seguente: `if (x != null) y = x;`</span><span class="sxs-lookup"><span data-stu-id="e9c9c-126">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x;`</span></span>  
  
-   <span data-ttu-id="e9c9c-127">Usare l'operatore `??` per assegnare un valore predefinito che verrà applicato quando un tipo nullable il cui valore corrente è `null` viene assegnato a un tipo non-nullable, ad esempio `int? x = null; int y = x ?? -1;`</span><span class="sxs-lookup"><span data-stu-id="e9c9c-127">Use the `??` operator to assign a default value that will be applied when a nullable type whose current value is `null` is assigned to a non-nullable type, for example `int? x = null; int y = x ?? -1;`</span></span>  
  
-   <span data-ttu-id="e9c9c-128">I tipi nullable nidificati non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="e9c9c-128">Nested nullable types are not allowed.</span></span> <span data-ttu-id="e9c9c-129">La riga seguente non verrà compilata: `Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="e9c9c-129">The following line will not compile: `Nullable<Nullable<int>> n;`</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e9c9c-130">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e9c9c-130">Related Sections</span></span>  
 <span data-ttu-id="e9c9c-131">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="e9c9c-131">For more information:</span></span>  
  
-   [<span data-ttu-id="e9c9c-132">Uso dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="e9c9c-132">Using Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [<span data-ttu-id="e9c9c-133">Conversione boxing dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="e9c9c-133">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [<span data-ttu-id="e9c9c-134">?? (operatore)</span><span class="sxs-lookup"><span data-stu-id="e9c9c-134">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="e9c9c-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e9c9c-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e9c9c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9c9c-136">See Also</span></span>  
 <xref:System.Nullable>  
 [<span data-ttu-id="e9c9c-137">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e9c9c-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e9c9c-138">C#</span><span class="sxs-lookup"><span data-stu-id="e9c9c-138">C#</span></span>](../../../csharp/index.md)  
 [<span data-ttu-id="e9c9c-139">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e9c9c-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e9c9c-140">Cosa significa esattamente "elevato"?</span><span class="sxs-lookup"><span data-stu-id="e9c9c-140">What exactly does 'lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
