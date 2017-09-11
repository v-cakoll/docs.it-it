---
title: Espressioni con valore predefinito (Guida per programmatori C#)
description: Le espressioni con valore predefinito producono il valore predefinito per qualsiasi tipo riferimento o tipo valore
ms.date: 2017-08-23
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: 7b5b53d7ed92c6f6377a3e494daf1d02a4cf0934
ms.contentlocale: it-it
ms.lasthandoff: 08/28/2017

---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="3f9d7-103">espressioni con valore predefinito (guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3f9d7-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="3f9d7-104">Un'espressione con valore predefinito produce il valore predefinito per un tipo.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-104">A default value expression produces the default value for a type.</span></span> <span data-ttu-id="3f9d7-105">Le espressioni con valore predefinito risultano particolarmente utili nelle classi e nei metodi generici.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-105">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="3f9d7-106">Un problema relativo all'uso dei metodi generici riguarda l'assegnazione di un valore predefinito a un tipo con parametri `T` quando non è noto quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3f9d7-106">One issue that arises using generics is how to assign a default value to a parameterized type `T` when you do not know the following in advance:</span></span>

- <span data-ttu-id="3f9d7-107">Se `T` è un tipo riferimento o un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-107">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="3f9d7-108">Nel caso in cui `T` sia un tipo valore, se è un valore numerico o uno struct definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-108">If `T` is a value type, whether is a numeric value or a user-defined struct.</span></span>

 <span data-ttu-id="3f9d7-109">Data una variabile `t` di un tipo con parametri `T`, l'istruzione `t = null` è valida solo se `T` è un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-109">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="3f9d7-110">L'assegnazione `t = 0` funziona solo per i tipi di valore numerico ma non per gli struct.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-110">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="3f9d7-111">La soluzione consiste nell'usare un'espressione con valore predefinito, che restituisce `null` per i tipi di riferimento (tipi di classe e tipi di interfaccia) e zero per i tipi di valore numerico.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-111">The solution is to use a default value expression, which returns `null` for reference types (class types and interface types) and zero for numeric value types.</span></span> <span data-ttu-id="3f9d7-112">Per gli struct definiti dall'utente restituisce lo struct inizializzato in base allo schema di bit zero, che produce 0 o `null` per ogni membro, in base al fatto che il tipo del membro sia valore o riferimento.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-112">For user-defined structs, it returns the struct initialized to the zero bit pattern, which produces 0 or `null` for each member depending on whether that member is a value or reference type.</span></span> <span data-ttu-id="3f9d7-113">Per i tipi di valore nullable, `default` restituisce <xref:System.Nullable%601?displayProperty=fullName>, che viene inizializzato come qualsiasi struct.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-113">For nullable value types, `default` returns a <xref:System.Nullable%601?displayProperty=fullName>, which is initialized like any struct.</span></span>

<span data-ttu-id="3f9d7-114">L'espressione `default(T)` non è limitata a classi e metodi generici.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-114">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="3f9d7-115">Le espressioni con valore predefinito possono essere usate con qualsiasi tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-115">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="3f9d7-116">Tutte le espressioni seguenti sono valide:</span><span class="sxs-lookup"><span data-stu-id="3f9d7-116">Any of these expressions are valid:</span></span>

 <span data-ttu-id="3f9d7-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span><span class="sxs-lookup"><span data-stu-id="3f9d7-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span></span>

 <span data-ttu-id="3f9d7-118">L'esempio seguente dalla classe `GenericList<T>` mostra come usare l'operatore `default(T)` in una classe generica.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-118">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="3f9d7-119">Per altre informazioni, vedere [Generics Overview](../generics/introduction-to-generics.md) (Panoramica dei generics).</span><span class="sxs-lookup"><span data-stu-id="3f9d7-119">For more information, see [Generics Overview](../generics/introduction-to-generics.md).</span></span>

 <span data-ttu-id="3f9d7-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span><span class="sxs-lookup"><span data-stu-id="3f9d7-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span></span>

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="3f9d7-121">Valore letterale e inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="3f9d7-121">default literal and type inference</span></span>

<span data-ttu-id="3f9d7-122">A partire dalla versione C# 7.1, il valore letterale `default` può essere usato per le espressioni con valore predefinito quando il compilatore è in grado di eseguire l'inferenza del tipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-122">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="3f9d7-123">Il valore letterale `default` produce lo stesso valore dell'equivalente `default(T)` dove `T` è il tipo dedotto.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-123">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="3f9d7-124">Questo approccio può consentire di rendere più conciso il codice, riducendo la ridondanza dovuta alla dichiarazione ripetuta di un tipo.</span><span class="sxs-lookup"><span data-stu-id="3f9d7-124">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="3f9d7-125">Il valore letterale `default` può essere usato in una qualsiasi delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f9d7-125">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="3f9d7-126">Inizializzatore di variabile</span><span class="sxs-lookup"><span data-stu-id="3f9d7-126">variable initializer</span></span>
- <span data-ttu-id="3f9d7-127">assegnazione di variabili</span><span class="sxs-lookup"><span data-stu-id="3f9d7-127">variable assignment</span></span>
- <span data-ttu-id="3f9d7-128">Dichiarazione del valore predefinito per un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="3f9d7-128">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="3f9d7-129">Specifica del valore per l'argomento della chiamata di un metodo</span><span class="sxs-lookup"><span data-stu-id="3f9d7-129">providing the value for a method call argument</span></span>
- <span data-ttu-id="3f9d7-130">Istruzione return (o espressione in un membro con corpo di espressione)</span><span class="sxs-lookup"><span data-stu-id="3f9d7-130">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="3f9d7-131">L'esempio seguente mostra molti utilizzi del valore letterale `default` in un'espressione con valore predefinito:</span><span class="sxs-lookup"><span data-stu-id="3f9d7-131">The following example shows many usages of the `default` literal in a default value expression:</span></span>

<span data-ttu-id="3f9d7-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span><span class="sxs-lookup"><span data-stu-id="3f9d7-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3f9d7-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f9d7-133">See also</span></span>

 <span data-ttu-id="3f9d7-134"><xref:System.Collections.Generic> [Guida per programmatori C#](../index.md) </span><span class="sxs-lookup"><span data-stu-id="3f9d7-134"><xref:System.Collections.Generic> [C# Programming Guide](../index.md) </span></span>  
 <span data-ttu-id="3f9d7-135">[Generics](../generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f9d7-135">[Generics](../generics/index.md) </span></span>  
 <span data-ttu-id="3f9d7-136">[Metodi generici](../generics/generic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="3f9d7-136">[Generic Methods](../generics/generic-methods.md) </span></span>  
 [<span data-ttu-id="3f9d7-137">Generics</span><span class="sxs-lookup"><span data-stu-id="3f9d7-137">Generics</span></span>](~/docs/standard/generics/index.md)   

