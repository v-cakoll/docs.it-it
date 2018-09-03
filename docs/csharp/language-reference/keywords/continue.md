---
title: Istruzione continue (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 37315caf14ba829dfc91da065bc49982f21b947f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43408231"
---
# <a name="continue-c-reference"></a><span data-ttu-id="a00f2-102">continue (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a00f2-102">continue (C# Reference)</span></span>

<span data-ttu-id="a00f2-103">L'istruzione `continue` passa il controllo all'iterazione successiva dell'istruzione [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) o [foreach](../../../csharp/language-reference/keywords/foreach-in.md) di inclusione in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="a00f2-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="a00f2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a00f2-104">Example</span></span>

<span data-ttu-id="a00f2-105">In questo esempio viene inizializzato un contatore per il conteggio da 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="a00f2-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="a00f2-106">Usando l'istruzione `continue` in combinazione con l'espressione `(i < 9)`, le istruzioni comprese tra `continue` e la fine del corpo di `for` vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="a00f2-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="a00f2-107">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a00f2-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a00f2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a00f2-108">See also</span></span>

- [<span data-ttu-id="a00f2-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a00f2-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a00f2-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a00f2-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a00f2-111">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="a00f2-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="a00f2-112">Istruzione break</span><span class="sxs-lookup"><span data-stu-id="a00f2-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)  
- [<span data-ttu-id="a00f2-113">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="a00f2-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)