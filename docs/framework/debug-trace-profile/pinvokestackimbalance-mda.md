---
title: MDA pInvokeStackImbalance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9da05a84568a6168ed9f450afa48aa6864ed575
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="a1264-102">MDA pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="a1264-102">pInvokeStackImbalance MDA</span></span>
<span data-ttu-id="a1264-103">L'assistente al debug gestito `pInvokeStackImbalance` viene attivato quando CLR rileva che la profondità dello stack dopo una chiamata PInvoke non corrisponde a quella prevista, in base alla convenzione di chiamata specificata nell'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> e alla dichiarazione dei parametri nella firma gestita.</span><span class="sxs-lookup"><span data-stu-id="a1264-103">The `pInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute as well as the declaration of the parameters in the managed signature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1264-104">L'assistente al debug gestito `pInvokeStackImbalance` viene implementato solo per piattaforme x86 a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="a1264-104">The `pInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1264-105">In .NET Framework versione 3.5, l'assistente al debug gestito `pInvokeStackImbalance` è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a1264-105">In the .NET Framework version 3.5, the `pInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="a1264-106">Quando si usa .NET Framework versione 3.5 con Visual Studio 2005, l'assistente al debug gestito `pInvokeStackImbalance` viene visualizzato nell'elenco **Assistenti al debug gestito** nella finestra di dialogo **Eccezioni** (visualizzata quando si fa clic su **Eccezioni** nel menu **Debug**).</span><span class="sxs-lookup"><span data-stu-id="a1264-106">When you use the .NET Framework version 3.5 with Visual Studio 2005, the `pInvokeStackImbalance` MDA will appear in the **Managed Debugging Assistants** list in the **Exceptions** dialog box (which is displayed when you click **Exceptions** on the **Debug** menu).</span></span> <span data-ttu-id="a1264-107">Tuttavia, quando si seleziona o si deseleziona la casella di controllo **Generata** per `pInvokeStackImbalance` l'assistente al debug gestito non viene abilitato o disabilitato. L'opzione controlla solo se Visual Studio genera un'eccezione quando viene attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="a1264-107">However, selecting or clearing the **Thrown** check box for `pInvokeStackImbalance` does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a1264-108">Sintomi</span><span class="sxs-lookup"><span data-stu-id="a1264-108">Symptoms</span></span>  
 <span data-ttu-id="a1264-109">Un'applicazione rileva una violazione di accesso o un danneggiamento della memoria durante o dopo una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="a1264-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a1264-110">Causa</span><span class="sxs-lookup"><span data-stu-id="a1264-110">Cause</span></span>  
 <span data-ttu-id="a1264-111">La firma gestita della chiamata PInvoke potrebbe non corrispondere alla firma non gestita del metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="a1264-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="a1264-112">Questa mancata corrispondenza può essere causata dalla firma gestita che non dichiara il numero corretto di parametri o non specifica le dimensioni appropriate per i parametri.</span><span class="sxs-lookup"><span data-stu-id="a1264-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="a1264-113">L'assistente al debug gestito può essere attivato anche perché la convenzione di chiamata specificata dall'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> non corrisponde alla convenzione di chiamata non gestita.</span><span class="sxs-lookup"><span data-stu-id="a1264-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a1264-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="a1264-114">Resolution</span></span>  
 <span data-ttu-id="a1264-115">Rivedere la firma PInvoke gestita e la convenzione di chiamata per verificare la corrispondenza con la firma e la convenzione di chiamata della destinazione nativa.</span><span class="sxs-lookup"><span data-stu-id="a1264-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="a1264-116">Provare a specificare in modo esplicito la convenzione di chiamata su entrambi i lati, gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="a1264-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="a1264-117">È anche possibile, anche se improbabile, che la funzione non gestita abbia sbilanciato lo stack per altri motivi, ad esempio un bug nel compilatore non gestito.</span><span class="sxs-lookup"><span data-stu-id="a1264-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a1264-118">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="a1264-118">Effect on the Runtime</span></span>  
 <span data-ttu-id="a1264-119">Forza l'uso del percorso non ottimizzato in CLR per tutte le chiamate PInvoke.</span><span class="sxs-lookup"><span data-stu-id="a1264-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a1264-120">Output</span><span class="sxs-lookup"><span data-stu-id="a1264-120">Output</span></span>  
 <span data-ttu-id="a1264-121">Il messaggio dell'assistente al debug gestito fornisce il nome della chiamata al metodo PInvoke che sta causando lo sbilanciamento dello stack.</span><span class="sxs-lookup"><span data-stu-id="a1264-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span>  <span data-ttu-id="a1264-122">Un messaggio di esempio di una chiamata PInvoke al metodo `SampleMethod` è:</span><span class="sxs-lookup"><span data-stu-id="a1264-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>  
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a><span data-ttu-id="a1264-123">Configurazione</span><span class="sxs-lookup"><span data-stu-id="a1264-123">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1264-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1264-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="a1264-125">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="a1264-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="a1264-126">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="a1264-126">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
