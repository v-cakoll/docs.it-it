---
title: Timer
description: Informazioni su quali timer .NET usare in un ambiente con multithreading.
ms.date: 07/03/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: d463eb2a8d598dc5ba9b2fb51a6fc08c563e6fe4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739493"
---
# <a name="timers"></a><span data-ttu-id="3f820-103">Timer</span><span class="sxs-lookup"><span data-stu-id="3f820-103">Timers</span></span>

<span data-ttu-id="3f820-104">.NET fornisce due timer da usare in un ambiente con multithreading:</span><span class="sxs-lookup"><span data-stu-id="3f820-104">.NET provides two timers to use in a multithreaded environment:</span></span>

- <span data-ttu-id="3f820-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, che esegue un metodo di callback singolo su un thread <xref:System.Threading.ThreadPool> a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="3f820-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, which executes a single callback method on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>
- <span data-ttu-id="3f820-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, che per impostazione predefinita genera un evento in un thread <xref:System.Threading.ThreadPool> a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="3f820-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, which by default raises an event on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>

> [!NOTE]
> <span data-ttu-id="3f820-107">Alcune implementazioni .NET possono includere altri timer:</span><span class="sxs-lookup"><span data-stu-id="3f820-107">Some .NET implementations may include additional timers:</span></span>
>
> - <span data-ttu-id="3f820-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: un componente di Windows Form che genera un evento a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="3f820-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: a Windows Forms component that fires an event at regular intervals.</span></span> <span data-ttu-id="3f820-109">Il componente non dispone di interfacce utente ed è progettato per l'uso in un ambiente a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="3f820-109">The component has no user interface and is designed for use in a single-threaded environment.</span></span>  
> - <span data-ttu-id="3f820-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: un componente ASP.NET che esegue postback asincroni o sincroni di pagina Web in base a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="3f820-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: an ASP.NET component that performs asynchronous or synchronous web page postbacks at a regular interval.</span></span>
> - <span data-ttu-id="3f820-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: un timer integrato nella coda del <xref:System.Windows.Threading.Dispatcher> che viene elaborata in un intervallo di tempo specifico e con una priorità specifica.</span><span class="sxs-lookup"><span data-stu-id="3f820-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: a timer that is integrated into the <xref:System.Windows.Threading.Dispatcher> queue which is processed at a specified interval of time and at a specified priority.</span></span>

## <a name="the-systemthreadingtimer-class"></a><span data-ttu-id="3f820-112">Classe System.Threading.Timer</span><span class="sxs-lookup"><span data-stu-id="3f820-112">The System.Threading.Timer class</span></span>

<span data-ttu-id="3f820-113">La classe <xref:System.Threading.Timer?displayProperty=nameWithType> consente di chiamare in modo continuativo un delegato a determinati intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="3f820-113">The <xref:System.Threading.Timer?displayProperty=nameWithType> class enables you to continuously call a delegate at specified time intervals.</span></span> <span data-ttu-id="3f820-114">È inoltre possibile utilizzare questa classe per pianificare una singola chiamata a un delegato in un intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="3f820-114">You can also use this class to schedule a single call to a delegate in a specified time interval.</span></span> <span data-ttu-id="3f820-115">Il delegato viene eseguito su un thread <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="3f820-115">The delegate is executed on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="3f820-116">Quando si crea un oggetto <xref:System.Threading.Timer?displayProperty=nameWithType>, si specifica un delegato <xref:System.Threading.TimerCallback> che definisce il metodo di callback, un oggetto di stato facoltativo passato al callback, il tempo di attesa prima della prima chiamata di callback e l'intervallo di tempo tra le chiamate di callback.</span><span class="sxs-lookup"><span data-stu-id="3f820-116">When you create a <xref:System.Threading.Timer?displayProperty=nameWithType> object, you specify a <xref:System.Threading.TimerCallback> delegate that defines the callback method, an optional state object that is passed to the callback, the amount of time to delay before the first invocation of the callback, and the time interval between callback invocations.</span></span> <span data-ttu-id="3f820-117">Per annullare un timer in sospeso, chiamare il metodo <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3f820-117">To cancel a pending timer, call the <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="3f820-118">L'esempio seguente illustra come creare un timer che chiama il delegato fornito per la prima volta dopo un secondo (1000 millisecondi) e quindi ogni due secondi.</span><span class="sxs-lookup"><span data-stu-id="3f820-118">The following example creates a timer that calls the provided delegate for the first time after one second (1000 milliseconds) and then calls it every two seconds.</span></span> <span data-ttu-id="3f820-119">L'oggetto di stato nell'esempio viene usato per contare quante volte viene chiamato il delegato.</span><span class="sxs-lookup"><span data-stu-id="3f820-119">The state object in the example is used to count how many times the delegate is called.</span></span> <span data-ttu-id="3f820-120">Il timer viene arrestato dopo aver chiamato il delegato almeno 10 volte.</span><span class="sxs-lookup"><span data-stu-id="3f820-120">The timer is stopped when the delegate has been called at least 10 times.</span></span>

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

