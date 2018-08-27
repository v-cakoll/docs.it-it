---
title: do (Riferimenti per C#)
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 89c13f5b547c13052e229ff6eb3a39ae5babce41
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932387"
---
# <a name="do-c-reference"></a><span data-ttu-id="fcf8c-102">do (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="fcf8c-102">do (C# Reference)</span></span>

<span data-ttu-id="fcf8c-103">L'istruzione `do` esegue un'istruzione o un blocco di istruzioni mentre un'espressione booleana specificata restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="fcf8c-103">The `do` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span> <span data-ttu-id="fcf8c-104">Poiché tale espressione viene valutata dopo ogni esecuzione del ciclo, un ciclo `do-while` viene eseguito una o più volte.</span><span class="sxs-lookup"><span data-stu-id="fcf8c-104">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="fcf8c-105">Questo comportamento è diverso da quello del ciclo [while](while.md), che viene eseguito zero o più volte.</span><span class="sxs-lookup"><span data-stu-id="fcf8c-105">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="fcf8c-106">In qualsiasi punto all'interno del blocco `do` è possibile uscire dal ciclo usando l'istruzione [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="fcf8c-106">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="fcf8c-107">È possibile passare direttamente alla valutazione dell'espressione `while` tramite l'istruzione [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="fcf8c-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="fcf8c-108">Se l'espressione restituisce `true`, l'esecuzione continua con la prima istruzione nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="fcf8c-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="fcf8c-109">In caso contrario, l'esecuzione continua con la prima istruzione dopo il ciclo.</span><span class="sxs-lookup"><span data-stu-id="fcf8c-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="fcf8c-110">Si può uscire da un ciclo `do-while` anche usando l'istruzione [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="fcf8c-110">You also can exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="fcf8c-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcf8c-111">Example</span></span>

<span data-ttu-id="fcf8c-112">L'esempio seguente illustra l'utilizzo dell'istruzione `do`.</span><span class="sxs-lookup"><span data-stu-id="fcf8c-112">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="fcf8c-113">Selezionare **Esegui** per eseguire il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="fcf8c-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="fcf8c-114">Dopo l'esecuzione è possibile modificare il codice ed eseguirlo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="fcf8c-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="fcf8c-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="fcf8c-115">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fcf8c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcf8c-116">See also</span></span>

- [<span data-ttu-id="fcf8c-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="fcf8c-117">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="fcf8c-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fcf8c-118">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="fcf8c-119">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="fcf8c-119">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="fcf8c-120">Istruzione do-while (C++)</span><span class="sxs-lookup"><span data-stu-id="fcf8c-120">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
- [<span data-ttu-id="fcf8c-121">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="fcf8c-121">Iteration Statements</span></span>](iteration-statements.md)  
- [<span data-ttu-id="fcf8c-122">Istruzione While</span><span class="sxs-lookup"><span data-stu-id="fcf8c-122">while statement</span></span>](while.md)  
