---
title: try...catch...finally - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 3419ad46d5bbe13bb4308ad15b7819d615cdbe86
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244726"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="dd12f-102">try...catch...finally (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="dd12f-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="dd12f-103">Le parole chiave `catch` e `finally` vengono in genere usate insieme per rilevare e usare le risorse in un blocco `try`, gestire situazioni anomale in un blocco `catch` e liberare le risorse nel blocco `finally`.</span><span class="sxs-lookup"><span data-stu-id="dd12f-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="dd12f-104">Per altre informazioni ed esempi sulla rigenerazione di un'eccezione, vedere [try-catch](try-catch.md) e [Generazione di eccezioni](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="dd12f-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="dd12f-105">Per altre informazioni sul blocco `finally`, vedere la pagina [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="dd12f-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="dd12f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd12f-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="dd12f-107">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="dd12f-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dd12f-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd12f-108">See also</span></span>

- [<span data-ttu-id="dd12f-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="dd12f-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dd12f-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="dd12f-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dd12f-111">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="dd12f-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dd12f-112">Istruzioni try, throw e catch (C++)</span><span class="sxs-lookup"><span data-stu-id="dd12f-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="dd12f-113">Istruzioni di gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="dd12f-113">Exception Handling Statements</span></span>](exception-handling-statements.md)
- [<span data-ttu-id="dd12f-114">throw</span><span class="sxs-lookup"><span data-stu-id="dd12f-114">throw</span></span>](throw.md)
- [<span data-ttu-id="dd12f-115">Procedura: Generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="dd12f-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="dd12f-116">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="dd12f-116">using Statement</span></span>](using-statement.md)