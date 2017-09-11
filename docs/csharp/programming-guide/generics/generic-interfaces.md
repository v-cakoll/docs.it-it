---
title: Interfacce generiche (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
caps.latest.revision: 28
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
ms.openlocfilehash: 2a9a994c339553b923b930660c0e129dd930de96
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="3ebd2-102">Interfacce generiche (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3ebd2-102">Generic Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="3ebd2-103">Spesso è utile definire interfacce per classi di raccolta generiche o per le classi generiche che rappresentano elementi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-103">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="3ebd2-104">Per le classi generiche è preferibile usare interfacce generiche, ad esempio <xref:System.IComparable%601> invece di <xref:System.IComparable>, per evitare operazioni di conversione boxing e unboxing sui tipi valore.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-104">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="3ebd2-105">La libreria di classi .NET Framework definisce diverse interfacce generiche da usare con le classi di raccolta nello spazio dei nomi <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-105">The .NET Framework class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="3ebd2-106">Quando un'interfaccia viene specificata come vincolo o parametro di tipo, è possibile usare solo i tipi che implementano l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-106">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="3ebd2-107">L'esempio di codice seguente mostra una classe `SortedList<T>` che deriva dalla classe `GenericList<T>`.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-107">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="3ebd2-108">Per altre informazioni, vedere [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="3ebd2-108">For more information, see [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span></span> <span data-ttu-id="3ebd2-109">`SortedList<T>` aggiunge il vincolo `where T : IComparable<T>`.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-109">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="3ebd2-110">In questo modo, il metodo `BubbleSort` in `SortedList<T>` può usare il metodo <xref:System.IComparable%601.CompareTo%2A> generico negli elementi dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-110">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="3ebd2-111">In questo esempio gli elementi dell'elenco sono una classe semplice, ovvero `Person`, che implementa `IComparable<Person>`.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-111">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 <span data-ttu-id="3ebd2-112">[!code-cs[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ebd2-112">[!code-cs[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="3ebd2-113">È possibile specificare più interfacce come vincoli su un unico tipo, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="3ebd2-113">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 <span data-ttu-id="3ebd2-114">[!code-cs[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ebd2-114">[!code-cs[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="3ebd2-115">Un'interfaccia può definire più parametri di tipo, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="3ebd2-115">An interface can define more than one type parameter, as follows:</span></span>  
  
 <span data-ttu-id="3ebd2-116">[!code-cs[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ebd2-116">[!code-cs[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]</span></span>  
  
 <span data-ttu-id="3ebd2-117">Le regole di ereditarietà valide per le classi si applicano anche alle interfacce:</span><span class="sxs-lookup"><span data-stu-id="3ebd2-117">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 <span data-ttu-id="3ebd2-118">[!code-cs[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ebd2-118">[!code-cs[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]</span></span>  
  
 <span data-ttu-id="3ebd2-119">Le interfacce generiche possono ereditare da interfacce non generiche se l'interfaccia generica è controvariante, ovvero usa solo il proprio parametro di tipo come valore restituito.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-119">Generic interfaces can inherit from non-generic interfaces if the generic interface is contra-variant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="3ebd2-120">Nella libreria di classi .NET Framework <xref:System.Collections.Generic.IEnumerable%601> eredita da <xref:System.Collections.IEnumerable> perché <xref:System.Collections.Generic.IEnumerable%601> usa solo `T` nel valore restituito di <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> e nel getter proprietà <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-120">In the .NET Framework class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="3ebd2-121">Le classi concrete possono implementare interfacce costruite chiuse, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="3ebd2-121">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 <span data-ttu-id="3ebd2-122">[!code-cs[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ebd2-122">[!code-cs[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]</span></span>  
  
 <span data-ttu-id="3ebd2-123">Le classi generiche possono implementare interfacce generiche o interfacce costruite chiuse purché l'elenco di parametri delle classi specifichi tutti gli argomenti necessari per l'interfaccia, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="3ebd2-123">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 <span data-ttu-id="3ebd2-124">[!code-cs[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ebd2-124">[!code-cs[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]</span></span>  
  
 <span data-ttu-id="3ebd2-125">Le regole che controllano l'overload dei metodi sono le stesse per i metodi all'interno di classi generiche, struct generici o interfacce generiche.</span><span class="sxs-lookup"><span data-stu-id="3ebd2-125">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="3ebd2-126">Per altre informazioni, vedere [Metodi generici](../../../csharp/programming-guide/generics/generic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="3ebd2-126">For more information, see [Generic Methods](../../../csharp/programming-guide/generics/generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ebd2-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ebd2-127">See Also</span></span>  
 <span data-ttu-id="3ebd2-128">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3ebd2-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3ebd2-129">[Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="3ebd2-129">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="3ebd2-130">[interface](../../../csharp/language-reference/keywords/interface.md) </span><span class="sxs-lookup"><span data-stu-id="3ebd2-130">[interface](../../../csharp/language-reference/keywords/interface.md) </span></span>  
 [<span data-ttu-id="3ebd2-131">Generics</span><span class="sxs-lookup"><span data-stu-id="3ebd2-131">Generics</span></span>](~/docs/standard/generics/index.md)

