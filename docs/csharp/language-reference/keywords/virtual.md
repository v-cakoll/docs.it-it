---
title: virtual (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
dev_langs:
- CSharp
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 26
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
ms.openlocfilehash: 24ca77a0a645a17c0223437e73539bc04ba80f23
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="virtual-c-reference"></a><span data-ttu-id="0ef21-102">virtual (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0ef21-102">virtual (C# Reference)</span></span>
<span data-ttu-id="0ef21-103">La parola chiave `virtual` viene usata per modificare una dichiarazione di metodo, proprietà, indicizzatore o evento e consentire che sia sottoposta a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0ef21-103">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="0ef21-104">Ad esempio, questo metodo può essere sottoposto a override da qualsiasi classe che lo eredita:</span><span class="sxs-lookup"><span data-stu-id="0ef21-104">For example, this method can be overridden by any class that inherits it:</span></span>  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 <span data-ttu-id="0ef21-105">L'implementazione di un membro virtuale può essere modificata da un [membro di sostituzione](../../../csharp/language-reference/keywords/override.md) di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0ef21-105">The implementation of a virtual member can be changed by an [overriding member](../../../csharp/language-reference/keywords/override.md) in a derived class.</span></span> <span data-ttu-id="0ef21-106">Per altre informazioni sull'uso della parola chiave `virtual`, vedere [Controllo delle versioni con le parole chiave Override e New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Sapere quando utilizzare le parole chiave Override e New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="0ef21-106">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ef21-107">Note</span><span class="sxs-lookup"><span data-stu-id="0ef21-107">Remarks</span></span>  
 <span data-ttu-id="0ef21-108">Quando viene richiamato un metodo virtuale, il tipo di runtime dell'oggetto viene controllato per verificare la presenza di un membro di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="0ef21-108">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="0ef21-109">Viene chiamato il membro di sostituzione nella classe più derivata e potrebbe trattarsi del membro originale, se nessuna classe derivata ha eseguito l'override del membro.</span><span class="sxs-lookup"><span data-stu-id="0ef21-109">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>  
  
 <span data-ttu-id="0ef21-110">Per impostazione predefinita, i metodi sono non virtuali.</span><span class="sxs-lookup"><span data-stu-id="0ef21-110">By default, methods are non-virtual.</span></span> <span data-ttu-id="0ef21-111">Non è possibile eseguire l'override di un metodo non virtuale.</span><span class="sxs-lookup"><span data-stu-id="0ef21-111">You cannot override a non-virtual method.</span></span>  
  
 <span data-ttu-id="0ef21-112">Non è possibile usare il modificatore `virtual` con i modificatori `static`, `abstract, private` o `override`.</span><span class="sxs-lookup"><span data-stu-id="0ef21-112">You cannot use the `virtual` modifier with the `static`, `abstract, private`, or `override` modifiers.</span></span> <span data-ttu-id="0ef21-113">L'esempio seguente illustra una proprietà virtuale:</span><span class="sxs-lookup"><span data-stu-id="0ef21-113">The following example shows a virtual property:</span></span>  
  
 <span data-ttu-id="0ef21-114">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0ef21-114">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]</span></span>  
  
 <span data-ttu-id="0ef21-115">Le proprietà virtuali si comportano come i metodi astratti, ad eccezione delle differenze nella sintassi di dichiarazione e di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0ef21-115">Virtual properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="0ef21-116">Non è possibile usare il modificatore `virtual` su una proprietà static.</span><span class="sxs-lookup"><span data-stu-id="0ef21-116">It is an error to use the `virtual` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="0ef21-117">Una proprietà virtuale ereditata può essere sottoposta a override in una classe derivata includendo una dichiarazione di proprietà che usa il modificatore `override`.</span><span class="sxs-lookup"><span data-stu-id="0ef21-117">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ef21-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ef21-118">Example</span></span>  
 <span data-ttu-id="0ef21-119">In questo esempio la classe `Shape` contiene le due coordinate `x`, `y`e il metodo virtuale `Area()`.</span><span class="sxs-lookup"><span data-stu-id="0ef21-119">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="0ef21-120">Le classi di forma diversa, ad esempio `Circle`, `Cylinder` e `Sphere`, ereditano la classe `Shape` e la superficie viene calcolata per ogni figura.</span><span class="sxs-lookup"><span data-stu-id="0ef21-120">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="0ef21-121">Ogni classe derivata ha la propria implementazione di override di `Area()`.</span><span class="sxs-lookup"><span data-stu-id="0ef21-121">Each derived class has it own override implementation of `Area()`.</span></span>  
  
 <span data-ttu-id="0ef21-122">Si noti che le classi ereditate `Circle`, `Sphere` e `Cylinder` usano tutte costruttori che inizializzano la classe di base, come illustrato nella seguente dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0ef21-122">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 <span data-ttu-id="0ef21-123">Il programma seguente calcola e visualizza l'area appropriata per ogni figura richiamando l'implementazione corretta del metodo `Area()` in base all'oggetto associato al metodo.</span><span class="sxs-lookup"><span data-stu-id="0ef21-123">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>  
  
 <span data-ttu-id="0ef21-124">[!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0ef21-124">[!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0ef21-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0ef21-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ef21-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ef21-126">See Also</span></span>  
 <span data-ttu-id="0ef21-127">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ef21-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0ef21-128">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ef21-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0ef21-129">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="0ef21-129">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="0ef21-130">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ef21-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0ef21-131">[Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span><span class="sxs-lookup"><span data-stu-id="0ef21-131">[Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span></span>  
 <span data-ttu-id="0ef21-132">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span><span class="sxs-lookup"><span data-stu-id="0ef21-132">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span></span>  
 <span data-ttu-id="0ef21-133">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="0ef21-133">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 [<span data-ttu-id="0ef21-134">new</span><span class="sxs-lookup"><span data-stu-id="0ef21-134">new</span></span>](../../../csharp/language-reference/keywords/new.md)

