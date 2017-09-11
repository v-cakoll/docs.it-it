---
title: Reflection (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: acfcb519128de0d616757398c94ec70dc7de6ef1
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="reflection-visual-basic"></a><span data-ttu-id="66c2e-102">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66c2e-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="66c2e-103">La reflection fornisce oggetti (di tipo <xref:System.Type>) che descrivono gli assembly, moduli e tipi.</xref:System.Type></span><span class="sxs-lookup"><span data-stu-id="66c2e-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="66c2e-104">È possibile utilizzare la reflection per creare un'istanza di un tipo, associare il tipo a un oggetto esistente, o ottenere il tipo da un oggetto esistente e richiamarne i metodi o dinamicamente accedere ai relativi campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="66c2e-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="66c2e-105">Se si utilizza gli attributi nel codice, la reflection consente di accedervi.</span><span class="sxs-lookup"><span data-stu-id="66c2e-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="66c2e-106">Per ulteriori informazioni, vedere [attributi](https://msdn.microsoft.com/library/5x6cd29c).</span><span class="sxs-lookup"><span data-stu-id="66c2e-106">For more information, see [Attributes](https://msdn.microsoft.com/library/5x6cd29c).</span></span>  
  
 <span data-ttu-id="66c2e-107">Di seguito è riportato un esempio semplice di reflection che utilizza il metodo statico `GetType` , ereditato da tutti i tipi del `Object` - classe per ottenere il tipo di una variabile di base:</span><span class="sxs-lookup"><span data-stu-id="66c2e-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="66c2e-108">L'output è:</span><span class="sxs-lookup"><span data-stu-id="66c2e-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="66c2e-109">Nell'esempio seguente utilizza la reflection per ottenere il nome completo dell'assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="66c2e-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="66c2e-110">L'output è:</span><span class="sxs-lookup"><span data-stu-id="66c2e-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="66c2e-111">Cenni preliminari sulla reflection</span><span class="sxs-lookup"><span data-stu-id="66c2e-111">Reflection Overview</span></span>  
 <span data-ttu-id="66c2e-112">Reflection è utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66c2e-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="66c2e-113">Quando è necessario accedere agli attributi nei metadati del programma.</span><span class="sxs-lookup"><span data-stu-id="66c2e-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="66c2e-114">Per ulteriori informazioni, vedere [il recupero di informazioni memorizzate negli attributi](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).</span><span class="sxs-lookup"><span data-stu-id="66c2e-114">For more information, see [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).</span></span>  
  
-   <span data-ttu-id="66c2e-115">Per esaminare e creare istanze di tipi in un assembly.</span><span class="sxs-lookup"><span data-stu-id="66c2e-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="66c2e-116">Per la creazione di nuovi tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="66c2e-116">For building new types at runtime.</span></span> <span data-ttu-id="66c2e-117">Utilizzare le classi in <xref:System.Reflection.Emit>.</xref:System.Reflection.Emit></span><span class="sxs-lookup"><span data-stu-id="66c2e-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="66c2e-118">Per eseguire l'associazione tardiva, accedere ai metodi su tipi creati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="66c2e-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="66c2e-119">Vedere l'argomento [dinamicamente durante il caricamento e utilizzo dei tipi](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).</span><span class="sxs-lookup"><span data-stu-id="66c2e-119">See the topic [Dynamically Loading and Using Types](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="66c2e-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="66c2e-120">Related Sections</span></span>  
 <span data-ttu-id="66c2e-121">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="66c2e-121">For more information:</span></span>  
  
-   [<span data-ttu-id="66c2e-122">Reflection</span><span class="sxs-lookup"><span data-stu-id="66c2e-122">Reflection</span></span>](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [<span data-ttu-id="66c2e-123">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="66c2e-123">Viewing Type Information</span></span>](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [<span data-ttu-id="66c2e-124">Reflection e tipi generici</span><span class="sxs-lookup"><span data-stu-id="66c2e-124">Reflection and Generic Types</span></span>](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <span data-ttu-id="66c2e-125"><xref:System.Reflection.Emit></xref:System.Reflection.Emit></span><span class="sxs-lookup"><span data-stu-id="66c2e-125"><xref:System.Reflection.Emit></span></span>  
  
-   [<span data-ttu-id="66c2e-126">Recupero di informazioni memorizzate negli attributi</span><span class="sxs-lookup"><span data-stu-id="66c2e-126">Retrieving Information Stored in Attributes</span></span>](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a><span data-ttu-id="66c2e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66c2e-127">See Also</span></span>  
 <span data-ttu-id="66c2e-128">[Guida per programmatori Visual Basic](../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="66c2e-128">[Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="66c2e-129"> [Assembly in Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)</span><span class="sxs-lookup"><span data-stu-id="66c2e-129"> [Assemblies in the Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)</span></span>
