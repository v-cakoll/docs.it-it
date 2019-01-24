---
title: . - operatore - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: a59f69d0349a054c8c2a5b701b8f63df113a6580
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333720"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c8b2c-103">.</span><span class="sxs-lookup"><span data-stu-id="c8b2c-103">.</span></span> <span data-ttu-id="c8b2c-104">operator (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c8b2c-104">operator (C# Reference)</span></span>

<span data-ttu-id="c8b2c-105">L'operatore punto (`.`) viene usato per l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="c8b2c-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="c8b2c-106">L'operatore punto specifica un membro di un tipo o di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c8b2c-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="c8b2c-107">Ad esempio, viene usato per accedere a metodi specifici all'interno delle librerie di classi .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c8b2c-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>

[!code-csharp[csRefOperators#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#16)]

<span data-ttu-id="c8b2c-108">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="c8b2c-108">For example, consider the following class:</span></span>

[!code-csharp[csRefOperators#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#17)]

[!code-csharp[csRefOperators#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#18)]

<span data-ttu-id="c8b2c-109">La variabile `s` ha due membri, `a` e `b`, per accedere ai quali è necessario usare l'operatore punto:</span><span class="sxs-lookup"><span data-stu-id="c8b2c-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>

[!code-csharp[csRefOperators#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#19)]

<span data-ttu-id="c8b2c-110">Il punto viene usato anche per formare nomi completi, ovvero nomi che specificano lo spazio dei nomi o l'interfaccia, ad esempio, a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="c8b2c-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>

[!code-csharp[csRefOperators#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#20)]

<span data-ttu-id="c8b2c-111">La direttiva using rende facoltativa la qualificazione di alcuni nomi:</span><span class="sxs-lookup"><span data-stu-id="c8b2c-111">The using directive makes some name qualification optional:</span></span>

[!code-csharp[csRefOperators#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#21)]

<span data-ttu-id="c8b2c-112">Ma quando un identificatore è ambiguo, deve essere qualificato:</span><span class="sxs-lookup"><span data-stu-id="c8b2c-112">But when an identifier is ambiguous, it must be qualified:</span></span>

[!code-csharp[csRefOperators#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="c8b2c-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c8b2c-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c8b2c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8b2c-114">See also</span></span>

- [<span data-ttu-id="c8b2c-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c8b2c-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c8b2c-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c8b2c-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c8b2c-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="c8b2c-117">C# Operators</span></span>](index.md)