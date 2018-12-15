---
title: while - Riferimenti per C#
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: d360db7b9b740bef997327dda9b628c1edab0f35
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242568"
---
# <a name="while-c-reference"></a><span data-ttu-id="ad6b7-102">while (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ad6b7-102">while (C# Reference)</span></span>

<span data-ttu-id="ad6b7-103">L'istruzione `while` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-103">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="ad6b7-104">Poiché tale espressione viene valutata prima di ogni esecuzione del ciclo, un ciclo `while` viene eseguito zero o più volte.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="ad6b7-105">Questo comportamento è diverso dal ciclo [do](do.md), che viene eseguito una o più volte.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="ad6b7-106">In qualsiasi punto all'interno del blocco `while` è possibile uscire dal ciclo usando l'istruzione [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="ad6b7-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="ad6b7-107">È possibile passare direttamente alla valutazione dell'espressione `while` tramite l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="ad6b7-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="ad6b7-108">Se l'espressione restituisce `true`, l'esecuzione continua con la prima istruzione nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="ad6b7-109">In caso contrario, l'esecuzione continua con la prima istruzione dopo il ciclo.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="ad6b7-110">Si può uscire da un ciclo `while` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="ad6b7-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="ad6b7-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad6b7-111">Example</span></span>

<span data-ttu-id="ad6b7-112">L'esempio seguente illustra l'utilizzo dell'istruzione `while`.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="ad6b7-113">Selezionare **Esegui** per eseguire il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="ad6b7-114">Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="ad6b7-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ad6b7-115">C# language specification</span></span>

<span data-ttu-id="ad6b7-116">Per altre informazioni, vedere la sezione [L'istruzione while](~/_csharplang/spec/statements.md#the-while-statement) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad6b7-116">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad6b7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad6b7-117">See also</span></span>

- [<span data-ttu-id="ad6b7-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="ad6b7-118">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="ad6b7-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ad6b7-119">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="ad6b7-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="ad6b7-120">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="ad6b7-121">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="ad6b7-121">Iteration Statements</span></span>](iteration-statements.md)  
- [<span data-ttu-id="ad6b7-122">Istruzione do</span><span class="sxs-lookup"><span data-stu-id="ad6b7-122">do statement</span></span>](do.md)  
