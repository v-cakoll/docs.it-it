---
title: MDA dllMainReturnsFalse
description: Per informazioni sull'Assistente al debug gestito dllMainReturnsFalse, vedere .NET. Questo assistente al debug gestito viene attivato in caso di errore di inizializzazione DLL.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
ms.openlocfilehash: 21d5e37d6823876e07cf5b2cbb881c1cf8b47b11
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416057"
---
# <a name="dllmainreturnsfalse-mda"></a><span data-ttu-id="ac07b-104">MDA dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="ac07b-104">dllMainReturnsFalse MDA</span></span>
<span data-ttu-id="ac07b-105">L'assistente al debug gestito `dllMainReturnsFalse` viene attivato se la funzione `DllMain` gestita di un assembly utente, chiamata per il motivo DLL_PROCESS_ATTACH, restituisce FALSE.</span><span class="sxs-lookup"><span data-stu-id="ac07b-105">The `dllMainReturnsFalse` managed debugging assistant (MDA) is activated if the managed `DllMain` function of a user assembly, called with reason DLL_PROCESS_ATTACH, returns FALSE.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ac07b-106">Sintomi</span><span class="sxs-lookup"><span data-stu-id="ac07b-106">Symptoms</span></span>  
 <span data-ttu-id="ac07b-107">La funzione `DllMain` ha restituito FALSE, che indica che non è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="ac07b-107">The `DllMain` function returned FALSE, indicating that it did not execute properly.</span></span> <span data-ttu-id="ac07b-108">Questo può causare problemi non determinati perché le funzioni `DllMain` contengono in genere un codice di inizializzazione importante.</span><span class="sxs-lookup"><span data-stu-id="ac07b-108">This can cause undetermined issues because `DllMain` functions typically contain important initialization code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ac07b-109">Causa</span><span class="sxs-lookup"><span data-stu-id="ac07b-109">Cause</span></span>  
 <span data-ttu-id="ac07b-110">La funzione `DllMain` viene chiamata con il motivo DLL_PROCESS_ATTACH per l'inizializzazione della DLL nel carico.</span><span class="sxs-lookup"><span data-stu-id="ac07b-110">The `DllMain` function is called with reason DLL_PROCESS_ATTACH for DLL initialization upon load.</span></span> <span data-ttu-id="ac07b-111">Se restituisce FALSE, significa che l'inizializzazione della DLL non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ac07b-111">If it returns FALSE, it means that DLL initialization failed.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ac07b-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="ac07b-112">Resolution</span></span>  
 <span data-ttu-id="ac07b-113">Analizzare il codice della funzione `DllMain` della DLL non riuscita e identificare la causa dell'errore di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="ac07b-113">Analyze the code of the `DllMain` function of the failed DLL and identify the cause of the initialization failure.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ac07b-114">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="ac07b-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="ac07b-115">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="ac07b-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="ac07b-116">Fornisce solo dati sul valore restituito per `DllMain`.</span><span class="sxs-lookup"><span data-stu-id="ac07b-116">It only reports data about the return value for `DllMain`.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ac07b-117">Output</span><span class="sxs-lookup"><span data-stu-id="ac07b-117">Output</span></span>  
 <span data-ttu-id="ac07b-118">Messaggio indicante che una funzione `DllMain`, chiamata per il motivo DLL_PROCESS_ATTACH, ha restituito FALSE.</span><span class="sxs-lookup"><span data-stu-id="ac07b-118">A message indicating that a `DllMain` function, called for reason DLL_PROCESS_ATTACH, returned FALSE.</span></span> <span data-ttu-id="ac07b-119">Si noti che questo assistente al debug gestito viene attivato solo se si implementa `DllMain` nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="ac07b-119">Note that this MDA is activated only if `DllMain` is implemented in managed code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ac07b-120">Configurazione</span><span class="sxs-lookup"><span data-stu-id="ac07b-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac07b-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ac07b-121">See also</span></span>

- [<span data-ttu-id="ac07b-122">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="ac07b-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
