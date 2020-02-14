---
title: MDA marshalCleanupError
ms.date: 03/30/2017
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
ms.openlocfilehash: 1a14c548ce960d53f47934595171189db28edfbb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216149"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="ff385-102">MDA marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="ff385-102">marshalCleanupError MDA</span></span>
<span data-ttu-id="ff385-103">L'assistente al debug gestito `marshalCleanupError` viene attivato quando in Common Language Runtime si verifica un errore durante il tentativo di eseguire la pulizia di strutture temporanee e della memoria usata per effettuare il marshalling dei tipi di dati tra limiti del codice gestito e nativo.</span><span class="sxs-lookup"><span data-stu-id="ff385-103">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ff385-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="ff385-104">Symptoms</span></span>  
 <span data-ttu-id="ff385-105">Si verifica una perdita di memoria durante transizioni di codice gestito e nativo, lo stato di esecuzione, ad esempio le impostazioni cultura del thread, non viene ripristinato o si verificano errori durante la pulizia di <xref:System.Runtime.InteropServices.SafeHandle>.</span><span class="sxs-lookup"><span data-stu-id="ff385-105">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ff385-106">Causa</span><span class="sxs-lookup"><span data-stu-id="ff385-106">Cause</span></span>  
 <span data-ttu-id="ff385-107">Si è verificato un errore imprevisto durante la pulizia delle strutture temporanee.</span><span class="sxs-lookup"><span data-stu-id="ff385-107">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ff385-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="ff385-108">Resolution</span></span>  
 <span data-ttu-id="ff385-109">Rivedere tutte le implementazioni del marshaler personalizzato, del finalizzatore e del distruttore <xref:System.Runtime.InteropServices.SafeHandle> per individuare eventuali errori.</span><span class="sxs-lookup"><span data-stu-id="ff385-109">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ff385-110">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="ff385-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="ff385-111">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="ff385-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ff385-112">Output</span><span class="sxs-lookup"><span data-stu-id="ff385-112">Output</span></span>  
 <span data-ttu-id="ff385-113">Un messaggio che indica l'operazione non riuscita durante la pulizia.</span><span class="sxs-lookup"><span data-stu-id="ff385-113">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ff385-114">Configurazione</span><span class="sxs-lookup"><span data-stu-id="ff385-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff385-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff385-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ff385-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="ff385-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ff385-117">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="ff385-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
