---
title: Metodi generici - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
ms.openlocfilehash: 5f066ca39c97b70554886e423c37c4ee47d49158
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712195"
---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="f799a-102">Metodi generici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f799a-102">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="f799a-103">Un metodo generico è un metodo che viene dichiarato con parametri di tipo, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="f799a-103">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#22)]  
  
 <span data-ttu-id="f799a-104">L'esempio di codice seguente mostra un modo per chiamare il metodo usando `int` per l'argomento tipo:</span><span class="sxs-lookup"><span data-stu-id="f799a-104">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#23)]  
  
 <span data-ttu-id="f799a-105">È anche possibile omettere l'argomento tipo perché venga dedotto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="f799a-105">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="f799a-106">La chiamata seguente a `Swap` equivale alla chiamata precedente:</span><span class="sxs-lookup"><span data-stu-id="f799a-106">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#24)]  
  
 <span data-ttu-id="f799a-107">Ai metodi statici e ai metodi di istanza si applicano le stesse regole relative all'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="f799a-107">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="f799a-108">Il compilatore può dedurre i parametri di tipo in base agli argomenti metodo passati, ma non può dedurli solo da un vincolo o da un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="f799a-108">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="f799a-109">Di conseguenza, l'inferenza del tipo non funziona con metodi che non includono parametri.</span><span class="sxs-lookup"><span data-stu-id="f799a-109">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="f799a-110">L'inferenza del tipo avviene in fase di compilazione prima che il compilatore provi a risolvere le firme dei metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="f799a-110">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="f799a-111">Il compilatore applica la logica di inferenza del tipo a tutti i metodi generici che condividono lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="f799a-111">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="f799a-112">Nel passaggio di risoluzione dell'overload, il compilatore include solo i metodi generici per cui l'inferenza del tipo è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f799a-112">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="f799a-113">All'interno di una classe generica metodi non generici possono accedere ai parametri di tipo a livello di classe, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="f799a-113">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#25)]  
  
 <span data-ttu-id="f799a-114">Se si definisce un metodo generico che accetta gli stessi parametri di tipo della classe che lo contiene, il compilatore genera l'avviso [CS0693](../../misc/cs0693.md) perché nell'ambito del metodo l'argomento specificato per il parametro `T` interno nasconde l'argomento specificato per il parametro `T` esterno.</span><span class="sxs-lookup"><span data-stu-id="f799a-114">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning [CS0693](../../misc/cs0693.md) because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="f799a-115">Se è necessaria la flessibilità di poter chiamare un metodo di una classe generica con argomenti tipo diversi da quelli specificati alla creazione di un'istanza della classe, provare a specificare un altro identificatore per il parametro di tipo del metodo, come mostrato in `GenericList2<T>` nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f799a-115">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#26)]  
  
 <span data-ttu-id="f799a-116">Usare vincoli per consentire operazioni più specializzate sui parametri di tipo nei metodi.</span><span class="sxs-lookup"><span data-stu-id="f799a-116">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="f799a-117">Questa versione di `Swap<T>`, ora chiamata `SwapIfGreater<T>`, può essere usata solo con argomenti tipo che implementano <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="f799a-117">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#27)]  
  
 <span data-ttu-id="f799a-118">È possibile eseguire l'overload di metodi generici in diversi parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="f799a-118">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="f799a-119">Ad esempio, i metodi seguenti possono essere contenuti tutti nella stessa classe:</span><span class="sxs-lookup"><span data-stu-id="f799a-119">For example, the following methods can all be located in the same class:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#28)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f799a-120">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f799a-120">C# Language Specification</span></span>  
 <span data-ttu-id="f799a-121">Per altre informazioni, vedere la [specifica del linguaggio C#](~/_csharplang/spec/classes.md#methods).</span><span class="sxs-lookup"><span data-stu-id="f799a-121">For more information, see the [C# Language Specification](~/_csharplang/spec/classes.md#methods).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f799a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f799a-122">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="f799a-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f799a-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f799a-124">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="f799a-124">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="f799a-125">Metodi</span><span class="sxs-lookup"><span data-stu-id="f799a-125">Methods</span></span>](../classes-and-structs/methods.md)
