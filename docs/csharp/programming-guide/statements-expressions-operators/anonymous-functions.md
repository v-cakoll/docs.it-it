---
title: Funzioni anonime (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: e368105c090f95435a4529470bdf1b41346d039c
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936750"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="de5d4-102">Funzioni anonime (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="de5d4-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="de5d4-103">Una funzione anonima è un'istruzione o un'espressione "inline" che può essere usata in tutti i casi in cui è previsto un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="de5d4-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="de5d4-104">Consente di inizializzare un delegato denominato o passarlo al posto di un tipo delegato denominato come parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="de5d4-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="de5d4-105">Ci sono due tipi di funzioni anonime, illustrati singolarmente negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="de5d4-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
-   <span data-ttu-id="de5d4-106">[Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="de5d4-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
-   [<span data-ttu-id="de5d4-107">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="de5d4-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="de5d4-108">Le espressioni lambda possono essere associate ad alberi di espressioni e a delegati.</span><span class="sxs-lookup"><span data-stu-id="de5d4-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="de5d4-109">Evoluzione dei delegati in C#</span><span class="sxs-lookup"><span data-stu-id="de5d4-109">The Evolution of Delegates in C#</span></span>  
 <span data-ttu-id="de5d4-110">In C# 1.0 è stata creata un'istanza di un delegato inizializzandola in modo esplicito con un metodo che è stato definito altrove nel codice.</span><span class="sxs-lookup"><span data-stu-id="de5d4-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="de5d4-111">C# 2.0 ha introdotto il concetto di metodi anonimi come modo per scrivere blocchi di istruzioni inline senza nome che possono essere eseguiti in una chiamata a delegati.</span><span class="sxs-lookup"><span data-stu-id="de5d4-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="de5d4-112">C# 3.0 ha introdotto le espressioni lambda, che sono concettualmente analoghe ai metodi anonimi, ma più espressive e concise.</span><span class="sxs-lookup"><span data-stu-id="de5d4-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="de5d4-113">Queste due funzionalità sono noti collettivamente come *funzioni anonime*.</span><span class="sxs-lookup"><span data-stu-id="de5d4-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="de5d4-114">In generale, le applicazioni destinate alla versione 3.5 o successiva di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] devono usare le espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="de5d4-114">In general, applications that target version 3.5 and later of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] should use lambda expressions.</span></span>  
  
 <span data-ttu-id="de5d4-115">L'esempio seguente illustra l'evoluzione della creazione di delegati da C# 1.0 a C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="de5d4-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="de5d4-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="de5d4-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de5d4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de5d4-117">See also</span></span>

[<span data-ttu-id="de5d4-118">Istruzioni, espressioni e operatori</span><span class="sxs-lookup"><span data-stu-id="de5d4-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
[<span data-ttu-id="de5d4-119">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="de5d4-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
[<span data-ttu-id="de5d4-120">Delegati</span><span class="sxs-lookup"><span data-stu-id="de5d4-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
[<span data-ttu-id="de5d4-121">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="de5d4-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)  
