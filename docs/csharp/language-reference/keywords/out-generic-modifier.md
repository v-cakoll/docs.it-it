---
title: Parola chiave out (modificatore generico) - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
ms.openlocfilehash: 97ddae2efe55be89840f7a483c18d61259020283
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713293"
---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="7ad00-102">out (modificatore generico) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7ad00-102">out (generic modifier) (C# Reference)</span></span>

<span data-ttu-id="7ad00-103">Per i parametri di tipo generico, la parola chiave `out` specifica che il parametro di tipo è covariante.</span><span class="sxs-lookup"><span data-stu-id="7ad00-103">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="7ad00-104">È possibile usare la parola chiave `out` in interfacce e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="7ad00-104">You can use the `out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="7ad00-105">La covarianza consente di usare un tipo più derivato di quello specificato dal parametro generico.</span><span class="sxs-lookup"><span data-stu-id="7ad00-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="7ad00-106">Ciò consente la conversione implicita di classi che implementano interfacce covarianti e la conversione implicita di tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="7ad00-106">This allows for implicit conversion of classes that implement covariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="7ad00-107">La covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="7ad00-107">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="7ad00-108">Un'interfaccia che dispone di un parametro di tipo covariante consente ai metodi di restituire tipi più derivati di quelli specificati dal parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="7ad00-108">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="7ad00-109">Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, il tipo T è covariante, è possibile assegnare un oggetto di tipo `IEnumerable(Of String)` a un oggetto di tipo `IEnumerable(Of Object)` senza usare alcun metodo di conversione speciale.</span><span class="sxs-lookup"><span data-stu-id="7ad00-109">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="7ad00-110">A un delegato covariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico più derivato.</span><span class="sxs-lookup"><span data-stu-id="7ad00-110">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

<span data-ttu-id="7ad00-111">Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="7ad00-111">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="example---covariant-generic-interface"></a><span data-ttu-id="7ad00-112">Esempio: interfaccia generica covariante</span><span class="sxs-lookup"><span data-stu-id="7ad00-112">Example - covariant generic interface</span></span>

<span data-ttu-id="7ad00-113">L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica covariante.</span><span class="sxs-lookup"><span data-stu-id="7ad00-113">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="7ad00-114">L'esempio descrive anche come usare la conversione implicita per le classi che implementano un'interfaccia covariante.</span><span class="sxs-lookup"><span data-stu-id="7ad00-114">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-csharp[csVarianceKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#3)]

<span data-ttu-id="7ad00-115">In un'interfaccia generica un parametro di tipo può essere dichiarato covariante se soddisfa le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ad00-115">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="7ad00-116">Il parametro di tipo viene usato solo come tipo restituito di metodi di interfaccia e non viene usato come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="7ad00-116">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7ad00-117">Esiste un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="7ad00-117">There is one exception to this rule.</span></span> <span data-ttu-id="7ad00-118">Se in un'interfaccia covariante è presente un delegato generico controvariante come parametro del metodo, è possibile usare il tipo covariante come parametro di tipo generico per questo delegato.</span><span class="sxs-lookup"><span data-stu-id="7ad00-118">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="7ad00-119">Per altre informazioni sui delegati generici covarianti e controvarianti, vedere [Varianza nei delegati](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) e [Uso della varianza per i delegati generici Func e Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="7ad00-119">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="7ad00-120">Il parametro di tipo non viene usato come vincolo generico per i metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7ad00-120">The type parameter is not used as a generic constraint for the interface methods.</span></span>

## <a name="example---covariant-generic-delegate"></a><span data-ttu-id="7ad00-121">Esempio: delegato generico covariante</span><span class="sxs-lookup"><span data-stu-id="7ad00-121">Example - covariant generic delegate</span></span>

<span data-ttu-id="7ad00-122">L'esempio seguente illustra come dichiarare, creare un'istanza e richiamare un delegato generico covariante.</span><span class="sxs-lookup"><span data-stu-id="7ad00-122">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="7ad00-123">Viene anche descritto come convertire in modo implicito i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="7ad00-123">It also shows how to implicitly convert delegate types.</span></span>

[!code-csharp[csVarianceKeywords#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#4)]

<span data-ttu-id="7ad00-124">In un delegato generico un tipo può essere dichiarato covariante se viene usato solo come tipo restituito del metodo e non per gli argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="7ad00-124">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7ad00-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7ad00-125">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7ad00-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ad00-126">See also</span></span>

- [<span data-ttu-id="7ad00-127">Varianza nelle interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="7ad00-127">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="7ad00-128">in</span><span class="sxs-lookup"><span data-stu-id="7ad00-128">in</span></span>](in-generic-modifier.md)
- [<span data-ttu-id="7ad00-129">Modificatori</span><span class="sxs-lookup"><span data-stu-id="7ad00-129">Modifiers</span></span>](index.md)
