---
title: "Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic) | Documenti di Microsoft"
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
- interoperability, COM and .NET framework objects
- COM interop
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6b68f35c1c63e2d7d229f89336b86c4a062e5ec9
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="515c7-102">Interoperabilità COM nelle applicazioni .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="515c7-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="515c7-103">Quando si desidera utilizzare oggetti COM e .NET Framework nella stessa applicazione, è necessario risolvere le differenze nella modalità con cui gli oggetti presenti in memoria.</span><span class="sxs-lookup"><span data-stu-id="515c7-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="515c7-104">Un oggetto .NET Framework si trova nella memoria gestita, la memoria controllata da common language runtime e possono essere spostati dal runtime in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="515c7-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="515c7-105">Un oggetto COM si trova nella memoria non gestita e non è previsto per spostare in un'altra posizione di memoria.</span><span class="sxs-lookup"><span data-stu-id="515c7-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="515c7-106">e [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] forniscono strumenti per controllare l'interazione tra le gestite e i componenti.</span><span class="sxs-lookup"><span data-stu-id="515c7-106"> and the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="515c7-107">Per ulteriori informazioni sul codice gestito, vedere [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).</span><span class="sxs-lookup"><span data-stu-id="515c7-107">For more information about managed code, see [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).</span></span>  
  
 <span data-ttu-id="515c7-108">Oltre a utilizzare oggetti COM nelle applicazioni .NET, è inoltre consiglia di utilizzare [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] per sviluppare oggetti accessibili dal codice non gestito tramite COM.</span><span class="sxs-lookup"><span data-stu-id="515c7-108">In addition to using COM objects in .NET applications, you may also want to use [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="515c7-109">I collegamenti in questa pagina forniscono dettagli sulle interazioni tra gli oggetti COM e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="515c7-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="515c7-110">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="515c7-110">Related Sections</span></span>  
 [<span data-ttu-id="515c7-111">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="515c7-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="515c7-112">Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM in Visual Basic, inclusi gli oggetti COM, controlli ActiveX, DLL Win32, gli oggetti gestiti ed ereditarietà degli oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="515c7-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="515c7-113">Errore del wrapper di interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="515c7-113">COM Interop Wrapper Error</span></span>](https://docs.microsoft.com/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="515c7-114">Descrive le conseguenze e le opzioni se il sistema di progetto non può creare un wrapper di interoperabilità COM per un particolare componente.</span><span class="sxs-lookup"><span data-stu-id="515c7-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="515c7-115">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="515c7-115">Interoperating with Unmanaged Code</span></span>](https://msdn.microsoft.com/library/sd10k43k)  
 <span data-ttu-id="515c7-116">Descrive brevemente alcuni dei problemi di interazione tra codice gestito e e vengono forniti collegamenti per approfondire l'argomento.</span><span class="sxs-lookup"><span data-stu-id="515c7-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="515c7-117">Wrapper COM</span><span class="sxs-lookup"><span data-stu-id="515c7-117">COM Wrappers</span></span>](http://msdn.microsoft.com/library/e56c485b-6b67-4345-8e66-fd21835a6092)  
 <span data-ttu-id="515c7-118">Vengono illustrati i runtime callable wrapper, che consentono al codice gestito chiamare i metodi COM, e COM callable wrapper, che consentono ai client COM di chiamare metodi oggetto .NET.</span><span class="sxs-lookup"><span data-stu-id="515c7-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="515c7-119">Interoperabilità COM avanzata</span><span class="sxs-lookup"><span data-stu-id="515c7-119">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="515c7-120">Vengono forniti collegamenti ad argomenti che illustrano l'interoperabilità COM per quanto riguarda i wrapper, eccezioni, ereditarietà, threading, eventi, conversioni e marshalling.</span><span class="sxs-lookup"><span data-stu-id="515c7-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="515c7-121">Tlbimp.exe (Type Library Importer)</span><span class="sxs-lookup"><span data-stu-id="515c7-121">Tlbimp.exe (Type Library Importer)</span></span>](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 <span data-ttu-id="515c7-122">Viene descritto lo strumento che è possibile utilizzare per convertire le definizioni dei tipi presenti in una libreria dei tipi COM nelle definizioni equivalenti in un assembly di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="515c7-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
