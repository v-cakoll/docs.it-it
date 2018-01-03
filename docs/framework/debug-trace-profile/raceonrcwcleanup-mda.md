---
title: MDA raceOnRCWCleanup
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33d1c7d91c33c194353af43deed9329b9b4ec841
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="342f9-102">MDA raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="342f9-102">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="342f9-103">L'assistente al debug gestito `raceOnRCWCleanup` viene attivato quando Common Language Runtime (CLR) rileva che è in uso un oggetto [Runtime Callable Wrapper (RCW)](../../../docs/framework/interop/runtime-callable-wrapper.md) quando viene eseguita una chiamata per rilasciarlo con un comando come il metodo <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="342f9-103">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="342f9-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="342f9-104">Symptoms</span></span>  
 <span data-ttu-id="342f9-105">Violazioni di accesso o danneggiamento della memoria durante o dopo il rilascio di un RCW con <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> o un metodo simile.</span><span class="sxs-lookup"><span data-stu-id="342f9-105">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="342f9-106">Causa</span><span class="sxs-lookup"><span data-stu-id="342f9-106">Cause</span></span>  
 <span data-ttu-id="342f9-107">Il wrapper RCW è in uso in un altro thread o durante il rilascio dello stack di thread.</span><span class="sxs-lookup"><span data-stu-id="342f9-107">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="342f9-108">Non è possibile rilasciare un RCW in uso.</span><span class="sxs-lookup"><span data-stu-id="342f9-108">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="342f9-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="342f9-109">Resolution</span></span>  
 <span data-ttu-id="342f9-110">Non rilasciare un RCW che potrebbe essere in uso nel thread corrente o in altri.</span><span class="sxs-lookup"><span data-stu-id="342f9-110">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="342f9-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="342f9-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="342f9-112">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="342f9-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="342f9-113">Output</span><span class="sxs-lookup"><span data-stu-id="342f9-113">Output</span></span>  
 <span data-ttu-id="342f9-114">Messaggio che descrive l'errore.</span><span class="sxs-lookup"><span data-stu-id="342f9-114">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="342f9-115">Configurazione</span><span class="sxs-lookup"><span data-stu-id="342f9-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="342f9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="342f9-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="342f9-117">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="342f9-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="342f9-118">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="342f9-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
