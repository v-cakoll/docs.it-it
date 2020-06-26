---
title: MDA failedQI
description: Esaminare l'assistente al debug gestito di failedQI in .NET, che può essere attivato quando un cast o una chiamata COM da un Runtime Callable Wrapper (RCW) ha esito negativo.
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
ms.openlocfilehash: 2d7f14c67d47e58bcb88eab4621df63d7c598a7a
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415940"
---
# <a name="failedqi-mda"></a><span data-ttu-id="19fe1-103">MDA failedQI</span><span class="sxs-lookup"><span data-stu-id="19fe1-103">failedQI MDA</span></span>
<span data-ttu-id="19fe1-104">L'assistente al debug gestito `failedQI` viene attivato quando il runtime chiama `QueryInterface` su un puntatore a interfaccia COM per conto di un Runtime Callable Wrapper (RWC) e la chiamata `QueryInterface` non riesce.</span><span class="sxs-lookup"><span data-stu-id="19fe1-104">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="19fe1-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="19fe1-105">Symptoms</span></span>  
 <span data-ttu-id="19fe1-106">Mancata riuscita di un cast su un RCW oppure errore imprevisto di una chiamata a COM da parte di un RCW.</span><span class="sxs-lookup"><span data-stu-id="19fe1-106">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="19fe1-107">Causa</span><span class="sxs-lookup"><span data-stu-id="19fe1-107">Cause</span></span>  
  
- <span data-ttu-id="19fe1-108">La chiamata viene effettuata da un contesto errato.</span><span class="sxs-lookup"><span data-stu-id="19fe1-108">The call is made from the wrong context.</span></span>  
  
- <span data-ttu-id="19fe1-109">Il proxy registrato non riesce a chiamare `QueryInterface` perché il tentativo di chiamata è stato effettuato nel contesto errato.</span><span class="sxs-lookup"><span data-stu-id="19fe1-109">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
- <span data-ttu-id="19fe1-110">Un proxy di proprietà di OLE ha restituito un HRESULT di errore.</span><span class="sxs-lookup"><span data-stu-id="19fe1-110">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="19fe1-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="19fe1-111">Resolution</span></span>  
 <span data-ttu-id="19fe1-112">Vedere la documentazione MSDN relativa alle regole COM.</span><span class="sxs-lookup"><span data-stu-id="19fe1-112">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="19fe1-113">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="19fe1-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="19fe1-114">Se una chiamata a `QueryInterface` non riesce, viene cambiato il contesto e viene tentata di nuovo la chiamata a `QueryInterface` per verificare se l'errore è stato causato da un contesto errato.</span><span class="sxs-lookup"><span data-stu-id="19fe1-114">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="19fe1-115">Output</span><span class="sxs-lookup"><span data-stu-id="19fe1-115">Output</span></span>  
 <span data-ttu-id="19fe1-116">Il nome gestito e il GUID dell'interfaccia e l'oggetto HRESULT dell'errore.</span><span class="sxs-lookup"><span data-stu-id="19fe1-116">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="19fe1-117">Configurazione</span><span class="sxs-lookup"><span data-stu-id="19fe1-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19fe1-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="19fe1-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="19fe1-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="19fe1-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="19fe1-120">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="19fe1-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
