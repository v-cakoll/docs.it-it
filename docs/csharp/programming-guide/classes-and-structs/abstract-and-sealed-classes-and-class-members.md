---
title: Classi e membri delle classi astratte e sealed (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0788ea0778b3f8b846231fc2408938b2236314c9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a><span data-ttu-id="d875a-102">Classi e membri delle classi astratte e sealed (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d875a-102">Abstract and Sealed Classes and Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="d875a-103">La parola chiave [abstract](../../../csharp/language-reference/keywords/abstract.md) consente di creare classi e membri di [classe](../../../csharp/language-reference/keywords/class.md), che sono incompleti e devono essere implementati in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d875a-103">The [abstract](../../../csharp/language-reference/keywords/abstract.md) keyword enables you to create classes and [class](../../../csharp/language-reference/keywords/class.md) members that are incomplete and must be implemented in a derived class.</span></span>  
  
 <span data-ttu-id="d875a-104">La parola chiave [sealed](../../../csharp/language-reference/keywords/sealed.md) consente di impedire l'ereditarietà di una classe o di determinati membri di classe contrassegnati in precedenza come [virtuali](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="d875a-104">The [sealed](../../../csharp/language-reference/keywords/sealed.md) keyword enables you to prevent the inheritance of a class or certain class members that were previously marked [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
## <a name="abstract-classes-and-class-members"></a><span data-ttu-id="d875a-105">Classi e membri di classi astratte</span><span class="sxs-lookup"><span data-stu-id="d875a-105">Abstract Classes and Class Members</span></span>  
 <span data-ttu-id="d875a-106">Una classe può essere dichiarata astratta inserendo la parola chiave `abstract` prima della definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="d875a-106">Classes can be declared as abstract by putting the keyword `abstract` before the class definition.</span></span> <span data-ttu-id="d875a-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d875a-107">For example:</span></span>  
  
 <span data-ttu-id="d875a-108">[!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d875a-108">[!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]</span></span>  
  
 <span data-ttu-id="d875a-109">Non è possibile creare un'istanza di una classe astratta.</span><span class="sxs-lookup"><span data-stu-id="d875a-109">An abstract class cannot be instantiated.</span></span> <span data-ttu-id="d875a-110">Lo scopo di una classe astratta è quello di fornire una definizione comune di una classe base condivisibile da più classi derivate.</span><span class="sxs-lookup"><span data-stu-id="d875a-110">The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.</span></span> <span data-ttu-id="d875a-111">Una libreria di classi può, ad esempio, definire una classe astratta utilizzata come parametro per molte funzioni e richiedere ai programmatori che utilizzano tale libreria di fornire un'implementazione personalizzata della classe creando una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d875a-111">For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.</span></span>  
  
 <span data-ttu-id="d875a-112">Le classi astratte possono inoltre definire metodi astratti</span><span class="sxs-lookup"><span data-stu-id="d875a-112">Abstract classes may also define abstract methods.</span></span> <span data-ttu-id="d875a-113">aggiungendo la parola chiave `abstract` prima del tipo restituito del metodo.</span><span class="sxs-lookup"><span data-stu-id="d875a-113">This is accomplished by adding the keyword `abstract` before the return type of the method.</span></span> <span data-ttu-id="d875a-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d875a-114">For example:</span></span>  
  
 <span data-ttu-id="d875a-115">[!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d875a-115">[!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]</span></span>  
  
 <span data-ttu-id="d875a-116">I metodi astratti non prevedono implementazione, pertanto la definizione del metodo è seguita da un punto e virgola, anziché da un normale blocco di metodi.</span><span class="sxs-lookup"><span data-stu-id="d875a-116">Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block.</span></span> <span data-ttu-id="d875a-117">Le classi derivate della classe astratta devono implementare tutti i metodi astratti.</span><span class="sxs-lookup"><span data-stu-id="d875a-117">Derived classes of the abstract class must implement all abstract methods.</span></span> <span data-ttu-id="d875a-118">Quando una classe astratta eredita un metodo virtuale da una classe base, la classe astratta può eseguire l'override del metodo virtuale con un metodo astratto.</span><span class="sxs-lookup"><span data-stu-id="d875a-118">When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.</span></span> <span data-ttu-id="d875a-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d875a-119">For example:</span></span>  
  
 <span data-ttu-id="d875a-120">[!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d875a-120">[!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]</span></span>  
  
 <span data-ttu-id="d875a-121">Un metodo `virtual` dichiarato `abstract` rimane virtuale in qualsiasi classe che eredita dalla classe astratta.</span><span class="sxs-lookup"><span data-stu-id="d875a-121">If a `virtual` method is declared `abstract`, it is still virtual to any class inheriting from the abstract class.</span></span> <span data-ttu-id="d875a-122">Una classe che eredita un metodo astratto non può accedere all'implementazione originale del metodo. Nell'esempio precedente, `DoWork` sulla classe F non può chiamare `DoWork` sulla classe D. In questo modo una classe astratta può imporre alle classi derivate di fornire nuove implementazioni per i metodi virtuali.</span><span class="sxs-lookup"><span data-stu-id="d875a-122">A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, `DoWork` on class F cannot call `DoWork` on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.</span></span>  
  
## <a name="sealed-classes-and-class-members"></a><span data-ttu-id="d875a-123">Classi e membri di classi sealed</span><span class="sxs-lookup"><span data-stu-id="d875a-123">Sealed Classes and Class Members</span></span>  
 <span data-ttu-id="d875a-124">Le classi possono essere dichiarate [sealed](../../../csharp/language-reference/keywords/sealed.md) inserendo la parola chiave `sealed` prima della definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="d875a-124">Classes can be declared as [sealed](../../../csharp/language-reference/keywords/sealed.md) by putting the keyword `sealed` before the class definition.</span></span> <span data-ttu-id="d875a-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d875a-125">For example:</span></span>  
  
 <span data-ttu-id="d875a-126">[!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d875a-126">[!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]</span></span>  
  
 <span data-ttu-id="d875a-127">Una classe sealed non può essere utilizzata come classe base.</span><span class="sxs-lookup"><span data-stu-id="d875a-127">A sealed class cannot be used as a base class.</span></span> <span data-ttu-id="d875a-128">Per questo motivo non può neppure essere una classe astratta.</span><span class="sxs-lookup"><span data-stu-id="d875a-128">For this reason, it cannot also be an abstract class.</span></span> <span data-ttu-id="d875a-129">Le classi sealed impediscono la derivazione.</span><span class="sxs-lookup"><span data-stu-id="d875a-129">Sealed classes prevent derivation.</span></span> <span data-ttu-id="d875a-130">Poiché non possono mai essere utilizzate come classe base, in alcune ottimizzazioni runtime la chiamata ai membri di classi sealed può risultare leggermente più rapida.</span><span class="sxs-lookup"><span data-stu-id="d875a-130">Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.</span></span>  
  
 <span data-ttu-id="d875a-131">Un metodo, un indicizzatore, una proprietà o un evento di una classe derivata che esegue l'override di un membro virtuale della classe base può dichiarare tale membro come sealed.</span><span class="sxs-lookup"><span data-stu-id="d875a-131">A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed.</span></span> <span data-ttu-id="d875a-132">In questo modo viene negato l'aspetto virtuale del membro per qualsiasi ulteriore classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d875a-132">This negates the virtual aspect of the member for any further derived class.</span></span> <span data-ttu-id="d875a-133">A questo scopo è necessario inserire la parola chiave `sealed` prima della parola chiave [override](../../../csharp/language-reference/keywords/override.md) nella dichiarazione del membro di classe.</span><span class="sxs-lookup"><span data-stu-id="d875a-133">This is accomplished by putting the `sealed` keyword before the [override](../../../csharp/language-reference/keywords/override.md) keyword in the class member declaration.</span></span> <span data-ttu-id="d875a-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d875a-134">For example:</span></span>  
  
 <span data-ttu-id="d875a-135">[!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="d875a-135">[!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d875a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d875a-136">See Also</span></span>  
 <span data-ttu-id="d875a-137">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d875a-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d875a-138">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="d875a-138">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="d875a-139">[Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="d875a-139">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="d875a-140">[Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="d875a-140">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 <span data-ttu-id="d875a-141">[Campi](../../../csharp/programming-guide/classes-and-structs/fields.md) </span><span class="sxs-lookup"><span data-stu-id="d875a-141">[Fields](../../../csharp/programming-guide/classes-and-structs/fields.md) </span></span>  
 [<span data-ttu-id="d875a-142">Procedura: Definire proprietà astratte</span><span class="sxs-lookup"><span data-stu-id="d875a-142">How to: Define Abstract Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)

