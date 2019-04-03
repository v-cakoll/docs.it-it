---
title: Associazione anticipata e tardiva (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 20eb96d0d9f81ec9dfa359edf63a60f72a45aa01
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824793"
---
# <a name="early-and-late-binding-visual-basic"></a><span data-ttu-id="7dc04-102">Associazione anticipata e tardiva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dc04-102">Early and Late Binding (Visual Basic)</span></span>
<span data-ttu-id="7dc04-103">Il compilatore Visual Basic esegue un processo denominato `binding` quando un oggetto viene assegnato a una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="7dc04-103">The Visual Basic compiler performs a process called `binding` when an object is assigned to an object variable.</span></span> <span data-ttu-id="7dc04-104">Un oggetto è *ad associazione anticipata* quando viene assegnato a una variabile di un tipo object specifico.</span><span class="sxs-lookup"><span data-stu-id="7dc04-104">An object is *early bound* when it is assigned to a variable declared to be of a specific object type.</span></span> <span data-ttu-id="7dc04-105">Gli oggetti ad associazione anticipata consentono al compilatore di allocare memoria ed effettuare altre ottimizzazioni prima dell'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7dc04-105">Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes.</span></span> <span data-ttu-id="7dc04-106">Il frammento di codice seguente, ad esempio, dichiara una variabile di tipo <xref:System.IO.FileStream>:</span><span class="sxs-lookup"><span data-stu-id="7dc04-106">For example, the following code fragment declares a variable to be of type <xref:System.IO.FileStream>:</span></span>  
  
 [!code-vb[VbVbalrOOP#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#90)]  
  
 <span data-ttu-id="7dc04-107">Poiché <xref:System.IO.FileStream> è un tipo object specifico, l'istanza assegnata a `FS` è ad associazione anticipata.</span><span class="sxs-lookup"><span data-stu-id="7dc04-107">Because <xref:System.IO.FileStream> is a specific object type, the instance assigned to `FS` is early bound.</span></span>  
  
 <span data-ttu-id="7dc04-108">Al contrario, un oggetto è *ad associazione tardiva* quando viene assegnato a una variabile dichiarata di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="7dc04-108">By contrast, an object is *late bound* when it is assigned to a variable declared to be of type `Object`.</span></span> <span data-ttu-id="7dc04-109">Gli oggetti di questo tipo possono contenere riferimenti a qualsiasi oggetto, ma non presentano molti dei vantaggi offerti dagli oggetti ad associazione anticipata.</span><span class="sxs-lookup"><span data-stu-id="7dc04-109">Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects.</span></span> <span data-ttu-id="7dc04-110">Il frammento di codice seguente, ad esempio, dichiara una variabile oggetto contenente un oggetto restituito dalla funzione `CreateObject`:</span><span class="sxs-lookup"><span data-stu-id="7dc04-110">For example, the following code fragment declares an object variable to hold an object returned by the `CreateObject` function:</span></span>  
  
 [!code-vb[VbVbalrOOP#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/LateBinding.vb#91)]  
  
## <a name="advantages-of-early-binding"></a><span data-ttu-id="7dc04-111">Vantaggi offerti dall'associazione anticipata</span><span class="sxs-lookup"><span data-stu-id="7dc04-111">Advantages of Early Binding</span></span>  
 <span data-ttu-id="7dc04-112">Quando possibile, è consigliabile usare oggetti ad associazione anticipata. Tali oggetti consentono infatti al compilatore di eseguire ottimizzazioni significative che aumentano l'efficienza delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7dc04-112">You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications.</span></span> <span data-ttu-id="7dc04-113">Gli oggetti ad associazione anticipata sono notevolmente più veloci di quelli ad associazione tardiva e facilitano la lettura e la gestione del codice dichiarando esattamente il tipo degli oggetti usati.</span><span class="sxs-lookup"><span data-stu-id="7dc04-113">Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used.</span></span> <span data-ttu-id="7dc04-114">Un altro vantaggio dall'associazione anticipata è che consente la funzionalità utili, ad esempio il completamento del codice automatica e la Guida dinamica perché l'ambiente di sviluppo integrato (IDE) di Visual Studio è possibile determinare esattamente quale tipo di oggetto vengono utilizzati durante la modifica di codice.</span><span class="sxs-lookup"><span data-stu-id="7dc04-114">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the Visual Studio integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span></span> <span data-ttu-id="7dc04-115">L'associazione anticipata riduce il numero e la gravità degli errori di run-time poiché consente al compilatore di segnalare gli errori al momento della compilazione di un programma.</span><span class="sxs-lookup"><span data-stu-id="7dc04-115">Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dc04-116">L'associazione tardiva può essere usata soltanto per accedere ai membri di tipi che vengono dichiarati come `Public`.</span><span class="sxs-lookup"><span data-stu-id="7dc04-116">Late binding can only be used to access type members that are declared as `Public`.</span></span> <span data-ttu-id="7dc04-117">L'accesso a membri dichiarati come `Friend` o `Protected Friend` determina un errore di run-time.</span><span class="sxs-lookup"><span data-stu-id="7dc04-117">Accessing members declared as `Friend` or `Protected Friend` results in a run-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc04-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dc04-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>
- [<span data-ttu-id="7dc04-119">Durata degli oggetti: Come gli oggetti vengono creati ed eliminati</span><span class="sxs-lookup"><span data-stu-id="7dc04-119">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [<span data-ttu-id="7dc04-120">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="7dc04-120">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
