---
title: MDA invalidVariant
description: Esaminare l'assistente al debug gestito invalidVariant, che viene richiamato se viene rilevata una variante non valida in una chiamata dal codice nativo/non gestito a quello gestito.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
ms.openlocfilehash: ab1233d9faa86ef1508fa8fe2b5af46cb37bd523
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051636"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="fab32-103">MDA invalidVariant</span><span class="sxs-lookup"><span data-stu-id="fab32-103">invalidVariant MDA</span></span>
<span data-ttu-id="fab32-104">L'assistente al debug gestito `invalidVariant` viene attivato quando viene rilevata una struttura `VARIANT` non valida durante una chiamata dal codice nativo o non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fab32-104">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="fab32-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="fab32-105">Symptoms</span></span>  
 <span data-ttu-id="fab32-106">Comportamento imprevisto durante una transizione tra il codice nativo e quello gestito in cui è previsto il marshalling di una struttura `VARIANT` a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="fab32-106">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="fab32-107">Causa</span><span class="sxs-lookup"><span data-stu-id="fab32-107">Cause</span></span>  
 <span data-ttu-id="fab32-108">Il codice nativo passa al codice gestito una struttura `VARIANT` in un formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="fab32-108">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="fab32-109">Il runtime tenta il marshalling di questa struttura `VARIANT` a un oggetto e, se non ritiene valida la struttura `VARIANT`, attiva l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="fab32-109">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="fab32-110">Tra gli esempi di strutture `VARIANT` non valide sono incluse strutture `VARIANT` con `VARTYPE` VT_EMPTY &#124; VT_BYREF o strutture `VARIANT` con `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="fab32-110">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="fab32-111">Soluzione</span><span class="sxs-lookup"><span data-stu-id="fab32-111">Resolution</span></span>  
 <span data-ttu-id="fab32-112">Il codice nativo o non gestito che passa la struttura `VARIANT` deve verificare la correttezza del formato e dell'inizializzazione della struttura `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="fab32-112">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="fab32-113">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="fab32-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="fab32-114">L'assistente al debug gestito non produce effetti sul comportamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="fab32-114">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="fab32-115">Output</span><span class="sxs-lookup"><span data-stu-id="fab32-115">Output</span></span>  
 <span data-ttu-id="fab32-116">Un messaggio dell'assistente al debug gestito in cui è indicato che il runtime ha rilevato una struttura `VARIANT` non valida passata al codice gestito da un modulo non gestito.</span><span class="sxs-lookup"><span data-stu-id="fab32-116">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="fab32-117">Configurazione</span><span class="sxs-lookup"><span data-stu-id="fab32-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fab32-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fab32-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="fab32-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="fab32-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="fab32-120">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="fab32-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
