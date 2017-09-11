---
title: "Interoperabilità COM (Visual Basic)"
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
helpviewer_keywords:
- Visual Basic code, COM interop
- COM interop, in Visual Basic
ms.assetid: 3ffd1bdf-1b8d-47f5-87eb-75b659f64294
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 29275519a00ad0c33a5b85e592532ce456daefe0
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="com-interop-visual-basic"></a><span data-ttu-id="cfe3a-102">Interoperabilità COM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfe3a-102">COM Interop (Visual Basic)</span></span>
<span data-ttu-id="cfe3a-103">Il modello COM (Component Object Model) consente a un oggetto di esporre la relativa funzionalità agli altri componenti e alle applicazioni host.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-103">The Component Object Model (COM) allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="cfe3a-104">La maggior parte del software in uso oggi include oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-104">Most of today's software includes COM objects.</span></span> <span data-ttu-id="cfe3a-105">Anche se gli assembly .NET sono la scelta migliore per le nuove applicazioni, in alcuni casi può essere necessario usare oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-105">Although .NET assemblies are the best choice for new applications, you may at times need to employ COM objects.</span></span> <span data-ttu-id="cfe3a-106">In questa sezione vengono illustrati alcuni dei problemi associati alla creazione e all'uso degli oggetti COM con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfe3a-106">This section covers some of the issues associated with creating and using COM objects with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfe3a-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cfe3a-107">In This Section</span></span>  
 [<span data-ttu-id="cfe3a-108">Introduzione all'interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="cfe3a-108">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)  
 <span data-ttu-id="cfe3a-109">Offre una panoramica dell'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-109">Provides an overview of COM interoperability.</span></span>  
  
 [<span data-ttu-id="cfe3a-110">Procedura: Fare riferimento a oggetti COM da Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cfe3a-110">How to: Reference COM Objects from Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-reference-com-objects.md)  
 <span data-ttu-id="cfe3a-111">Spiega come aggiungere riferimenti agli oggetti COM con librerie dei tipi.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-111">Covers how to add references to COM objects that have type libraries.</span></span>  
  
 [<span data-ttu-id="cfe3a-112">Procedura: Utilizzare i controlli ActiveX</span><span class="sxs-lookup"><span data-stu-id="cfe3a-112">How to: Work with ActiveX Controls</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-work-with-activex-controls.md)  
 <span data-ttu-id="cfe3a-113">Spiega come usare i controlli ActiveX esistenti per aggiungere funzionalità alla casella degli strumenti di [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfe3a-113">Demonstrates how to use existing ActiveX controls to add features to the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Toolbox.</span></span>  
  
 [<span data-ttu-id="cfe3a-114">Procedura dettagliata: Chiamata delle API di Windows</span><span class="sxs-lookup"><span data-stu-id="cfe3a-114">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 <span data-ttu-id="cfe3a-115">Descrive i passaggi della procedura di chiamata delle API che fanno parte del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-115">Steps you through the process of calling the APIs that are part of the Windows operating system.</span></span>  
  
 [<span data-ttu-id="cfe3a-116">Procedura: Chiamare API di Windows</span><span class="sxs-lookup"><span data-stu-id="cfe3a-116">How to: Call Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-windows-apis.md)  
 <span data-ttu-id="cfe3a-117">Illustra come definire e chiamare la funzione `MessageBox` in User32.dll.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-117">Demonstrates how to define and call the `MessageBox` function in User32.dll.</span></span>  
  
 [<span data-ttu-id="cfe3a-118">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="cfe3a-118">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 <span data-ttu-id="cfe3a-119">Illustra come chiamare una funzione Windows che ha un parametro di tipo senza segno.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-119">Demonstrates how to call a Windows function that has a parameter of an unsigned type.</span></span>  
  
 [<span data-ttu-id="cfe3a-120">Procedura dettagliata: Creazione di oggetti COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cfe3a-120">Walkthrough: Creating COM Objects with Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-creating-com-objects.md)  
 <span data-ttu-id="cfe3a-121">Illustra la procedura di creazione degli oggetti COM con e senza il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-121">Steps you through the process of creating COM objects with and without the COM class template.</span></span>  
  
 [<span data-ttu-id="cfe3a-122">Risoluzione dei problemi relativi all'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cfe3a-122">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 <span data-ttu-id="cfe3a-123">Descrive alcuni dei problemi che possono verificarsi quando si usa COM.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-123">Covers some of the problems you may encounter when using COM.</span></span>  
  
 [<span data-ttu-id="cfe3a-124">Interoperabilità COM nelle applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cfe3a-124">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 <span data-ttu-id="cfe3a-125">Panoramica dell'uso degli oggetti COM e degli oggetti .NET Framework nella stessa applicazione.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-125">Provides an overview of how to use COM objects and .NET Framework objects in the same application.</span></span>  
  
 [<span data-ttu-id="cfe3a-126">Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM</span><span class="sxs-lookup"><span data-stu-id="cfe3a-126">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 <span data-ttu-id="cfe3a-127">Spiega come usare gli oggetti COM esistenti come base per i nuovi oggetti.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-127">Describes using existing COM objects as the basis for new objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cfe3a-128">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="cfe3a-128">Related Sections</span></span>  
 [<span data-ttu-id="cfe3a-129">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="cfe3a-129">Interoperating with Unmanaged Code</span></span>](https://msdn.microsoft.com/library/sd10k43k)  
 <span data-ttu-id="cfe3a-130">Descrive i servizi di interoperabilità forniti da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-130">Describes interoperability services provided by the common language runtime.</span></span>  
  
 [<span data-ttu-id="cfe3a-131">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cfe3a-131">Exposing COM Components to the .NET Framework</span></span>](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730)  
 <span data-ttu-id="cfe3a-132">Descrive il processo di chiamata dei tipi COM usando l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-132">Describes the process of calling COM types through COM interop.</span></span>  
  
 [<span data-ttu-id="cfe3a-133">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="cfe3a-133">Exposing .NET Framework Components to COM</span></span>](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6)  
 <span data-ttu-id="cfe3a-134">Descrive la preparazione e l'uso dei tipi gestiti da COM.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-134">Describes the preparation and use of managed types from COM.</span></span>  
  
 [<span data-ttu-id="cfe3a-135">Applicazione di attributi di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cfe3a-135">Applying Interop Attributes</span></span>](https://msdn.microsoft.com/library/d4w8x20h)  
 <span data-ttu-id="cfe3a-136">Descrive gli attributi che è possibile usare quando si lavora con codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="cfe3a-136">Covers attributes you can use when working with unmanaged code.</span></span>

