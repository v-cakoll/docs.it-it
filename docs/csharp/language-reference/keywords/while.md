---
title: while (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords: while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 420b409689d877c3e1ac744e8d7a65500cf8f964
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="while-c-reference"></a><span data-ttu-id="96250-102">while (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="96250-102">while (C# Reference)</span></span>
<span data-ttu-id="96250-103">L'istruzione `while` esegue un'istruzione o un blocco di istruzioni finché un'espressione specificata non restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="96250-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96250-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="96250-104">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="96250-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="96250-105">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="96250-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="96250-106">Example</span></span>  
 <span data-ttu-id="96250-107">Poiché il test dell'espressione `while` viene eseguito prima di ogni esecuzione del ciclo, un ciclo `while` viene eseguito zero o più volte.</span><span class="sxs-lookup"><span data-stu-id="96250-107">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="96250-108">Questo comportamento è diverso dal ciclo [do](../../../csharp/language-reference/keywords/do.md), che viene eseguito una o più volte.</span><span class="sxs-lookup"><span data-stu-id="96250-108">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="96250-109">Un ciclo `while` può essere terminato quando un'istruzione [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) trasferisce il controllo all'esterno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="96250-109">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="96250-110">Per passare il controllo all'iterazione successiva senza uscire dal ciclo, usare l'istruzione [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="96250-110">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="96250-111">Si noti la differenza di output nei tre esempi precedenti, a seconda di dove `int n` viene incrementato.</span><span class="sxs-lookup"><span data-stu-id="96250-111">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="96250-112">Nell'esempio seguente non viene generato alcun output.</span><span class="sxs-lookup"><span data-stu-id="96250-112">In the example below no output is generated.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="96250-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="96250-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="96250-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96250-114">See Also</span></span>  
 [<span data-ttu-id="96250-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="96250-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="96250-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="96250-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="96250-117">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="96250-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="96250-118">Istruzione while (C++)</span><span class="sxs-lookup"><span data-stu-id="96250-118">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
 [<span data-ttu-id="96250-119">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="96250-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
