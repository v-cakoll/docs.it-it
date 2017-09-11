---
title: explicit (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
dev_langs:
- CSharp
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
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
ms.openlocfilehash: f11a930f0be5d504c92271b66009613de5d68579
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-c-reference"></a><span data-ttu-id="84869-102">explicit (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="84869-102">explicit (C# Reference)</span></span>
<span data-ttu-id="84869-103">La parola chiave `explicit` dichiara un operatore di conversione di tipo definito dall'utente che deve essere chiamato con un cast.</span><span class="sxs-lookup"><span data-stu-id="84869-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="84869-104">Questo operatore, ad esempio, esegue la conversione da una classe chiamata Fahrenheit a una classe chiamata Celsius:</span><span class="sxs-lookup"><span data-stu-id="84869-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 <span data-ttu-id="84869-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="84869-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span></span>  
  
 <span data-ttu-id="84869-106">L'operatore di conversione può essere chiamato come segue:</span><span class="sxs-lookup"><span data-stu-id="84869-106">This conversion operator can be invoked like this:</span></span>  
  
 <span data-ttu-id="84869-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="84869-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span></span>  
  
 <span data-ttu-id="84869-108">L'operatore di conversione converte da un tipo di origine a un tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="84869-108">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="84869-109">Il tipo di origine fornisce l'operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="84869-109">The source type provides the conversion operator.</span></span> <span data-ttu-id="84869-110">A differenza degli operatori di conversione impliciti, gli operatori di conversione espliciti devono essere chiamati tramite un cast.</span><span class="sxs-lookup"><span data-stu-id="84869-110">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="84869-111">Se un'operazione di conversione può generare eccezioni o perdita di informazioni, è necessario contrassegnarla come `explicit`.</span><span class="sxs-lookup"><span data-stu-id="84869-111">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="84869-112">In questo modo si impedisce al compilatore di chiamare automaticamente l'operazione di conversione, con conseguenze imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="84869-112">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="84869-113">Se si omette il cast, viene generato l'errore in fase di compilazione CS0266.</span><span class="sxs-lookup"><span data-stu-id="84869-113">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="84869-114">Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="84869-114">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84869-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="84869-115">Example</span></span>  
 <span data-ttu-id="84869-116">Nell'esempio seguente vengono fornite una classe `Fahrenheit` e una classe `Celsius`, ognuna delle quali fornisce un operatore di conversione esplicito all'altra classe.</span><span class="sxs-lookup"><span data-stu-id="84869-116">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 <span data-ttu-id="84869-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="84869-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="84869-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="84869-118">Example</span></span>  
 <span data-ttu-id="84869-119">Nell'esempio seguente viene definito la struct `Digit`, che rappresenta una singola cifra decimale.</span><span class="sxs-lookup"><span data-stu-id="84869-119">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="84869-120">Viene definito un operatore per le conversioni da `byte` a `Digit`, tuttavia, poiché non è possibile convertire tutti i byte in `Digit`, la conversione è esplicita.</span><span class="sxs-lookup"><span data-stu-id="84869-120">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 <span data-ttu-id="84869-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="84869-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="84869-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="84869-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84869-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84869-123">See Also</span></span>  
 <span data-ttu-id="84869-124">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="84869-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="84869-125">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="84869-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="84869-126">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="84869-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="84869-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="84869-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="84869-128">[Operatore (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="84869-128">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 <span data-ttu-id="84869-129">[Procedura: Implementare conversioni tra struct definite dall'utente](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span><span class="sxs-lookup"><span data-stu-id="84869-129">[How to: Implement User-Defined Conversions Between Structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span></span>  
 [<span data-ttu-id="84869-130">Conversioni esplicite concatenate definite dall'utente in C#</span><span class="sxs-lookup"><span data-stu-id="84869-130">Chained user-defined explicit conversions in C#</span></span>](http://go.microsoft.com/fwlink/?LinkId=112384)

