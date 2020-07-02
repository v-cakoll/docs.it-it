---
title: MDA raceOnRCWCleanup
description: Esaminare l'assistente al debug gestito raceOnRCWCleanup, che viene attivato se il wrapper RCW è in uso in un altro thread o nello stack di thread di liberazione in .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
ms.openlocfilehash: e86ef96bebb648c7927ae5fec8b68fc4429b268b
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803651"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="a6cb4-103">MDA raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="a6cb4-103">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="a6cb4-104">L'assistente al debug gestito `raceOnRCWCleanup` viene attivato quando Common Language Runtime (CLR) rileva che è in uso un oggetto [Runtime Callable Wrapper (RCW)](../../standard/native-interop/runtime-callable-wrapper.md) quando viene eseguita una chiamata per rilasciarlo con un comando come il metodo <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a6cb4-104">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a6cb4-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="a6cb4-105">Symptoms</span></span>  
 <span data-ttu-id="a6cb4-106">Violazioni di accesso o danneggiamento della memoria durante o dopo il rilascio di un RCW con <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> o un metodo simile.</span><span class="sxs-lookup"><span data-stu-id="a6cb4-106">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a6cb4-107">Causa</span><span class="sxs-lookup"><span data-stu-id="a6cb4-107">Cause</span></span>  
 <span data-ttu-id="a6cb4-108">Il wrapper RCW è in uso in un altro thread o durante il rilascio dello stack di thread.</span><span class="sxs-lookup"><span data-stu-id="a6cb4-108">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="a6cb4-109">Non è possibile rilasciare un RCW in uso.</span><span class="sxs-lookup"><span data-stu-id="a6cb4-109">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a6cb4-110">Soluzione</span><span class="sxs-lookup"><span data-stu-id="a6cb4-110">Resolution</span></span>  
 <span data-ttu-id="a6cb4-111">Non rilasciare un RCW che potrebbe essere in uso nel thread corrente o in altri.</span><span class="sxs-lookup"><span data-stu-id="a6cb4-111">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a6cb4-112">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="a6cb4-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="a6cb4-113">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="a6cb4-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a6cb4-114">Output</span><span class="sxs-lookup"><span data-stu-id="a6cb4-114">Output</span></span>  
 <span data-ttu-id="a6cb4-115">Messaggio che descrive l'errore.</span><span class="sxs-lookup"><span data-stu-id="a6cb4-115">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a6cb4-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="a6cb4-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6cb4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6cb4-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="a6cb4-118">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="a6cb4-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a6cb4-119">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="a6cb4-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
