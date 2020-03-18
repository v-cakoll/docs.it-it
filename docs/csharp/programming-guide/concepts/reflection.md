---
title: Reflection (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74711666"
---
# <a name="reflection-c"></a><span data-ttu-id="c0106-102">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="c0106-102">Reflection (C#)</span></span>

<span data-ttu-id="c0106-103">La reflection fornisce <xref:System.Type>oggetti (di tipo ) che descrivono assembly, moduli e tipi.</span><span class="sxs-lookup"><span data-stu-id="c0106-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="c0106-104">È possibile usare la reflection per creare in modo dinamico un'istanza di un tipo, associare il tipo a un oggetto esistente oppure ottenere il tipo da un oggetto esistente e richiamarne i metodi o accedere ai relativi campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="c0106-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="c0106-105">Se si usano attributi nel codice, la reflection consente di accedervi.</span><span class="sxs-lookup"><span data-stu-id="c0106-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="c0106-106">Per altre informazioni, vedere [Attributi](../../../standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0106-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="c0106-107">Di seguito è riportato un <xref:System.Object.GetType> semplice esempio di reflection `Object` utilizzando il metodo , ereditato da tutti i tipi dalla classe base, per ottenere il tipo di una variabile:Here's a simple example of reflection using the method - inherited by all types from the base class - to obtain the type of a variable:</span><span class="sxs-lookup"><span data-stu-id="c0106-107">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="c0106-108">Assicurati di `using System;` aggiungere `using System.Reflection;` e nella parte superiore del file *.cs.*</span><span class="sxs-lookup"><span data-stu-id="c0106-108">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="c0106-109">L'output `System.Int32`è: .</span><span class="sxs-lookup"><span data-stu-id="c0106-109">The output is: `System.Int32`.</span></span>

<span data-ttu-id="c0106-110">L'esempio seguente usa la reflection per ottenere il nome completo dell'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="c0106-110">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="c0106-111">L'output `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`è: .</span><span class="sxs-lookup"><span data-stu-id="c0106-111">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="c0106-112">Le parole chiave di C# `protected` e `internal` non hanno significato in IL e non sono usate nelle API di reflection.</span><span class="sxs-lookup"><span data-stu-id="c0106-112">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="c0106-113">I termini corrispondenti in IL sono *Famiglia* e *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="c0106-113">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="c0106-114">Per identificare un metodo `internal` tramite reflection, usare la proprietà <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="c0106-114">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="c0106-115">Per identificare un metodo `protected internal`, usare <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="c0106-115">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="c0106-116">Panoramica della riflessione</span><span class="sxs-lookup"><span data-stu-id="c0106-116">Reflection overview</span></span>

<span data-ttu-id="c0106-117">La reflection è utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0106-117">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="c0106-118">Quando è necessario accedere agli attributi nei metadati del programma.</span><span class="sxs-lookup"><span data-stu-id="c0106-118">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="c0106-119">Per altre informazioni, vedere [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c0106-119">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="c0106-120">Per esaminare e creare istanze di tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="c0106-120">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="c0106-121">Per creare nuovi tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c0106-121">For building new types at runtime.</span></span> <span data-ttu-id="c0106-122">Usare le classi in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="c0106-122">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="c0106-123">Per eseguire l'associazione tardiva, accedere ai metodi per i tipi creati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c0106-123">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="c0106-124">Vedere l'argomento relativo a [caricamento e uso dinamico dei tipi](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="c0106-124">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="c0106-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c0106-125">Related sections</span></span>

<span data-ttu-id="c0106-126">Per altre informazioni:</span><span class="sxs-lookup"><span data-stu-id="c0106-126">For more information:</span></span>

- [<span data-ttu-id="c0106-127">Riflessione</span><span class="sxs-lookup"><span data-stu-id="c0106-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="c0106-128">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="c0106-128">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="c0106-129">Reflection e tipi generici</span><span class="sxs-lookup"><span data-stu-id="c0106-129">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="c0106-130">Recupero di informazioni memorizzate negli attributi</span><span class="sxs-lookup"><span data-stu-id="c0106-130">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="c0106-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0106-131">See also</span></span>

- [<span data-ttu-id="c0106-132">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c0106-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c0106-133">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="c0106-133">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
