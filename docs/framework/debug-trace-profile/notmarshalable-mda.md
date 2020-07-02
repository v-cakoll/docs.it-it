---
title: notMarshalable (MDA)
description: Esaminare l'assistente al debug gestito notMarshalable, che può essere attivato se le chiamate non vengono gestite o si verificano nel contesto errato per i puntatori di interfaccia COM.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
ms.openlocfilehash: b464d914a8d83504daaf4cb276914da7798262dc
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803794"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="f94aa-103">notMarshalable (MDA)</span><span class="sxs-lookup"><span data-stu-id="f94aa-103">notMarshalable MDA</span></span>
<span data-ttu-id="f94aa-104">L'assistente al debug gestito `notMarshalable` viene attivato quando Common Language Runtime rileva un puntatore a interfaccia COM senza un proxy/stub registrato valido oppure un'implementazione non corretta dell'interfaccia `IMarshal` durante il marshalling dell'interfaccia tra i vari contesti.</span><span class="sxs-lookup"><span data-stu-id="f94aa-104">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f94aa-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="f94aa-105">Symptoms</span></span>  
 <span data-ttu-id="f94aa-106">Le chiamate non vengono eseguite oppure vengono eseguite nel contesto errato per i puntatori a interfaccia COM.</span><span class="sxs-lookup"><span data-stu-id="f94aa-106">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f94aa-107">Causa</span><span class="sxs-lookup"><span data-stu-id="f94aa-107">Cause</span></span>  
 <span data-ttu-id="f94aa-108">Nessun proxy/stub registrato valido oppure un'implementazione non corretta dell'interfaccia `IMarshal` durante il marshalling dell'interfaccia tra i vari contesti.</span><span class="sxs-lookup"><span data-stu-id="f94aa-108">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f94aa-109">Soluzione</span><span class="sxs-lookup"><span data-stu-id="f94aa-109">Resolution</span></span>  
 <span data-ttu-id="f94aa-110">Assicurarsi di disporre di uno stub proxy registrato e che l'implementazione dell'interfaccia `IMarshal` sia valida.</span><span class="sxs-lookup"><span data-stu-id="f94aa-110">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f94aa-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="f94aa-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="f94aa-112">L'assistente al debug gestito non ha alcun effetto sull'ambiente di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f94aa-112">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f94aa-113">Output</span><span class="sxs-lookup"><span data-stu-id="f94aa-113">Output</span></span>  
 <span data-ttu-id="f94aa-114">Messaggio che descrive il problema.</span><span class="sxs-lookup"><span data-stu-id="f94aa-114">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f94aa-115">Configurazione</span><span class="sxs-lookup"><span data-stu-id="f94aa-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f94aa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f94aa-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f94aa-117">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="f94aa-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f94aa-118">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f94aa-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
