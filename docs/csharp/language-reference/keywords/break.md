---
title: Istruzione break (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 987ee1ca5601b3dd105412bf0fa18361c57a95fd
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315238"
---
# <a name="break-c-reference"></a><span data-ttu-id="7cfd0-102">break (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7cfd0-102">break (C# Reference)</span></span>

<span data-ttu-id="7cfd0-103">L'istruzione `break` termina il ciclo di inclusione più vicino o l'istruzione [switch](../../../csharp/language-reference/keywords/switch.md) in cui appare.</span><span class="sxs-lookup"><span data-stu-id="7cfd0-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="7cfd0-104">Il controllo viene passato all'istruzione che segue l'istruzione terminata, se presente.</span><span class="sxs-lookup"><span data-stu-id="7cfd0-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="7cfd0-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="7cfd0-105">Example</span></span>

<span data-ttu-id="7cfd0-106">In questo esempio, l'istruzione condizionale contiene un contatore che dovrebbe contare da 1 a 100. L'istruzione `break` tuttavia termina il ciclo dopo 4 conteggi.</span><span class="sxs-lookup"><span data-stu-id="7cfd0-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="7cfd0-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="7cfd0-107">Example</span></span>

<span data-ttu-id="7cfd0-108">In questo esempio, l'istruzione `break` viene usata per interrompere un ciclo annidato interno e restituire il controllo al ciclo esterno.</span><span class="sxs-lookup"><span data-stu-id="7cfd0-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="7cfd0-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7cfd0-109">Example</span></span>

<span data-ttu-id="7cfd0-110">Questo esempio illustra l'uso di `break` in un'istruzione [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="7cfd0-110">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="7cfd0-111">Se è stato immesso `4`, l'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7cfd0-111">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a><span data-ttu-id="7cfd0-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7cfd0-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7cfd0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cfd0-113">See Also</span></span>

[<span data-ttu-id="7cfd0-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7cfd0-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="7cfd0-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7cfd0-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="7cfd0-116">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="7cfd0-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="7cfd0-117">switch</span><span class="sxs-lookup"><span data-stu-id="7cfd0-117">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)  
[<span data-ttu-id="7cfd0-118">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="7cfd0-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)  
[<span data-ttu-id="7cfd0-119">Istruzioni di iterazione</span><span class="sxs-lookup"><span data-stu-id="7cfd0-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
