---
title: Tipi nullable (Guida per programmatori C#)
ms.date: 2017-05-15
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
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
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 56e22638457017688ff380f6683b463b47c53a17
ms.contentlocale: it-it
ms.lasthandoff: 09/02/2017

---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="6cfd6-102">Tipi nullable (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6cfd6-102">Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="6cfd6-103">I tipi nullable sono istanze dello struct <xref:System.Nullable%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-103">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=fullName> struct.</span></span> <span data-ttu-id="6cfd6-104">Un tipo nullable può rappresentare l'intervallo di valori corretto del tipo valore sottostante, più un valore `null` aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-104">A nullable type can represent the correct range of values for its underlying value type, plus an additional `null` value.</span></span> <span data-ttu-id="6cfd6-105">Ad esempio, a un tipo `Nullable<Int32>`, detto anche "Nullable of Int32", può essere assegnato qualsiasi valore compreso tra -2147483648 e 2147483647. In alternativa, può essere assegnato il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-105">For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from -2147483648 to 2147483647, or it can be assigned the `null` value.</span></span> <span data-ttu-id="6cfd6-106">A un tipo `Nullable<bool>` può essere assegnato il valore [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) o [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="6cfd6-106">A `Nullable<bool>` can be assigned the values [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), or [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="6cfd6-107">La possibilità di assegnare il valore `null` a tipi numerici e booleani è particolarmente utile quando si gestiscono database e altri tipi di dati contenenti elementi a cui non è possibile assegnare un valore.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-107">The ability to assign `null` to numeric and Boolean types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value.</span></span> <span data-ttu-id="6cfd6-108">Ad esempio, un campo booleano di un database può archiviare i valori `true` o `false` oppure può essere non definito.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-108">For example, a Boolean field in a database can store the values `true` or `false`, or it may be undefined.</span></span> 
  
<span data-ttu-id="6cfd6-109">[!code-cs[tipi nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6cfd6-109">[!code-cs[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]</span></span>  
  
<span data-ttu-id="6cfd6-110">Per altri esempi, vedere [Uso dei tipi nullable](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span><span class="sxs-lookup"><span data-stu-id="6cfd6-110">For more examples, see [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span></span>  
  
## <a name="nullable-types-overview"></a><span data-ttu-id="6cfd6-111">Panoramica dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="6cfd6-111">Nullable Types Overview</span></span>  
 <span data-ttu-id="6cfd6-112">I tipi nullable hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cfd6-112">Nullable types have the following characteristics:</span></span>  
  
-   <span data-ttu-id="6cfd6-113">I tipi nullable rappresentano variabili di tipo valore a cui può essere assegnato il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-113">Nullable types represent value-type variables that can be assigned the value of `null`.</span></span> <span data-ttu-id="6cfd6-114">Non è possibile creare un tipi nullable sulla base di un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-114">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="6cfd6-115">I tipi riferimento supportano già il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-115">(Reference types already support the `null` value.)</span></span>  
  
-   <span data-ttu-id="6cfd6-116">La sintassi `T?` è l'abbreviazione di <xref:System.Nullable%601>, dove `T` è un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-116">The syntax `T?` is shorthand for <xref:System.Nullable%601>, where `T` is a value type.</span></span> <span data-ttu-id="6cfd6-117">Le due forme sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-117">The two forms are interchangeable.</span></span>  
  
-   <span data-ttu-id="6cfd6-118">Per assegnare un valore a un tipo nullable è possibile procedere come per un comune tipo valore, ad esempio `int? x = 10;` o `double? d = 4.108`.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-118">Assign a value to a nullable type just as you would for an ordinary value type, for example `int? x = 10;` or `double? d = 4.108`.</span></span> <span data-ttu-id="6cfd6-119">A un tipo nullable può essere assegnato anche il valore `null`: `int? x = null.`</span><span class="sxs-lookup"><span data-stu-id="6cfd6-119">A nullable type can also be assigned the value `null`: `int? x = null.`</span></span>  
  
-   <span data-ttu-id="6cfd6-120">Usare il metodo <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> per restituire il valore assegnato oppure il valore predefinito del tipo sottostante se il valore è `null`, ad esempio `int j = x.GetValueOrDefault();`</span><span class="sxs-lookup"><span data-stu-id="6cfd6-120">Use the <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> method to return either the assigned value, or the default value for the underlying type if the value is `null`, for example `int j = x.GetValueOrDefault();`</span></span>  
  
-   <span data-ttu-id="6cfd6-121">Usare le proprietà di sola lettura <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> per verificare la presenza di valori null e recuperare il valore, come illustrato nell'esempio seguente: `if(x.HasValue) j = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="6cfd6-121">Use the <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> read-only properties to test for null and retrieve the value, as shown in the following example: `if(x.HasValue) j = x.Value;`</span></span>  
  
    -   <span data-ttu-id="6cfd6-122">La proprietà `HasValue` restituisce `true` se la variabile contiene un valore o `false` se è `null`.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-122">The `HasValue` property returns `true` if the variable contains a value, or `false` if it is `null`.</span></span>  
  
    -   <span data-ttu-id="6cfd6-123">La proprietà `Value` restituisce un valore se ne è stato assegnato uno.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-123">The `Value` property returns a value if one is assigned.</span></span> <span data-ttu-id="6cfd6-124">In caso contrario viene generata un'eccezione <xref:System.InvalidOperationException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-124">Otherwise, a <xref:System.InvalidOperationException?displayProperty=fullName> is thrown.</span></span>  
  
    -   <span data-ttu-id="6cfd6-125">Il valore predefinito per la proprietà `HasValue` è `false`.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-125">The default value for `HasValue` is `false`.</span></span> <span data-ttu-id="6cfd6-126">La proprietà `Value` non ha alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-126">The `Value` property has no default value.</span></span>  
  
    -   <span data-ttu-id="6cfd6-127">Con un tipo nullable è anche possibile usare gli operatori `==` e `!=`, come mostrato nell'esempio seguente: `if (x != null) y = x;`</span><span class="sxs-lookup"><span data-stu-id="6cfd6-127">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x;`</span></span>  
  
-   <span data-ttu-id="6cfd6-128">Usare l'operatore `??` per assegnare un valore predefinito che verrà applicato quando un tipo nullable il cui valore corrente è `null` viene assegnato a un tipo non-nullable, ad esempio `int? x = null; int y = x ?? -1;`</span><span class="sxs-lookup"><span data-stu-id="6cfd6-128">Use the `??` operator to assign a default value that will be applied when a nullable type whose current value is `null` is assigned to a non-nullable type, for example `int? x = null; int y = x ?? -1;`</span></span>  
  
-   <span data-ttu-id="6cfd6-129">I tipi nullable nidificati non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-129">Nested nullable types are not allowed.</span></span> <span data-ttu-id="6cfd6-130">La riga seguente non verrà compilata: `Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="6cfd6-130">The following line will not compile: `Nullable<Nullable<int>> n;`</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6cfd6-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6cfd6-131">Related Sections</span></span>  
 <span data-ttu-id="6cfd6-132">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="6cfd6-132">For more information:</span></span>  
  
-   [<span data-ttu-id="6cfd6-133">Uso dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="6cfd6-133">Using Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [<span data-ttu-id="6cfd6-134">Conversione boxing dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="6cfd6-134">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [<span data-ttu-id="6cfd6-135">?? (operatore)</span><span class="sxs-lookup"><span data-stu-id="6cfd6-135">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="6cfd6-136">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6cfd6-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6cfd6-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cfd6-137">See Also</span></span>  
 <span data-ttu-id="6cfd6-138"><xref:System.Nullable></span><span class="sxs-lookup"><span data-stu-id="6cfd6-138"><xref:System.Nullable></span></span>   
 <span data-ttu-id="6cfd6-139">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6cfd6-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6cfd6-140">[C#](../../../csharp/index.md) </span><span class="sxs-lookup"><span data-stu-id="6cfd6-140">[C#](../../../csharp/index.md) </span></span>  
 <span data-ttu-id="6cfd6-141">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6cfd6-141">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="6cfd6-142">Cosa significa esattamente "elevato"?</span><span class="sxs-lookup"><span data-stu-id="6cfd6-142">What exactly does 'lifted' mean?</span></span>](http://go.microsoft.com/fwlink/?LinkId=112382)

