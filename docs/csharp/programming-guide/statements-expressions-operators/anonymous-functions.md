---
title: Funzioni anonime - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 4d266584e1867a512e4b61e8839fe948aafb007f
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363922"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="2b629-102">Funzioni anonime (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2b629-102">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="2b629-103">Una funzione anonima è un'istruzione o un'espressione "inline" che può essere usata in tutti i casi in cui è previsto un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="2b629-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="2b629-104">Consente di inizializzare un delegato denominato o passarlo al posto di un tipo delegato denominato come parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="2b629-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="2b629-105">Per creare una funzione anonima, è possibile usare un'[espressione lambda](lambda-expressions.md) o un [metodo anonimo](../../language-reference/operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2b629-105">You can use a [lambda expression](lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="2b629-106">È consigliabile usare le espressioni lambda perché forniscono un modo più conciso ed espressivo per scrivere codice inline.</span><span class="sxs-lookup"><span data-stu-id="2b629-106">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="2b629-107">A differenza dei metodi anonimi, è possibile convertire alcuni tipi di espressioni lambda nei tipi di albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="2b629-107">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="2b629-108">Evoluzione dei delegati in C\#</span><span class="sxs-lookup"><span data-stu-id="2b629-108">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="2b629-109">In C# 1.0 è stata creata un'istanza di un delegato inizializzandola in modo esplicito con un metodo che è stato definito altrove nel codice.</span><span class="sxs-lookup"><span data-stu-id="2b629-109">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="2b629-110">C# 2.0 ha introdotto il concetto di metodi anonimi come modo per scrivere blocchi di istruzioni inline senza nome che possono essere eseguiti in una chiamata a delegati.</span><span class="sxs-lookup"><span data-stu-id="2b629-110">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="2b629-111">C# 3.0 ha introdotto le espressioni lambda, che sono concettualmente analoghe ai metodi anonimi, ma più espressive e concise.</span><span class="sxs-lookup"><span data-stu-id="2b629-111">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="2b629-112">Queste due funzionalità sono noti collettivamente come *funzioni anonime*.</span><span class="sxs-lookup"><span data-stu-id="2b629-112">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="2b629-113">In generale, le applicazioni destinate alla versione 3.5 o successiva di .NET Framework devono usare le espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="2b629-113">In general, applications that target version 3.5 and later of the .NET Framework should use lambda expressions.</span></span>  
  
 <span data-ttu-id="2b629-114">L'esempio seguente illustra l'evoluzione della creazione di delegati da C# 1.0 a C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="2b629-114">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="2b629-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2b629-115">C# language specification</span></span>

<span data-ttu-id="2b629-116">Per altre informazioni, vedere la sezione [Espressioni di funzioni anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="2b629-116">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2b629-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b629-117">See also</span></span>

- [<span data-ttu-id="2b629-118">Istruzioni, espressioni e operatori</span><span class="sxs-lookup"><span data-stu-id="2b629-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [<span data-ttu-id="2b629-119">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="2b629-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="2b629-120">Delegati</span><span class="sxs-lookup"><span data-stu-id="2b629-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="2b629-121">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="2b629-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
