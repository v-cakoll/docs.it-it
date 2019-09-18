---
title: MDA invalidIUnknown
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea7f48ab61c16cb0430717074f1b1feab4827763
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052599"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="f5ae3-102">MDA invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="f5ae3-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="f5ae3-103">L'assistente al debug gestito `invalidIUnknown` viene attivato quando un puntatore `IUnknown` non valido viene passato dal codice nativo al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f5ae3-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="f5ae3-104">La ricerca dell'interfaccia `IUnknown` nel puntatore `IUnknown` non riesce.</span><span class="sxs-lookup"><span data-stu-id="f5ae3-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f5ae3-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="f5ae3-105">Symptoms</span></span>  
 <span data-ttu-id="f5ae3-106">Si verifica un errore imprevisto durante il marshalling degli argomenti di un puntatore a interfaccia COM.</span><span class="sxs-lookup"><span data-stu-id="f5ae3-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f5ae3-107">Causa</span><span class="sxs-lookup"><span data-stu-id="f5ae3-107">Cause</span></span>  
 <span data-ttu-id="f5ae3-108">Un'implementazione non valida di `QueryInterface` sull'interfaccia COM passata a CLR.</span><span class="sxs-lookup"><span data-stu-id="f5ae3-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f5ae3-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="f5ae3-109">Resolution</span></span>  
 <span data-ttu-id="f5ae3-110">Correggere l'implementazione di `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="f5ae3-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f5ae3-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="f5ae3-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="f5ae3-112">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="f5ae3-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f5ae3-113">Output</span><span class="sxs-lookup"><span data-stu-id="f5ae3-113">Output</span></span>  
 <span data-ttu-id="f5ae3-114">Descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="f5ae3-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f5ae3-115">Configurazione</span><span class="sxs-lookup"><span data-stu-id="f5ae3-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5ae3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5ae3-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f5ae3-117">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="f5ae3-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f5ae3-118">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f5ae3-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
