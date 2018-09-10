---
title: Parola chiave explicit (Riferimenti per C#)
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: 3567a2c5aa549aa3141ed59c3e93e7b07975da70
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43463143"
---
# <a name="explicit-c-reference"></a><span data-ttu-id="e2694-102">explicit (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e2694-102">explicit (C# Reference)</span></span>

<span data-ttu-id="e2694-103">La parola chiave `explicit` dichiara un operatore di conversione di tipo definito dall'utente che deve essere chiamato con un cast.</span><span class="sxs-lookup"><span data-stu-id="e2694-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span>

<span data-ttu-id="e2694-104">L'esempio seguente definisce l'operatore che converte una classe `Fahrenheit` in una classe `Celsius`.</span><span class="sxs-lookup"><span data-stu-id="e2694-104">The following example defines the operator that converts from a `Fahrenheit` class to a `Celsius` class.</span></span> <span data-ttu-id="e2694-105">L'operatore deve essere definito all'interno una classe `Fahrenheit` o `Celsius`:</span><span class="sxs-lookup"><span data-stu-id="e2694-105">The operator must be defined either inside a `Fahrenheit` class or a `Celsius` class:</span></span>

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

<span data-ttu-id="e2694-106">L'operatore di conversione definito viene richiamato con un cast, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e2694-106">You invoke the defined conversion operator with a cast, as the following example shows:</span></span>

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

<span data-ttu-id="e2694-107">L'operatore di conversione converte da un tipo di origine a un tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e2694-107">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="e2694-108">Il tipo di origine fornisce l'operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="e2694-108">The source type provides the conversion operator.</span></span> <span data-ttu-id="e2694-109">A differenza degli operatori di conversione impliciti, gli operatori di conversione espliciti devono essere chiamati tramite un cast.</span><span class="sxs-lookup"><span data-stu-id="e2694-109">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="e2694-110">Se un'operazione di conversione può generare eccezioni o perdita di informazioni, è necessario contrassegnarla come `explicit`.</span><span class="sxs-lookup"><span data-stu-id="e2694-110">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="e2694-111">In questo modo si impedisce al compilatore di chiamare automaticamente l'operazione di conversione, con conseguenze imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="e2694-111">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>

<span data-ttu-id="e2694-112">Se si omette il cast, viene generato l'errore in fase di compilazione CS0266.</span><span class="sxs-lookup"><span data-stu-id="e2694-112">Omitting the cast results in compile-time error CS0266.</span></span>

<span data-ttu-id="e2694-113">Per altre informazioni, vedere [Uso degli operatori di conversione](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e2694-113">For more information, see [Using Conversion Operators](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="example"></a><span data-ttu-id="e2694-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2694-114">Example</span></span>

<span data-ttu-id="e2694-115">Nell'esempio seguente vengono fornite una classe `Fahrenheit` e una classe `Celsius`, ognuna delle quali fornisce un operatore di conversione esplicito all'altra classe.</span><span class="sxs-lookup"><span data-stu-id="e2694-115">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a><span data-ttu-id="e2694-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2694-116">Example</span></span>

<span data-ttu-id="e2694-117">Nell'esempio seguente viene definito la struct `Digit`, che rappresenta una singola cifra decimale.</span><span class="sxs-lookup"><span data-stu-id="e2694-117">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="e2694-118">Viene definito un operatore per le conversioni da `byte` a `Digit`, tuttavia, poiché non è possibile convertire tutti i byte in `Digit`, la conversione è esplicita.</span><span class="sxs-lookup"><span data-stu-id="e2694-118">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="e2694-119">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e2694-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e2694-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2694-120">See also</span></span>

- [<span data-ttu-id="e2694-121">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e2694-121">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="e2694-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e2694-122">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="e2694-123">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e2694-123">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="e2694-124">implicit</span><span class="sxs-lookup"><span data-stu-id="e2694-124">implicit</span></span>](implicit.md)  
- [<span data-ttu-id="e2694-125">operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e2694-125">operator (C# Reference)</span></span>](operator.md)  
- [<span data-ttu-id="e2694-126">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="e2694-126">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
- [<span data-ttu-id="e2694-127">Conversioni esplicite concatenate definite dall'utente in C#</span><span class="sxs-lookup"><span data-stu-id="e2694-127">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)  
