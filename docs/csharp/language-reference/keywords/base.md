---
title: Parola chiave base - Riferimenti per C#
description: Informazioni sulla parola chiave base, usata per accedere ai membri della classe di base dall'interno di una classe derivata in C#.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: a4686fc5d4245a50de5d77dc0e71c231772f40ef
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713765"
---
# <a name="base-c-reference"></a><span data-ttu-id="cb996-103">base (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cb996-103">base (C# Reference)</span></span>

<span data-ttu-id="cb996-104">La parola chiave `base` viene usata per accedere ai membri della classe di base dall'interno di una classe derivata:</span><span class="sxs-lookup"><span data-stu-id="cb996-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="cb996-105">Chiamare un metodo sulla classe di base che è stato sostituito da un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="cb996-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="cb996-106">Specificare quale costruttore di classe di base deve essere chiamato durante la creazione di istanze della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="cb996-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="cb996-107">Una classe di base di accesso è consentita solo in un costruttore, in un metodo di istanza o in una funzione di accesso alla proprietà dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="cb996-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="cb996-108">Non è possibile usare la parola chiave `base` dall'interno di un metodo statico.</span><span class="sxs-lookup"><span data-stu-id="cb996-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="cb996-109">La classe di base alla quale si accede è la classe di base specificata nella dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="cb996-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="cb996-110">Ad esempio, se si specifica `class ClassB : ClassA`, i membri di ClassA sono accessibili da ClassB, indipendentemente dalla classe di base di ClassA.</span><span class="sxs-lookup"><span data-stu-id="cb996-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="cb996-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb996-111">Example</span></span>

<span data-ttu-id="cb996-112">In questo esempio, la classe di base `Person` e la classe derivata `Employee` hanno un metodo denominato `Getinfo`.</span><span class="sxs-lookup"><span data-stu-id="cb996-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="cb996-113">Tramite la parola chiave `base` è possibile chiamare il meotod `Getinfo` sulla classe di base, dall'interno della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="cb996-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

<span data-ttu-id="cb996-114">Per altri esempi, vedere [new](new-modifier.md), [virtual](virtual.md) e [override](override.md).</span><span class="sxs-lookup"><span data-stu-id="cb996-114">For additional examples, see [new](new-modifier.md), [virtual](virtual.md), and [override](override.md).</span></span>

## <a name="example"></a><span data-ttu-id="cb996-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb996-115">Example</span></span>

<span data-ttu-id="cb996-116">Questo esempio illustra come specificare il costruttore della classe di base chiamato durante la creazione di istanze di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="cb996-116">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="cb996-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cb996-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="cb996-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb996-118">See also</span></span>

- [<span data-ttu-id="cb996-119">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="cb996-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cb996-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cb996-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cb996-121">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="cb996-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="cb996-122">this</span><span class="sxs-lookup"><span data-stu-id="cb996-122">this</span></span>](./this.md)
