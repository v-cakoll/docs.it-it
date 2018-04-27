---
title: Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25fbde3845d378d4a2bcfc13c71124ad1bc29514
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="dd1a5-102">Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd1a5-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="dd1a5-103">Quando si desidera utilizzare oggetti COM e .NET Framework nella stessa applicazione, è necessario risolvere le differenze nella modalità con cui gli oggetti presenti in memoria.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="dd1a5-104">Un oggetto .NET Framework si trova nella memoria gestita, la memoria controllata da common language runtime e possono essere spostati dal runtime in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="dd1a5-105">Un oggetto COM si trova nella memoria non gestita e non è previsto per spostare in un'altra posizione di memoria.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="dd1a5-106"> e [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] forniscono strumenti per controllare l'interazione di questi gestito e componenti.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-106"> and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="dd1a5-107">Per ulteriori informazioni sul codice gestito, vedere [Common Language Runtime](../../../standard/clr.md).</span><span class="sxs-lookup"><span data-stu-id="dd1a5-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="dd1a5-108">Oltre a utilizzare gli oggetti COM nelle applicazioni .NET, è possibile che si voglia usare Visual Basic per sviluppare gli oggetti accessibili dal codice non gestito tramite COM.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="dd1a5-109">I collegamenti in questa pagina forniscono dettagli sulle interazioni tra gli oggetti COM e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dd1a5-110">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="dd1a5-110">Related Sections</span></span>  
 [<span data-ttu-id="dd1a5-111">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="dd1a5-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="dd1a5-112">Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM in Visual Basic, inclusi gli oggetti COM, controlli ActiveX, DLL Win32, oggetti gestiti ed ereditarietà degli oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="dd1a5-113">Errore del wrapper di interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="dd1a5-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="dd1a5-114">Descrive le opzioni e conseguenze se il sistema del progetto non è possibile creare un wrapper di interoperabilità COM per un determinato componente.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="dd1a5-115">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="dd1a5-115">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="dd1a5-116">Descrive brevemente alcuni problemi di interazione tra codice gestito e e vengono forniti collegamenti a ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="dd1a5-117">Wrapper COM</span><span class="sxs-lookup"><span data-stu-id="dd1a5-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="dd1a5-118">Vengono descritti i runtime callable wrapper, che consentono di codice gestito di chiamare i metodi COM, e COM callable wrapper, che consentono ai client COM di chiamare metodi oggetto .NET.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="dd1a5-119">Interoperabilità COM avanzata</span><span class="sxs-lookup"><span data-stu-id="dd1a5-119">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="dd1a5-120">Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM rispetto wrapper, eccezioni, ereditarietà, threading, eventi, conversioni e marshalling.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="dd1a5-121">Tlbimp.exe (utilità di importazione della libreria dei tipi)</span><span class="sxs-lookup"><span data-stu-id="dd1a5-121">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="dd1a5-122">Viene descritto lo strumento che è possibile utilizzare per convertire le definizioni dei tipi presenti all'interno di una libreria dei tipi COM nelle definizioni equivalenti in un assembly di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="dd1a5-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
