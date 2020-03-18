---
title: Istruzione continue - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 83b43b31eacf0ed835ee3d7a919538eb9f1dd1e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713667"
---
# <a name="continue-c-reference"></a><span data-ttu-id="9b76a-102">continue (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9b76a-102">continue (C# Reference)</span></span>

<span data-ttu-id="9b76a-103">L'istruzione `continue` passa il controllo all'iterazione successiva dell'istruzione [while](./while.md), [do](./do.md), [for](./for.md) o [foreach](./foreach-in.md) di inclusione in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="9b76a-103">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="9b76a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b76a-104">Example</span></span>

<span data-ttu-id="9b76a-105">In questo esempio viene inizializzato un contatore per il conteggio da 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="9b76a-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="9b76a-106">Usando l'istruzione `continue` in combinazione con l'espressione `(i < 9)`, le istruzioni comprese tra `continue` e la fine del corpo di `for` vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="9b76a-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="9b76a-107">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="9b76a-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9b76a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b76a-108">See also</span></span>

- [<span data-ttu-id="9b76a-109">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="9b76a-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9b76a-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9b76a-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9b76a-111">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="9b76a-111">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="9b76a-112">Istruzione break</span><span class="sxs-lookup"><span data-stu-id="9b76a-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
