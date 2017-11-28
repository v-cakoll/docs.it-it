---
title: float (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 846f132812fe90a285c81a020d440fc846f88b5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="float-c-reference"></a><span data-ttu-id="78c3f-102">float (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="78c3f-102">float (C# Reference)</span></span>
<span data-ttu-id="78c3f-103">La parola chiave `float` indica un tipo semplice che archivia valori a virgola mobile a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="78c3f-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="78c3f-104">Nella tabella riportata di seguito sono indicati l'intervallo approssimativo e il grado di precisione del tipo `float`.</span><span class="sxs-lookup"><span data-stu-id="78c3f-104">The following table shows the precision and approximate range for the `float` type.</span></span>  
  
|<span data-ttu-id="78c3f-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="78c3f-105">Type</span></span>|<span data-ttu-id="78c3f-106">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="78c3f-106">Approximate range</span></span>|<span data-ttu-id="78c3f-107">Precisione</span><span class="sxs-lookup"><span data-stu-id="78c3f-107">Precision</span></span>|<span data-ttu-id="78c3f-108">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="78c3f-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="78c3f-109">da -3,4 × 10<sup>38</sup>a +3,4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="78c3f-109">-3.4 × 10<sup>38</sup>to +3.4 × 10<sup>38</sup></span></span>|<span data-ttu-id="78c3f-110">7 cifre</span><span class="sxs-lookup"><span data-stu-id="78c3f-110">7 digits</span></span>|<xref:System.Single?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="78c3f-111">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="78c3f-111">Literals</span></span>  
 <span data-ttu-id="78c3f-112">Per impostazione predefinita, un valore letterale numerico reale a destra dell'operatore di assegnazione viene gestito come tipo [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="78c3f-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="78c3f-113">Per inizializzare una variabile float è quindi necessario usare il suffisso `f` o `F`, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="78c3f-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>  
  
```csharp
float x = 3.5F;  
```
  
 <span data-ttu-id="78c3f-114">Se nella dichiarazione precedente non si usa il suffisso, verrà generato un errore di compilazione poiché si sta tentando di archiviare un valore [double](double.md) in una variabile `float`.</span><span class="sxs-lookup"><span data-stu-id="78c3f-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="78c3f-115">Conversioni</span><span class="sxs-lookup"><span data-stu-id="78c3f-115">Conversions</span></span>  
 <span data-ttu-id="78c3f-116">In una stessa espressione è possibile combinare tipi integrali numerici e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="78c3f-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="78c3f-117">In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="78c3f-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="78c3f-118">La valutazione dell'espressione viene eseguita in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="78c3f-118">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="78c3f-119">Se uno dei tipi a virgola mobile è [double](double.md), l'espressione restituirà un valore [double](double.md) o [bool](bool.md) in caso di espressioni relazionali o booleane.</span><span class="sxs-lookup"><span data-stu-id="78c3f-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md) or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="78c3f-120">Se l'espressione non contiene alcun tipo [double](double.md), restituirà un valore `float` o [bool](bool.md) in caso di espressioni relazionali o booleane.</span><span class="sxs-lookup"><span data-stu-id="78c3f-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float` or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="78c3f-121">Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="78c3f-121">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="78c3f-122">Zero positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="78c3f-122">Positive and negative zero</span></span>  
  
-   <span data-ttu-id="78c3f-123">Infinito positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="78c3f-123">Positive and negative infinity</span></span>  
  
-   <span data-ttu-id="78c3f-124">Non un numero</span><span class="sxs-lookup"><span data-stu-id="78c3f-124">Not-a-Number value (NaN)</span></span>  
  
-   <span data-ttu-id="78c3f-125">Insieme finito di valori diversi da zero</span><span class="sxs-lookup"><span data-stu-id="78c3f-125">The finite set of nonzero values</span></span>  
  
 <span data-ttu-id="78c3f-126">Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](http://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="78c3f-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://www.ieee.org) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78c3f-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="78c3f-127">Example</span></span>  
 <span data-ttu-id="78c3f-128">Nell'esempio seguente [int](int.md), [short](short.md) e `float` sono inclusi in un'espressione matematica che dà come risultato un valore `float`.</span><span class="sxs-lookup"><span data-stu-id="78c3f-128">In the following example, an [int](int.md), a [short](short.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="78c3f-129">Tenere presente che `float` è un alias per il tipo <xref:System.Single?displayProperty=nameWithType>. Si noti che nell'istruzione non sono inclusi valori [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="78c3f-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=nameWithType> type.) Notice that there is no [double](double.md) in the expression.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="78c3f-130">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="78c3f-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="78c3f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78c3f-131">See Also</span></span>  
 <xref:System.Single>  
 [<span data-ttu-id="78c3f-132">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="78c3f-132">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="78c3f-133">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="78c3f-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="78c3f-134">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="78c3f-134">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [<span data-ttu-id="78c3f-135">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="78c3f-135">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="78c3f-136">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="78c3f-136">Integral Types Table</span></span>](integral-types-table.md)  
 [<span data-ttu-id="78c3f-137">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="78c3f-137">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="78c3f-138">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="78c3f-138">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="78c3f-139">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="78c3f-139">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
