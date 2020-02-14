---
title: MDA invalidGCHandleCookie
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
ms.openlocfilehash: c1d8fab863c34313c0cdb778136c6f69a64defeb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216312"
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="81720-102">MDA invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="81720-102">invalidGCHandleCookie MDA</span></span>
<span data-ttu-id="81720-103">L'assistente al debug gestito `invalidGCHandleCookie` viene attivato quando si tenta una conversione da un cookie <xref:System.IntPtr> non valido a un oggetto <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="81720-103">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="81720-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="81720-104">Symptoms</span></span>  
 <span data-ttu-id="81720-105">Comportamento indefinito, ad esempio violazioni di accesso e danneggiamento della memoria durante il tentativo di usare o recuperare un oggetto <xref:System.Runtime.InteropServices.GCHandle> da un cookie <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="81720-105">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="81720-106">Causa</span><span class="sxs-lookup"><span data-stu-id="81720-106">Cause</span></span>  
 <span data-ttu-id="81720-107">Il cookie è probabilmente non valido perché in origine non è stato creato da un oggetto <xref:System.Runtime.InteropServices.GCHandle>, rappresenta un oggetto <xref:System.Runtime.InteropServices.GCHandle> che è già stato liberato, è un cookie per un oggetto <xref:System.Runtime.InteropServices.GCHandle> in un dominio dell'applicazione diverso o è stato sottoposto a marshalling al codice nativo come <xref:System.Runtime.InteropServices.GCHandle> ma passato di nuovo a CLR come oggetto <xref:System.IntPtr>, in cui è stato tentato un cast.</span><span class="sxs-lookup"><span data-stu-id="81720-107">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="81720-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="81720-108">Resolution</span></span>  
 <span data-ttu-id="81720-109">Specificare un cookie <xref:System.IntPtr> valido per <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="81720-109">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="81720-110">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="81720-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="81720-111">Quando questo assistente al debug gestito è abilitato, il debugger non è più in grado di tracciare di nuovo le radici ai rispettivi oggetti perché i valori del cookie restituiti sono diversi da quelli restituiti quando l'assistente al debug gestito non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="81720-111">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="81720-112">Output</span><span class="sxs-lookup"><span data-stu-id="81720-112">Output</span></span>  
 <span data-ttu-id="81720-113">Viene segnalato il valore non valido del cookie <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="81720-113">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="81720-114">Configurazione</span><span class="sxs-lookup"><span data-stu-id="81720-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81720-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81720-115">See also</span></span>

- <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>
- <xref:System.Runtime.InteropServices.GCHandle>
- [<span data-ttu-id="81720-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="81720-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
