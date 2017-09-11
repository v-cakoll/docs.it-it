---
title: do (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
dev_langs:
- CSharp
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
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
ms.openlocfilehash: 58a9361c440bc1b17c5ab929ff7b45ba71ce50a4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="do-c-reference"></a><span data-ttu-id="58cfd-102">do (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="58cfd-102">do (C# Reference)</span></span>
<span data-ttu-id="58cfd-103">L'istruzione `do` esegue ripetutamente un'istruzione o un blocco di istruzioni finché un'espressione specificata non restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="58cfd-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="58cfd-104">Il corpo del ciclo deve essere racchiuso tra parentesi graffe, `{}`, a meno che sia costituito da una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="58cfd-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="58cfd-105">In tal caso le parentesi graffe sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="58cfd-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58cfd-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="58cfd-106">Example</span></span>  
 <span data-ttu-id="58cfd-107">Nell'esempio seguente vengono eseguite le istruzioni del ciclo `do-while` fino a quando la variabile `x` è minore di 5.</span><span class="sxs-lookup"><span data-stu-id="58cfd-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 <span data-ttu-id="58cfd-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="58cfd-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span></span>  
  
 <span data-ttu-id="58cfd-109">A differenza dell'istruzione [while](../../../csharp/language-reference/keywords/while.md), un ciclo `do-while` viene eseguito una sola volta prima che sia valutata l'espressione condizionale.</span><span class="sxs-lookup"><span data-stu-id="58cfd-109">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="58cfd-110">In qualsiasi momento nel blocco `do-while` è possibile uscire dal ciclo usando l'istruzione [break](../../../csharp/language-reference/keywords/break.md).</span><span class="sxs-lookup"><span data-stu-id="58cfd-110">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="58cfd-111">Si può eseguire direttamente l'istruzione di valutazione dell'espressione `while` usando l'istruzione [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="58cfd-111">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="58cfd-112">Se l'espressione `while` restituisce true, l'esecuzione continua con la prima istruzione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="58cfd-112">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="58cfd-113">Se l'espressione restituisce false, l'esecuzione continua con la prima istruzione dopo il ciclo `do-while`.</span><span class="sxs-lookup"><span data-stu-id="58cfd-113">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="58cfd-114">È possibile uscire da un ciclo `do-while` anche con le istruzioni [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="58cfd-114">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="58cfd-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="58cfd-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="58cfd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58cfd-116">See Also</span></span>  
 <span data-ttu-id="58cfd-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="58cfd-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="58cfd-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="58cfd-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="58cfd-119">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="58cfd-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="58cfd-120">[Istruzione do-while (C++)](/cpp/cpp/do-while-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="58cfd-120">[do-while Statement (C++)](/cpp/cpp/do-while-statement-cpp) </span></span>  
 [<span data-ttu-id="58cfd-121">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="58cfd-121">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

