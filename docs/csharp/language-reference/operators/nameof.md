---
title: Operatore nameof - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 965b3e96a20906187df4c8693f050c550a747091
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331442"
---
# <a name="nameof-operator-c-reference"></a><span data-ttu-id="aa721-102">Operatore nameof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="aa721-102">nameof operator (C# reference)</span></span>

<span data-ttu-id="aa721-103">L'operatore `nameof` ottiene il nome di una variabile, di un tipo o di un membro come costante stringa:</span><span class="sxs-lookup"><span data-stu-id="aa721-103">The `nameof` operator obtains the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

<span data-ttu-id="aa721-104">Come illustrato nell'esempio precedente, nel caso di un tipo e di uno spazio dei nomi, il nome prodotto in genere non è [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="aa721-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="aa721-105">L'operatore `nameof` viene valutato in fase di compilazione e non ha alcun effetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="aa721-105">The `nameof` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="aa721-106">È possibile usare l'operatore `nameof` per rendere più gestibile il codice per il controllo degli argomenti:</span><span class="sxs-lookup"><span data-stu-id="aa721-106">You can use the `nameof` operator to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="aa721-107">L'operatore `nameof` è disponibile in C# 6 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="aa721-107">The `nameof` operator is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="aa721-108">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="aa721-108">C# language specification</span></span>

<span data-ttu-id="aa721-109">Per altre informazioni, vedere la sezione [Espressioni Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="aa721-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aa721-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa721-110">See also</span></span>

- [<span data-ttu-id="aa721-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="aa721-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="aa721-112">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="aa721-112">C# operators</span></span>](index.md)
