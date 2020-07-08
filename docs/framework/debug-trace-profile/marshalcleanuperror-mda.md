---
title: MDA marshalCleanupError
description: Esaminare l'assistente al debug gestito marshalCleanupError, che viene richiamato a causa di un errore imprevisto durante la pulizia delle strutture temporanee.
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
ms.openlocfilehash: 3c7498d6f51484de3a2e84d611a2634f53724ab6
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051611"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="cd0a1-103">MDA marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="cd0a1-103">marshalCleanupError MDA</span></span>
<span data-ttu-id="cd0a1-104">L'assistente al debug gestito `marshalCleanupError` viene attivato quando in Common Language Runtime si verifica un errore durante il tentativo di eseguire la pulizia di strutture temporanee e della memoria usata per effettuare il marshalling dei tipi di dati tra limiti del codice gestito e nativo.</span><span class="sxs-lookup"><span data-stu-id="cd0a1-104">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="cd0a1-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="cd0a1-105">Symptoms</span></span>  
 <span data-ttu-id="cd0a1-106">Si verifica una perdita di memoria durante transizioni di codice gestito e nativo, lo stato di esecuzione, ad esempio le impostazioni cultura del thread, non viene ripristinato o si verificano errori durante la pulizia di <xref:System.Runtime.InteropServices.SafeHandle>.</span><span class="sxs-lookup"><span data-stu-id="cd0a1-106">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="cd0a1-107">Causa</span><span class="sxs-lookup"><span data-stu-id="cd0a1-107">Cause</span></span>  
 <span data-ttu-id="cd0a1-108">Si è verificato un errore imprevisto durante la pulizia delle strutture temporanee.</span><span class="sxs-lookup"><span data-stu-id="cd0a1-108">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="cd0a1-109">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cd0a1-109">Resolution</span></span>  
 <span data-ttu-id="cd0a1-110">Rivedere tutte le implementazioni del marshaler personalizzato, del finalizzatore e del distruttore <xref:System.Runtime.InteropServices.SafeHandle> per individuare eventuali errori.</span><span class="sxs-lookup"><span data-stu-id="cd0a1-110">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="cd0a1-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="cd0a1-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="cd0a1-112">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="cd0a1-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="cd0a1-113">Output</span><span class="sxs-lookup"><span data-stu-id="cd0a1-113">Output</span></span>  
 <span data-ttu-id="cd0a1-114">Un messaggio che indica l'operazione non riuscita durante la pulizia.</span><span class="sxs-lookup"><span data-stu-id="cd0a1-114">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="cd0a1-115">Configurazione</span><span class="sxs-lookup"><span data-stu-id="cd0a1-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd0a1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd0a1-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="cd0a1-117">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="cd0a1-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="cd0a1-118">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cd0a1-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
