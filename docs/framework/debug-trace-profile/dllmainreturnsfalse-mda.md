---
title: MDA dllMainReturnsFalse
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
ms.openlocfilehash: 0b413521e0a2dc06c2ff0be642f080eaf541202f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216435"
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="31183-102">MDA dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="31183-102">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="31183-103">L'assistente al debug gestito `dllMainReturnsFalse` viene attivato se la funzione `DllMain` gestita di un assembly utente, chiamata per il motivo DLL_PROCESS_ATTACH, restituisce FALSE.</span><span class="sxs-lookup"><span data-stu-id="31183-103">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="31183-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="31183-104">Symptoms</span></span>  
 <span data-ttu-id="31183-105">La funzione `DllMain` ha restituito FALSE, che indica che non è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="31183-105">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="31183-106">Questo può causare problemi non determinati perché le funzioni `DllMain` contengono in genere un codice di inizializzazione importante.</span><span class="sxs-lookup"><span data-stu-id="31183-106">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="31183-107">Causa</span><span class="sxs-lookup"><span data-stu-id="31183-107">Cause</span></span>  
 <span data-ttu-id="31183-108">La funzione `DllMain` viene chiamata con il motivo DLL_PROCESS_ATTACH per l'inizializzazione della DLL nel carico.</span><span class="sxs-lookup"><span data-stu-id="31183-108">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="31183-109">Se restituisce FALSE, significa che l'inizializzazione della DLL non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="31183-109">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="31183-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="31183-110">Resolution</span></span>  
 <span data-ttu-id="31183-111">Analizzare il codice della funzione `DllMain` della DLL non riuscita e identificare la causa dell'errore di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="31183-111">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="31183-112">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="31183-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="31183-113">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="31183-113">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="31183-114">Fornisce solo dati sul valore restituito per `DllMain`.</span><span class="sxs-lookup"><span data-stu-id="31183-114">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="31183-115">Output</span><span class="sxs-lookup"><span data-stu-id="31183-115">Output</span></span>  
 <span data-ttu-id="31183-116">Messaggio indicante che una funzione `DllMain`, chiamata per il motivo DLL_PROCESS_ATTACH, ha restituito FALSE.</span><span class="sxs-lookup"><span data-stu-id="31183-116">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="31183-117">Si noti che questo assistente al debug gestito viene attivato solo se si implementa `DllMain` nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="31183-117">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="31183-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="31183-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="31183-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31183-119">See also</span></span>

- [<span data-ttu-id="31183-120">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="31183-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
