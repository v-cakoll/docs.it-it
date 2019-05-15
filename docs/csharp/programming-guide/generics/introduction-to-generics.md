---
title: Introduzione ai generics - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
ms.openlocfilehash: 0d7ecb7f7fd0bb0985234cdc2cf8d37b53323c86
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595480"
---
# <a name="introduction-to-generics-c-programming-guide"></a><span data-ttu-id="70f78-102">Introduzione ai generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="70f78-102">Introduction to Generics (C# Programming Guide)</span></span>
<span data-ttu-id="70f78-103">Le classi e i metodi generici sono riutilizzabili, indipendenti dai tipi e molto più efficaci delle rispettive controparti non generiche.</span><span class="sxs-lookup"><span data-stu-id="70f78-103">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="70f78-104">I generics sono in genere usati con le raccolte e i metodi che operano su di essi.</span><span class="sxs-lookup"><span data-stu-id="70f78-104">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="70f78-105">La versione 2.0 della libreria di classi .NET Framework offre un nuovo spazio dei nomi, <xref:System.Collections.Generic>, che contiene diverse nuove classi di raccolta generiche.</span><span class="sxs-lookup"><span data-stu-id="70f78-105">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="70f78-106">È consigliabile che tutte le applicazioni destinate a .NET Framework 2.0 e versioni successive usino le nuove classi di raccolte generiche anziché le controparti non generiche meno recenti, ad esempio <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="70f78-106">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="70f78-107">Per altre informazioni, vedere [Generics in .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="70f78-107">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="70f78-108">Naturalmente, è anche possibile creare tipi e metodi generici personalizzati per offrire le proprie soluzioni e schemi progettuali generalizzati che sono indipendenti dai tipi ed efficienti.</span><span class="sxs-lookup"><span data-stu-id="70f78-108">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="70f78-109">Nell'esempio di codice riportato di seguito viene illustrata una classe di elenco collegato generica semplice a scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="70f78-109">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="70f78-110">Nella maggior parte dei casi, è necessario usare la classe <xref:System.Collections.Generic.List%601> specificata dalla libreria di classi .NET Framework anziché crearne una propria. Il parametro di tipo `T` viene usato in diverse posizioni in cui di norma verrebbe usato un tipo concreto per indicare il tipo dell'elemento archiviato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="70f78-110">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="70f78-111">In particolare, viene usato nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="70f78-111">It is used in the following ways:</span></span>  
  
- <span data-ttu-id="70f78-112">Come tipo di un parametro del metodo nel metodo `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="70f78-112">As the type of a method parameter in the `AddHead` method.</span></span>  
  
- <span data-ttu-id="70f78-113">Come tipo restituito della proprietà `Data` nella classe `Node` annidata.</span><span class="sxs-lookup"><span data-stu-id="70f78-113">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
- <span data-ttu-id="70f78-114">Come tipo del membro privato `data` nella classe annidata.</span><span class="sxs-lookup"><span data-stu-id="70f78-114">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="70f78-115">Si noti che T è disponibile per la classe `Node` annidata.</span><span class="sxs-lookup"><span data-stu-id="70f78-115">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="70f78-116">Quando si crea un'istanza di `GenericList<T>` con un tipo concreto, ad esempio `GenericList<int>`, ogni occorrenza di `T` verrà sostituita con `int`.</span><span class="sxs-lookup"><span data-stu-id="70f78-116">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 <span data-ttu-id="70f78-117">Nell'esempio di codice riportato di seguito viene illustrato come il codice client usa la classe generica `GenericList<T>` per creare un elenco di interi.</span><span class="sxs-lookup"><span data-stu-id="70f78-117">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="70f78-118">Cambiando semplicemente l'argomento relativo al tipo, è possibile modificare il codice riportato di seguito per creare elenchi di stringhe o di qualsiasi altro tipo personalizzato:</span><span class="sxs-lookup"><span data-stu-id="70f78-118">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="70f78-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70f78-119">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="70f78-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="70f78-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="70f78-121">Generics</span><span class="sxs-lookup"><span data-stu-id="70f78-121">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
