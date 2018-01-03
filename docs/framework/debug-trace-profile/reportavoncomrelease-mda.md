---
title: MDA reportAvOnComRelease
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b198c6a026cded788c0030f1319b37e874d0eb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="2f0a9-102">MDA reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="2f0a9-102">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="2f0a9-103">L'assistente al debug gestito `reportAvOnComRelease` viene attivato quando vengono generate eccezioni a causa di errori nel conteggio dei riferimenti utente durante l'esecuzione dell'interoperabilità COM e l'uso del metodo <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> in combinazione con chiamate COM non elaborate.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-103">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="2f0a9-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="2f0a9-104">Symptoms</span></span>  
 <span data-ttu-id="2f0a9-105">Violazioni di accesso e danneggiamento della memoria.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-105">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="2f0a9-106">Causa</span><span class="sxs-lookup"><span data-stu-id="2f0a9-106">Cause</span></span>  
 <span data-ttu-id="2f0a9-107">Occasionalmente viene generata un'eccezione a causa di errori nel conteggio dei riferimenti utente durante l'esecuzione dell'interoperabilità COM e l'uso del metodo <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> in combinazione con chiamate COM non elaborate.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-107">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="2f0a9-108">Di solito questa eccezione viene eliminata in quanto, in caso contrario, si verificherebbe una violazione di accesso in CLR con il conseguente arresto di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-108">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="2f0a9-109">Quando l'assistente è abilitato, le eccezioni di questo tipo possono essere rilevate e segnalate anziché semplicemente eliminate.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-109">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="2f0a9-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="2f0a9-110">Resolution</span></span>  
 <span data-ttu-id="2f0a9-111">Esaminare il codice del conteggio dei riferimenti e cercare gli errori e verificare la presenza di errori nel conteggio dei riferimenti sui client nativi dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-111">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="2f0a9-112">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="2f0a9-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="2f0a9-113">Sono disponibili due modalità.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-113">Two modes are available.</span></span> <span data-ttu-id="2f0a9-114">Se l'attributo `allowAv` è `true`, l'assistente impedisce al runtime l'eliminazione della violazione di accesso.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-114">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="2f0a9-115">Se invece l'attributo `allowAv` è `false`, impostazione predefinita, il runtime elimina la violazione di accesso ma l'utente riceve un messaggio di avviso nel quale è indicato che un'eccezione è stata generata ed eliminata.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-115">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="2f0a9-116">Output</span><span class="sxs-lookup"><span data-stu-id="2f0a9-116">Output</span></span>  
 <span data-ttu-id="2f0a9-117">Se possibile, l'output contiene il vtable originale del puntatore a interfaccia COM.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-117">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="2f0a9-118">In caso contrario, viene visualizzato un messaggio informativo.</span><span class="sxs-lookup"><span data-stu-id="2f0a9-118">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="2f0a9-119">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2f0a9-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f0a9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f0a9-120">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="2f0a9-121">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="2f0a9-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="2f0a9-122">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="2f0a9-122">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
