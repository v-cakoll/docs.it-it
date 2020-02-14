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
ms.openlocfilehash: 5df9a3f506d8c2de6f1a3125459adc2d59d510bf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217357"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="0b50a-102">MDA invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="0b50a-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="0b50a-103">L'assistente al debug gestito `invalidIUnknown` viene attivato quando un puntatore `IUnknown` non valido viene passato dal codice nativo al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="0b50a-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="0b50a-104">La ricerca dell'interfaccia `IUnknown` nel puntatore `IUnknown` non riesce.</span><span class="sxs-lookup"><span data-stu-id="0b50a-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0b50a-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="0b50a-105">Symptoms</span></span>  
 <span data-ttu-id="0b50a-106">Si verifica un errore imprevisto durante il marshalling degli argomenti di un puntatore a interfaccia COM.</span><span class="sxs-lookup"><span data-stu-id="0b50a-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0b50a-107">Causa</span><span class="sxs-lookup"><span data-stu-id="0b50a-107">Cause</span></span>  
 <span data-ttu-id="0b50a-108">Un'implementazione non valida di `QueryInterface` sull'interfaccia COM passata a CLR.</span><span class="sxs-lookup"><span data-stu-id="0b50a-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0b50a-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="0b50a-109">Resolution</span></span>  
 <span data-ttu-id="0b50a-110">Correggere l'implementazione di `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="0b50a-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0b50a-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="0b50a-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="0b50a-112">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="0b50a-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0b50a-113">Output</span><span class="sxs-lookup"><span data-stu-id="0b50a-113">Output</span></span>  
 <span data-ttu-id="0b50a-114">Descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="0b50a-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0b50a-115">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0b50a-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b50a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b50a-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="0b50a-117">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="0b50a-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="0b50a-118">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="0b50a-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
