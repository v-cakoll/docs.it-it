---
title: Reflection (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: 4dfd9391407fec4bd20ac4ae05162763e909d665
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841316"
---
# <a name="reflection-c"></a><span data-ttu-id="843b7-102">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="843b7-102">Reflection (C#)</span></span>
<span data-ttu-id="843b7-103">La reflection specifica oggetti di tipo <xref:System.Type> che descrivono assembly, moduli e tipi.</span><span class="sxs-lookup"><span data-stu-id="843b7-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="843b7-104">È possibile usare la reflection per creare in modo dinamico un'istanza di un tipo, associare il tipo a un oggetto esistente oppure ottenere il tipo da un oggetto esistente e richiamarne i metodi o accedere ai relativi campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="843b7-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="843b7-105">Se si usano attributi nel codice, la reflection consente di accedervi.</span><span class="sxs-lookup"><span data-stu-id="843b7-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="843b7-106">Per altre informazioni, vedere [Attributi](../../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="843b7-106">For more information, see [Attributes](../../../../docs/standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="843b7-107">Di seguito è riportato un esempio semplice di reflection che usa il metodo statico `GetType` ereditato da tutti i tipi dalla classe di base `Object` per ottenere il tipo di una variabile:</span><span class="sxs-lookup"><span data-stu-id="843b7-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 <span data-ttu-id="843b7-108">L'output è:</span><span class="sxs-lookup"><span data-stu-id="843b7-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="843b7-109">L'esempio seguente usa la reflection per ottenere il nome completo dell'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="843b7-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```csharp  
// Using Reflection to get information of an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 <span data-ttu-id="843b7-110">L'output è:</span><span class="sxs-lookup"><span data-stu-id="843b7-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  <span data-ttu-id="843b7-111">Le parole chiave di C# `protected` e `internal` non hanno significato in IL e non sono usate nelle API di reflection.</span><span class="sxs-lookup"><span data-stu-id="843b7-111">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="843b7-112">I termini corrispondenti in IL sono *Famiglia* e *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="843b7-112">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="843b7-113">Per identificare un metodo `internal` tramite reflection, usare la proprietà <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="843b7-113">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="843b7-114">Per identificare un metodo `protected internal`, usare <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="843b7-114">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>  
  
## <a name="reflection-overview"></a><span data-ttu-id="843b7-115">Panoramica della reflection</span><span class="sxs-lookup"><span data-stu-id="843b7-115">Reflection Overview</span></span>  
 <span data-ttu-id="843b7-116">La reflection è utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="843b7-116">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="843b7-117">Quando è necessario accedere agli attributi nei metadati del programma.</span><span class="sxs-lookup"><span data-stu-id="843b7-117">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="843b7-118">Per altre informazioni, vedere [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="843b7-118">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="843b7-119">Per esaminare e creare istanze di tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="843b7-119">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="843b7-120">Per creare nuovi tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="843b7-120">For building new types at runtime.</span></span> <span data-ttu-id="843b7-121">Usare le classi in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="843b7-121">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="843b7-122">Per eseguire l'associazione tardiva, accedere ai metodi per i tipi creati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="843b7-122">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="843b7-123">Vedere l'argomento relativo a [caricamento e uso dinamico dei tipi](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="843b7-123">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="843b7-124">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="843b7-124">Related Sections</span></span>  
 <span data-ttu-id="843b7-125">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="843b7-125">For more information:</span></span>  
  
-   [<span data-ttu-id="843b7-126">Reflection</span><span class="sxs-lookup"><span data-stu-id="843b7-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="843b7-127">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="843b7-127">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="843b7-128">Reflection e tipi generici</span><span class="sxs-lookup"><span data-stu-id="843b7-128">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="843b7-129">Recupero di informazioni memorizzate negli attributi</span><span class="sxs-lookup"><span data-stu-id="843b7-129">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="843b7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="843b7-130">See also</span></span>

- [<span data-ttu-id="843b7-131">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="843b7-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="843b7-132">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="843b7-132">Assemblies in the Common Language Runtime</span></span>](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
