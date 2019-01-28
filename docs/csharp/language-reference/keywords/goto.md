---
title: Istruzione goto - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: e4642d0e43a538217493298b58d572e435db5dae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645327"
---
# <a name="goto-c-reference"></a><span data-ttu-id="bb5f8-102">goto (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bb5f8-102">goto (C# Reference)</span></span>

<span data-ttu-id="bb5f8-103">L'istruzione `goto` passa direttamente il controllo del programma a un'istruzione con etichetta.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="bb5f8-104">L'istruzione `goto` viene generalmente usata per trasferire il controllo a un'etichetta switch case specifica o all'etichetta predefinita di un'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="bb5f8-105">L'istruzione `goto` viene anche usata per uscire da cicli annidati più interni.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="bb5f8-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb5f8-106">Example</span></span>

<span data-ttu-id="bb5f8-107">Nell'esempio riportato di seguito viene illustrato l'uso di `goto` in un'istruzione [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="bb5f8-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="bb5f8-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb5f8-108">Example</span></span>

<span data-ttu-id="bb5f8-109">Nell'esempio riportato di seguito viene illustrato come usare `goto` per uscire da cicli annidati.</span><span class="sxs-lookup"><span data-stu-id="bb5f8-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="bb5f8-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bb5f8-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bb5f8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb5f8-111">See also</span></span>

- [<span data-ttu-id="bb5f8-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="bb5f8-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bb5f8-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bb5f8-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bb5f8-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="bb5f8-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bb5f8-115">Istruzione goto (C++)</span><span class="sxs-lookup"><span data-stu-id="bb5f8-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
- [<span data-ttu-id="bb5f8-116">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="bb5f8-116">Jump Statements</span></span>](jump-statements.md)
