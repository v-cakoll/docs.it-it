---
title: double (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- double
- double_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
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
ms.openlocfilehash: d5588f8391157fb56a5e5067bb8e11f9269fe733
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="double-c-reference"></a><span data-ttu-id="3d8d2-102">double (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3d8d2-102">double (C# Reference)</span></span>
<span data-ttu-id="3d8d2-103">La parola chiave `double` indica un tipo semplice che archivia valori a virgola mobile a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="3d8d2-104">Nella tabella riportata di seguito sono indicati l'intervallo approssimativo e il grado di precisione del tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-104">The following table shows the precision and approximate range for the `double` type.</span></span>  
  
|<span data-ttu-id="3d8d2-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="3d8d2-105">Type</span></span>|<span data-ttu-id="3d8d2-106">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="3d8d2-106">Approximate range</span></span>|<span data-ttu-id="3d8d2-107">Precisione</span><span class="sxs-lookup"><span data-stu-id="3d8d2-107">Precision</span></span>|<span data-ttu-id="3d8d2-108">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3d8d2-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|<span data-ttu-id="3d8d2-109">Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="3d8d2-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="3d8d2-110">15-16 cifre</span><span class="sxs-lookup"><span data-stu-id="3d8d2-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="3d8d2-111">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="3d8d2-111">Literals</span></span>  
 <span data-ttu-id="3d8d2-112">Per impostazione predefinita, un valore letterale numerico reale a destra dell'operatore di assegnazione viene gestito come tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="3d8d2-113">Se invece un numero intero deve essere trattato come `double`, usare il suffisso d o D, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3d8d2-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>  
  
```  
double x = 3D;  
```  
  
## <a name="conversions"></a><span data-ttu-id="3d8d2-114">Conversioni</span><span class="sxs-lookup"><span data-stu-id="3d8d2-114">Conversions</span></span>  
 <span data-ttu-id="3d8d2-115">In una stessa espressione è possibile combinare tipi integrali numerici e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="3d8d2-116">In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="3d8d2-117">La valutazione dell'espressione viene eseguita in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d8d2-117">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="3d8d2-118">Se uno dei tipi a virgola mobile è `double`, l'espressione restituirà un valore `double` o [bool](../../../csharp/language-reference/keywords/bool.md) in caso di espressioni relazionali o booleane.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="3d8d2-119">Se l'espressione non contiene alcun tipo `double` restituirà un valore [float](../../../csharp/language-reference/keywords/float.md) o [bool](../../../csharp/language-reference/keywords/bool.md) in caso di espressioni relazionali o booleane.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="3d8d2-120">Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d8d2-120">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="3d8d2-121">Zero positivo e negativo.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-121">Positive and negative zero.</span></span>  
  
-   <span data-ttu-id="3d8d2-122">Infinito positivo e negativo.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-122">Positive and negative infinity.</span></span>  
  
-   <span data-ttu-id="3d8d2-123">Non un numero (NaN).</span><span class="sxs-lookup"><span data-stu-id="3d8d2-123">Not-a-Number value (NaN).</span></span>  
  
-   <span data-ttu-id="3d8d2-124">Insieme finito di valori diversi da zero.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-124">The finite set of nonzero values.</span></span>  
  
 <span data-ttu-id="3d8d2-125">Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).</span><span class="sxs-lookup"><span data-stu-id="3d8d2-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d8d2-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d8d2-126">Example</span></span>  
 <span data-ttu-id="3d8d2-127">Nell'esempio seguente, i valori [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md), e `double` vengono sommati per restituire un risultato `double`.</span><span class="sxs-lookup"><span data-stu-id="3d8d2-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>  
  
 <span data-ttu-id="3d8d2-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3d8d2-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3d8d2-129">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3d8d2-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d8d2-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d8d2-130">See Also</span></span>  
 <span data-ttu-id="3d8d2-131">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d8d2-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3d8d2-132">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d8d2-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3d8d2-133">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d8d2-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3d8d2-134">[Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md) </span><span class="sxs-lookup"><span data-stu-id="3d8d2-134">[Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) </span></span>  
 <span data-ttu-id="3d8d2-135">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="3d8d2-135">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="3d8d2-136">[Tabella dei tipi a virgola mobile](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="3d8d2-136">[Floating-Point Types Table](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span></span>  
 <span data-ttu-id="3d8d2-137">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="3d8d2-137">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="3d8d2-138">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="3d8d2-138">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

