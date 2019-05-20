---
title: Parola chiave contestuale value - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: cfd370df771998057fd421a0917b3e2fcd96d9f8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633033"
---
# <a name="value-c-reference"></a><span data-ttu-id="02584-102">value (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="02584-102">value (C# Reference)</span></span>

<span data-ttu-id="02584-103">La parola chiave contestuale `value` viene usata nella funzione di accesso set nelle dichiarazioni di proprietà ordinarie.</span><span class="sxs-lookup"><span data-stu-id="02584-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="02584-104">È simile a un parametro di input su un metodo.</span><span class="sxs-lookup"><span data-stu-id="02584-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="02584-105">La parola `value` fa riferimento al valore che il codice client tenta di assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="02584-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="02584-106">Nell'esempio seguente, `MyDerivedClass` ha una proprietà denominata `Name` che usa il parametro `value` per assegnare una nuova stringa al campo sottostante `name`.</span><span class="sxs-lookup"><span data-stu-id="02584-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="02584-107">Dal punto di vista del codice client, l'operazione viene scritta come assegnazione semplice.</span><span class="sxs-lookup"><span data-stu-id="02584-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="02584-108">Per altre informazioni sull'uso di `value`, vedere [Proprietà](../../programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="02584-108">For more information about the use of `value`, see [Properties](../../programming-guide/classes-and-structs/properties.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="02584-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="02584-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="02584-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02584-110">See also</span></span>

- [<span data-ttu-id="02584-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="02584-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="02584-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="02584-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="02584-113">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="02584-113">C# Keywords</span></span>](index.md)
