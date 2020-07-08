---
title: MDA invalidApartmentStateChange
description: Informazioni sull'Assistente al debug gestito di invalidApartmentStateChange in .NET, che viene attivato in caso di problemi con lo stato dell'apartment COM.
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
ms.openlocfilehash: c6f7b6a5e450d4167946d22b2ada268ea2b0135f
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051827"
---
# <a name="invalidapartmentstatechange-mda"></a><span data-ttu-id="47083-103">MDA invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="47083-103">invalidApartmentStateChange MDA</span></span>
<span data-ttu-id="47083-104">L'assistente al debug gestito `invalidApartmentStateChange` viene attivato quando si verificano due problemi diversi:</span><span class="sxs-lookup"><span data-stu-id="47083-104">The `invalidApartmentStateChange` managed debugging assistant (MDS) is activated by either of two problems:</span></span>  
  
- <span data-ttu-id="47083-105">Viene effettuato un tentativo di modificare lo stato di apartment COM di un thread che è già stato inizializzato da COM in uno stato di apartment diverso.</span><span class="sxs-lookup"><span data-stu-id="47083-105">An attempt is made to change the COM apartment state of a thread that has already been initialized by COM to a different apartment state.</span></span>  
  
- <span data-ttu-id="47083-106">Lo stato di apartment COM di un thread cambia in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="47083-106">The COM apartment state of a thread changes unexpectedly.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="47083-107">Sintomi</span><span class="sxs-lookup"><span data-stu-id="47083-107">Symptoms</span></span>  
  
- <span data-ttu-id="47083-108">Lo stato di apartment COM di un thread è diverso da quello richiesto.</span><span class="sxs-lookup"><span data-stu-id="47083-108">A thread's COM apartment state is not what was requested.</span></span> <span data-ttu-id="47083-109">Questo problema può causare l'uso di proxy per componenti COM associati a un modello di threading diverso da quello corrente.</span><span class="sxs-lookup"><span data-stu-id="47083-109">This may cause proxies to be used for COM components that have a threading model different from the current one.</span></span> <span data-ttu-id="47083-110">A sua volta, questo comportamento può provocare la generazione di un'eccezione <xref:System.InvalidCastException> quando viene chiamato l'oggetto COM tramite interfacce che non sono configurate per il marshalling tra diversi apartment.</span><span class="sxs-lookup"><span data-stu-id="47083-110">This in turn may cause an <xref:System.InvalidCastException> to be thrown when calling the COM object through interfaces that are not set up for cross-apartment marshaling.</span></span>  
  
- <span data-ttu-id="47083-111">Lo stato di apartment COM del thread è diverso da quello previsto.</span><span class="sxs-lookup"><span data-stu-id="47083-111">The COM apartment state of the thread is different than expected.</span></span> <span data-ttu-id="47083-112">Questo problema può provocare un'eccezione <xref:System.Runtime.InteropServices.COMException> con valore HRESULT impostato su RPC_E_WRONG_THREAD, nonché un'eccezione <xref:System.InvalidCastException> quando si effettuano chiamate in un [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW).</span><span class="sxs-lookup"><span data-stu-id="47083-112">This can cause a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD as well as a <xref:System.InvalidCastException> when making calls on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="47083-113">Questo problema può anche far sì che diversi thread accedano contemporaneamente ad alcuni componenti COM a thread singolo, danneggiando i dati o provocandone la perdita.</span><span class="sxs-lookup"><span data-stu-id="47083-113">This can also cause some single-threaded COM components to be accessed by multiple threads at the same time, which can lead to corruption or data loss.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="47083-114">Causa</span><span class="sxs-lookup"><span data-stu-id="47083-114">Cause</span></span>  
  
