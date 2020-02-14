---
title: MDA invalidApartmentStateChange
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
ms.openlocfilehash: 8acafcc2fba9a7d30cc77f25f06adaca7c79db32
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217420"
---
# <a name="invalidapartmentstatechange-mda"></a><span data-ttu-id="f50dc-102">MDA invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="f50dc-102">invalidApartmentStateChange MDA</span></span>
<span data-ttu-id="f50dc-103">L'assistente al debug gestito `invalidApartmentStateChange` viene attivato quando si verificano due problemi diversi:</span><span class="sxs-lookup"><span data-stu-id="f50dc-103">The `invalidApartmentStateChange` managed debugging assistant (MDS) is activated by either of two problems:</span></span>  
  
- <span data-ttu-id="f50dc-104">Viene effettuato un tentativo di modificare lo stato di apartment COM di un thread che è già stato inizializzato da COM in uno stato di apartment diverso.</span><span class="sxs-lookup"><span data-stu-id="f50dc-104">An attempt is made to change the COM apartment state of a thread that has already been initialized by COM to a different apartment state.</span></span>  
  
- <span data-ttu-id="f50dc-105">Lo stato di apartment COM di un thread cambia in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="f50dc-105">The COM apartment state of a thread changes unexpectedly.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f50dc-106">Sintomi</span><span class="sxs-lookup"><span data-stu-id="f50dc-106">Symptoms</span></span>  
  
- <span data-ttu-id="f50dc-107">Lo stato di apartment COM di un thread è diverso da quello richiesto.</span><span class="sxs-lookup"><span data-stu-id="f50dc-107">A thread's COM apartment state is not what was requested.</span></span> <span data-ttu-id="f50dc-108">Questo problema può causare l'uso di proxy per componenti COM associati a un modello di threading diverso da quello corrente.</span><span class="sxs-lookup"><span data-stu-id="f50dc-108">This may cause proxies to be used for COM components that have a threading model different from the current one.</span></span> <span data-ttu-id="f50dc-109">A sua volta, questo comportamento può provocare la generazione di un'eccezione <xref:System.InvalidCastException> quando viene chiamato l'oggetto COM tramite interfacce che non sono configurate per il marshalling tra diversi apartment.</span><span class="sxs-lookup"><span data-stu-id="f50dc-109">This in turn may cause an <xref:System.InvalidCastException> to be thrown when calling the COM object through interfaces that are not set up for cross-apartment marshaling.</span></span>  
  
- <span data-ttu-id="f50dc-110">Lo stato di apartment COM del thread è diverso da quello previsto.</span><span class="sxs-lookup"><span data-stu-id="f50dc-110">The COM apartment state of the thread is different than expected.</span></span> <span data-ttu-id="f50dc-111">Questo problema può provocare un'eccezione <xref:System.Runtime.InteropServices.COMException> con valore HRESULT impostato su RPC_E_WRONG_THREAD, nonché un'eccezione <xref:System.InvalidCastException> quando si effettuano chiamate in un [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW).</span><span class="sxs-lookup"><span data-stu-id="f50dc-111">This can cause a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD as well as a <xref:System.InvalidCastException> when making calls on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="f50dc-112">Questo problema può anche far sì che diversi thread accedano contemporaneamente ad alcuni componenti COM a thread singolo, danneggiando i dati o provocandone la perdita.</span><span class="sxs-lookup"><span data-stu-id="f50dc-112">This can also cause some single-threaded COM components to be accessed by multiple threads at the same time, which can lead to corruption or data loss.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f50dc-113">Causa</span><span class="sxs-lookup"><span data-stu-id="f50dc-113">Cause</span></span>  
  
