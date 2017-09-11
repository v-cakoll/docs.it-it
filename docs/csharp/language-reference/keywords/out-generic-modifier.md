---
title: out (Modificatore generico) (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
caps.latest.revision: 15
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
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: a560a0307723d32750a7e26ad4ee1afec360a849
ms.contentlocale: it-it
ms.lasthandoff: 08/11/2017

---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="d3e36-102">out (Modificatore generico) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d3e36-102">out (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="d3e36-103">Per i parametri di tipo generico, la parola chiave `out` specifica che il parametro di tipo è covariante.</span><span class="sxs-lookup"><span data-stu-id="d3e36-103">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="d3e36-104">È possibile usare la parola chiave `out` in interfacce e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="d3e36-104">You can use the `out` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="d3e36-105">La covarianza consente di usare un tipo più derivato di quello specificato dal parametro generico.</span><span class="sxs-lookup"><span data-stu-id="d3e36-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="d3e36-106">Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="d3e36-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="d3e36-107">La covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="d3e36-107">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="d3e36-108">Un'interfaccia che dispone di un parametro di tipo covariante consente ai metodi di restituire tipi più derivati di quelli specificati dal parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="d3e36-108">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="d3e36-109">Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, il tipo T è covariante, è possibile assegnare un oggetto di tipo `IEnumerabe(Of String)` a un oggetto di tipo `IEnumerable(Of Object)` senza usare alcun metodo di conversione speciale.</span><span class="sxs-lookup"><span data-stu-id="d3e36-109">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerabe(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>  
  
 <span data-ttu-id="d3e36-110">A un delegato covariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico più derivato.</span><span class="sxs-lookup"><span data-stu-id="d3e36-110">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>  
  
 <span data-ttu-id="d3e36-111">Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="d3e36-111">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3e36-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3e36-112">Example</span></span>  
 <span data-ttu-id="d3e36-113">L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica covariante.</span><span class="sxs-lookup"><span data-stu-id="d3e36-113">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="d3e36-114">L'esempio descrive anche come usare la conversione implicita per le classi che implementano un'interfaccia covariante.</span><span class="sxs-lookup"><span data-stu-id="d3e36-114">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>  
  
 <span data-ttu-id="d3e36-115">[!code-cs[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3e36-115">[!code-cs[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]</span></span>  
  
 <span data-ttu-id="d3e36-116">In un'interfaccia generica un parametro di tipo può essere dichiarato covariante se soddisfa le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3e36-116">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>  
  
-   <span data-ttu-id="d3e36-117">Il parametro di tipo viene usato solo come tipo restituito di metodi di interfaccia e non viene usato come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="d3e36-117">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3e36-118">Esiste un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="d3e36-118">There is one exception to this rule.</span></span> <span data-ttu-id="d3e36-119">Se in un'interfaccia covariante è presente un delegato generico controvariante come parametro del metodo, è possibile usare il tipo covariante come parametro di tipo generico per questo delegato.</span><span class="sxs-lookup"><span data-stu-id="d3e36-119">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="d3e36-120">Per altre informazioni sui delegati generici covarianti e controvarianti, vedere [Varianza nei delegati](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) e [Uso della varianza per i delegati generici Func e Action](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span><span class="sxs-lookup"><span data-stu-id="d3e36-120">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) and [Using Variance for Func and Action Generic Delegates](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span></span>  
  
-   <span data-ttu-id="d3e36-121">Il parametro di tipo non viene usato come vincolo generico per i metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d3e36-121">The type parameter is not used as a generic constraint for the interface methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3e36-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3e36-122">Example</span></span>  
 <span data-ttu-id="d3e36-123">L'esempio seguente illustra come dichiarare, creare un'istanza e richiamare un delegato generico covariante.</span><span class="sxs-lookup"><span data-stu-id="d3e36-123">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="d3e36-124">Viene anche descritto come convertire in modo implicito i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="d3e36-124">It also shows how to implicitly convert delegate types.</span></span>  
  
 <span data-ttu-id="d3e36-125">[!code-cs[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3e36-125">[!code-cs[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]</span></span>  
  
 <span data-ttu-id="d3e36-126">In un delegato generico un tipo può essere dichiarato covariante se viene usato solo come tipo restituito del metodo e non per gli argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="d3e36-126">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d3e36-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d3e36-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3e36-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3e36-128">See Also</span></span>  
 <span data-ttu-id="d3e36-129">[Varianza nelle interfacce generiche](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="d3e36-129">[Variance in Generic Interfaces](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span></span>  
 <span data-ttu-id="d3e36-130">[in](../../../csharp/language-reference/keywords/in-generic-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="d3e36-130">[in](../../../csharp/language-reference/keywords/in-generic-modifier.md) </span></span>  
 [<span data-ttu-id="d3e36-131">Modificatori</span><span class="sxs-lookup"><span data-stu-id="d3e36-131">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

