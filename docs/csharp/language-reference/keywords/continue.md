---
title: Istruzione continue (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 6a409fe8c7fd07342138eac11bfd1766014da1bd
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948355"
---
# <a name="continue-c-reference"></a><span data-ttu-id="92e2e-102">continue (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="92e2e-102">continue (C# Reference)</span></span>

<span data-ttu-id="92e2e-103">L'istruzione `continue` passa il controllo all'iterazione successiva dell'istruzione [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) o [foreach](../../../csharp/language-reference/keywords/foreach-in.md) di inclusione in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="92e2e-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="92e2e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="92e2e-104">Example</span></span>

<span data-ttu-id="92e2e-105">In questo esempio viene inizializzato un contatore per il conteggio da 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="92e2e-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="92e2e-106">Usando l'istruzione `continue` in combinazione con l'espressione `(i < 9)`, le istruzioni comprese tra `continue` e la fine del corpo di `for` vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="92e2e-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="92e2e-107">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="92e2e-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="92e2e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92e2e-108">See also</span></span>

[<span data-ttu-id="92e2e-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="92e2e-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="92e2e-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="92e2e-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="92e2e-111">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="92e2e-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="92e2e-112">Istruzione break</span><span class="sxs-lookup"><span data-stu-id="92e2e-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)  
[<span data-ttu-id="92e2e-113">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="92e2e-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)