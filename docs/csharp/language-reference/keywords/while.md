---
title: while (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
dev_langs:
- CSharp
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
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
ms.openlocfilehash: ed531c83dba02b38576bf8354b1ff92f075048bc
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="while-c-reference"></a><span data-ttu-id="06d97-102">while (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="06d97-102">while (C# Reference)</span></span>
<span data-ttu-id="06d97-103">L'istruzione `while` esegue un'istruzione o un blocco di istruzioni finché un'espressione specificata non restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="06d97-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06d97-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="06d97-104">Example</span></span>  
 <span data-ttu-id="06d97-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="06d97-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="06d97-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="06d97-106">Example</span></span>  
 <span data-ttu-id="06d97-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="06d97-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="06d97-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="06d97-108">Example</span></span>  
 <span data-ttu-id="06d97-109">Poiché il test dell'espressione `while` viene eseguito prima di ogni esecuzione del ciclo, un ciclo `while` viene eseguito zero o più volte.</span><span class="sxs-lookup"><span data-stu-id="06d97-109">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="06d97-110">Questo comportamento è diverso dal ciclo [do](../../../csharp/language-reference/keywords/do.md), che viene eseguito una o più volte.</span><span class="sxs-lookup"><span data-stu-id="06d97-110">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="06d97-111">Un ciclo `while` può essere terminato quando un'istruzione [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) trasferisce il controllo all'esterno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="06d97-111">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="06d97-112">Per passare il controllo all'iterazione successiva senza uscire dal ciclo, usare l'istruzione [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="06d97-112">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="06d97-113">Si noti la differenza di output nei tre esempi precedenti, a seconda di dove `int n` viene incrementato.</span><span class="sxs-lookup"><span data-stu-id="06d97-113">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="06d97-114">Nell'esempio seguente non viene generato alcun output.</span><span class="sxs-lookup"><span data-stu-id="06d97-114">In the example below no output is generated.</span></span>  
  
 <span data-ttu-id="06d97-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="06d97-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="06d97-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="06d97-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="06d97-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06d97-117">See Also</span></span>  
 <span data-ttu-id="06d97-118">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="06d97-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="06d97-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="06d97-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="06d97-120">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="06d97-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="06d97-121">[Istruzione while (C++)](/cpp/cpp/while-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="06d97-121">[while Statement (C++)](/cpp/cpp/while-statement-cpp) </span></span>  
 [<span data-ttu-id="06d97-122">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="06d97-122">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

