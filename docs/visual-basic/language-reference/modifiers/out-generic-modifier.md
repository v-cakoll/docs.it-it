---
title: Out (modificatore generico)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: 28ae7d6fd51170aa822072fc2f5357443f51a353
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392093"
---
# <a name="out-generic-modifier-visual-basic"></a><span data-ttu-id="d81ee-102">Out (modificatore generico) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d81ee-102">Out (Generic Modifier) (Visual Basic)</span></span>

<span data-ttu-id="d81ee-103">Per i parametri di tipo generico, la `Out` parola chiave specifica che il tipo è covariante.</span><span class="sxs-lookup"><span data-stu-id="d81ee-103">For generic type parameters, the `Out` keyword specifies that the type is covariant.</span></span>

## <a name="remarks"></a><span data-ttu-id="d81ee-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="d81ee-104">Remarks</span></span>

<span data-ttu-id="d81ee-105">La covarianza consente di usare un tipo più derivato di quello specificato dal parametro generico.</span><span class="sxs-lookup"><span data-stu-id="d81ee-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="d81ee-106">Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="d81ee-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>

<span data-ttu-id="d81ee-107">Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="d81ee-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="d81ee-108">Regole</span><span class="sxs-lookup"><span data-stu-id="d81ee-108">Rules</span></span>

<span data-ttu-id="d81ee-109">È possibile usare la parola chiave `Out` in interfacce e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="d81ee-109">You can use the `Out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="d81ee-110">In un'interfaccia generica un parametro di tipo può essere dichiarato covariante se soddisfa le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d81ee-110">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="d81ee-111">Il parametro di tipo viene usato solo come tipo restituito di metodi di interfaccia e non viene usato come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="d81ee-111">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d81ee-112">Esiste un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="d81ee-112">There is one exception to this rule.</span></span> <span data-ttu-id="d81ee-113">Se in un'interfaccia covariante è presente un delegato generico controvariante come parametro del metodo, è possibile usare il tipo covariante come parametro di tipo generico per questo delegato.</span><span class="sxs-lookup"><span data-stu-id="d81ee-113">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="d81ee-114">Per altre informazioni sui delegati generici covarianti e controvarianti, vedere [Varianza nei delegati](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) e [Uso della varianza per i delegati generici Func e Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="d81ee-114">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="d81ee-115">Il parametro di tipo non viene usato come vincolo generico per i metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d81ee-115">The type parameter is not used as a generic constraint for the interface methods.</span></span>

<span data-ttu-id="d81ee-116">In un delegato generico, un parametro di tipo può essere dichiarato covariante se viene usato solo come tipo restituito del metodo e non usato per gli argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="d81ee-116">In a generic delegate, a type parameter can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

<span data-ttu-id="d81ee-117">La covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="d81ee-117">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="d81ee-118">In Visual Basic non è possibile dichiarare gli eventi nelle interfacce covariante senza specificare il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="d81ee-118">In Visual Basic, you cannot declare events in covariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="d81ee-119">Inoltre, le interfacce covariante non possono avere classi, enumerazioni o strutture annidate, ma possono avere interfacce nidificate.</span><span class="sxs-lookup"><span data-stu-id="d81ee-119">Also, covariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>

## <a name="behavior"></a><span data-ttu-id="d81ee-120">Comportamento</span><span class="sxs-lookup"><span data-stu-id="d81ee-120">Behavior</span></span>

<span data-ttu-id="d81ee-121">Un'interfaccia che dispone di un parametro di tipo covariante consente ai metodi di restituire tipi più derivati di quelli specificati dal parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="d81ee-121">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="d81ee-122">Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, il tipo T è covariante, è possibile assegnare un oggetto di tipo `IEnumerable(Of String)` a un oggetto di tipo `IEnumerable(Of Object)` senza usare alcun metodo di conversione speciale.</span><span class="sxs-lookup"><span data-stu-id="d81ee-122">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="d81ee-123">A un delegato covariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico più derivato.</span><span class="sxs-lookup"><span data-stu-id="d81ee-123">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="d81ee-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="d81ee-124">Example</span></span>

<span data-ttu-id="d81ee-125">L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica covariante.</span><span class="sxs-lookup"><span data-stu-id="d81ee-125">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="d81ee-126">L'esempio descrive anche come usare la conversione implicita per le classi che implementano un'interfaccia covariante.</span><span class="sxs-lookup"><span data-stu-id="d81ee-126">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-vb[vbVarianceKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="d81ee-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="d81ee-127">Example</span></span>

<span data-ttu-id="d81ee-128">L'esempio seguente illustra come dichiarare, creare un'istanza e richiamare un delegato generico covariante.</span><span class="sxs-lookup"><span data-stu-id="d81ee-128">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="d81ee-129">Viene inoltre illustrato come è possibile utilizzare la conversione implicita per i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="d81ee-129">It also shows how you can use implicit conversion for delegate types.</span></span>

[!code-vb[vbVarianceKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="d81ee-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d81ee-130">See also</span></span>

- [<span data-ttu-id="d81ee-131">Varianza nelle interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="d81ee-131">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="d81ee-132">In</span><span class="sxs-lookup"><span data-stu-id="d81ee-132">In</span></span>](in-generic-modifier.md)
