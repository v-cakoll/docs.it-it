---
title: Parola chiave namespace - Riferimenti per C#
ms.custom: seoapril2019
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: f938e49267faad8aebbf4c22fc921f305d160123
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633429"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="971d7-102">namespace (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="971d7-102">namespace (C# Reference)</span></span>

<span data-ttu-id="971d7-103">La parola chiave `namespace` è usata per dichiarare un ambito che contiene un set di oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="971d7-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="971d7-104">È possibile usare uno spazio dei nomi per organizzare gli elementi di codice e creare tipi univoci globali.</span><span class="sxs-lookup"><span data-stu-id="971d7-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="971d7-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="971d7-105">Remarks</span></span>

<span data-ttu-id="971d7-106">All'interno di uno spazio dei nomi è possibile dichiarare nessuno o più di uno dei tipi elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="971d7-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="971d7-107">un altro spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="971d7-107">another namespace</span></span>

- [<span data-ttu-id="971d7-108">class</span><span class="sxs-lookup"><span data-stu-id="971d7-108">class</span></span>](class.md)

- [<span data-ttu-id="971d7-109">interface</span><span class="sxs-lookup"><span data-stu-id="971d7-109">interface</span></span>](interface.md)

- [<span data-ttu-id="971d7-110">struct</span><span class="sxs-lookup"><span data-stu-id="971d7-110">struct</span></span>](struct.md)

- [<span data-ttu-id="971d7-111">enum</span><span class="sxs-lookup"><span data-stu-id="971d7-111">enum</span></span>](enum.md)

- [<span data-ttu-id="971d7-112">delegate</span><span class="sxs-lookup"><span data-stu-id="971d7-112">delegate</span></span>](delegate.md)

<span data-ttu-id="971d7-113">Il compilatore aggiunge uno spazio dei nomi predefinito indipendentemente dal fatto che venga dichiarato o meno uno spazio dei nomi in modo esplicito in un file di origine C#.</span><span class="sxs-lookup"><span data-stu-id="971d7-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="971d7-114">Questo spazio dei nomi senza nome, talvolta chiamato spazio dei nomi globale, è presente in ogni file.</span><span class="sxs-lookup"><span data-stu-id="971d7-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="971d7-115">Qualsiasi identificatore nello spazio dei nomi globale può essere usato all'interno di uno spazio dei nomi denominato.</span><span class="sxs-lookup"><span data-stu-id="971d7-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="971d7-116">Gli spazi dei nomi hanno in modo implicito accesso pubblico, non modificabile.</span><span class="sxs-lookup"><span data-stu-id="971d7-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="971d7-117">Per informazioni sui modificatori di accesso che è possibile assegnare agli elementi all'interno di uno spazio dei nomi, vedere [Modificatori di accesso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="971d7-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="971d7-118">È possibile definire uno spazio dei nomi in una o più dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="971d7-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="971d7-119">L'esempio seguente definisce due classi come parte dello spazio dei nomi `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="971d7-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="971d7-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="971d7-120">Example</span></span>

<span data-ttu-id="971d7-121">L'esempio seguente illustra come chiamare un metodo statico in uno spazio dei nomi annidato.</span><span class="sxs-lookup"><span data-stu-id="971d7-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a><span data-ttu-id="971d7-122">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="971d7-122">Related resources</span></span>

<span data-ttu-id="971d7-123">Per altre informazioni sull'uso degli spazi dei nomi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="971d7-123">For more information about using namespaces, see the following topics:</span></span>

- [<span data-ttu-id="971d7-124">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="971d7-124">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

- [<span data-ttu-id="971d7-125">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="971d7-125">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

- [<span data-ttu-id="971d7-126">Procedura: Usare l'alias dello spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="971d7-126">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="971d7-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="971d7-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="971d7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="971d7-128">See also</span></span>

- [<span data-ttu-id="971d7-129">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="971d7-129">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="971d7-130">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="971d7-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="971d7-131">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="971d7-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="971d7-132">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="971d7-132">Namespace Keywords</span></span>](namespace-keywords.md)
- [<span data-ttu-id="971d7-133">using</span><span class="sxs-lookup"><span data-stu-id="971d7-133">using</span></span>](using-directive.md)
- [<span data-ttu-id="971d7-134">using static</span><span class="sxs-lookup"><span data-stu-id="971d7-134">using static</span></span>](using-static.md)
