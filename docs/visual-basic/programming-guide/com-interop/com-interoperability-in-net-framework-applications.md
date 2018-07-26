---
title: Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: ceef4255321e208911a16db0227890bc6654b8c5
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244664"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="1e2e9-102">Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e2e9-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="1e2e9-103">Quando si desidera usare oggetti COM e .NET Framework nella stessa applicazione, è necessario risolvere le differenze nel modo in cui gli oggetti presenti in memoria.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="1e2e9-104">Un oggetto .NET Framework si trova nella memoria gestita, ovvero la memoria controllata da common language runtime e può essere spostato dal runtime in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="1e2e9-105">Un oggetto COM si trova nella memoria non gestita e non è previsto per spostare in un'altra posizione di memoria.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="1e2e9-106">Visual Studio e [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] forniscono strumenti per controllare l'interazione di queste gestito e i componenti.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-106">Visual Studio and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="1e2e9-107">Per altre informazioni sul codice gestito, vedere [Common Language Runtime](../../../standard/clr.md).</span><span class="sxs-lookup"><span data-stu-id="1e2e9-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="1e2e9-108">Oltre a usare gli oggetti COM nelle applicazioni .NET, è anche possibile usare Visual Basic per sviluppare gli oggetti accessibili da codice non gestito tramite COM.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="1e2e9-109">I collegamenti in questa pagina offrono informazioni dettagliate sulle interazioni tra gli oggetti COM e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1e2e9-110">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1e2e9-110">Related Sections</span></span>  
 [<span data-ttu-id="1e2e9-111">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="1e2e9-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="1e2e9-112">Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM in Visual Basic, inclusi gli oggetti COM, controlli ActiveX, DLL Win32, gli oggetti gestiti ed ereditarietà degli oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="1e2e9-113">Errore del wrapper di interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="1e2e9-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="1e2e9-114">Descrive le opzioni e conseguenze se il sistema di progetto non è possibile creare un wrapper di interoperabilità COM per un determinato componente.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="1e2e9-115">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="1e2e9-115">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="1e2e9-116">Descrive brevemente alcuni dei problemi di interazione tra codice gestito e e vengono forniti collegamenti per approfondire l'argomento.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="1e2e9-117">Wrapper COM</span><span class="sxs-lookup"><span data-stu-id="1e2e9-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="1e2e9-118">Vengono illustrati i runtime callable wrapper, che consentono al codice gestito chiamare i metodi COM, e COM callable wrapper, che consentono ai client COM di chiamare metodi oggetto .NET.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="1e2e9-119">Interoperabilità COM avanzata</span><span class="sxs-lookup"><span data-stu-id="1e2e9-119">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="1e2e9-120">Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM rispetto al wrapper, eccezioni, ereditarietà, threading, eventi, conversioni e di marshalling.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="1e2e9-121">Tlbimp.exe (utilità di importazione della libreria dei tipi)</span><span class="sxs-lookup"><span data-stu-id="1e2e9-121">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="1e2e9-122">Viene descritto lo strumento che è possibile usare per convertire le definizioni dei tipi presenti all'interno di una libreria dei tipi COM nelle definizioni equivalenti in un assembly di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="1e2e9-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
