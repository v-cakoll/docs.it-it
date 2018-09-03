---
title: while (Riferimenti per C#)
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: e3e9493b5371fbd6f53a779ba73743efc6d6e05b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43390024"
---
# <a name="while-c-reference"></a><span data-ttu-id="7f2f9-102">while (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7f2f9-102">while (C# Reference)</span></span>

<span data-ttu-id="7f2f9-103">L'istruzione `while` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="7f2f9-103">The `while` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span> <span data-ttu-id="7f2f9-104">Poiché tale espressione viene valutata prima di ogni esecuzione del ciclo, un ciclo `while` viene eseguito zero o più volte.</span><span class="sxs-lookup"><span data-stu-id="7f2f9-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="7f2f9-105">Questo comportamento è diverso dal ciclo [do](do.md), che viene eseguito una o più volte.</span><span class="sxs-lookup"><span data-stu-id="7f2f9-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="7f2f9-106">In qualsiasi punto all'interno del blocco `while` è possibile uscire dal ciclo usando l'istruzione [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="7f2f9-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="7f2f9-107">È possibile passare direttamente alla valutazione dell'espressione `while` tramite l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="7f2f9-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="7f2f9-108">Se l'espressione restituisce `true`, l'esecuzione continua con la prima istruzione nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="7f2f9-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="7f2f9-109">In caso contrario, l'esecuzione continua con la prima istruzione dopo il ciclo.</span><span class="sxs-lookup"><span data-stu-id="7f2f9-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="7f2f9-110">Si può uscire da un ciclo `while` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="7f2f9-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="7f2f9-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f2f9-111">Example</span></span>

<span data-ttu-id="7f2f9-112">L'esempio seguente illustra l'utilizzo dell'istruzione `while`.</span><span class="sxs-lookup"><span data-stu-id="7f2f9-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="7f2f9-113">Selezionare **Esegui** per eseguire il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="7f2f9-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="7f2f9-114">Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="7f2f9-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="7f2f9-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7f2f9-115">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7f2f9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f2f9-116">See also</span></span>

- [<span data-ttu-id="7f2f9-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7f2f9-117">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="7f2f9-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7f2f9-118">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="7f2f9-119">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="7f2f9-119">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="7f2f9-120">Istruzione while (C++)</span><span class="sxs-lookup"><span data-stu-id="7f2f9-120">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
- [<span data-ttu-id="7f2f9-121">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="7f2f9-121">Iteration Statements</span></span>](iteration-statements.md)  
- [<span data-ttu-id="7f2f9-122">Istruzione do</span><span class="sxs-lookup"><span data-stu-id="7f2f9-122">do statement</span></span>](do.md)  
