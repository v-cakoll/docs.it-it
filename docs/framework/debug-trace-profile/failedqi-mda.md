---
title: MDA failedQI
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0ac478644561d2aab13d10811987d8d02c8d7608
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217627"
---
# <a name="failedqi-mda"></a><span data-ttu-id="3b916-102">MDA failedQI</span><span class="sxs-lookup"><span data-stu-id="3b916-102">failedQI MDA</span></span>
<span data-ttu-id="3b916-103">L'assistente al debug gestito `failedQI` viene attivato quando il runtime chiama `QueryInterface` su un puntatore a interfaccia COM per conto di un Runtime Callable Wrapper (RWC) e la chiamata `QueryInterface` non riesce.</span><span class="sxs-lookup"><span data-stu-id="3b916-103">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3b916-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="3b916-104">Symptoms</span></span>  
 <span data-ttu-id="3b916-105">Mancata riuscita di un cast su un RCW oppure errore imprevisto di una chiamata a COM da parte di un RCW.</span><span class="sxs-lookup"><span data-stu-id="3b916-105">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3b916-106">Causa</span><span class="sxs-lookup"><span data-stu-id="3b916-106">Cause</span></span>  
  
-   <span data-ttu-id="3b916-107">La chiamata viene effettuata da un contesto errato.</span><span class="sxs-lookup"><span data-stu-id="3b916-107">The call is made from the wrong context.</span></span>  
  
-   <span data-ttu-id="3b916-108">Il proxy registrato non riesce a chiamare `QueryInterface` perché il tentativo di chiamata è stato effettuato nel contesto errato.</span><span class="sxs-lookup"><span data-stu-id="3b916-108">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
-   <span data-ttu-id="3b916-109">Un proxy di proprietà di OLE ha restituito un HRESULT di errore.</span><span class="sxs-lookup"><span data-stu-id="3b916-109">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3b916-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="3b916-110">Resolution</span></span>  
 <span data-ttu-id="3b916-111">Vedere la documentazione MSDN relativa alle regole COM.</span><span class="sxs-lookup"><span data-stu-id="3b916-111">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3b916-112">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="3b916-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="3b916-113">Se una chiamata a `QueryInterface` non riesce, viene cambiato il contesto e viene tentata di nuovo la chiamata a `QueryInterface` per verificare se l'errore è stato causato da un contesto errato.</span><span class="sxs-lookup"><span data-stu-id="3b916-113">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3b916-114">Output</span><span class="sxs-lookup"><span data-stu-id="3b916-114">Output</span></span>  
 <span data-ttu-id="3b916-115">Il nome gestito e il GUID dell'interfaccia e l'oggetto HRESULT dell'errore.</span><span class="sxs-lookup"><span data-stu-id="3b916-115">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3b916-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="3b916-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b916-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b916-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="3b916-118">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="3b916-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3b916-119">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="3b916-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
