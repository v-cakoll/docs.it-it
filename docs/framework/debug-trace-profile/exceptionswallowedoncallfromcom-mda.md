---
title: MDA exceptionSwallowedOnCallFromCom
description: Esaminare l'assistente al debug gestito di exceptionSwallowedOnCallFromCOM in .NET. Questo assistente al debug gestito si verifica se è stata generata un'eccezione, ma non esiste un modo efficace per segnalarlo.
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
ms.openlocfilehash: 434f06cf953147d5c245e625db997bed6dbef700
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415953"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="aa8c8-104">MDA exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="aa8c8-104">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="aa8c8-105">L'assistente al debug gestito `exceptionSwallowedOnCallFromCOM` viene attivato alla generazione di un'eccezione da parte del codice Common Language Runtime (CLR) chiamato da COM mediante un metodo che non presenta un tipo restituito HRESULT non gestito.</span><span class="sxs-lookup"><span data-stu-id="aa8c8-105">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="aa8c8-106">Sintomi</span><span class="sxs-lookup"><span data-stu-id="aa8c8-106">Symptoms</span></span>  
 <span data-ttu-id="aa8c8-107">Il valore restituito per una chiamata a un componente gestito da COM corrisponde a FALSE o a 0.</span><span class="sxs-lookup"><span data-stu-id="aa8c8-107">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="aa8c8-108">In alternativa, se il metodo presenta un tipo restituito void, potrebbero non esservi indicazioni relative alla generazione di un'eccezione durante l'esecuzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="aa8c8-108">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="aa8c8-109">In tal caso, l'eccezione verrà intercettata senza avviso e l'esecuzione tornerà al chiamante COM.</span><span class="sxs-lookup"><span data-stu-id="aa8c8-109">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="aa8c8-110">Causa</span><span class="sxs-lookup"><span data-stu-id="aa8c8-110">Cause</span></span>  
 <span data-ttu-id="aa8c8-111">È stata generata un'eccezione, ma non esiste un modo valido per segnalarla.</span><span class="sxs-lookup"><span data-stu-id="aa8c8-111">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="aa8c8-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="aa8c8-112">Resolution</span></span>  
 <span data-ttu-id="aa8c8-113">Messaggio esclusivamente informativo. Non indica necessariamente la presenza di un bug.</span><span class="sxs-lookup"><span data-stu-id="aa8c8-113">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="aa8c8-114">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="aa8c8-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="aa8c8-115">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="aa8c8-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="aa8c8-116">Si limita a restituire dati relativi alle eccezioni intercettate senza avviso.</span><span class="sxs-lookup"><span data-stu-id="aa8c8-116">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="aa8c8-117">Output</span><span class="sxs-lookup"><span data-stu-id="aa8c8-117">Output</span></span>  
 <span data-ttu-id="aa8c8-118">Messaggio informativo contenente il nome del metodo, il nome del tipo e il messaggio dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="aa8c8-118">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="aa8c8-119">Configurazione</span><span class="sxs-lookup"><span data-stu-id="aa8c8-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa8c8-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="aa8c8-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="aa8c8-121">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="aa8c8-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="aa8c8-122">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="aa8c8-122">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
