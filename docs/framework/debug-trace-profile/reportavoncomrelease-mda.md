---
title: MDA reportAvOnComRelease
description: Esaminare l'assistente al debug gestito reportAvOnComRelease, che può essere attivato a causa di violazioni di accesso e danneggiamento della memoria in .NET.
ms.date: 03/30/2017
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
ms.openlocfilehash: f9ba343060cb4d16de5909a5b619353546aca8ca
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803610"
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="71d0a-103">MDA reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="71d0a-103">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="71d0a-104">L'assistente al debug gestito `reportAvOnComRelease` viene attivato quando vengono generate eccezioni a causa di errori nel conteggio dei riferimenti utente durante l'esecuzione dell'interoperabilità COM e l'uso del metodo <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> in combinazione con chiamate COM non elaborate.</span><span class="sxs-lookup"><span data-stu-id="71d0a-104">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="71d0a-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="71d0a-105">Symptoms</span></span>  
 <span data-ttu-id="71d0a-106">Violazioni di accesso e danneggiamento della memoria.</span><span class="sxs-lookup"><span data-stu-id="71d0a-106">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="71d0a-107">Causa</span><span class="sxs-lookup"><span data-stu-id="71d0a-107">Cause</span></span>  
 <span data-ttu-id="71d0a-108">Occasionalmente viene generata un'eccezione a causa di errori nel conteggio dei riferimenti utente durante l'esecuzione dell'interoperabilità COM e l'uso del metodo <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> in combinazione con chiamate COM non elaborate.</span><span class="sxs-lookup"><span data-stu-id="71d0a-108">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="71d0a-109">Di solito questa eccezione viene eliminata in quanto, in caso contrario, si verificherebbe una violazione di accesso in CLR con il conseguente arresto di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="71d0a-109">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="71d0a-110">Quando l'assistente è abilitato, le eccezioni di questo tipo possono essere rilevate e segnalate anziché semplicemente eliminate.</span><span class="sxs-lookup"><span data-stu-id="71d0a-110">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="71d0a-111">Soluzione</span><span class="sxs-lookup"><span data-stu-id="71d0a-111">Resolution</span></span>  
 <span data-ttu-id="71d0a-112">Esaminare il codice del conteggio dei riferimenti e cercare gli errori e verificare la presenza di errori nel conteggio dei riferimenti sui client nativi dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="71d0a-112">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="71d0a-113">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="71d0a-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="71d0a-114">Sono disponibili due modalità.</span><span class="sxs-lookup"><span data-stu-id="71d0a-114">Two modes are available.</span></span> <span data-ttu-id="71d0a-115">Se l'attributo `allowAv` è `true`, l'assistente impedisce al runtime l'eliminazione della violazione di accesso.</span><span class="sxs-lookup"><span data-stu-id="71d0a-115">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="71d0a-116">Se invece l'attributo `allowAv` è `false`, impostazione predefinita, il runtime elimina la violazione di accesso ma l'utente riceve un messaggio di avviso nel quale è indicato che un'eccezione è stata generata ed eliminata.</span><span class="sxs-lookup"><span data-stu-id="71d0a-116">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="71d0a-117">Output</span><span class="sxs-lookup"><span data-stu-id="71d0a-117">Output</span></span>  
 <span data-ttu-id="71d0a-118">Se possibile, l'output contiene il vtable originale del puntatore a interfaccia COM.</span><span class="sxs-lookup"><span data-stu-id="71d0a-118">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="71d0a-119">In caso contrario, viene visualizzato un messaggio informativo.</span><span class="sxs-lookup"><span data-stu-id="71d0a-119">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="71d0a-120">Configurazione</span><span class="sxs-lookup"><span data-stu-id="71d0a-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="71d0a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71d0a-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="71d0a-122">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="71d0a-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="71d0a-123">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="71d0a-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
