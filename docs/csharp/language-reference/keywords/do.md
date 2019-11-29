---
title: do - Riferimenti per C#
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5612cfb2462117ac431de9c702cd8137f495e5dc
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "74551802"
---
# <a name="do-c-reference"></a><span data-ttu-id="fcfde-102">do (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="fcfde-102">do (C# Reference)</span></span>

<span data-ttu-id="fcfde-103">L'istruzione `do` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="fcfde-103">The `do` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="fcfde-104">Poiché tale espressione viene valutata dopo ogni esecuzione del ciclo, un ciclo `do-while` viene eseguito una o più volte.</span><span class="sxs-lookup"><span data-stu-id="fcfde-104">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="fcfde-105">Questo comportamento è diverso da quello del ciclo [while](while.md), che viene eseguito zero o più volte.</span><span class="sxs-lookup"><span data-stu-id="fcfde-105">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="fcfde-106">In qualsiasi punto all'interno del blocco `do` è possibile uscire dal ciclo usando l'istruzione [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="fcfde-106">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="fcfde-107">È possibile passare direttamente alla valutazione dell'espressione `while` tramite l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="fcfde-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="fcfde-108">Se l'espressione restituisce `true`, l'esecuzione continua con la prima istruzione nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="fcfde-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="fcfde-109">In caso contrario, l'esecuzione continua con la prima istruzione dopo il ciclo.</span><span class="sxs-lookup"><span data-stu-id="fcfde-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="fcfde-110">Si può uscire da un ciclo `do-while` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="fcfde-110">You also can exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="fcfde-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcfde-111">Example</span></span>

<span data-ttu-id="fcfde-112">L'esempio seguente illustra l'utilizzo dell'istruzione `do`.</span><span class="sxs-lookup"><span data-stu-id="fcfde-112">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="fcfde-113">Selezionare **Esegui** per eseguire il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="fcfde-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="fcfde-114">Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="fcfde-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="fcfde-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="fcfde-115">C# language specification</span></span>

<span data-ttu-id="fcfde-116">Per altre informazioni, vedere la sezione [Istruzione do](~/_csharplang/spec/statements.md#the-do-statement) della [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="fcfde-116">For more information, see [The do statement](~/_csharplang/spec/statements.md#the-do-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="fcfde-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcfde-117">See also</span></span>

- [<span data-ttu-id="fcfde-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="fcfde-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fcfde-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fcfde-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fcfde-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="fcfde-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fcfde-121">Istruzione While</span><span class="sxs-lookup"><span data-stu-id="fcfde-121">while statement</span></span>](while.md)
