---
title: Spazi dei nomi (Guida per programmatori C#)
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: c5431e5141b1b4b1981f4a1399ca11939fe7dc45
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151110"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="d5bbd-102">Spazi dei nomi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d5bbd-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="d5bbd-103">Gli spazi dei nomi vengono usati frequentemente nella programmazione C# in due modi.</span><span class="sxs-lookup"><span data-stu-id="d5bbd-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="d5bbd-104">Primo, .NET Framework usa gli spazi dei nomi per organizzare numerose classi, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d5bbd-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
<span data-ttu-id="d5bbd-105">`System` è uno spazio dei nomi e `Console` è una classe in quello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d5bbd-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="d5bbd-106">Si può usare la parola chiave `using` in modo tale che il nome completo non sia necessario, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d5bbd-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
<span data-ttu-id="d5bbd-107">Per altre informazioni, vedere la [direttiva using](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="d5bbd-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="d5bbd-108">Secondo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi.</span><span class="sxs-lookup"><span data-stu-id="d5bbd-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="d5bbd-109">Usare la parola chiave [namespace](../../language-reference/keywords/namespace.md) per dichiarare uno spazio dei nomi, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d5bbd-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

<span data-ttu-id="d5bbd-110">Il nome dello spazio dei nomi deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido.</span><span class="sxs-lookup"><span data-stu-id="d5bbd-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="d5bbd-111">Panoramica degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="d5bbd-111">Namespaces Overview</span></span>  

<span data-ttu-id="d5bbd-112">Gli spazi dei nomi hanno le proprietà riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="d5bbd-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="d5bbd-113">Consentono di organizzare progetti di codice di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d5bbd-113">They organize large code projects.</span></span>  
- <span data-ttu-id="d5bbd-114">Vengono delimitati usando l'operatore `.`.</span><span class="sxs-lookup"><span data-stu-id="d5bbd-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="d5bbd-115">La direttiva `using` elimina la necessità di specificare il nome dello spazio dei nomi per ogni classe.</span><span class="sxs-lookup"><span data-stu-id="d5bbd-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="d5bbd-116">Lo spazio dei nomi `global` è lo spazio dei nomi "radice": `global::System` farà sempre riferimento allo spazio dei nomi <xref:System> di .NET.</span><span class="sxs-lookup"><span data-stu-id="d5bbd-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="d5bbd-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d5bbd-117">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5bbd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5bbd-118">See Also</span></span>

- [<span data-ttu-id="d5bbd-119">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="d5bbd-119">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="d5bbd-120">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="d5bbd-120">How to: Use the Global Namespace Alias</span></span>](how-to-use-the-global-namespace-alias.md)
- [<span data-ttu-id="d5bbd-121">Procedura: Usare lo spazio dei nomi My</span><span class="sxs-lookup"><span data-stu-id="d5bbd-121">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="d5bbd-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d5bbd-122">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="d5bbd-123">Nomi di identificatore</span><span class="sxs-lookup"><span data-stu-id="d5bbd-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="d5bbd-124">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="d5bbd-124">Namespace Keywords</span></span>](../../language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="d5bbd-125">Direttiva using</span><span class="sxs-lookup"><span data-stu-id="d5bbd-125">using Directive</span></span>](../../language-reference/keywords/using-directive.md)  
- [<span data-ttu-id="d5bbd-126">Operatore ::</span><span class="sxs-lookup"><span data-stu-id="d5bbd-126">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="d5bbd-127">. (operatore)</span><span class="sxs-lookup"><span data-stu-id="d5bbd-127">. Operator</span></span>](../../language-reference/operators/member-access-operator.md)
