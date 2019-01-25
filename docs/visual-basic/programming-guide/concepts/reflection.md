---
title: Reflection (Visual Basic)
ms.date: 07/20/2015
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
ms.openlocfilehash: 59910edda8e2dfc4ec8e697b1d5b9a0f47ff9dbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690111"
---
# <a name="reflection-visual-basic"></a><span data-ttu-id="5bdb9-102">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bdb9-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="5bdb9-103">La reflection specifica oggetti di tipo <xref:System.Type> che descrivono assembly, moduli e tipi.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="5bdb9-104">È possibile usare la reflection per creare in modo dinamico un'istanza di un tipo, associare il tipo a un oggetto esistente oppure ottenere il tipo da un oggetto esistente e richiamarne i metodi o accedere ai relativi campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="5bdb9-105">Se si usano attributi nel codice, la reflection consente di accedervi.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="5bdb9-106">Per altre informazioni, vedere [Attributi](../../../standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="5bdb9-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="5bdb9-107">Di seguito è riportato un esempio semplice di reflection che usa il metodo statico `GetType` ereditato da tutti i tipi dalla classe di base `Object` per ottenere il tipo di una variabile:</span><span class="sxs-lookup"><span data-stu-id="5bdb9-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="5bdb9-108">L'output è:</span><span class="sxs-lookup"><span data-stu-id="5bdb9-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="5bdb9-109">L'esempio seguente usa la reflection per ottenere il nome completo dell'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="5bdb9-110">L'output è:</span><span class="sxs-lookup"><span data-stu-id="5bdb9-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="5bdb9-111">Panoramica della reflection</span><span class="sxs-lookup"><span data-stu-id="5bdb9-111">Reflection Overview</span></span>  
 <span data-ttu-id="5bdb9-112">La reflection è utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5bdb9-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="5bdb9-113">Quando è necessario accedere agli attributi nei metadati del programma.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="5bdb9-114">Per altre informazioni, vedere [Recupero di informazioni memorizzate negli attributi](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="5bdb9-114">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="5bdb9-115">Per esaminare e creare istanze di tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="5bdb9-116">Per creare nuovi tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-116">For building new types at runtime.</span></span> <span data-ttu-id="5bdb9-117">Usare le classi in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="5bdb9-118">Per eseguire l'associazione tardiva, accedere ai metodi per i tipi creati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5bdb9-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="5bdb9-119">Vedere l'argomento relativo a [caricamento e uso dinamico dei tipi](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="5bdb9-119">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5bdb9-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5bdb9-120">Related Sections</span></span>  
 <span data-ttu-id="5bdb9-121">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="5bdb9-121">For more information:</span></span>  
  
-   [<span data-ttu-id="5bdb9-122">Reflection</span><span class="sxs-lookup"><span data-stu-id="5bdb9-122">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="5bdb9-123">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="5bdb9-123">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="5bdb9-124">Reflection e tipi generici</span><span class="sxs-lookup"><span data-stu-id="5bdb9-124">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="5bdb9-125">Recupero di informazioni memorizzate negli attributi</span><span class="sxs-lookup"><span data-stu-id="5bdb9-125">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="5bdb9-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bdb9-126">See also</span></span>
- [<span data-ttu-id="5bdb9-127">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5bdb9-127">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="5bdb9-128">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="5bdb9-128">Assemblies in the Common Language Runtime</span></span>](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md)
