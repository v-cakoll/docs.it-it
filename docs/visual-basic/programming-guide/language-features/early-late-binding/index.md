---
title: Associazione anticipata e tardiva (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aceffe59fb6043b3089621b9a3f95b0425f9a522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="early-and-late-binding-visual-basic"></a><span data-ttu-id="102f9-102">Associazione anticipata e tardiva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="102f9-102">Early and Late Binding (Visual Basic)</span></span>
<span data-ttu-id="102f9-103">Quando un oggetto viene assegnato a una variabile oggetto, il compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] esegue un processo denominato `binding`.</span><span class="sxs-lookup"><span data-stu-id="102f9-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler performs a process called `binding` when an object is assigned to an object variable.</span></span> <span data-ttu-id="102f9-104">Un oggetto è *ad associazione anticipata* quando viene assegnato a una variabile di un tipo object specifico.</span><span class="sxs-lookup"><span data-stu-id="102f9-104">An object is *early bound* when it is assigned to a variable declared to be of a specific object type.</span></span> <span data-ttu-id="102f9-105">Gli oggetti ad associazione anticipata consentono al compilatore di allocare memoria ed effettuare altre ottimizzazioni prima dell'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="102f9-105">Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes.</span></span> <span data-ttu-id="102f9-106">Il frammento di codice seguente, ad esempio, dichiara una variabile di tipo <xref:System.IO.FileStream>:</span><span class="sxs-lookup"><span data-stu-id="102f9-106">For example, the following code fragment declares a variable to be of type <xref:System.IO.FileStream>:</span></span>  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 <span data-ttu-id="102f9-107">Poiché <xref:System.IO.FileStream> è un tipo object specifico, l'istanza assegnata a `FS` è ad associazione anticipata.</span><span class="sxs-lookup"><span data-stu-id="102f9-107">Because <xref:System.IO.FileStream> is a specific object type, the instance assigned to `FS` is early bound.</span></span>  
  
 <span data-ttu-id="102f9-108">Al contrario, un oggetto è *ad associazione tardiva* quando viene assegnato a una variabile dichiarata di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="102f9-108">By contrast, an object is *late bound* when it is assigned to a variable declared to be of type `Object`.</span></span> <span data-ttu-id="102f9-109">Gli oggetti di questo tipo possono contenere riferimenti a qualsiasi oggetto, ma non presentano molti dei vantaggi offerti dagli oggetti ad associazione anticipata.</span><span class="sxs-lookup"><span data-stu-id="102f9-109">Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects.</span></span> <span data-ttu-id="102f9-110">Il frammento di codice seguente, ad esempio, dichiara una variabile oggetto contenente un oggetto restituito dalla funzione `CreateObject`:</span><span class="sxs-lookup"><span data-stu-id="102f9-110">For example, the following code fragment declares an object variable to hold an object returned by the `CreateObject` function:</span></span>  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## <a name="advantages-of-early-binding"></a><span data-ttu-id="102f9-111">Vantaggi offerti dall'associazione anticipata</span><span class="sxs-lookup"><span data-stu-id="102f9-111">Advantages of Early Binding</span></span>  
 <span data-ttu-id="102f9-112">Quando possibile, è consigliabile usare oggetti ad associazione anticipata. Tali oggetti consentono infatti al compilatore di eseguire ottimizzazioni significative che aumentano l'efficienza delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="102f9-112">You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications.</span></span> <span data-ttu-id="102f9-113">Gli oggetti ad associazione anticipata sono notevolmente più veloci di quelli ad associazione tardiva e facilitano la lettura e la gestione del codice dichiarando esattamente il tipo degli oggetti usati.</span><span class="sxs-lookup"><span data-stu-id="102f9-113">Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used.</span></span> <span data-ttu-id="102f9-114">Un altro vantaggio offerto dall'associazione anticipata è l'abilitazione di funzionalità utili quali il completamento automatico del codice e la Guida dinamica, perché l'ambiente di sviluppo integrato (IDE) [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] è in grado di determinare esattamente quale tipo di oggetto viene utilizzato durante la modifica del codice.</span><span class="sxs-lookup"><span data-stu-id="102f9-114">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span></span> <span data-ttu-id="102f9-115">L'associazione anticipata riduce il numero e la gravità degli errori di run-time poiché consente al compilatore di segnalare gli errori al momento della compilazione di un programma.</span><span class="sxs-lookup"><span data-stu-id="102f9-115">Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="102f9-116">L'associazione tardiva può essere usata soltanto per accedere ai membri di tipi che vengono dichiarati come `Public`.</span><span class="sxs-lookup"><span data-stu-id="102f9-116">Late binding can only be used to access type members that are declared as `Public`.</span></span> <span data-ttu-id="102f9-117">L'accesso a membri dichiarati come `Friend` o `Protected Friend` determina un errore di run-time.</span><span class="sxs-lookup"><span data-stu-id="102f9-117">Accessing members declared as `Friend` or `Protected Friend` results in a run-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="102f9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="102f9-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>  
 [<span data-ttu-id="102f9-119">Durata degli oggetti: come creare e distruggere oggetti</span><span class="sxs-lookup"><span data-stu-id="102f9-119">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [<span data-ttu-id="102f9-120">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="102f9-120">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
