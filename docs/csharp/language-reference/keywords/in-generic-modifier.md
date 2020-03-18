---
title: in (modificatore generico) - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: 57da13f6dc6719166b9051afeb2532ba5fbeff3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713479"
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="d2b47-102">in (Modificatore generico) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d2b47-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="d2b47-103">Per i parametri di tipo generico, la parola chiave `in` specifica che il parametro di tipo è controvariante.</span><span class="sxs-lookup"><span data-stu-id="d2b47-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="d2b47-104">È possibile usare la parola chiave `in` in interfacce e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="d2b47-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="d2b47-105">La controvarianza consente di usare un tipo meno derivato di quello specificato dal parametro generico.</span><span class="sxs-lookup"><span data-stu-id="d2b47-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="d2b47-106">Ciò consente la conversione implicita di classi che implementano interfacce controvarianti e la conversione implicita di tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="d2b47-106">This allows for implicit conversion of classes that implement contravariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="d2b47-107">Nei parametri di tipo generico la covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="d2b47-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="d2b47-108">Un tipo può essere dichiarato controvariante in un'interfaccia o in un delegato generico solo se definisce il tipo dei parametri di un metodo e non di un tipo restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="d2b47-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="d2b47-109">I parametri `In`, `ref` e `out` devono essere invarianti, ovvero non sono né covariante né controvariante.</span><span class="sxs-lookup"><span data-stu-id="d2b47-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>

<span data-ttu-id="d2b47-110">Un'interfaccia che dispone di un parametro di tipo controvariante consente ai metodi di accettare argomenti di tipi meno derivati di quelli specificati dal parametro di tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d2b47-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="d2b47-111">Ad esempio, nell'interfaccia <xref:System.Collections.Generic.IComparer%601>, il tipo T è controvariante, è possibile assegnare un oggetto di tipo `IComparer<Person>` a un oggetto di tipo `IComparer<Employee>` senza usare alcun metodo di conversione speciale se `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="d2b47-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>

<span data-ttu-id="d2b47-112">A un delegato controvariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico meno derivato.</span><span class="sxs-lookup"><span data-stu-id="d2b47-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

<span data-ttu-id="d2b47-113">Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="d2b47-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="contravariant-generic-interface"></a><span data-ttu-id="d2b47-114">Interfaccia generica controvariante</span><span class="sxs-lookup"><span data-stu-id="d2b47-114">Contravariant generic interface</span></span>

<span data-ttu-id="d2b47-115">L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica controvariante.</span><span class="sxs-lookup"><span data-stu-id="d2b47-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="d2b47-116">L'esempio descrive anche come usare la conversione implicita per le classi che implementano quest'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d2b47-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-csharp[csVarianceKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#1)]

## <a name="contravariant-generic-delegate"></a><span data-ttu-id="d2b47-117">Delegato generico controvariante</span><span class="sxs-lookup"><span data-stu-id="d2b47-117">Contravariant generic delegate</span></span>

<span data-ttu-id="d2b47-118">L'esempio seguente illustra come dichiarare, creare un'istanza e chiamare un delegato generico controvariante.</span><span class="sxs-lookup"><span data-stu-id="d2b47-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="d2b47-119">Illustra anche come convertire in modo implicito un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="d2b47-119">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-csharp[csVarianceKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="d2b47-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d2b47-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d2b47-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2b47-121">See also</span></span>

- [<span data-ttu-id="d2b47-122">Cambio</span><span class="sxs-lookup"><span data-stu-id="d2b47-122">out</span></span>](out-generic-modifier.md)
- [<span data-ttu-id="d2b47-123">Covarianza e controvarianza</span><span class="sxs-lookup"><span data-stu-id="d2b47-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="d2b47-124">Modificatori</span><span class="sxs-lookup"><span data-stu-id="d2b47-124">Modifiers</span></span>](index.md)
