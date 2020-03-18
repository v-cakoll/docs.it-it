---
title: Operatori di conversione definiti dall'utente - Riferimenti per C#
description: Informazioni su come definire conversioni di tipi impliciti ed espliciti personalizzate in C#.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: b6061492cc1a4f756196fb8a9050b68651431e38
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847267"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="f0535-103">Operatori di conversione definiti dall'utente (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f0535-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="f0535-104">Un tipo definito dall'utente può definire una conversione implicita o esplicita da o in un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="f0535-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="f0535-105">Le conversioni implicite non richiedono una sintassi specifica per essere richiamate e possono essere usate in diverse situazioni, ad esempio durante le chiamate di metodi e assegnazioni.</span><span class="sxs-lookup"><span data-stu-id="f0535-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="f0535-106">Le conversioni implicite predefinite di C' hanno sempre esito positivo e non generano mai un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f0535-106">Predefined C# implicit conversions always succeed and never throw an exception.</span></span> <span data-ttu-id="f0535-107">Anche le conversioni implicite definite dall'utente si devono comportare nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="f0535-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="f0535-108">Se una conversione personalizzata può generare un'eccezione o una perdita di informazioni, è necessario definirla come conversione esplicita.</span><span class="sxs-lookup"><span data-stu-id="f0535-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="f0535-109">Le conversioni definite dall'utente non vengono considerate dagli operatori [is](type-testing-and-cast.md#is-operator) e [as](type-testing-and-cast.md#as-operator).</span><span class="sxs-lookup"><span data-stu-id="f0535-109">User-defined conversions are not considered by the [is](type-testing-and-cast.md#is-operator) and [as](type-testing-and-cast.md#as-operator) operators.</span></span> <span data-ttu-id="f0535-110">Usare l'[operatore cast ()](type-testing-and-cast.md#cast-operator-) per richiamare una conversione esplicita definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f0535-110">Use the [cast operator ()](type-testing-and-cast.md#cast-operator-) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="f0535-111">Usare `operator` e `implicit` o le parole chiave `explicit` per definire rispettivamente una conversione implicita o esplicita.</span><span class="sxs-lookup"><span data-stu-id="f0535-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="f0535-112">Il tipo che definisce una conversione deve essere un tipo di origine o un tipo di destinazione della conversione.</span><span class="sxs-lookup"><span data-stu-id="f0535-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="f0535-113">È possibile definire una conversione tra due tipi definiti dall'utente in uno dei due tipi.</span><span class="sxs-lookup"><span data-stu-id="f0535-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="f0535-114">L'esempio seguente illustra come definire una conversione implicita ed esplicita:</span><span class="sxs-lookup"><span data-stu-id="f0535-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](snippets/UserDefinedConversions.cs)]

<span data-ttu-id="f0535-115">È anche possibile usare la parola chiave `operator` per eseguire l'overload di un operatore C# predefinito.</span><span class="sxs-lookup"><span data-stu-id="f0535-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="f0535-116">Per altre informazioni, vedere [Overload degli operatori](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="f0535-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f0535-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f0535-117">C# language specification</span></span>

<span data-ttu-id="f0535-118">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="f0535-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="f0535-119">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="f0535-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="f0535-120">Conversioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="f0535-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="f0535-121">Conversioni implicite</span><span class="sxs-lookup"><span data-stu-id="f0535-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="f0535-122">Conversioni espliciteExplicit conversions</span><span class="sxs-lookup"><span data-stu-id="f0535-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="f0535-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0535-123">See also</span></span>

- [<span data-ttu-id="f0535-124">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="f0535-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f0535-125">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="f0535-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="f0535-126">Sovraccarico dell'operatore</span><span class="sxs-lookup"><span data-stu-id="f0535-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="f0535-127">Operatori di cast e di test del tipo</span><span class="sxs-lookup"><span data-stu-id="f0535-127">Type-testing and cast operators</span></span>](type-testing-and-cast.md)
- [<span data-ttu-id="f0535-128">Esecuzione del cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="f0535-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="f0535-129">Linee guida di progettazione - Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="f0535-129">Design guidelines - Conversion operators</span></span>](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- [<span data-ttu-id="f0535-130">Conversioni esplicite concatenate definite dall'utente in C#</span><span class="sxs-lookup"><span data-stu-id="f0535-130">Chained user-defined explicit conversions in C#</span></span>](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)
