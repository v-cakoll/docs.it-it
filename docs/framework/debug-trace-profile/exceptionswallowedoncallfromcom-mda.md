---
title: MDA exceptionSwallowedOnCallFromCom
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b4c1cbf075ef96073061679b6d062075490f5e4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390608"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a><span data-ttu-id="e6bff-102">MDA exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="e6bff-102">exceptionSwallowedOnCallFromCom MDA</span></span>
<span data-ttu-id="e6bff-103">L'assistente al debug gestito `exceptionSwallowedOnCallFromCOM` viene attivato alla generazione di un'eccezione da parte del codice Common Language Runtime (CLR) chiamato da COM mediante un metodo che non presenta un tipo restituito HRESULT non gestito.</span><span class="sxs-lookup"><span data-stu-id="e6bff-103">The `exceptionSwallowedOnCallFromCOM` managed debugging assistant (MDA) is activated when an exception is thrown from common language runtime (CLR) code called from COM via a method that does not have an unmanaged HRESULT return type.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e6bff-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="e6bff-104">Symptoms</span></span>  
 <span data-ttu-id="e6bff-105">Il valore restituito per una chiamata a un componente gestito da COM corrisponde a FALSE o a 0.</span><span class="sxs-lookup"><span data-stu-id="e6bff-105">A call to a managed component from COM returns with a value of FALSE or 0.</span></span> <span data-ttu-id="e6bff-106">In alternativa, se il metodo presenta un tipo restituito void, potrebbero non esservi indicazioni relative alla generazione di un'eccezione durante l'esecuzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="e6bff-106">Alternatively, if the method has a void return type, there may be no indication that an exception was thrown during the execution of the method.</span></span> <span data-ttu-id="e6bff-107">In tal caso, l'eccezione verrà intercettata senza avviso e l'esecuzione tornerà al chiamante COM.</span><span class="sxs-lookup"><span data-stu-id="e6bff-107">In this case, the exception will be silently caught and execution will return to the COM caller.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e6bff-108">Causa</span><span class="sxs-lookup"><span data-stu-id="e6bff-108">Cause</span></span>  
 <span data-ttu-id="e6bff-109">È stata generata un'eccezione, ma non esiste un modo valido per segnalarla.</span><span class="sxs-lookup"><span data-stu-id="e6bff-109">An exception was thrown, but there is no valid way to report it.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e6bff-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="e6bff-110">Resolution</span></span>  
 <span data-ttu-id="e6bff-111">Messaggio esclusivamente informativo. Non indica necessariamente la presenza di un bug.</span><span class="sxs-lookup"><span data-stu-id="e6bff-111">Informational only, not necessarily indicative of a bug.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e6bff-112">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e6bff-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="e6bff-113">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="e6bff-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="e6bff-114">Si limita a restituire dati relativi alle eccezioni intercettate senza avviso.</span><span class="sxs-lookup"><span data-stu-id="e6bff-114">It only reports data about silently caught exceptions.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e6bff-115">Output</span><span class="sxs-lookup"><span data-stu-id="e6bff-115">Output</span></span>  
 <span data-ttu-id="e6bff-116">Messaggio informativo contenente il nome del metodo, il nome del tipo e il messaggio dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e6bff-116">Informational message containing the method name, type name, and exception message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e6bff-117">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e6bff-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6bff-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6bff-118">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="e6bff-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="e6bff-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="e6bff-120">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="e6bff-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
