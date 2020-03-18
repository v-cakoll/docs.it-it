---
title: Parametri di tipo generico - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 8412980d35989c445d2e0a44c0b9f35e6087bb8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712182"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="a9b46-102">Parametri di tipo generico (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a9b46-102">Generic type parameters (C# Programming Guide)</span></span>

<span data-ttu-id="a9b46-103">In una definizione di tipo o metodo generico un parametro di tipo è un segnaposto per un determinato tipo specificato da un client durante la creazione di un'istanza del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="a9b46-103">In a generic type or method definition, a type parameter is a placeholder for a specific type that a client specifies when they create an instance of the generic type.</span></span> <span data-ttu-id="a9b46-104">Una classe generica, ad esempio `GenericList<T>`, elencata in [Introduzione ai generics](./index.md), non può essere usata in quanto tale perché non è effettivamente un tipo, ma è piuttosto un progetto iniziale per un tipo.</span><span class="sxs-lookup"><span data-stu-id="a9b46-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](./index.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="a9b46-105">Per usare `GenericList<T>`, il codice client deve dichiarare un tipo costruito e crearne un'istanza specificando un argomento tipo racchiuso tra parentesi angolari.</span><span class="sxs-lookup"><span data-stu-id="a9b46-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="a9b46-106">L'argomento tipo per questa classe specifica può essere qualsiasi tipo riconosciuto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="a9b46-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="a9b46-107">È possibile creare un numero qualsiasi di istanze del tipo costruito, ognuna con un argomento tipo diverso, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="a9b46-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
<span data-ttu-id="a9b46-108">In ognuna di queste istanze di `GenericList<T>` ogni occorrenza di `T` nella classe viene sostituita in fase di esecuzione con l'argomento tipo.</span><span class="sxs-lookup"><span data-stu-id="a9b46-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class is substituted at run time with the type argument.</span></span> <span data-ttu-id="a9b46-109">Per mezzo di questa sostituzione, sono stati creati tre oggetti efficienti e indipendenti dai tipi separati usando un'unica definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="a9b46-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="a9b46-110">Per altre informazioni su come viene eseguita questa sostituzione da CLR, vedere [Generics nel runtime](./generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="a9b46-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](./generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="a9b46-111">Linee guida per la denominazione dei parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a9b46-111">Type parameter naming guidelines</span></span>  
  
- <span data-ttu-id="a9b46-112">**Assegnare** ai parametri di tipo generico nomi descrittivi, a meno che un nome di una sola lettera non sia già completamente comprensibile, senza che sia necessario un nome descrittivo più lungo.</span><span class="sxs-lookup"><span data-stu-id="a9b46-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- <span data-ttu-id="a9b46-113">**Provare** a usare T come nome del parametro di tipo per i tipi con parametro di tipo di una sola lettera.</span><span class="sxs-lookup"><span data-stu-id="a9b46-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- <span data-ttu-id="a9b46-114">**Aggiungere** ai nomi di parametro di tipo descrittivi il prefisso "T".</span><span class="sxs-lookup"><span data-stu-id="a9b46-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- <span data-ttu-id="a9b46-115">**Provare** a indicare i vincoli applicati a un parametro di tipo nel nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="a9b46-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="a9b46-116">Ad esempio, assegnare a un parametro vincolato a `ISession` il nome `TSession`.</span><span class="sxs-lookup"><span data-stu-id="a9b46-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>

<span data-ttu-id="a9b46-117">La regola di analisi codice [CA1715](/visualstudio/code-quality/ca1715) può essere usata per garantire che i parametri di tipo vengano denominati in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="a9b46-117">The code analysis rule [CA1715](/visualstudio/code-quality/ca1715) can be used to ensure that type parameters are named appropriately.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a9b46-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9b46-118">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="a9b46-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a9b46-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a9b46-120">Generics</span><span class="sxs-lookup"><span data-stu-id="a9b46-120">Generics</span></span>](./index.md)
- [<span data-ttu-id="a9b46-121">Differenze tra modelli C++ e generics C#</span><span class="sxs-lookup"><span data-stu-id="a9b46-121">Differences Between C++ Templates and C# Generics</span></span>](./differences-between-cpp-templates-and-csharp-generics.md)
