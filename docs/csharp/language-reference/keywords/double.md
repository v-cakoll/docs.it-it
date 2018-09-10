---
title: Parola chiave double (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: 4c11065d9354d44c1da8354c6f7b4f52d7b84c10
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44190781"
---
# <a name="double-c-reference"></a><span data-ttu-id="ce9fa-102">double (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ce9fa-102">double (C# Reference)</span></span>

<span data-ttu-id="ce9fa-103">La parola chiave `double` indica un tipo semplice che archivia valori a virgola mobile a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="ce9fa-104">Nella tabella riportata di seguito sono indicati l'intervallo approssimativo e il grado di precisione del tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-104">The following table shows the precision and approximate range for the `double` type.</span></span>

|<span data-ttu-id="ce9fa-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="ce9fa-105">Type</span></span>|<span data-ttu-id="ce9fa-106">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="ce9fa-106">Approximate range</span></span>|<span data-ttu-id="ce9fa-107">Precisione</span><span class="sxs-lookup"><span data-stu-id="ce9fa-107">Precision</span></span>|<span data-ttu-id="ce9fa-108">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="ce9fa-108">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`double`|<span data-ttu-id="ce9fa-109">Compreso tra ±5,0 × 10<sup>−324</sup> e ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="ce9fa-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="ce9fa-110">15-16 cifre</span><span class="sxs-lookup"><span data-stu-id="ce9fa-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="ce9fa-111">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="ce9fa-111">Literals</span></span>

<span data-ttu-id="ce9fa-112">Per impostazione predefinita, un valore letterale numerico reale a destra dell'operatore di assegnazione viene gestito come tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="ce9fa-113">Se invece un numero intero deve essere trattato come `double`, usare il suffisso d o D, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ce9fa-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>

```csharp
double x = 3D;
```

## <a name="conversions"></a><span data-ttu-id="ce9fa-114">Conversioni</span><span class="sxs-lookup"><span data-stu-id="ce9fa-114">Conversions</span></span>

<span data-ttu-id="ce9fa-115">In una stessa espressione è possibile combinare tipi integrali numerici e tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="ce9fa-116">In questo caso i tipi integrali vengono convertiti in tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="ce9fa-117">La valutazione dell'espressione viene eseguita in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce9fa-117">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="ce9fa-118">Se uno dei tipi a virgola mobile è `double`, l'espressione restituirà un valore `double` o [bool](../../../csharp/language-reference/keywords/bool.md) nei confronti relazionali o nei confronti per l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

- <span data-ttu-id="ce9fa-119">Se nell'espressione non è presente alcun tipo `double`, l'espressione restituirà un valore [float](../../../csharp/language-reference/keywords/float.md) o [bool](../../../csharp/language-reference/keywords/bool.md) nei confronti relazionali o nei confronti per l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

 <span data-ttu-id="ce9fa-120">Un'espressione a virgola mobile può contenere gli insiemi di valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce9fa-120">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="ce9fa-121">Zero positivo e negativo.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-121">Positive and negative zero.</span></span>

- <span data-ttu-id="ce9fa-122">Infinito positivo e negativo.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-122">Positive and negative infinity.</span></span>

- <span data-ttu-id="ce9fa-123">Non un numero (NaN).</span><span class="sxs-lookup"><span data-stu-id="ce9fa-123">Not-a-Number value (NaN).</span></span>

- <span data-ttu-id="ce9fa-124">Insieme finito di valori diversi da zero.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-124">The finite set of nonzero values.</span></span>

<span data-ttu-id="ce9fa-125">Per altre informazioni su questi valori, vedere lo standard IEEE per l'aritmetica a virgola mobile binaria, disponibile nel sito Web [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="ce9fa-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) Web site.</span></span>

## <a name="example"></a><span data-ttu-id="ce9fa-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce9fa-126">Example</span></span>

<span data-ttu-id="ce9fa-127">Nell'esempio seguente, i valori [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md), e `double` vengono sommati per restituire un risultato `double`.</span><span class="sxs-lookup"><span data-stu-id="ce9fa-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>

[!code-csharp[csrefKeywordsTypes#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="ce9fa-128">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ce9fa-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ce9fa-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce9fa-129">See Also</span></span>

- [<span data-ttu-id="ce9fa-130">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="ce9fa-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ce9fa-131">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ce9fa-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ce9fa-132">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="ce9fa-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="ce9fa-133">Tabella dei valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="ce9fa-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
- [<span data-ttu-id="ce9fa-134">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="ce9fa-134">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="ce9fa-135">Tabella dei tipi a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="ce9fa-135">Floating-Point Types Table</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
- [<span data-ttu-id="ce9fa-136">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="ce9fa-136">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="ce9fa-137">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="ce9fa-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
