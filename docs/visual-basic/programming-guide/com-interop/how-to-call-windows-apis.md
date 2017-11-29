---
title: 'Procedura: chiamare API di Windows (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a219e031cdd36c713db8dcee6cc1da3849c9cf93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="76a55-102">Procedura: chiamare API di Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76a55-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="76a55-103">In questo esempio definisce e chiama il `MessageBox` funzione User32. dll e quindi passa una stringa a esso.</span><span class="sxs-lookup"><span data-stu-id="76a55-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76a55-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="76a55-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="76a55-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="76a55-105">Compiling the Code</span></span>  
 <span data-ttu-id="76a55-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a55-106">This example requires:</span></span>  
  
-   <span data-ttu-id="76a55-107">Un riferimento allo spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="76a55-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="76a55-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="76a55-108">Robust Programming</span></span>  
 <span data-ttu-id="76a55-109">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="76a55-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="76a55-110">Il metodo non è statico, è di tipo abstract o è già stato definito.</span><span class="sxs-lookup"><span data-stu-id="76a55-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="76a55-111">Il tipo padre è un'interfaccia o la lunghezza di *nome* o *NomeDLL* è zero.</span><span class="sxs-lookup"><span data-stu-id="76a55-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="76a55-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="76a55-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="76a55-113">Il *nome* o *NomeDLL* è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="76a55-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="76a55-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="76a55-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="76a55-115">Il tipo contenitore è stato creato in precedenza con `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="76a55-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="76a55-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="76a55-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a55-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76a55-117">See Also</span></span>  
 [<span data-ttu-id="76a55-118">Informazioni dettagliate su Platform Invoke</span><span class="sxs-lookup"><span data-stu-id="76a55-118">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="76a55-119">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="76a55-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="76a55-120">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="76a55-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="76a55-121">Definizione di un metodo con Reflection Emit</span><span class="sxs-lookup"><span data-stu-id="76a55-121">Defining a Method with Reflection Emit</span></span>](http://msdn.microsoft.com/en-us/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [<span data-ttu-id="76a55-122">Procedura dettagliata: Chiamata delle API di Windows</span><span class="sxs-lookup"><span data-stu-id="76a55-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="76a55-123">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="76a55-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