- <span data-ttu-id="47083-115">Il thread è stato precedentemente inizializzato in uno stato di apartment COM diverso.</span><span class="sxs-lookup"><span data-stu-id="47083-115">The thread was previously initialized to a different COM apartment state.</span></span> <span data-ttu-id="47083-116">Si noti che lo stato di apartment di un thread può essere impostato in modo sia esplicito sia implicito.</span><span class="sxs-lookup"><span data-stu-id="47083-116">Note that the apartment state of a thread can be set either explicitly or implicitly.</span></span> <span data-ttu-id="47083-117">Le operazioni esplicite includono la proprietà <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> e i metodi <xref:System.Threading.Thread.SetApartmentState%2A> e <xref:System.Threading.Thread.TrySetApartmentState%2A>.</span><span class="sxs-lookup"><span data-stu-id="47083-117">The explicit operations include the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property and the <xref:System.Threading.Thread.SetApartmentState%2A> and <xref:System.Threading.Thread.TrySetApartmentState%2A> methods.</span></span> <span data-ttu-id="47083-118">Un thread creato con il metodo <xref:System.Threading.Thread.Start%2A> viene impostato in modo implicito su <xref:System.Threading.ApartmentState.MTA>, a meno che <xref:System.Threading.Thread.SetApartmentState%2A> non venga chiamato prima dell'avvio del thread.</span><span class="sxs-lookup"><span data-stu-id="47083-118">A thread created using the <xref:System.Threading.Thread.Start%2A> method is implicitly set to <xref:System.Threading.ApartmentState.MTA> unless <xref:System.Threading.Thread.SetApartmentState%2A> is called before the thread is started.</span></span> <span data-ttu-id="47083-119">Anche il thread principale dell'applicazione viene inizializzato in modo implicito in <xref:System.Threading.ApartmentState.MTA>, a meno che nel metodo principale non sia specificato l'attributo <xref:System.STAThreadAttribute>.</span><span class="sxs-lookup"><span data-stu-id="47083-119">The main thread of the application is also implicitly initialized to <xref:System.Threading.ApartmentState.MTA> unless the <xref:System.STAThreadAttribute> attribute is specified on the main method.</span></span>  
  
- <span data-ttu-id="47083-120">Nel thread viene chiamato il metodo `CoUninitialize` (o il metodo `CoInitializeEx`) con un modello di concorrenza diverso.</span><span class="sxs-lookup"><span data-stu-id="47083-120">The `CoUninitialize` method (or the `CoInitializeEx` method) with a different concurrency model is called on the thread.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="47083-121">Soluzione</span><span class="sxs-lookup"><span data-stu-id="47083-121">Resolution</span></span>  
 <span data-ttu-id="47083-122">Impostare lo stato di apartment del thread prima dell'avvio dell'esecuzione oppure applicare l'attributo <xref:System.STAThreadAttribute> o <xref:System.MTAThreadAttribute> al metodo principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="47083-122">Set the apartment state of the thread before it begins executing, or apply either the <xref:System.STAThreadAttribute> attribute or the <xref:System.MTAThreadAttribute> attribute to the main method of the application.</span></span>  
  
 <span data-ttu-id="47083-123">Per la seconda causa, idealmente, il codice che chiama il metodo `CoUninitialize` deve essere modificato in modo da ritardare la chiamata finché il thread non sta per terminare e non vi sono RCW, né i rispettivi componenti COM sottostanti, ancora in uso da parte del thread.</span><span class="sxs-lookup"><span data-stu-id="47083-123">For the second cause, ideally, the code that calls the `CoUninitialize` method should be modified to delay the call until the thread is about to terminate and there are no RCWs and their underlying COM components still in use by the thread.</span></span> <span data-ttu-id="47083-124">Tuttavia, se non è possibile modificare il codice che chiama il metodo `CoUninitialize`, nessun RCW può essere usato dai thread non inizializzati in questo modo.</span><span class="sxs-lookup"><span data-stu-id="47083-124">However, if it is not possible to modify the code that calls the `CoUninitialize` method, then no RCWs should be used from threads that are uninitialized in this way.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="47083-125">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="47083-125">Effect on the Runtime</span></span>  
 <span data-ttu-id="47083-126">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="47083-126">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="47083-127">Output</span><span class="sxs-lookup"><span data-stu-id="47083-127">Output</span></span>  
 <span data-ttu-id="47083-128">Stato di apartment COM del thread corrente e stato che il codice stava tentando di applicare.</span><span class="sxs-lookup"><span data-stu-id="47083-128">The COM apartment state of the current thread, and the state that the code was attempting to apply.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="47083-129">Configurazione</span><span class="sxs-lookup"><span data-stu-id="47083-129">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="47083-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="47083-130">Example</span></span>  
 <span data-ttu-id="47083-131">L'esempio di codice seguente mostra una situazione che può comportare l'attivazione di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="47083-131">The following code example demonstrates a situation that can activate this MDA.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="47083-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47083-132">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="47083-133">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="47083-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="47083-134">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="47083-134">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