<span data-ttu-id="3f820-121">Per altre informazioni ed esempi, vedere <xref:System.Threading.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3f820-121">For more information and examples, see <xref:System.Threading.Timer?displayProperty=nameWithType>.</span></span>

## <a name="the-systemtimerstimer-class"></a><span data-ttu-id="3f820-122">Classe System.Timers.Timer</span><span class="sxs-lookup"><span data-stu-id="3f820-122">The System.Timers.Timer class</span></span>

<span data-ttu-id="3f820-123">Un altro timer utilizzabile in un ambiente con multithreading è <xref:System.Timers.Timer?displayProperty=nameWithType>, che per impostazione predefinita genera un evento in un thread <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="3f820-123">Another timer that can be used in a multithreaded environment is <xref:System.Timers.Timer?displayProperty=nameWithType> that by default raises an event on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="3f820-124">Quando si crea un oggetto <xref:System.Timers.Timer?displayProperty=nameWithType>, è possibile specificare l'intervallo di tempo in cui si desidera generare un evento <xref:System.Timers.Timer.Elapsed>.</span><span class="sxs-lookup"><span data-stu-id="3f820-124">When you create a <xref:System.Timers.Timer?displayProperty=nameWithType> object, you may specify the time interval in which to raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="3f820-125">Usare la proprietà <xref:System.Timers.Timer.Enabled%2A> per indicare se un timer deve generare un evento <xref:System.Timers.Timer.Elapsed>.</span><span class="sxs-lookup"><span data-stu-id="3f820-125">Use the <xref:System.Timers.Timer.Enabled%2A> property to indicate if a timer should raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="3f820-126">Se un evento <xref:System.Timers.Timer.Elapsed> deve essere generato una sola volta dopo l'intervallo specificato, impostare <xref:System.Timers.Timer.AutoReset%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="3f820-126">If you need an <xref:System.Timers.Timer.Elapsed> event to be raised only once after the specified interval has elapsed, set the <xref:System.Timers.Timer.AutoReset%2A> to `false`.</span></span> <span data-ttu-id="3f820-127">Il valore predefinito della proprietà <xref:System.Timers.Timer.AutoReset%2A> è `true`, vale a dire che un evento <xref:System.Timers.Timer.Elapsed> viene generato periodicamente in base all'intervallo definito dalla proprietà <xref:System.Timers.Timer.Interval%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f820-127">The default value of the <xref:System.Timers.Timer.AutoReset%2A> property is `true`, which means that an <xref:System.Timers.Timer.Elapsed> event is raised regularly at the interval defined by the <xref:System.Timers.Timer.Interval%2A> property.</span></span>

<span data-ttu-id="3f820-128">Per altre informazioni ed esempi, vedere <xref:System.Timers.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3f820-128">For more information and examples, see <xref:System.Timers.Timer?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3f820-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f820-129">See also</span></span>

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [<span data-ttu-id="3f820-130">Funzionalità e oggetti di threading</span><span class="sxs-lookup"><span data-stu-id="3f820-130">Threading Objects and Features</span></span>](threading-objects-and-features.md)