- <span data-ttu-id="f50dc-114">Il thread è stato precedentemente inizializzato in uno stato di apartment COM diverso.</span><span class="sxs-lookup"><span data-stu-id="f50dc-114">The thread was previously initialized to a different COM apartment state.</span></span> <span data-ttu-id="f50dc-115">Si noti che lo stato di apartment di un thread può essere impostato in modo sia esplicito sia implicito.</span><span class="sxs-lookup"><span data-stu-id="f50dc-115">Note that the apartment state of a thread can be set either explicitly or implicitly.</span></span> <span data-ttu-id="f50dc-116">Le operazioni esplicite includono la proprietà <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> e i metodi <xref:System.Threading.Thread.SetApartmentState%2A> e <xref:System.Threading.Thread.TrySetApartmentState%2A>.</span><span class="sxs-lookup"><span data-stu-id="f50dc-116">The explicit operations include the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property and the <xref:System.Threading.Thread.SetApartmentState%2A> and <xref:System.Threading.Thread.TrySetApartmentState%2A> methods.</span></span> <span data-ttu-id="f50dc-117">Un thread creato con il metodo <xref:System.Threading.Thread.Start%2A> viene impostato in modo implicito su <xref:System.Threading.ApartmentState.MTA>, a meno che <xref:System.Threading.Thread.SetApartmentState%2A> non venga chiamato prima dell'avvio del thread.</span><span class="sxs-lookup"><span data-stu-id="f50dc-117">A thread created using the <xref:System.Threading.Thread.Start%2A> method is implicitly set to <xref:System.Threading.ApartmentState.MTA> unless <xref:System.Threading.Thread.SetApartmentState%2A> is called before the thread is started.</span></span> <span data-ttu-id="f50dc-118">Anche il thread principale dell'applicazione viene inizializzato in modo implicito in <xref:System.Threading.ApartmentState.MTA>, a meno che nel metodo principale non sia specificato l'attributo <xref:System.STAThreadAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f50dc-118">The main thread of the application is also implicitly initialized to <xref:System.Threading.ApartmentState.MTA> unless the <xref:System.STAThreadAttribute> attribute is specified on the main method.</span></span>  
  
- <span data-ttu-id="f50dc-119">Nel thread viene chiamato il metodo `CoUninitialize` (o il metodo `CoInitializeEx`) con un modello di concorrenza diverso.</span><span class="sxs-lookup"><span data-stu-id="f50dc-119">The `CoUninitialize` method (or the `CoInitializeEx` method) with a different concurrency model is called on the thread.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f50dc-120">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="f50dc-120">Resolution</span></span>  
 <span data-ttu-id="f50dc-121">Impostare lo stato di apartment del thread prima dell'avvio dell'esecuzione oppure applicare l'attributo <xref:System.STAThreadAttribute> o <xref:System.MTAThreadAttribute> al metodo principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f50dc-121">Set the apartment state of the thread before it begins executing, or apply either the <xref:System.STAThreadAttribute> attribute or the <xref:System.MTAThreadAttribute> attribute to the main method of the application.</span></span>  
  
 <span data-ttu-id="f50dc-122">Per la seconda causa, idealmente, il codice che chiama il metodo `CoUninitialize` deve essere modificato in modo da ritardare la chiamata finché il thread non sta per terminare e non vi sono RCW, né i rispettivi componenti COM sottostanti, ancora in uso da parte del thread.</span><span class="sxs-lookup"><span data-stu-id="f50dc-122">For the second cause, ideally, the code that calls the `CoUninitialize` method should be modified to delay the call until the thread is about to terminate and there are no RCWs and their underlying COM components still in use by the thread.</span></span> <span data-ttu-id="f50dc-123">Tuttavia, se non è possibile modificare il codice che chiama il metodo `CoUninitialize`, nessun RCW può essere usato dai thread non inizializzati in questo modo.</span><span class="sxs-lookup"><span data-stu-id="f50dc-123">However, if it is not possible to modify the code that calls the `CoUninitialize` method, then no RCWs should be used from threads that are uninitialized in this way.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f50dc-124">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="f50dc-124">Effect on the Runtime</span></span>  
 <span data-ttu-id="f50dc-125">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="f50dc-125">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f50dc-126">Output</span><span class="sxs-lookup"><span data-stu-id="f50dc-126">Output</span></span>  
 <span data-ttu-id="f50dc-127">Stato di apartment COM del thread corrente e stato che il codice stava tentando di applicare.</span><span class="sxs-lookup"><span data-stu-id="f50dc-127">The COM apartment state of the current thread, and the state that the code was attempting to apply.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f50dc-128">Configurazione</span><span class="sxs-lookup"><span data-stu-id="f50dc-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="f50dc-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="f50dc-129">Example</span></span>  
 <span data-ttu-id="f50dc-130">L'esempio di codice seguente mostra una situazione che può comportare l'attivazione di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f50dc-130">The following code example demonstrates a situation that can activate this MDA.</span></span>  
  
```csharp
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f50dc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f50dc-131">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f50dc-132">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="f50dc-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f50dc-133">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f50dc-133">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
