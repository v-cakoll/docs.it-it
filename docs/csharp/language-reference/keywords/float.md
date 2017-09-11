---
title: float (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
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
ms.openlocfilehash: 2f1fb02f84de504112eee826dbee1275fa3ccb7a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="float-c-reference"></a><span data-ttu-id="111f4-102">float (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="111f4-102">float (C# Reference)</span></span>
<span data-ttu-id="111f4-103">La parola chiave `float` indica un tipo semplice che archivia valori a virgola mobile a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="111f4-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="111f4-104">Nella tabella riportata di seguito sono indicati l'intervallo approssimativo e il grado di precisione del tipo `float`.</span><span class="sxs-lookup"><span data-stu-id="111f4-104">The following table shows the precision and approximate range for the `float` type.</span></span>  
  
|<span data-ttu-id="111f4-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="111f4-105">Type</span></span>|<span data-ttu-id="111f4-106">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="111f4-106">Approximate range</span></span>|<span data-ttu-id="111f4-107">Precisione</span><span class="sxs-lookup"><span data-stu-id="111f4-107">Precision</span></span>|<span data-ttu-id="111f4-108">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="111f4-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="111f4-109">da -3,4 × 10<sup>38</sup>a +3,4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="111f4-109">-3.4 × 10<sup>38</sup>to +3.4 × 10<sup>38</sup></span></span>|<span data-ttu-id="111f4-110">7 cifre</span><span class="sxs-lookup"><span data-stu-id="111f4-110">7 digits</span></span>|<xref:System.Single?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="111f4-111">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="111f4-111">Literals</span></span>  
 <span data-ttu-id="111f4-112">Per impostazione predefinita, un valore letterale numerico reale a destra dell'operatore di assegnazione viene gestito come tipo [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="111f4-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="111f4-113">Per inizializzare una variabile float è quindi necessario usare il suffisso `f` o `F`, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="111f4-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>  
  
```csharp
float x = 3.5F;  
```
  
 <span data-ttu-id="111f4-114">Se nella dichiarazione precedente non si usa il suffisso, verrà generato un errore di compilazione poiché si sta tentando di archiviare un valore [double](double.md) in una variabile `float`.</span><span class="sxs-lookup"><span data-stu-id="111f4-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="111f4-115">Conversioni</span><span class="sxs-lookup"><span data-stu-id="111f4-115">Conversions</span></span>  
 <span data-ttu-id="111f4-116">In una stessa espressione è possibile combinare tipi integrali numerici e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="111f4-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="111f4-117">In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="111f4-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="111f4-118">La valutazione dell'espressione viene eseguita in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="111f4-118">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="111f4-119">Se uno dei tipi a virgola mobile è [double](double.md), l'espressione restituirà un valore [double](double.md) o [bool](bool.md) in caso di espressioni relazionali o booleane.</span><span class="sxs-lookup"><span data-stu-id="111f4-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md) or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="111f4-120">Se l'espressione non contiene alcun tipo [double](double.md), restituirà un valore `float` o [bool](bool.md) in caso di espressioni relazionali o booleane.</span><span class="sxs-lookup"><span data-stu-id="111f4-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float` or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="111f4-121">Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="111f4-121">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="111f4-122">Zero positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="111f4-122">Positive and negative zero</span></span>  
  
-   <span data-ttu-id="111f4-123">Infinito positivo e negativo</span><span class="sxs-lookup"><span data-stu-id="111f4-123">Positive and negative infinity</span></span>  
  
-   <span data-ttu-id="111f4-124">Non un numero</span><span class="sxs-lookup"><span data-stu-id="111f4-124">Not-a-Number value (NaN)</span></span>  
  
-   <span data-ttu-id="111f4-125">Insieme finito di valori diversi da zero</span><span class="sxs-lookup"><span data-stu-id="111f4-125">The finite set of nonzero values</span></span>  
  
 <span data-ttu-id="111f4-126">Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).</span><span class="sxs-lookup"><span data-stu-id="111f4-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="111f4-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="111f4-127">Example</span></span>  
 <span data-ttu-id="111f4-128">Nell'esempio seguente [int](int.md), [short](short.md) e `float` sono inclusi in un'espressione matematica che dà come risultato un valore `float`.</span><span class="sxs-lookup"><span data-stu-id="111f4-128">In the following example, an [int](int.md), a [short](short.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="111f4-129">Tenere presente che `float` è un alias per il tipo <xref:System.Single?displayProperty=fullName>. Si noti che nell'istruzione non sono inclusi valori [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="111f4-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=fullName> type.) Notice that there is no [double](double.md) in the expression.</span></span>  
  
 <span data-ttu-id="111f4-130">[!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="111f4-130">[!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="111f4-131">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="111f4-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="111f4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="111f4-132">See Also</span></span>  
 <span data-ttu-id="111f4-133"><xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="111f4-133"><xref:System.Single></span></span>   
 <span data-ttu-id="111f4-134">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="111f4-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="111f4-135">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="111f4-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="111f4-136">[Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="111f4-136">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 <span data-ttu-id="111f4-137">[Parole chiave di C#](index.md) </span><span class="sxs-lookup"><span data-stu-id="111f4-137">[C# Keywords](index.md) </span></span>  
 <span data-ttu-id="111f4-138">[Tabella dei tipi integrali](integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="111f4-138">[Integral Types Table](integral-types-table.md) </span></span>  
 <span data-ttu-id="111f4-139">[Tabella dei tipi predefiniti](built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="111f4-139">[Built-In Types Table](built-in-types-table.md) </span></span>  
 <span data-ttu-id="111f4-140">[Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="111f4-140">[Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="111f4-141">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="111f4-141">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)

