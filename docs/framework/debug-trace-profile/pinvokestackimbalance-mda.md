---
title: MDA pInvokeStackImbalance
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 117e0838f78d43bf9ffa555947bf8749830c9840
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802000"
---
# <a name="pinvokestackimbalance-mda"></a><span data-ttu-id="ba989-102">PInvokeStackImbalance (MDA)</span><span class="sxs-lookup"><span data-stu-id="ba989-102">PInvokeStackImbalance MDA</span></span>

<span data-ttu-id="ba989-103">Il `PInvokeStackImbalance` assistente al debug gestito viene attivato quando CLR rileva che la profondità dello stack dopo una chiamata platform invoke non corrisponde alla profondità dello stack prevista, in base alla convenzione di chiamata specificata nell'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> e alla dichiarazione dei parametri nella firma gestita.</span><span class="sxs-lookup"><span data-stu-id="ba989-103">The `PInvokeStackImbalance` managed debugging assistant (MDA) is activated when the CLR detects that the stack depth after a platform invoke call does not match the expected stack depth, given the calling convention specified in the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute and the declaration of the parameters in the managed signature.</span></span>

<span data-ttu-id="ba989-104">L'assistente al debug gestito `PInvokeStackImbalance` viene implementato solo per piattaforme x86 a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="ba989-104">The `PInvokeStackImbalance` MDA is implemented only for 32-bit x86 platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="ba989-105">Il `PInvokeStackImbalance` MDA è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ba989-105">The `PInvokeStackImbalance` MDA is disabled by default.</span></span> <span data-ttu-id="ba989-106">In Visual Studio 2017 e versioni successive, il `PInvokeStackImbalance` MDA viene visualizzato nell'elenco **assistenti al debug gestito** nella finestra di dialogo **Impostazioni eccezioni** (visualizzata quando si seleziona **debug** > **Windows** > **Impostazioni eccezioni**).</span><span class="sxs-lookup"><span data-stu-id="ba989-106">In Visual Studio 2017 and later versions, the `PInvokeStackImbalance` MDA appears in the **Managed Debugging Assistants** list in the **Exception Settings** dialog box (which is displayed when you select **Debug** > **Windows** > **Exception Settings**).</span></span> <span data-ttu-id="ba989-107">Tuttavia, la selezione o la cancellazione della casella di controllo **Interrompi quando viene generata** non Abilita o Disabilita l'assistente al debug gestito; controlla solo se Visual Studio genera un'eccezione quando viene attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="ba989-107">However, selecting or clearing the **Break When Thrown** check box does not enable or disable the MDA; it only controls whether Visual Studio throws an exception when the MDA is activated.</span></span>

## <a name="symptoms"></a><span data-ttu-id="ba989-108">Sintomi</span><span class="sxs-lookup"><span data-stu-id="ba989-108">Symptoms</span></span>

<span data-ttu-id="ba989-109">Un'applicazione rileva una violazione di accesso o un danneggiamento della memoria durante o dopo una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ba989-109">An application encounters an access violation or memory corruption when making or following a platform invoke call.</span></span>

## <a name="cause"></a><span data-ttu-id="ba989-110">Causa</span><span class="sxs-lookup"><span data-stu-id="ba989-110">Cause</span></span>

<span data-ttu-id="ba989-111">La firma gestita della chiamata PInvoke potrebbe non corrispondere alla firma non gestita del metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="ba989-111">The managed signature of the platform invoke call might not match the unmanaged signature of the method being called.</span></span>  <span data-ttu-id="ba989-112">Questa mancata corrispondenza può essere causata dalla firma gestita che non dichiara il numero corretto di parametri o non specifica le dimensioni appropriate per i parametri.</span><span class="sxs-lookup"><span data-stu-id="ba989-112">This mismatch can be caused by the managed signature not declaring the correct number of parameters or not specifying the appropriate size for the parameters.</span></span>  <span data-ttu-id="ba989-113">L'assistente al debug gestito può essere attivato anche perché la convenzione di chiamata specificata dall'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> non corrisponde alla convenzione di chiamata non gestita.</span><span class="sxs-lookup"><span data-stu-id="ba989-113">The MDA can also activate because the calling convention, possibly specified by the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute, does not match the unmanaged calling convention.</span></span>

## <a name="resolution"></a><span data-ttu-id="ba989-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="ba989-114">Resolution</span></span>

<span data-ttu-id="ba989-115">Rivedere la firma PInvoke gestita e la convenzione di chiamata per verificare la corrispondenza con la firma e la convenzione di chiamata della destinazione nativa.</span><span class="sxs-lookup"><span data-stu-id="ba989-115">Review the managed platform invoke signature and calling convention to confirm it matches the signature and calling convention of the native target.</span></span>  <span data-ttu-id="ba989-116">Provare a specificare in modo esplicito la convenzione di chiamata su entrambi i lati, gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="ba989-116">Try explicitly specifying the calling convention on both the managed and unmanaged sides.</span></span> <span data-ttu-id="ba989-117">È anche possibile, anche se improbabile, che la funzione non gestita abbia sbilanciato lo stack per altri motivi, ad esempio un bug nel compilatore non gestito.</span><span class="sxs-lookup"><span data-stu-id="ba989-117">It is also possible, although not as likely, that the unmanaged function unbalanced the stack for some other reason, such as a bug in the unmanaged compiler.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="ba989-118">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="ba989-118">Effect on the Runtime</span></span>

<span data-ttu-id="ba989-119">Forza l'uso del percorso non ottimizzato in CLR per tutte le chiamate PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ba989-119">Forces all platform invoke calls to take the nonoptimized path in the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="ba989-120">Output</span><span class="sxs-lookup"><span data-stu-id="ba989-120">Output</span></span>

<span data-ttu-id="ba989-121">Il messaggio dell'assistente al debug gestito fornisce il nome della chiamata al metodo PInvoke che sta causando lo sbilanciamento dello stack.</span><span class="sxs-lookup"><span data-stu-id="ba989-121">The MDA message gives the name of the platform invoke method call that is causing the stack imbalance.</span></span> <span data-ttu-id="ba989-122">Un messaggio di esempio di una chiamata PInvoke al metodo `SampleMethod` è:</span><span class="sxs-lookup"><span data-stu-id="ba989-122">A sample message of a platform invoke call on method `SampleMethod` is:</span></span>

<span data-ttu-id="ba989-123">**Una chiamata alla funzione PInvoke ' SampleMethod ' ha sbilanciato lo stack. Questa operazione è probabilmente dovuta al fatto che la firma PInvoke gestita non corrisponde alla firma di destinazione non gestita. Verificare che la convenzione di chiamata e i parametri della firma PInvoke corrispondano alla firma non gestita di destinazione.**</span><span class="sxs-lookup"><span data-stu-id="ba989-123">**A call to PInvoke function 'SampleMethod' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.**</span></span>

## <a name="configuration"></a><span data-ttu-id="ba989-124">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="ba989-124">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="ba989-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba989-125">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ba989-126">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="ba989-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ba989-127">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="ba989-127">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
