---
title: while (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 23c5ca3bb7dc401a894a6c3918fbaec9a9306153
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="while-c-reference"></a><span data-ttu-id="d24be-102">while (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d24be-102">while (C# Reference)</span></span>
<span data-ttu-id="d24be-103">L'istruzione `while` esegue un'istruzione o un blocco di istruzioni finché un'espressione specificata non restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="d24be-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d24be-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d24be-104">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="d24be-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d24be-105">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="d24be-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d24be-106">Example</span></span>  
 <span data-ttu-id="d24be-107">Poiché il test dell'espressione `while` viene eseguito prima di ogni esecuzione del ciclo, un ciclo `while` viene eseguito zero o più volte.</span><span class="sxs-lookup"><span data-stu-id="d24be-107">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="d24be-108">Questo comportamento è diverso dal ciclo [do](../../../csharp/language-reference/keywords/do.md), che viene eseguito una o più volte.</span><span class="sxs-lookup"><span data-stu-id="d24be-108">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="d24be-109">Un ciclo `while` può essere terminato quando un'istruzione [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) trasferisce il controllo all'esterno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="d24be-109">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="d24be-110">Per passare il controllo all'iterazione successiva senza uscire dal ciclo, usare l'istruzione [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="d24be-110">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="d24be-111">Si noti la differenza di output nei tre esempi precedenti, a seconda di dove `int n` viene incrementato.</span><span class="sxs-lookup"><span data-stu-id="d24be-111">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="d24be-112">Nell'esempio seguente non viene generato alcun output.</span><span class="sxs-lookup"><span data-stu-id="d24be-112">In the example below no output is generated.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="d24be-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d24be-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d24be-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d24be-114">See Also</span></span>  
 [<span data-ttu-id="d24be-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d24be-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d24be-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d24be-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d24be-117">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="d24be-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d24be-118">Istruzione while (C++)</span><span class="sxs-lookup"><span data-stu-id="d24be-118">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
 [<span data-ttu-id="d24be-119">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="d24be-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
