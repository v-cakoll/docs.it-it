---
title: explicit (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords: explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eab79d3ac48192f3c176ed44685ab58e50fc89be
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2017
---
# <a name="explicit-c-reference"></a><span data-ttu-id="2366e-102">explicit (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2366e-102">explicit (C# Reference)</span></span>
<span data-ttu-id="2366e-103">La parola chiave `explicit` dichiara un operatore di conversione di tipo definito dall'utente che deve essere chiamato con un cast.</span><span class="sxs-lookup"><span data-stu-id="2366e-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="2366e-104">Questo operatore, ad esempio, esegue la conversione da una classe chiamata Fahrenheit a una classe chiamata Celsius:</span><span class="sxs-lookup"><span data-stu-id="2366e-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 <span data-ttu-id="2366e-105">L'operatore di conversione può essere chiamato come segue:</span><span class="sxs-lookup"><span data-stu-id="2366e-105">This conversion operator can be invoked like this:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 <span data-ttu-id="2366e-106">L'operatore di conversione converte da un tipo di origine a un tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2366e-106">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="2366e-107">Il tipo di origine fornisce l'operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="2366e-107">The source type provides the conversion operator.</span></span> <span data-ttu-id="2366e-108">A differenza degli operatori di conversione impliciti, gli operatori di conversione espliciti devono essere chiamati tramite un cast.</span><span class="sxs-lookup"><span data-stu-id="2366e-108">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="2366e-109">Se un'operazione di conversione può generare eccezioni o perdita di informazioni, è necessario contrassegnarla come `explicit`.</span><span class="sxs-lookup"><span data-stu-id="2366e-109">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="2366e-110">In questo modo si impedisce al compilatore di chiamare automaticamente l'operazione di conversione, con conseguenze imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="2366e-110">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="2366e-111">Se si omette il cast, viene generato l'errore in fase di compilazione CS0266.</span><span class="sxs-lookup"><span data-stu-id="2366e-111">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="2366e-112">Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="2366e-112">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2366e-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="2366e-113">Example</span></span>  
 <span data-ttu-id="2366e-114">Nell'esempio seguente vengono fornite una classe `Fahrenheit` e una classe `Celsius`, ognuna delle quali fornisce un operatore di conversione esplicito all'altra classe.</span><span class="sxs-lookup"><span data-stu-id="2366e-114">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="2366e-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="2366e-115">Example</span></span>  
 <span data-ttu-id="2366e-116">Nell'esempio seguente viene definito la struct `Digit`, che rappresenta una singola cifra decimale.</span><span class="sxs-lookup"><span data-stu-id="2366e-116">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="2366e-117">Viene definito un operatore per le conversioni da `byte` a `Digit`, tuttavia, poiché non è possibile convertire tutti i byte in `Digit`, la conversione è esplicita.</span><span class="sxs-lookup"><span data-stu-id="2366e-117">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="2366e-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2366e-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2366e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2366e-119">See Also</span></span>  
 [<span data-ttu-id="2366e-120">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2366e-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2366e-121">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2366e-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2366e-122">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="2366e-122">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="2366e-123">implicit</span><span class="sxs-lookup"><span data-stu-id="2366e-123">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="2366e-124">operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2366e-124">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="2366e-125">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="2366e-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 [<span data-ttu-id="2366e-126">Conversioni esplicite concatenate definite dall'utente in C#</span><span class="sxs-lookup"><span data-stu-id="2366e-126">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
