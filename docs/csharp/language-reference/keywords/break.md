---
title: Istruzione break - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: ef276fd9e8da0ea25695c5afdf06a300bbd2a123
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713758"
---
# <a name="break-c-reference"></a><span data-ttu-id="09e54-102">break (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="09e54-102">break (C# Reference)</span></span>

<span data-ttu-id="09e54-103">L'istruzione `break` termina il ciclo di inclusione più vicino o l'istruzione [switch](./switch.md) in cui appare.</span><span class="sxs-lookup"><span data-stu-id="09e54-103">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="09e54-104">Il controllo viene passato all'istruzione che segue l'istruzione terminata, se presente.</span><span class="sxs-lookup"><span data-stu-id="09e54-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="09e54-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="09e54-105">Example</span></span>

<span data-ttu-id="09e54-106">In questo esempio, l'istruzione condizionale contiene un contatore che dovrebbe contare da 1 a 100. L'istruzione `break` tuttavia termina il ciclo dopo 4 conteggi.</span><span class="sxs-lookup"><span data-stu-id="09e54-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="09e54-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="09e54-107">Example</span></span>

<span data-ttu-id="09e54-108">Questo esempio illustra l'uso di `break` in un'istruzione [switch](./switch.md).</span><span class="sxs-lookup"><span data-stu-id="09e54-108">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="09e54-109">Se è stato immesso `4`, l'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="09e54-109">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a><span data-ttu-id="09e54-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="09e54-110">Example</span></span>

<span data-ttu-id="09e54-111">In questo esempio, l'istruzione `break` viene usata per interrompere un ciclo annidato interno e restituire il controllo al ciclo esterno.</span><span class="sxs-lookup"><span data-stu-id="09e54-111">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span> <span data-ttu-id="09e54-112">Il controllo viene restituito _solo_ un livello verso l'alto nei cicli nidificati.</span><span class="sxs-lookup"><span data-stu-id="09e54-112">Control is _only_ returned one level up in the nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="09e54-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="09e54-113">Example</span></span>

<span data-ttu-id="09e54-114">In questo esempio, l'istruzione `break` viene utilizzata solo per interrompere il ramo corrente durante ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="09e54-114">In this example, the `break` statement is only used to break out of the current branch during each iteration of the loop.</span></span> <span data-ttu-id="09e54-115">Il ciclo stesso non è influenzato dalle istanze di `break` che appartengono all'istruzione [Switch](./switch.md) nidificata.</span><span class="sxs-lookup"><span data-stu-id="09e54-115">The loop itself is unaffected by the instances of `break` that belong to the nested [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="09e54-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="09e54-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="09e54-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09e54-117">See also</span></span>

- [<span data-ttu-id="09e54-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="09e54-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="09e54-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="09e54-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="09e54-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="09e54-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="09e54-121">switch</span><span class="sxs-lookup"><span data-stu-id="09e54-121">switch</span></span>](./switch.md)
