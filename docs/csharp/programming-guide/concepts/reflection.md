---
title: Reflection (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711666"
---
# <a name="reflection-c"></a><span data-ttu-id="82401-102">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="82401-102">Reflection (C#)</span></span>

<span data-ttu-id="82401-103">La reflection fornisce oggetti (di tipo <xref:System.Type>) che descrivono assembly, moduli e tipi.</span><span class="sxs-lookup"><span data-stu-id="82401-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="82401-104">È possibile usare la reflection per creare in modo dinamico un'istanza di un tipo, associare il tipo a un oggetto esistente oppure ottenere il tipo da un oggetto esistente e richiamarne i metodi o accedere ai relativi campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="82401-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="82401-105">Se si usano attributi nel codice, la reflection consente di accedervi.</span><span class="sxs-lookup"><span data-stu-id="82401-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="82401-106">Per altre informazioni, vedere [Attributi](../../../standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="82401-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="82401-107">Ecco un semplice esempio di reflection che usa il metodo <xref:System.Object.GetType> ereditato da tutti i tipi della classe di base `Object` per ottenere il tipo di una variabile:</span><span class="sxs-lookup"><span data-stu-id="82401-107">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="82401-108">Assicurarsi di aggiungere `using System;` e `using System.Reflection;` nella parte superiore del file con *estensione cs* .</span><span class="sxs-lookup"><span data-stu-id="82401-108">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="82401-109">L'output è: `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="82401-109">The output is: `System.Int32`.</span></span>

<span data-ttu-id="82401-110">L'esempio seguente usa la reflection per ottenere il nome completo dell'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="82401-110">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="82401-111">L'output è: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span><span class="sxs-lookup"><span data-stu-id="82401-111">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="82401-112">Le parole chiave di C# `protected` e `internal` non hanno significato in IL e non sono usate nelle API di reflection.</span><span class="sxs-lookup"><span data-stu-id="82401-112">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="82401-113">I termini corrispondenti in IL sono *Famiglia* e *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="82401-113">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="82401-114">Per identificare un metodo `internal` tramite reflection, usare la proprietà <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="82401-114">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="82401-115">Per identificare un metodo `protected internal`, usare <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="82401-115">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="82401-116">Panoramica della reflection</span><span class="sxs-lookup"><span data-stu-id="82401-116">Reflection overview</span></span>

<span data-ttu-id="82401-117">La reflection è utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82401-117">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="82401-118">Quando è necessario accedere agli attributi nei metadati del programma.</span><span class="sxs-lookup"><span data-stu-id="82401-118">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="82401-119">Per altre informazioni, vedere [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="82401-119">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="82401-120">Per esaminare e creare istanze di tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="82401-120">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="82401-121">Per creare nuovi tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="82401-121">For building new types at runtime.</span></span> <span data-ttu-id="82401-122">Usare le classi in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="82401-122">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="82401-123">Per eseguire l'associazione tardiva, accedere ai metodi per i tipi creati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="82401-123">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="82401-124">Vedere l'argomento relativo a [caricamento e uso dinamico dei tipi](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="82401-124">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="82401-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="82401-125">Related sections</span></span>

<span data-ttu-id="82401-126">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="82401-126">For more information:</span></span>

- [<span data-ttu-id="82401-127">Reflection</span><span class="sxs-lookup"><span data-stu-id="82401-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="82401-128">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="82401-128">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="82401-129">Reflection e tipi generici</span><span class="sxs-lookup"><span data-stu-id="82401-129">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="82401-130">Recupero di informazioni memorizzate negli attributi</span><span class="sxs-lookup"><span data-stu-id="82401-130">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="82401-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82401-131">See also</span></span>

- [<span data-ttu-id="82401-132">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="82401-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="82401-133">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="82401-133">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
