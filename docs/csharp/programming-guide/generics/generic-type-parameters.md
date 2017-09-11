---
title: Parametri di tipo generico (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
caps.latest.revision: 23
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
ms.openlocfilehash: ce1024215a381afb3a7b42f2127fe5e8c212d378
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="e973f-102">Parametri di tipo generico (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e973f-102">Generic Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="e973f-103">In una definizione di tipo o metodo generico un parametro di tipo è un segnaposto per un determinato tipo specificato da un client durante la creazione di un'istanza di una variabile del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="e973f-103">In a generic type or method definition, a type parameters is a placeholder for a specific type that a client specifies when they instantiate a variable of the generic type.</span></span> <span data-ttu-id="e973f-104">Una classe generica, ad esempio `GenericList<T>`, elencata in [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), non può essere usata in quanto tale perché non è effettivamente un tipo, ma è piuttosto un progetto iniziale per un tipo.</span><span class="sxs-lookup"><span data-stu-id="e973f-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="e973f-105">Per usare `GenericList<T>`, il codice client deve dichiarare un tipo costruito e crearne un'istanza specificando un argomento tipo racchiuso tra parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="e973f-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="e973f-106">L'argomento tipo per questa classe specifica può essere qualsiasi tipo riconosciuto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="e973f-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="e973f-107">È possibile creare un numero qualsiasi di istanze del tipo costruito, ognuna con un argomento tipo diverso, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="e973f-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
 <span data-ttu-id="e973f-108">[!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e973f-108">[!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="e973f-109">In ognuna di queste istanze di `GenericList<T>` ogni occorrenza di `T` nella classe verrà sostituita in fase di esecuzione con l'argomento tipo.</span><span class="sxs-lookup"><span data-stu-id="e973f-109">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class will be substituted at run time with the type argument.</span></span> <span data-ttu-id="e973f-110">Per mezzo di questa sostituzione, sono stati creati tre oggetti efficienti e indipendenti dai tipi separati usando un'unica definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="e973f-110">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="e973f-111">Per altre informazioni su come viene eseguita questa sostituzione da CLR, vedere [Generics nel runtime](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="e973f-111">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="e973f-112">Linee guida per la denominazione dei parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="e973f-112">Type Parameter Naming Guidelines</span></span>  
  
-   <span data-ttu-id="e973f-113">**Assegnare** ai parametri di tipo generico nomi descrittivi, a meno che un nome di una sola lettera non sia già completamente comprensibile, senza che sia necessario un nome descrittivo più lungo.</span><span class="sxs-lookup"><span data-stu-id="e973f-113">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
     <span data-ttu-id="e973f-114">[!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e973f-114">[!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]</span></span>  
  
-   <span data-ttu-id="e973f-115">**Provare** a usare T come nome del parametro di tipo per i tipi con parametro di tipo di una sola lettera.</span><span class="sxs-lookup"><span data-stu-id="e973f-115">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
     <span data-ttu-id="e973f-116">[!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e973f-116">[!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]</span></span>  
  
-   <span data-ttu-id="e973f-117">**Aggiungere** ai nomi di parametro di tipo descrittivi il prefisso "T".</span><span class="sxs-lookup"><span data-stu-id="e973f-117">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
     <span data-ttu-id="e973f-118">[!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e973f-118">[!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]</span></span>  
  
-   <span data-ttu-id="e973f-119">**Provare** a indicare i vincoli applicati a un parametro di tipo nel nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="e973f-119">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="e973f-120">Ad esempio, assegnare a un parametro vincolato a `ISession` il nome `TSession`.</span><span class="sxs-lookup"><span data-stu-id="e973f-120">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e973f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e973f-121">See Also</span></span>  
 <span data-ttu-id="e973f-122"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="e973f-122"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="e973f-123">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e973f-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e973f-124">[Generics](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="e973f-124">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 [<span data-ttu-id="e973f-125">Differenze tra modelli C++ e generics C#</span><span class="sxs-lookup"><span data-stu-id="e973f-125">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)

