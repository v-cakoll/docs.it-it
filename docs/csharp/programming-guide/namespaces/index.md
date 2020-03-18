---
title: Spazi dei nomi - Guida per programmatori C#
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 21452e259596c9ab10b3d653ec1d8fb90fad131d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75937618"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="fd80b-102">Spazi dei nomi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="fd80b-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="fd80b-103">Gli spazi dei nomi vengono usati frequentemente nella programmazione C# in due modi.</span><span class="sxs-lookup"><span data-stu-id="fd80b-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="fd80b-104">In primo luogo, .NET utilizza gli spazi dei nomi per organizzare le molte classi, come indicato di seguito:First, .NET uses namespaces to organize its many classes, as follows:</span><span class="sxs-lookup"><span data-stu-id="fd80b-104">First, .NET uses namespaces to organize its many classes, as follows:</span></span>  

[!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]

<span data-ttu-id="fd80b-105"><xref:System> è uno spazio dei nomi e <xref:System.Console> è una classe in quello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fd80b-105"><xref:System> is a namespace and <xref:System.Console> is a class in that namespace.</span></span> <span data-ttu-id="fd80b-106">Si può usare la parola chiave `using` in modo tale che il nome completo non sia necessario, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd80b-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]

<span data-ttu-id="fd80b-107">Per altre informazioni, vedere la [direttiva using](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="fd80b-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>

<span data-ttu-id="fd80b-108">Secondo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi.</span><span class="sxs-lookup"><span data-stu-id="fd80b-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="fd80b-109">Usare la parola chiave [namespace](../../language-reference/keywords/namespace.md) per dichiarare uno spazio dei nomi, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd80b-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>

[!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="fd80b-110">Il nome dello spazio dei nomi deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido.</span><span class="sxs-lookup"><span data-stu-id="fd80b-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="fd80b-111">Panoramica degli spazi dei nomiNamespaces overview</span><span class="sxs-lookup"><span data-stu-id="fd80b-111">Namespaces overview</span></span>

<span data-ttu-id="fd80b-112">Gli spazi dei nomi hanno le proprietà riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="fd80b-112">Namespaces have the following properties:</span></span>

- <span data-ttu-id="fd80b-113">Consentono di organizzare progetti di codice di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="fd80b-113">They organize large code projects.</span></span>
- <span data-ttu-id="fd80b-114">Vengono delimitati usando l'operatore `.`.</span><span class="sxs-lookup"><span data-stu-id="fd80b-114">They are delimited by using the `.` operator.</span></span>
- <span data-ttu-id="fd80b-115">La direttiva `using` elimina la necessità di specificare il nome dello spazio dei nomi per ogni classe.</span><span class="sxs-lookup"><span data-stu-id="fd80b-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>
- <span data-ttu-id="fd80b-116">Lo spazio dei nomi `global` è lo spazio dei nomi "radice": `global::System` farà sempre riferimento allo spazio dei nomi <xref:System> di .NET.</span><span class="sxs-lookup"><span data-stu-id="fd80b-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fd80b-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="fd80b-117">C# language specification</span></span>

<span data-ttu-id="fd80b-118">Per altre informazioni, vedere la sezione [Spazi dei nomi](~/_csharplang/spec/namespaces.md) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="fd80b-118">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd80b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd80b-119">See also</span></span>

- [<span data-ttu-id="fd80b-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fd80b-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fd80b-121">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="fd80b-121">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="fd80b-122">Come usare lo spazio dei nomi My</span><span class="sxs-lookup"><span data-stu-id="fd80b-122">How to use the My namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="fd80b-123">Nomi di identificatore</span><span class="sxs-lookup"><span data-stu-id="fd80b-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="fd80b-124">using Direttiva</span><span class="sxs-lookup"><span data-stu-id="fd80b-124">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="fd80b-125">:: Operatore</span><span class="sxs-lookup"><span data-stu-id="fd80b-125">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
