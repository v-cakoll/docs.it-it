---
title: base (Riferimenti per C#)
description: Informazioni sulla parola chiave base, usata per accedere ai membri della classe di base dall'interno di una classe derivata in C#.
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: b3a389d92373b6ba5995a7644b0440f9d8fad9ac
ms.contentlocale: it-it
ms.lasthandoff: 08/17/2017

---
# <a name="base-c-reference"></a><span data-ttu-id="f2b90-103">base (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f2b90-103">base (C# Reference)</span></span>

<span data-ttu-id="f2b90-104">La parola chiave `base` viene usata per accedere ai membri della classe di base dall'interno di una classe derivata:</span><span class="sxs-lookup"><span data-stu-id="f2b90-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="f2b90-105">Chiamare un metodo sulla classe di base che è stato sostituito da un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="f2b90-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="f2b90-106">Specificare quale costruttore di classe di base deve essere chiamato durante la creazione di istanze della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="f2b90-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="f2b90-107">Una classe di base di accesso è consentita solo in un costruttore, in un metodo di istanza o in una funzione di accesso alla proprietà dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="f2b90-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="f2b90-108">Non è possibile usare la parola chiave `base` dall'interno di un metodo statico.</span><span class="sxs-lookup"><span data-stu-id="f2b90-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="f2b90-109">La classe di base alla quale si accede è la classe di base specificata nella dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="f2b90-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="f2b90-110">Ad esempio, se si specifica `class ClassB : ClassA`, i membri di ClassA sono accessibili da ClassB, indipendentemente dalla classe di base di ClassA.</span><span class="sxs-lookup"><span data-stu-id="f2b90-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="f2b90-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2b90-111">Example</span></span>
<span data-ttu-id="f2b90-112">In questo esempio, la classe di base `Person` e la classe derivata `Employee` hanno un metodo denominato `Getinfo`.</span><span class="sxs-lookup"><span data-stu-id="f2b90-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="f2b90-113">Tramite la parola chiave `base` è possibile chiamare il meotod `Getinfo` sulla classe di base, dall'interno della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="f2b90-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

<span data-ttu-id="f2b90-114">[!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2b90-114">[!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]</span></span>

<span data-ttu-id="f2b90-115">Per altri esempi, vedere [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) e [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="f2b90-115">For additional examples, see [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md), and [override](../../../csharp/language-reference/keywords/override.md).</span></span>

## <a name="example"></a><span data-ttu-id="f2b90-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2b90-116">Example</span></span>
<span data-ttu-id="f2b90-117">Questo esempio illustra come specificare il costruttore della classe di base chiamato durante la creazione di istanze di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="f2b90-117">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

<span data-ttu-id="f2b90-118">[!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2b90-118">[!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f2b90-119">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f2b90-119">C# language specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f2b90-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2b90-120">See also</span></span>
 <span data-ttu-id="f2b90-121">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2b90-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f2b90-122">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2b90-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f2b90-123">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2b90-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="f2b90-124">this</span><span class="sxs-lookup"><span data-stu-id="f2b90-124">this</span></span>](../../../csharp/language-reference/keywords/this.md)
