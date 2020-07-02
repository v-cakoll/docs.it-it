---
ms.openlocfilehash: 80e61d4dd5b8d4754a39e95e37475fefff57fcbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617173"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a><span data-ttu-id="85036-101">Nuovi overload per Dispatcher.Invoke (ambigui) potrebbe causare un comportamento diverso</span><span class="sxs-lookup"><span data-stu-id="85036-101">New (ambiguous) Dispatcher.Invoke overloads could result in different behavior</span></span>

#### <a name="details"></a><span data-ttu-id="85036-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="85036-102">Details</span></span>

<span data-ttu-id="85036-103">.NET Framework 4.5 aggiunge nuovi overload a <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> che includono un parametro di tipo <xref:System.Action>.</span><span class="sxs-lookup"><span data-stu-id="85036-103">The .NET Framework 4.5 adds new overloads to <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> that include a parameter of type <xref:System.Action>.</span></span> <span data-ttu-id="85036-104">Se il codice esistente viene ricompilato, i compilatori possono risolvere le chiamate ai metodi Dispatcher.Invoke con un parametro <xref:System.Delegate> come chiamate ai metodi Dispatcher.Invoke con un parametro <xref:System.Action>.</span><span class="sxs-lookup"><span data-stu-id="85036-104">When existing code is recompiled, compilers may resolve calls to Dispatcher.Invoke methods that have a <xref:System.Delegate> parameter as calls to Dispatcher.Invoke methods with an <xref:System.Action> parameter.</span></span> <span data-ttu-id="85036-105">Se una chiamata a un overload di Dispatcher.Invoke con un parametro <xref:System.Delegate> viene risolta come una chiamata a un overload di Dispatcher.Invoke con un parametro <xref:System.Action>, è possibile che si verifichino le seguenti differenze nel comportamento:</span><span class="sxs-lookup"><span data-stu-id="85036-105">If a call to a Dispatcher.Invoke overload with a  <xref:System.Delegate> parameter is resolved as a call to a Dispatcher.Invoke overload with an <xref:System.Action> parameter, the following differences in behavior may occur:</span></span>

- <span data-ttu-id="85036-106">Se si verifica un'eccezione, gli eventi <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> e <xref:System.Windows.Threading.Dispatcher.UnhandledException> non vengono generati.</span><span class="sxs-lookup"><span data-stu-id="85036-106">If an exception occurs, the <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> and <xref:System.Windows.Threading.Dispatcher.UnhandledException> events are not raised.</span></span> <span data-ttu-id="85036-107">Al contrario, le eccezioni vengono gestite dall'evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="85036-107">Instead, exceptions are handled by the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName> event.</span></span>
- <span data-ttu-id="85036-108">Le chiamate ad alcuni membri, come <xref:System.Windows.Threading.DispatcherOperation.Result>, si bloccano fino a quando l'operazione non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="85036-108">Calls to some members, such as <xref:System.Windows.Threading.DispatcherOperation.Result>, block until the operation has completed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="85036-109">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="85036-109">Suggestion</span></span>

<span data-ttu-id="85036-110">Per evitare ambiguità (e potenziali differenze nella gestione delle eccezioni o per i comportamenti di blocco), il codice che chiama Dispatcher.Invoke può passare un oggetto vuoto [] come secondo parametro della chiamata Invoke per essere certi di usare l'overload del metodo .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="85036-110">To avoid ambiguity (and potential differences in exception handling or blocking behaviors), code calling Dispatcher.Invoke can pass an empty object[] as a second parameter to the Invoke call to be sure of resolving to the .NET Framework 4.0 method overload.</span></span>

| <span data-ttu-id="85036-111">Nome</span><span class="sxs-lookup"><span data-stu-id="85036-111">Name</span></span>    | <span data-ttu-id="85036-112">Valore</span><span class="sxs-lookup"><span data-stu-id="85036-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="85036-113">Scope</span><span class="sxs-lookup"><span data-stu-id="85036-113">Scope</span></span>   | <span data-ttu-id="85036-114">Minorenne</span><span class="sxs-lookup"><span data-stu-id="85036-114">Minor</span></span>       |
| <span data-ttu-id="85036-115">Version</span><span class="sxs-lookup"><span data-stu-id="85036-115">Version</span></span> | <span data-ttu-id="85036-116">4.5</span><span class="sxs-lookup"><span data-stu-id="85036-116">4.5</span></span>         |
| <span data-ttu-id="85036-117">Type</span><span class="sxs-lookup"><span data-stu-id="85036-117">Type</span></span>    | <span data-ttu-id="85036-118">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="85036-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="85036-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="85036-119">Affected APIs</span></span>

- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
