---
title: MDA invalidVariant
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c34f160b643a0431168097d3832357b4ac6e4557
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052567"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="36811-102">MDA invalidVariant</span><span class="sxs-lookup"><span data-stu-id="36811-102">invalidVariant MDA</span></span>
<span data-ttu-id="36811-103">L'assistente al debug gestito `invalidVariant` viene attivato quando viene rilevata una struttura `VARIANT` non valida durante una chiamata dal codice nativo o non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="36811-103">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="36811-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="36811-104">Symptoms</span></span>  
 <span data-ttu-id="36811-105">Comportamento imprevisto durante una transizione tra il codice nativo e quello gestito in cui è previsto il marshalling di una struttura `VARIANT` a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="36811-105">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="36811-106">Causa</span><span class="sxs-lookup"><span data-stu-id="36811-106">Cause</span></span>  
 <span data-ttu-id="36811-107">Il codice nativo passa al codice gestito una struttura `VARIANT` in un formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="36811-107">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="36811-108">Il runtime tenta il marshalling di questa struttura `VARIANT` a un oggetto e, se non ritiene valida la struttura `VARIANT`, attiva l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="36811-108">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="36811-109">Tra gli esempi di strutture `VARIANT` non valide sono incluse strutture `VARIANT` con `VARTYPE` VT_EMPTY &#124; VT_BYREF o strutture `VARIANT` con `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="36811-109">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="36811-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="36811-110">Resolution</span></span>  
 <span data-ttu-id="36811-111">Il codice nativo o non gestito che passa la struttura `VARIANT` deve verificare la correttezza del formato e dell'inizializzazione della struttura `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="36811-111">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="36811-112">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="36811-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="36811-113">L'assistente al debug gestito non produce effetti sul comportamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="36811-113">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="36811-114">Output</span><span class="sxs-lookup"><span data-stu-id="36811-114">Output</span></span>  
 <span data-ttu-id="36811-115">Un messaggio dell'assistente al debug gestito in cui è indicato che il runtime ha rilevato una struttura `VARIANT` non valida passata al codice gestito da un modulo non gestito.</span><span class="sxs-lookup"><span data-stu-id="36811-115">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="36811-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="36811-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36811-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36811-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="36811-118">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="36811-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="36811-119">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="36811-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
