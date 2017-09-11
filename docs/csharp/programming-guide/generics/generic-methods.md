---
title: Metodi generici (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
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
ms.openlocfilehash: 14461773303bafc098f79c3686b1f76827f11005
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="f7b49-102">Metodi generici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f7b49-102">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="f7b49-103">Un metodo generico è un metodo che viene dichiarato con parametri di tipo, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="f7b49-103">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 <span data-ttu-id="f7b49-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f7b49-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="f7b49-105">L'esempio di codice seguente mostra un modo per chiamare il metodo usando `int` per l'argomento tipo:</span><span class="sxs-lookup"><span data-stu-id="f7b49-105">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 <span data-ttu-id="f7b49-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f7b49-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="f7b49-107">È anche possibile omettere l'argomento tipo perché venga dedotto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="f7b49-107">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="f7b49-108">La chiamata seguente a `Swap` equivale alla chiamata precedente:</span><span class="sxs-lookup"><span data-stu-id="f7b49-108">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 <span data-ttu-id="f7b49-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f7b49-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span></span>  
  
 <span data-ttu-id="f7b49-110">Ai metodi statici e ai metodi di istanza si applicano le stesse regole relative all'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="f7b49-110">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="f7b49-111">Il compilatore può dedurre i parametri di tipo in base agli argomenti metodo passati, ma non può dedurli solo da un vincolo o da un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="f7b49-111">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="f7b49-112">Di conseguenza, l'inferenza del tipo non funziona con metodi che non includono parametri.</span><span class="sxs-lookup"><span data-stu-id="f7b49-112">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="f7b49-113">L'inferenza del tipo avviene in fase di compilazione prima che il compilatore provi a risolvere le firme dei metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="f7b49-113">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="f7b49-114">Il compilatore applica la logica di inferenza del tipo a tutti i metodi generici che condividono lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="f7b49-114">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="f7b49-115">Nel passaggio di risoluzione dell'overload, il compilatore include solo i metodi generici per cui l'inferenza del tipo è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f7b49-115">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="f7b49-116">All'interno di una classe generica metodi non generici possono accedere ai parametri di tipo a livello di classe, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="f7b49-116">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 <span data-ttu-id="f7b49-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f7b49-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="f7b49-118">Se si definisce un metodo generico che accetta gli stessi parametri di tipo della classe che lo contiene, il compilatore genera l'avviso CS0693 perché nell'ambito del metodo l'argomento specificato per il parametro `T` interno nasconde l'argomento specificato per il parametro `T` esterno.</span><span class="sxs-lookup"><span data-stu-id="f7b49-118">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning CS0693 because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="f7b49-119">Se è necessaria la flessibilità di poter chiamare un metodo di una classe generica con argomenti tipo diversi da quelli specificati alla creazione di un'istanza della classe, provare a specificare un altro identificatore per il parametro di tipo del metodo, come mostrato in `GenericList2<T>` nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f7b49-119">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 <span data-ttu-id="f7b49-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="f7b49-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span></span>  
  
 <span data-ttu-id="f7b49-121">Usare vincoli per consentire operazioni più specializzate sui parametri di tipo nei metodi.</span><span class="sxs-lookup"><span data-stu-id="f7b49-121">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="f7b49-122">Questa versione di `Swap<T>`, ora chiamata `SwapIfGreater<T>`, può essere usata solo con argomenti tipo che implementano <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="f7b49-122">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 <span data-ttu-id="f7b49-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="f7b49-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span></span>  
  
 <span data-ttu-id="f7b49-124">È possibile eseguire l'overload di metodi generici in diversi parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="f7b49-124">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="f7b49-125">Ad esempio, i metodi seguenti possono essere contenuti tutti nella stessa classe:</span><span class="sxs-lookup"><span data-stu-id="f7b49-125">For example, the following methods can all be located in the same class:</span></span>  
  
 <span data-ttu-id="f7b49-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="f7b49-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f7b49-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f7b49-127">C# Language Specification</span></span>  
 <span data-ttu-id="f7b49-128">Per altre informazioni, vedere la [specifica del linguaggio C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="f7b49-128">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b49-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7b49-129">See Also</span></span>  
 <span data-ttu-id="f7b49-130"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="f7b49-130"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="f7b49-131">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f7b49-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f7b49-132">[Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="f7b49-132">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 [<span data-ttu-id="f7b49-133">Metodi</span><span class="sxs-lookup"><span data-stu-id="f7b49-133">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

