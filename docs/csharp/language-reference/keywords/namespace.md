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
ms.openlocfilehash: 04595e96f6f14b8806a2d89625151910cac9e0d2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345413"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="20476-102">namespace (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="20476-102">namespace (C# Reference)</span></span>

<span data-ttu-id="20476-103">La parola chiave `namespace` è usata per dichiarare un ambito che contiene un set di oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="20476-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="20476-104">È possibile usare uno spazio dei nomi per organizzare gli elementi di codice e creare tipi univoci globali.</span><span class="sxs-lookup"><span data-stu-id="20476-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="20476-105">Note</span><span class="sxs-lookup"><span data-stu-id="20476-105">Remarks</span></span>

<span data-ttu-id="20476-106">All'interno di uno spazio dei nomi è possibile dichiarare nessuno o più di uno dei tipi elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="20476-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="20476-107">un altro spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="20476-107">another namespace</span></span>

- [<span data-ttu-id="20476-108">classe</span><span class="sxs-lookup"><span data-stu-id="20476-108">class</span></span>](class.md)

- [<span data-ttu-id="20476-109">interface</span><span class="sxs-lookup"><span data-stu-id="20476-109">interface</span></span>](interface.md)

- [<span data-ttu-id="20476-110">struct</span><span class="sxs-lookup"><span data-stu-id="20476-110">struct</span></span>](struct.md)

- [<span data-ttu-id="20476-111">enum</span><span class="sxs-lookup"><span data-stu-id="20476-111">enum</span></span>](../builtin-types/enum.md)

- [<span data-ttu-id="20476-112">delegate</span><span class="sxs-lookup"><span data-stu-id="20476-112">delegate</span></span>](../builtin-types/reference-types.md#the-delegate-type)

<span data-ttu-id="20476-113">Il compilatore aggiunge uno spazio dei nomi predefinito indipendentemente dal fatto che venga dichiarato o meno uno spazio dei nomi in modo esplicito in un file di origine C#.</span><span class="sxs-lookup"><span data-stu-id="20476-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="20476-114">Questo spazio dei nomi senza nome, talvolta chiamato spazio dei nomi globale, è presente in ogni file.</span><span class="sxs-lookup"><span data-stu-id="20476-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="20476-115">Qualsiasi identificatore nello spazio dei nomi globale può essere usato all'interno di uno spazio dei nomi denominato.</span><span class="sxs-lookup"><span data-stu-id="20476-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="20476-116">Gli spazi dei nomi hanno in modo implicito accesso pubblico, non modificabile.</span><span class="sxs-lookup"><span data-stu-id="20476-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="20476-117">Per informazioni sui modificatori di accesso che è possibile assegnare agli elementi all'interno di uno spazio dei nomi, vedere [Modificatori di accesso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="20476-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="20476-118">È possibile definire uno spazio dei nomi in una o più dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="20476-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="20476-119">L'esempio seguente definisce due classi come parte dello spazio dei nomi `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="20476-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="20476-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="20476-120">Example</span></span>

<span data-ttu-id="20476-121">L'esempio seguente illustra come chiamare un metodo statico in uno spazio dei nomi annidato.</span><span class="sxs-lookup"><span data-stu-id="20476-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="20476-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="20476-122">C# language specification</span></span>

<span data-ttu-id="20476-123">Per altre informazioni, vedere la sezione [Spazi dei nomi](~/_csharplang/spec/namespaces.md) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="20476-123">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="20476-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20476-124">See also</span></span>

- [<span data-ttu-id="20476-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="20476-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="20476-126">Parole chiave C#</span><span class="sxs-lookup"><span data-stu-id="20476-126">C# keywords</span></span>](index.md)
- [<span data-ttu-id="20476-127">using</span><span class="sxs-lookup"><span data-stu-id="20476-127">using</span></span>](using-directive.md)
- [<span data-ttu-id="20476-128">using static</span><span class="sxs-lookup"><span data-stu-id="20476-128">using static</span></span>](using-static.md)
- [<span data-ttu-id="20476-129">Qualificatore di alias dello spazio dei nomi `::`</span><span class="sxs-lookup"><span data-stu-id="20476-129">Namespace alias qualifier `::`</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="20476-130">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="20476-130">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
