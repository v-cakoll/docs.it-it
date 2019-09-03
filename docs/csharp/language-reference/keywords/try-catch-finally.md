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
ms.openlocfilehash: 9f2c82fb140e18454491660d17b570db0a8a2aef
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168596"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="75734-102">try...catch...finally (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="75734-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="75734-103">Le parole chiave `catch` e `finally` vengono in genere usate insieme per rilevare e usare le risorse in un blocco `try`, gestire situazioni anomale in un blocco `catch` e liberare le risorse nel blocco `finally`.</span><span class="sxs-lookup"><span data-stu-id="75734-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="75734-104">Per altre informazioni ed esempi sulla rigenerazione di un'eccezione, vedere [try-catch](try-catch.md) e [Generazione di eccezioni](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="75734-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="75734-105">Per altre informazioni sul blocco `finally`, vedere la pagina [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="75734-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="75734-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="75734-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="75734-107">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="75734-107">C# language specification</span></span>

<span data-ttu-id="75734-108">Per altre informazioni, vedere la sezione [Istruzione try](~/_csharplang/spec/statements.md#the-try-statement) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="75734-108">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="75734-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75734-109">See also</span></span>

- [<span data-ttu-id="75734-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="75734-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="75734-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="75734-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="75734-112">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="75734-112">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="75734-113">Istruzioni try, throw e catch (C++)</span><span class="sxs-lookup"><span data-stu-id="75734-113">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="75734-114">throw</span><span class="sxs-lookup"><span data-stu-id="75734-114">throw</span></span>](throw.md)
- [<span data-ttu-id="75734-115">Procedura: Generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="75734-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="75734-116">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="75734-116">using Statement</span></span>](using-statement.md)
