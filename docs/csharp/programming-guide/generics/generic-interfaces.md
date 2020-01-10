---
title: Interfacce generiche - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: 4cce23da7579e30ecff80b3afb92a5a58795c1bd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712208"
---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="c2f65-102">Interfacce generiche (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c2f65-102">Generic Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="c2f65-103">Spesso è utile definire interfacce per classi di raccolta generiche o per le classi generiche che rappresentano elementi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="c2f65-103">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="c2f65-104">Per le classi generiche è preferibile usare interfacce generiche, ad esempio <xref:System.IComparable%601> invece di <xref:System.IComparable>, per evitare operazioni di conversione boxing e unboxing sui tipi valore.</span><span class="sxs-lookup"><span data-stu-id="c2f65-104">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="c2f65-105">La libreria di classi .NET Framework definisce diverse interfacce generiche da usare con le classi di raccolta nello spazio dei nomi <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="c2f65-105">The .NET Framework class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="c2f65-106">Quando un'interfaccia viene specificata come vincolo o parametro di tipo, è possibile usare solo i tipi che implementano l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c2f65-106">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="c2f65-107">L'esempio di codice seguente mostra una classe `SortedList<T>` che deriva dalla classe `GenericList<T>`.</span><span class="sxs-lookup"><span data-stu-id="c2f65-107">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="c2f65-108">Per altre informazioni, vedere [Introduzione ai generics](./index.md).</span><span class="sxs-lookup"><span data-stu-id="c2f65-108">For more information, see [Introduction to Generics](./index.md).</span></span> <span data-ttu-id="c2f65-109">`SortedList<T>` aggiunge il vincolo `where T : IComparable<T>`.</span><span class="sxs-lookup"><span data-stu-id="c2f65-109">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="c2f65-110">In questo modo, il metodo `BubbleSort` in `SortedList<T>` può usare il metodo <xref:System.IComparable%601.CompareTo%2A> generico negli elementi dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c2f65-110">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="c2f65-111">In questo esempio gli elementi dell'elenco sono una classe semplice, ovvero `Person`, che implementa `IComparable<Person>`.</span><span class="sxs-lookup"><span data-stu-id="c2f65-111">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 <span data-ttu-id="c2f65-112">È possibile specificare più interfacce come vincoli su un unico tipo, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="c2f65-112">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 <span data-ttu-id="c2f65-113">Un'interfaccia può definire più parametri di tipo, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="c2f65-113">An interface can define more than one type parameter, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 <span data-ttu-id="c2f65-114">Le regole di ereditarietà valide per le classi si applicano anche alle interfacce:</span><span class="sxs-lookup"><span data-stu-id="c2f65-114">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 <span data-ttu-id="c2f65-115">Le interfacce generiche possono ereditare da interfacce non generiche se l'interfaccia generica è controvariante, ovvero usa solo il proprio parametro di tipo come valore restituito.</span><span class="sxs-lookup"><span data-stu-id="c2f65-115">Generic interfaces can inherit from non-generic interfaces if the generic interface is contravariant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="c2f65-116">Nella libreria di classi .NET Framework <xref:System.Collections.Generic.IEnumerable%601> eredita da <xref:System.Collections.IEnumerable> perché <xref:System.Collections.Generic.IEnumerable%601> usa solo `T` nel valore restituito di <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> e nel getter proprietà <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2f65-116">In the .NET Framework class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="c2f65-117">Le classi concrete possono implementare interfacce costruite chiuse, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="c2f65-117">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 <span data-ttu-id="c2f65-118">Le classi generiche possono implementare interfacce generiche o interfacce costruite chiuse purché l'elenco di parametri delle classi specifichi tutti gli argomenti necessari per l'interfaccia, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="c2f65-118">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 <span data-ttu-id="c2f65-119">Le regole che controllano l'overload dei metodi sono le stesse per i metodi all'interno di classi generiche, struct generici o interfacce generiche.</span><span class="sxs-lookup"><span data-stu-id="c2f65-119">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="c2f65-120">Per altre informazioni, vedere [Metodi generici](./generic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="c2f65-120">For more information, see [Generic Methods](./generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f65-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2f65-121">See also</span></span>

- [<span data-ttu-id="c2f65-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c2f65-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c2f65-123">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="c2f65-123">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="c2f65-124">interface</span><span class="sxs-lookup"><span data-stu-id="c2f65-124">interface</span></span>](../../language-reference/keywords/interface.md)
- [<span data-ttu-id="c2f65-125">Generics</span><span class="sxs-lookup"><span data-stu-id="c2f65-125">Generics</span></span>](../../../standard/generics/index.md)
