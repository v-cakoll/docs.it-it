---
title: Out (modificatore generico) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94d18200e6d7ce0ad63a229223ae77d99302e0e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="out-generic-modifier-visual-basic"></a><span data-ttu-id="9904d-102">Out (modificatore generico) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9904d-102">Out (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="9904d-103">Per i parametri di tipo generico, la `Out` (parola chiave) specifica che il tipo è covariante.</span><span class="sxs-lookup"><span data-stu-id="9904d-103">For generic type parameters, the `Out` keyword specifies that the type is covariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9904d-104">Note</span><span class="sxs-lookup"><span data-stu-id="9904d-104">Remarks</span></span>  
 <span data-ttu-id="9904d-105">La covarianza consente di usare un tipo più derivato di quello specificato dal parametro generico.</span><span class="sxs-lookup"><span data-stu-id="9904d-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="9904d-106">Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="9904d-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="9904d-107">Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="9904d-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9904d-108">Regole</span><span class="sxs-lookup"><span data-stu-id="9904d-108">Rules</span></span>  
 <span data-ttu-id="9904d-109">È possibile usare la parola chiave `Out` in interfacce e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="9904d-109">You can use the `Out` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="9904d-110">In un'interfaccia generica un parametro di tipo può essere dichiarato covariante se soddisfa le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9904d-110">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>  
  
-   <span data-ttu-id="9904d-111">Il parametro di tipo viene usato solo come tipo restituito di metodi di interfaccia e non viene usato come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="9904d-111">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9904d-112">Esiste un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="9904d-112">There is one exception to this rule.</span></span> <span data-ttu-id="9904d-113">Se in un'interfaccia covariante è presente un delegato generico controvariante come parametro del metodo, è possibile usare il tipo covariante come parametro di tipo generico per questo delegato.</span><span class="sxs-lookup"><span data-stu-id="9904d-113">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="9904d-114">Per altre informazioni sui delegati generici covarianti e controvarianti, vedere [Varianza nei delegati](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) e [Uso della varianza per i delegati generici Func e Action](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span><span class="sxs-lookup"><span data-stu-id="9904d-114">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) and [Using Variance for Func and Action Generic Delegates](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span></span>  
  
-   <span data-ttu-id="9904d-115">Il parametro di tipo non viene usato come vincolo generico per i metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9904d-115">The type parameter is not used as a generic constraint for the interface methods.</span></span>  
  
 <span data-ttu-id="9904d-116">In un delegato generico, un parametro di tipo può essere dichiarato covariante se viene utilizzata solo come un tipo restituito del metodo e non per gli argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="9904d-116">In a generic delegate, a type parameter can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>  
  
 <span data-ttu-id="9904d-117">La covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="9904d-117">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="9904d-118">In Visual Basic, è possibile dichiarare gli eventi nelle interfacce covariante senza specificare il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="9904d-118">In Visual Basic, you cannot declare events in covariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="9904d-119">Inoltre, interfacce covariante non possono avere, enumerazioni, strutture o classi annidate, ma può disporre di interfacce annidate.</span><span class="sxs-lookup"><span data-stu-id="9904d-119">Also, covariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="9904d-120">Comportamento</span><span class="sxs-lookup"><span data-stu-id="9904d-120">Behavior</span></span>  
 <span data-ttu-id="9904d-121">Un'interfaccia che dispone di un parametro di tipo covariante consente ai metodi di restituire tipi più derivati di quelli specificati dal parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="9904d-121">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="9904d-122">Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, il tipo T è covariante, è possibile assegnare un oggetto di tipo `IEnumerabe(Of String)` a un oggetto di tipo `IEnumerable(Of Object)` senza usare alcun metodo di conversione speciale.</span><span class="sxs-lookup"><span data-stu-id="9904d-122">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerabe(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>  
  
 <span data-ttu-id="9904d-123">A un delegato covariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico più derivato.</span><span class="sxs-lookup"><span data-stu-id="9904d-123">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9904d-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="9904d-124">Example</span></span>  
 <span data-ttu-id="9904d-125">L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica covariante.</span><span class="sxs-lookup"><span data-stu-id="9904d-125">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="9904d-126">L'esempio descrive anche come usare la conversione implicita per le classi che implementano un'interfaccia covariante.</span><span class="sxs-lookup"><span data-stu-id="9904d-126">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#3](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="9904d-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="9904d-127">Example</span></span>  
 <span data-ttu-id="9904d-128">L'esempio seguente illustra come dichiarare, creare un'istanza e richiamare un delegato generico covariante.</span><span class="sxs-lookup"><span data-stu-id="9904d-128">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="9904d-129">Spiega inoltre come è possibile utilizzare la conversione implicita per i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="9904d-129">It also shows how you can use implicit conversion for delegate types.</span></span>  
  
 [!code-vb[vbVarianceKeywords#4](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9904d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9904d-130">See Also</span></span>  
 [<span data-ttu-id="9904d-131">Varianza nelle interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="9904d-131">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="9904d-132">In</span><span class="sxs-lookup"><span data-stu-id="9904d-132">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
