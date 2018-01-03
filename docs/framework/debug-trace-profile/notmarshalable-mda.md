---
title: notMarshalable (MDA)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 489f0e2ff4dc1eeaa9721ec6cf59faad0bee2ca8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="45092-102">notMarshalable (MDA)</span><span class="sxs-lookup"><span data-stu-id="45092-102">notMarshalable MDA</span></span>
<span data-ttu-id="45092-103">L'assistente al debug gestito `notMarshalable` viene attivato quando Common Language Runtime rileva un puntatore a interfaccia COM senza un proxy/stub registrato valido oppure un'implementazione non corretta dell'interfaccia `IMarshal` durante il marshalling dell'interfaccia tra i vari contesti.</span><span class="sxs-lookup"><span data-stu-id="45092-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="45092-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="45092-104">Symptoms</span></span>  
 <span data-ttu-id="45092-105">Le chiamate non vengono eseguite oppure vengono eseguite nel contesto errato per i puntatori a interfaccia COM.</span><span class="sxs-lookup"><span data-stu-id="45092-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="45092-106">Causa</span><span class="sxs-lookup"><span data-stu-id="45092-106">Cause</span></span>  
 <span data-ttu-id="45092-107">Nessun proxy/stub registrato valido oppure un'implementazione non corretta dell'interfaccia `IMarshal` durante il marshalling dell'interfaccia tra i vari contesti.</span><span class="sxs-lookup"><span data-stu-id="45092-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="45092-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="45092-108">Resolution</span></span>  
 <span data-ttu-id="45092-109">Assicurarsi di disporre di uno stub proxy registrato e che l'implementazione dell'interfaccia `IMarshal` sia valida.</span><span class="sxs-lookup"><span data-stu-id="45092-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="45092-110">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="45092-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="45092-111">L'assistente al debug gestito non ha alcun effetto sull'ambiente di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="45092-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="45092-112">Output</span><span class="sxs-lookup"><span data-stu-id="45092-112">Output</span></span>  
 <span data-ttu-id="45092-113">Messaggio che descrive il problema.</span><span class="sxs-lookup"><span data-stu-id="45092-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="45092-114">Configurazione</span><span class="sxs-lookup"><span data-stu-id="45092-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45092-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45092-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="45092-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="45092-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="45092-117">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="45092-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
