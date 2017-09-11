---
title: sealed (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sealed
- sealed_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a8d0fe959eac03aad4f1ae1fada61c0ad2fd65cd
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="sealed-c-reference"></a><span data-ttu-id="0d272-102">sealed (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0d272-102">sealed (C# Reference)</span></span>
<span data-ttu-id="0d272-103">Quando applicato a una classe, il modificatore `sealed` impedisce che altre classi ereditino da esso.</span><span class="sxs-lookup"><span data-stu-id="0d272-103">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="0d272-104">Nell'esempio seguente, la classe `B` eredita dalla classe `A`, ma nessuna classe può ereditare dalla classe `B`.</span><span class="sxs-lookup"><span data-stu-id="0d272-104">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 <span data-ttu-id="0d272-105">È anche possibile usare il modificatore `sealed` su un metodo o su una proprietà che esegue l'override di un metodo o di una proprietà virtuale in una classe di base.</span><span class="sxs-lookup"><span data-stu-id="0d272-105">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="0d272-106">In questo modo è possibile consentire alle classi di derivare dalla classe e impedire l'override di proprietà o metodi virtuali specifici.</span><span class="sxs-lookup"><span data-stu-id="0d272-106">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d272-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d272-107">Example</span></span>  
 <span data-ttu-id="0d272-108">Nell'esempio seguente, `Z` eredita da `Y` ma `Z` non può eseguire l'override della funzione virtuale `F` dichiarata in `X` e bloccata in `Y`.</span><span class="sxs-lookup"><span data-stu-id="0d272-108">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>  
  
 <span data-ttu-id="0d272-109">[!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0d272-109">[!code-cs[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]</span></span>  
  
 <span data-ttu-id="0d272-110">Quando si definiscono nuovi metodi o proprietà in una classe, è possibile impedire alle classi derivate di eseguire l'override non dichiarandole come [virtuali](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="0d272-110">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
 <span data-ttu-id="0d272-111">È un errore usare il modificatore [abstract](../../../csharp/language-reference/keywords/abstract.md) con una classe sealed, poiché la classe astratta deve essere ereditata da una classe che fornisce un'implementazione dei metodi o delle proprietà astratti.</span><span class="sxs-lookup"><span data-stu-id="0d272-111">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>  
  
 <span data-ttu-id="0d272-112">Quando applicato a un metodo o a una proprietà, il modificatore `sealed` deve sempre essere usato con [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="0d272-112">When applied to a method or property, the `sealed` modifier must always be used with [override](../../../csharp/language-reference/keywords/override.md).</span></span>  
  
 <span data-ttu-id="0d272-113">Poiché gli struct sono sealed in modo implicito, non possono essere ereditati.</span><span class="sxs-lookup"><span data-stu-id="0d272-113">Because structs are implicitly sealed, they cannot be inherited.</span></span>  
  
 <span data-ttu-id="0d272-114">Per altre informazioni, vedere [Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="0d272-114">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="0d272-115">Per altri esempi, vedere [Classi e membri delle classi astratte e sealed](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="0d272-115">For more examples, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d272-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d272-116">Example</span></span>  
 <span data-ttu-id="0d272-117">[!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0d272-117">[!code-cs[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]</span></span>  
  
 <span data-ttu-id="0d272-118">Nell'esempio precedente è possibile ereditare dalla classe sealed tramite l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="0d272-118">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 <span data-ttu-id="0d272-119">Il risultato è un messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="0d272-119">The result is an error message:</span></span>  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="0d272-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0d272-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="0d272-121">Note</span><span class="sxs-lookup"><span data-stu-id="0d272-121">Remarks</span></span>  
 <span data-ttu-id="0d272-122">Per determinare se bloccare una classe, proprietà o metodo, è consigliabile in genere considerare i due punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d272-122">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>  
  
-   <span data-ttu-id="0d272-123">I potenziali vantaggi di cui le classi derivate possono usufruire grazie alla possibilità di personalizzare la classe.</span><span class="sxs-lookup"><span data-stu-id="0d272-123">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>  
  
-   <span data-ttu-id="0d272-124">La possibilità che le classi derivate possono modificare le classi in uso in modo tale che non funzionino più correttamente o come previsto.</span><span class="sxs-lookup"><span data-stu-id="0d272-124">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d272-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d272-125">See Also</span></span>  
 <span data-ttu-id="0d272-126">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d272-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0d272-127">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d272-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0d272-128">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d272-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0d272-129">[Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="0d272-129">[Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
 <span data-ttu-id="0d272-130">[Classi e membri delle classi astratte e sealed](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="0d272-130">[Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span></span>  
 <span data-ttu-id="0d272-131">[Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="0d272-131">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="0d272-132">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="0d272-132">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="0d272-133">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="0d272-133">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 [<span data-ttu-id="0d272-134">virtual</span><span class="sxs-lookup"><span data-stu-id="0d272-134">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)

