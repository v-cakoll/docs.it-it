---
title: Funzioni anonime (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: 14
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
ms.openlocfilehash: 9f0105ad5ee5a97243e9aeda42c9b1842ec15d0e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="7ef03-102">Funzioni anonime (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7ef03-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="7ef03-103">Una funzione anonima è un'istruzione o un'espressione "inline" che può essere usata in tutti i casi in cui è previsto un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="7ef03-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="7ef03-104">Consente di inizializzare un delegato denominato o passarlo al posto di un tipo delegato denominato come parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="7ef03-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="7ef03-105">Ci sono due tipi di funzioni anonime, illustrati singolarmente negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ef03-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
-   <span data-ttu-id="7ef03-106">[Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="7ef03-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
-   [<span data-ttu-id="7ef03-107">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="7ef03-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="7ef03-108">Le espressioni lambda possono essere associate ad alberi di espressioni e a delegati.</span><span class="sxs-lookup"><span data-stu-id="7ef03-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="7ef03-109">Evoluzione dei delegati in C#</span><span class="sxs-lookup"><span data-stu-id="7ef03-109">The Evolution of Delegates in C#</span></span>  
 <span data-ttu-id="7ef03-110">In C# 1.0 è stata creata un'istanza di un delegato inizializzandola in modo esplicito con un metodo che è stato definito altrove nel codice.</span><span class="sxs-lookup"><span data-stu-id="7ef03-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="7ef03-111">C# 2.0 ha introdotto il concetto di metodi anonimi come modo per scrivere blocchi di istruzioni inline senza nome che possono essere eseguiti in una chiamata a delegati.</span><span class="sxs-lookup"><span data-stu-id="7ef03-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="7ef03-112">C# 3.0 ha introdotto le espressioni lambda, che sono concettualmente analoghe ai metodi anonimi, ma più espressive e concise.</span><span class="sxs-lookup"><span data-stu-id="7ef03-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="7ef03-113">Queste due funzionalità sono noti collettivamente come *funzioni anonime*.</span><span class="sxs-lookup"><span data-stu-id="7ef03-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="7ef03-114">In generale, le applicazioni destinate alla versione 3.5 o successiva di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] devono usare le espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="7ef03-114">In general, applications that target version 3.5 and later of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] should use lambda expressions.</span></span>  
  
 <span data-ttu-id="7ef03-115">L'esempio seguente illustra l'evoluzione della creazione di delegati da C# 1.0 a C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="7ef03-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 <span data-ttu-id="7ef03-116">[!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7ef03-116">[!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7ef03-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7ef03-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7ef03-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ef03-118">See Also</span></span>  
 <span data-ttu-id="7ef03-119">[Istruzioni, espressioni e operatori](../../../csharp/programming-guide/statements-expressions-operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="7ef03-119">[Statements, Expressions, and Operators](../../../csharp/programming-guide/statements-expressions-operators/index.md) </span></span>  
 <span data-ttu-id="7ef03-120">[Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="7ef03-120">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="7ef03-121">[Delegati](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="7ef03-121">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 [<span data-ttu-id="7ef03-122">Alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="7ef03-122">Expression Trees</span></span>](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)

