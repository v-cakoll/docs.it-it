---
title: Interoperabilità COM (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, COM interop
- COM interop [Visual Basic], in Visual Basic
ms.assetid: 3ffd1bdf-1b8d-47f5-87eb-75b659f64294
ms.openlocfilehash: 1bcfba25c86c46f986c061241a5d09f9aaa6d248
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627078"
---
# <a name="com-interop-visual-basic"></a><span data-ttu-id="f48f5-102">Interoperabilità COM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f48f5-102">COM Interop (Visual Basic)</span></span>
<span data-ttu-id="f48f5-103">Il modello COM (Component Object Model) consente a un oggetto di esporre la relativa funzionalità agli altri componenti e alle applicazioni host.</span><span class="sxs-lookup"><span data-stu-id="f48f5-103">The Component Object Model (COM) allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="f48f5-104">La maggior parte del software in uso oggi include oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="f48f5-104">Most of today's software includes COM objects.</span></span> <span data-ttu-id="f48f5-105">Anche se gli assembly .NET sono la scelta migliore per le nuove applicazioni, in alcuni casi può essere necessario usare oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="f48f5-105">Although .NET assemblies are the best choice for new applications, you may at times need to employ COM objects.</span></span> <span data-ttu-id="f48f5-106">In questa sezione vengono illustrati alcuni dei problemi associati alla creazione e all'utilizzo di oggetti COM con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f48f5-106">This section covers some of the issues associated with creating and using COM objects with Visual Basic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f48f5-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f48f5-107">In This Section</span></span>  
 [<span data-ttu-id="f48f5-108">Introduzione all'interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="f48f5-108">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)  
 <span data-ttu-id="f48f5-109">Offre una panoramica dell'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="f48f5-109">Provides an overview of COM interoperability.</span></span>  
  
 [<span data-ttu-id="f48f5-110">Procedura: Fare riferimento a oggetti COM da Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f48f5-110">How to: Reference COM Objects from Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-reference-com-objects.md)  
 <span data-ttu-id="f48f5-111">Spiega come aggiungere riferimenti agli oggetti COM con librerie dei tipi.</span><span class="sxs-lookup"><span data-stu-id="f48f5-111">Covers how to add references to COM objects that have type libraries.</span></span>  
  
 [<span data-ttu-id="f48f5-112">Procedura: Utilizzare i controlli ActiveX</span><span class="sxs-lookup"><span data-stu-id="f48f5-112">How to: Work with ActiveX Controls</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-work-with-activex-controls.md)  
 <span data-ttu-id="f48f5-113">Viene illustrato come utilizzare i controlli ActiveX esistenti per aggiungere funzionalità alla casella degli strumenti di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f48f5-113">Demonstrates how to use existing ActiveX controls to add features to the Visual Studio Toolbox.</span></span>  
  
 [<span data-ttu-id="f48f5-114">Procedura dettagliata: Chiamata delle API di Windows</span><span class="sxs-lookup"><span data-stu-id="f48f5-114">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 <span data-ttu-id="f48f5-115">Descrive i passaggi della procedura di chiamata delle API che fanno parte del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="f48f5-115">Steps you through the process of calling the APIs that are part of the Windows operating system.</span></span>  
  
 [<span data-ttu-id="f48f5-116">Procedura: Chiamare le API di Windows</span><span class="sxs-lookup"><span data-stu-id="f48f5-116">How to: Call Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-windows-apis.md)  
 <span data-ttu-id="f48f5-117">Illustra come definire e chiamare la funzione `MessageBox` in User32.dll.</span><span class="sxs-lookup"><span data-stu-id="f48f5-117">Demonstrates how to define and call the `MessageBox` function in User32.dll.</span></span>  
  
 [<span data-ttu-id="f48f5-118">Procedura: Chiamare una funzione Windows che accetta tipi senza segno</span><span class="sxs-lookup"><span data-stu-id="f48f5-118">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 <span data-ttu-id="f48f5-119">Illustra come chiamare una funzione Windows che ha un parametro di tipo senza segno.</span><span class="sxs-lookup"><span data-stu-id="f48f5-119">Demonstrates how to call a Windows function that has a parameter of an unsigned type.</span></span>  
  
 [<span data-ttu-id="f48f5-120">Procedura dettagliata: Creazione di oggetti COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f48f5-120">Walkthrough: Creating COM Objects with Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-creating-com-objects.md)  
 <span data-ttu-id="f48f5-121">Illustra la procedura di creazione degli oggetti COM con e senza il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="f48f5-121">Steps you through the process of creating COM objects with and without the COM class template.</span></span>  
  
 [<span data-ttu-id="f48f5-122">Risoluzione dei problemi relativi all'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f48f5-122">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 <span data-ttu-id="f48f5-123">Descrive alcuni dei problemi che possono verificarsi quando si usa COM.</span><span class="sxs-lookup"><span data-stu-id="f48f5-123">Covers some of the problems you may encounter when using COM.</span></span>  
  
 [<span data-ttu-id="f48f5-124">Interoperabilità COM nelle applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f48f5-124">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 <span data-ttu-id="f48f5-125">Panoramica dell'uso degli oggetti COM e degli oggetti .NET Framework nella stessa applicazione.</span><span class="sxs-lookup"><span data-stu-id="f48f5-125">Provides an overview of how to use COM objects and .NET Framework objects in the same application.</span></span>  
  
 [<span data-ttu-id="f48f5-126">Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM</span><span class="sxs-lookup"><span data-stu-id="f48f5-126">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 <span data-ttu-id="f48f5-127">Spiega come usare gli oggetti COM esistenti come base per i nuovi oggetti.</span><span class="sxs-lookup"><span data-stu-id="f48f5-127">Describes using existing COM objects as the basis for new objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f48f5-128">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="f48f5-128">Related Sections</span></span>  
 [<span data-ttu-id="f48f5-129">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="f48f5-129">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="f48f5-130">Descrive i servizi di interoperabilità forniti da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f48f5-130">Describes interoperability services provided by the common language runtime.</span></span>  
  
 [<span data-ttu-id="f48f5-131">Esposizione di componenti COM a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f48f5-131">Exposing COM Components to the .NET Framework</span></span>](../../../framework/interop/exposing-com-components.md)  
 <span data-ttu-id="f48f5-132">Descrive il processo di chiamata dei tipi COM usando l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="f48f5-132">Describes the process of calling COM types through COM interop.</span></span>  
  
 [<span data-ttu-id="f48f5-133">Esposizione di componenti .NET Framework a COM</span><span class="sxs-lookup"><span data-stu-id="f48f5-133">Exposing .NET Framework Components to COM</span></span>](../../../framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="f48f5-134">Descrive la preparazione e l'uso dei tipi gestiti da COM.</span><span class="sxs-lookup"><span data-stu-id="f48f5-134">Describes the preparation and use of managed types from COM.</span></span>  
  
 [<span data-ttu-id="f48f5-135">Applicazione di attributi di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f48f5-135">Applying Interop Attributes</span></span>](../../../standard/native-interop/apply-interop-attributes.md)  
 <span data-ttu-id="f48f5-136">Descrive gli attributi che è possibile usare quando si lavora con codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="f48f5-136">Covers attributes you can use when working with unmanaged code.</span></span>
