---
title: Parola chiave protected - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: bec619d4f49bd26daa742c18c830909c14948adf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713183"
---
# <a name="protected-c-reference"></a><span data-ttu-id="b25c0-102">protected (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b25c0-102">protected (C# Reference)</span></span>

<span data-ttu-id="b25c0-103">La parola chiave `protected` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="b25c0-103">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="b25c0-104">Questa pagina illustra l'accesso `protected`.</span><span class="sxs-lookup"><span data-stu-id="b25c0-104">This page covers `protected` access.</span></span> <span data-ttu-id="b25c0-105">La `protected` parola chiave fa [`protected internal`](protected-internal.md) [`private protected`](private-protected.md) anche parte dei modificatori di accesso e .</span><span class="sxs-lookup"><span data-stu-id="b25c0-105">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="b25c0-106">Un membro protetto è accessibile all'interno della classe di appartenenza e dalle istanze della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="b25c0-106">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="b25c0-107">Per un confronto di `protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b25c0-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="b25c0-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="b25c0-108">Example</span></span>

<span data-ttu-id="b25c0-109">Un membro protetto di una classe di base è accessibile in una classe derivata solo se viene eseguito l'accesso tramite il tipo di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="b25c0-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="b25c0-110">Si consideri il segmento di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b25c0-110">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="b25c0-111">L'istruzione `a.x = 10` genera un errore perché usata all'interno del metodo statico Main e non in un'istanza della classe B.</span><span class="sxs-lookup"><span data-stu-id="b25c0-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="b25c0-112">I membri struct non possono essere protetti perché struct non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="b25c0-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="b25c0-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b25c0-113">Example</span></span>

<span data-ttu-id="b25c0-114">In questo esempio la classe `DerivedPoint` è derivata da `Point`.</span><span class="sxs-lookup"><span data-stu-id="b25c0-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="b25c0-115">Pertanto, è possibile accedere i membri protetti della classe di base direttamente dalla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="b25c0-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="b25c0-116">Se si impostano i livelli di accesso di `x` e `y` su [privato](private.md), il compilatore genererà i messaggi di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="b25c0-116">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="b25c0-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b25c0-117">C# language specification</span></span>  

<span data-ttu-id="b25c0-118">Per altre informazioni, vedere [Accessibilità dichiarata](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="b25c0-118">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="b25c0-119">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="b25c0-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b25c0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b25c0-120">See also</span></span>

- [<span data-ttu-id="b25c0-121">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="b25c0-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b25c0-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b25c0-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b25c0-123">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b25c0-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b25c0-124">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="b25c0-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="b25c0-125">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="b25c0-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="b25c0-126">Modificatori</span><span class="sxs-lookup"><span data-stu-id="b25c0-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b25c0-127">pubblico</span><span class="sxs-lookup"><span data-stu-id="b25c0-127">public</span></span>](public.md)
- [<span data-ttu-id="b25c0-128">Privato</span><span class="sxs-lookup"><span data-stu-id="b25c0-128">private</span></span>](private.md)
- [<span data-ttu-id="b25c0-129">Interno</span><span class="sxs-lookup"><span data-stu-id="b25c0-129">internal</span></span>](internal.md)
- <span data-ttu-id="b25c0-130">[Problemi di sicurezza per le parole chiave virtuali interne](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b25c0-130">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
