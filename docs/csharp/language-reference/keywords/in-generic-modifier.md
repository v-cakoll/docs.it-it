---
title: in (Modificatore generico) (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: 17
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
ms.openlocfilehash: 663fa75a7e214ed97efb45dda2c9ac298559653d
ms.contentlocale: it-it
ms.lasthandoff: 08/11/2017

---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="2d936-102">in (Modificatore generico) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2d936-102">in (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="2d936-103">Per i parametri di tipo generico, la parola chiave `in` specifica che il parametro di tipo è controvariante.</span><span class="sxs-lookup"><span data-stu-id="2d936-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="2d936-104">È possibile usare la parola chiave `in` in interfacce e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="2d936-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="2d936-105">La controvarianza consente di usare un tipo meno derivato di quello specificato dal parametro generico.</span><span class="sxs-lookup"><span data-stu-id="2d936-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="2d936-106">Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="2d936-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="2d936-107">Nei parametri di tipo generico la covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="2d936-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="2d936-108">Un tipo può essere dichiarato controvariante in un'interfaccia o in un delegato generico se viene usato solo come tipo di argomenti del metodo e non come tipo restituito dal metodo.</span><span class="sxs-lookup"><span data-stu-id="2d936-108">A type can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="2d936-109">I parametri `Ref` e `out` non possono essere variant.</span><span class="sxs-lookup"><span data-stu-id="2d936-109">`Ref` and `out` parameters cannot be variant.</span></span>  
  
 <span data-ttu-id="2d936-110">Un'interfaccia che dispone di un parametro di tipo controvariante consente ai metodi di accettare argomenti di tipi meno derivati di quelli specificati dal parametro di tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2d936-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="2d936-111">Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IComparer%601>, il tipo T è controvariante, è possibile assegnare un oggetto di tipo `IComparer(Of Person)` a un oggetto di tipo `IComparer(Of Employee)` senza usare alcun metodo di conversione speciale se `Employee` eredita `Person`.</span><span class="sxs-lookup"><span data-stu-id="2d936-111">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>  
  
 <span data-ttu-id="2d936-112">A un delegato controvariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico meno derivato.</span><span class="sxs-lookup"><span data-stu-id="2d936-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
 <span data-ttu-id="2d936-113">Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="2d936-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d936-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="2d936-114">Example</span></span>  
 <span data-ttu-id="2d936-115">L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica controvariante.</span><span class="sxs-lookup"><span data-stu-id="2d936-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="2d936-116">L'esempio descrive anche come usare la conversione implicita per le classi che implementano quest'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2d936-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 <span data-ttu-id="2d936-117">[!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2d936-117">[!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d936-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="2d936-118">Example</span></span>  
 <span data-ttu-id="2d936-119">L'esempio seguente illustra come dichiarare, creare un'istanza e chiamare un delegato generico controvariante.</span><span class="sxs-lookup"><span data-stu-id="2d936-119">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="2d936-120">Illustra anche come convertire in modo implicito un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="2d936-120">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 <span data-ttu-id="2d936-121">[!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2d936-121">[!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2d936-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2d936-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2d936-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d936-123">See Also</span></span>  
 <span data-ttu-id="2d936-124">[out](../../../csharp/language-reference/keywords/out-generic-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="2d936-124">[out](../../../csharp/language-reference/keywords/out-generic-modifier.md) </span></span>  
 <span data-ttu-id="2d936-125">[Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md) </span><span class="sxs-lookup"><span data-stu-id="2d936-125">[Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md) </span></span>  
 [<span data-ttu-id="2d936-126">Modificatori</span><span class="sxs-lookup"><span data-stu-id="2d936-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

