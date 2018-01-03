---
title: Reflection (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ca22705a0eee6749ff7121d63d9b505b153e45d9
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="reflection-visual-basic"></a><span data-ttu-id="ad7d7-102">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad7d7-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="ad7d7-103">La reflection specifica oggetti di tipo <xref:System.Type> che descrivono assembly, moduli e tipi.</span><span class="sxs-lookup"><span data-stu-id="ad7d7-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="ad7d7-104">È possibile usare la reflection per creare in modo dinamico un'istanza di un tipo, associare il tipo a un oggetto esistente oppure ottenere il tipo da un oggetto esistente e richiamarne i metodi o accedere ai relativi campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="ad7d7-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="ad7d7-105">Se si usano attributi nel codice, la reflection consente di accedervi.</span><span class="sxs-lookup"><span data-stu-id="ad7d7-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="ad7d7-106">Per altre informazioni, vedere [Attributi](../../../standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad7d7-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="ad7d7-107">Di seguito è riportato un esempio semplice di reflection che usa il metodo statico `GetType` ereditato da tutti i tipi dalla classe di base `Object` per ottenere il tipo di una variabile:</span><span class="sxs-lookup"><span data-stu-id="ad7d7-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="ad7d7-108">L'output è:</span><span class="sxs-lookup"><span data-stu-id="ad7d7-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="ad7d7-109">L'esempio seguente usa la reflection per ottenere il nome completo dell'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="ad7d7-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="ad7d7-110">L'output è:</span><span class="sxs-lookup"><span data-stu-id="ad7d7-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="ad7d7-111">Panoramica della reflection</span><span class="sxs-lookup"><span data-stu-id="ad7d7-111">Reflection Overview</span></span>  
 <span data-ttu-id="ad7d7-112">La reflection è utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad7d7-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="ad7d7-113">Quando è necessario accedere agli attributi nei metadati del programma.</span><span class="sxs-lookup"><span data-stu-id="ad7d7-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="ad7d7-114">Per altre informazioni, vedere [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ad7d7-114">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="ad7d7-115">Per esaminare e creare istanze di tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="ad7d7-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="ad7d7-116">Per creare nuovi tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ad7d7-116">For building new types at runtime.</span></span> <span data-ttu-id="ad7d7-117">Usare le classi in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="ad7d7-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="ad7d7-118">Per eseguire l'associazione tardiva, accedere ai metodi per i tipi creati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ad7d7-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="ad7d7-119">Vedere l'argomento relativo a [caricamento e uso dinamico dei tipi](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="ad7d7-119">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad7d7-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ad7d7-120">Related Sections</span></span>  
 <span data-ttu-id="ad7d7-121">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="ad7d7-121">For more information:</span></span>  
  
-   [<span data-ttu-id="ad7d7-122">Reflection</span><span class="sxs-lookup"><span data-stu-id="ad7d7-122">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="ad7d7-123">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="ad7d7-123">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="ad7d7-124">Reflection e tipi generici</span><span class="sxs-lookup"><span data-stu-id="ad7d7-124">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="ad7d7-125">Recupero di informazioni memorizzate negli attributi</span><span class="sxs-lookup"><span data-stu-id="ad7d7-125">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="ad7d7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad7d7-126">See Also</span></span>  
 [<span data-ttu-id="ad7d7-127">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad7d7-127">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="ad7d7-128">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="ad7d7-128">Assemblies in the Common Language Runtime</span></span>](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md)
