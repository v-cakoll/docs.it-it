---
title: In (modificatore generico) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: d1d9209cd583ac96ece59660ad29c76a66d3395a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597432"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="a7988-102">In (modificatore generico) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7988-102">In (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="a7988-103">Per i parametri di tipo generico, la parola chiave `In` specifica che il parametro di tipo è controvariante.</span><span class="sxs-lookup"><span data-stu-id="a7988-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7988-104">Note</span><span class="sxs-lookup"><span data-stu-id="a7988-104">Remarks</span></span>  
 <span data-ttu-id="a7988-105">La controvarianza consente di usare un tipo meno derivato di quello specificato dal parametro generico.</span><span class="sxs-lookup"><span data-stu-id="a7988-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="a7988-106">Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="a7988-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="a7988-107">Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="a7988-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a7988-108">Regole</span><span class="sxs-lookup"><span data-stu-id="a7988-108">Rules</span></span>  
 <span data-ttu-id="a7988-109">È possibile usare la parola chiave `In` in interfacce e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="a7988-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="a7988-110">Un parametro di tipo può essere dichiarato controvariante in un'interfaccia generica o delegato se viene utilizzata solo come tipo di argomenti del metodo e non come un tipo restituito del metodo.</span><span class="sxs-lookup"><span data-stu-id="a7988-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="a7988-111">`ByRef` parametri non possono essere di tipo covarianti o controvariante.</span><span class="sxs-lookup"><span data-stu-id="a7988-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>  
  
 <span data-ttu-id="a7988-112">Covarianza e controvarianza sono supportate per i tipi di riferimento e non è supportate per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="a7988-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>  
  
 <span data-ttu-id="a7988-113">In Visual Basic, è possibile dichiarare gli eventi nelle interfacce controvarianti senza specificare il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="a7988-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="a7988-114">Inoltre, interfacce controvariante non è possibile avere, enumerazioni, strutture o classi annidate, ma può disporre di interfacce annidate.</span><span class="sxs-lookup"><span data-stu-id="a7988-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a7988-115">Comportamento</span><span class="sxs-lookup"><span data-stu-id="a7988-115">Behavior</span></span>  
 <span data-ttu-id="a7988-116">Un'interfaccia che dispone di un parametro di tipo controvariante consente ai metodi di accettare argomenti di tipi meno derivati di quelli specificati dal parametro di tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a7988-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="a7988-117">Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IComparer%601>, il tipo T è controvariante, è possibile assegnare un oggetto di tipo `IComparer(Of Person)` a un oggetto di tipo `IComparer(Of Employee)` senza usare alcun metodo di conversione speciale se `Person` eredita `Employee`.</span><span class="sxs-lookup"><span data-stu-id="a7988-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Person` inherits `Employee`.</span></span>  
  
 <span data-ttu-id="a7988-118">A un delegato controvariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico meno derivato.</span><span class="sxs-lookup"><span data-stu-id="a7988-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7988-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7988-119">Example</span></span>  
 <span data-ttu-id="a7988-120">L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica controvariante.</span><span class="sxs-lookup"><span data-stu-id="a7988-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="a7988-121">L'esempio descrive anche come usare la conversione implicita per le classi che implementano quest'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a7988-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="a7988-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7988-122">Example</span></span>  
 <span data-ttu-id="a7988-123">L'esempio seguente illustra come dichiarare, creare un'istanza e chiamare un delegato generico controvariante.</span><span class="sxs-lookup"><span data-stu-id="a7988-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="a7988-124">Illustra anche come convertire in modo implicito un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="a7988-124">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-vb[vbVarianceKeywords#2](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a7988-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7988-125">See Also</span></span>  
 [<span data-ttu-id="a7988-126">Varianza nelle interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="a7988-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="a7988-127">Out</span><span class="sxs-lookup"><span data-stu-id="a7988-127">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
