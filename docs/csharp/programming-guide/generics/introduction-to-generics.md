---
title: Introduzione ai generics (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
caps.latest.revision: "32"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ec4fe9cc9fe7bf868fcc8afe4dc4e4234241e352
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-generics-c-programming-guide"></a><span data-ttu-id="5851c-102">Introduzione ai generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5851c-102">Introduction to Generics (C# Programming Guide)</span></span>
<span data-ttu-id="5851c-103">Le classi e i metodi generici sono riutilizzabili, indipendenti dai tipi e molto più efficaci delle rispettive controparti non generiche.</span><span class="sxs-lookup"><span data-stu-id="5851c-103">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="5851c-104">I generics sono in genere usati con le raccolte e i metodi che operano su di essi.</span><span class="sxs-lookup"><span data-stu-id="5851c-104">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="5851c-105">La versione 2.0 della libreria di classi .NET Framework offre un nuovo spazio dei nomi, <xref:System.Collections.Generic>, che contiene diverse nuove classi di raccolta generiche.</span><span class="sxs-lookup"><span data-stu-id="5851c-105">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="5851c-106">È consigliabile che tutte le applicazioni destinate a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 e versioni successive usino le nuove classi di raccolte generiche anziché le controparti non generiche meno recenti, ad esempio <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="5851c-106">It is recommended that all applications that target the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="5851c-107">Per altre informazioni, vedere [Generics nella libreria di classi .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span><span class="sxs-lookup"><span data-stu-id="5851c-107">For more information, see [Generics in the .NET Framework Class Library](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span></span>  
  
 <span data-ttu-id="5851c-108">Naturalmente, è anche possibile creare tipi e metodi generici personalizzati per offrire le proprie soluzioni e schemi progettuali generalizzati che sono indipendenti dai tipi ed efficienti.</span><span class="sxs-lookup"><span data-stu-id="5851c-108">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="5851c-109">Nell'esempio di codice riportato di seguito viene illustrata una classe di elenco collegato generica semplice a scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="5851c-109">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="5851c-110">Nella maggior parte dei casi, è necessario usare la classe <xref:System.Collections.Generic.List%601> specificata dalla libreria di classi .NET Framework anziché crearne una propria. Il parametro di tipo `T` viene usato in diverse posizioni in cui di norma verrebbe usato un tipo concreto per indicare il tipo dell'elemento archiviato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5851c-110">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="5851c-111">In particolare, viene usato nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="5851c-111">It is used in the following ways:</span></span>  
  
-   <span data-ttu-id="5851c-112">Come tipo di un parametro del metodo nel metodo `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="5851c-112">As the type of a method parameter in the `AddHead` method.</span></span>  
  
-   <span data-ttu-id="5851c-113">Come tipo restituito del metodo pubblico `GetNext` e della proprietà `Data` nella classe `Node` annidata.</span><span class="sxs-lookup"><span data-stu-id="5851c-113">As the return type of the public method `GetNext` and the `Data` property in the nested `Node` class.</span></span>  
  
-   <span data-ttu-id="5851c-114">Come tipo dei dati del membro privato della classe annidata.</span><span class="sxs-lookup"><span data-stu-id="5851c-114">As the type of the private member data in the nested class.</span></span>  
  
 <span data-ttu-id="5851c-115">Si noti che T è disponibile per la classe `Node` annidata.</span><span class="sxs-lookup"><span data-stu-id="5851c-115">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="5851c-116">Quando si crea un'istanza di `GenericList<T>` con un tipo concreto, ad esempio `GenericList<int>`, ogni occorrenza di `T` verrà sostituita con `int`.</span><span class="sxs-lookup"><span data-stu-id="5851c-116">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 <span data-ttu-id="5851c-117">Nell'esempio di codice riportato di seguito viene illustrato come il codice client usa la classe generica `GenericList<T>` per creare un elenco di interi.</span><span class="sxs-lookup"><span data-stu-id="5851c-117">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="5851c-118">Cambiando semplicemente l'argomento relativo al tipo, è possibile modificare il codice riportato di seguito per creare elenchi di stringhe o di qualsiasi altro tipo personalizzato:</span><span class="sxs-lookup"><span data-stu-id="5851c-118">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5851c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5851c-119">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="5851c-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5851c-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5851c-121">Generics</span><span class="sxs-lookup"><span data-stu-id="5851c-121">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
