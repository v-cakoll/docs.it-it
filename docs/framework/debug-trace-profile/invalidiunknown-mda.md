---
title: MDA invalidIUnknown
description: Esaminare l'assistente al debug gestito invalidIUnknown, che viene attivato quando un puntatore IUnknown non valido viene passato al codice gestito dal codice nativo.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 65d704463ed746390ff1710b590bf080013bf53d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051727"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="89074-103">MDA invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="89074-103">invalidIUnknown MDA</span></span>
<span data-ttu-id="89074-104">L'assistente al debug gestito `invalidIUnknown` viene attivato quando un puntatore `IUnknown` non valido viene passato dal codice nativo al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="89074-104">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="89074-105">La ricerca dell'interfaccia `IUnknown` nel puntatore `IUnknown` non riesce.</span><span class="sxs-lookup"><span data-stu-id="89074-105">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="89074-106">Sintomi</span><span class="sxs-lookup"><span data-stu-id="89074-106">Symptoms</span></span>  
 <span data-ttu-id="89074-107">Si verifica un errore imprevisto durante il marshalling degli argomenti di un puntatore a interfaccia COM.</span><span class="sxs-lookup"><span data-stu-id="89074-107">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="89074-108">Causa</span><span class="sxs-lookup"><span data-stu-id="89074-108">Cause</span></span>  
 <span data-ttu-id="89074-109">Un'implementazione non valida di `QueryInterface` sull'interfaccia COM passata a CLR.</span><span class="sxs-lookup"><span data-stu-id="89074-109">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="89074-110">Soluzione</span><span class="sxs-lookup"><span data-stu-id="89074-110">Resolution</span></span>  
 <span data-ttu-id="89074-111">Correggere l'implementazione di `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="89074-111">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="89074-112">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="89074-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="89074-113">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="89074-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="89074-114">Output</span><span class="sxs-lookup"><span data-stu-id="89074-114">Output</span></span>  
 <span data-ttu-id="89074-115">Descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="89074-115">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="89074-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="89074-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89074-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89074-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="89074-118">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="89074-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="89074-119">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="89074-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
