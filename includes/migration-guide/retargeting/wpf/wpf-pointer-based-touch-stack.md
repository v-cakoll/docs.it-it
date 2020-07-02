---
ms.openlocfilehash: eb89cbc72d8b09fd1aa5bc775a6c539eb208fa70
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614896"
---
### <a name="wpf-pointer-based-touch-stack"></a><span data-ttu-id="db09c-101">Stack per input tocco WPF basato sul puntatore</span><span class="sxs-lookup"><span data-stu-id="db09c-101">WPF Pointer-Based Touch Stack</span></span>

#### <a name="details"></a><span data-ttu-id="db09c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="db09c-102">Details</span></span>

<span data-ttu-id="db09c-103">Questa modifica aggiunge la possibilità di attivare uno stack facoltativo per l'input tocco/stilo WPF basato su WM_POINTER.</span><span class="sxs-lookup"><span data-stu-id="db09c-103">This change adds the ability to enable an optional WM_POINTER based WPF touch/stylus stack.</span></span>  <span data-ttu-id="db09c-104">Gli sviluppatori che non attivano in modo esplicito questo supporto non dovrebbero riscontrare alcuna modifica nel comportamento dell'input tocco/stilo WPF. Problemi noti correnti relativi allo stack facoltativo per l'input tocco/stilo basato su WM_POINTER:</span><span class="sxs-lookup"><span data-stu-id="db09c-104">Developers that do not explicitly enable this should see no change in WPF touch/stylus behavior.Current Known Issues With optional WM_POINTER based touch/stylus stack:</span></span>

- <span data-ttu-id="db09c-105">Nessun supporto per l'input penna in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="db09c-105">No support for real-time inking.</span></span>
- <span data-ttu-id="db09c-106">Anche se i plug-in dello stilo e dell'input penna continuano a funzionare, essi vengono elaborati nel thread dell'interfaccia utente, il che può comportare un peggioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="db09c-106">While inking and StylusPlugins will still work, they will be processed on the UI Thread which can lead to poor performance.</span></span>
- <span data-ttu-id="db09c-107">Modifiche del comportamento dovute alla promozione da eventi di tocco/stilo agli eventi del mouse</span><span class="sxs-lookup"><span data-stu-id="db09c-107">Behavioral changes due to changes in promotion from touch/stylus events to mouse events</span></span>
- <span data-ttu-id="db09c-108">La modifica potrebbe avere un comportamento diverso</span><span class="sxs-lookup"><span data-stu-id="db09c-108">Manipulation may behave differently</span></span>
- <span data-ttu-id="db09c-109">L'opzione Trascina selezione non dà la risposta appropriata per l'input tocco</span><span class="sxs-lookup"><span data-stu-id="db09c-109">Drag/Drop will not show appropriate feedback for touch input</span></span>
- <span data-ttu-id="db09c-110">Questa operazione non influisce sull'input dello stilo</span><span class="sxs-lookup"><span data-stu-id="db09c-110">This does not affect stylus input</span></span>
- <span data-ttu-id="db09c-111">L'opzione Trascina selezione non può essere avviata per gli eventi di tocco/stilo</span><span class="sxs-lookup"><span data-stu-id="db09c-111">Drag/Drop can no longer be initiated on touch/stylus events</span></span>
- <span data-ttu-id="db09c-112">Questo può potenzialmente bloccare l'applicazione fino a quando non viene rilevato l'input del mouse.</span><span class="sxs-lookup"><span data-stu-id="db09c-112">This can potentially hang the application until mouse input is detected.</span></span>
- <span data-ttu-id="db09c-113">Gli sviluppatori dovranno quindi avviare l'opzione di trascinamento della selezione dagli eventi del mouse.</span><span class="sxs-lookup"><span data-stu-id="db09c-113">Instead, developers should initiate drag and drop from mouse events.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="db09c-114">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="db09c-114">Suggestion</span></span>

<span data-ttu-id="db09c-115">Gli sviluppatori che desiderano abilitare questo stack possono aggiungere o unire quanto segue al file App.config dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="db09c-115">Developers who wish to enable this stack can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="db09c-116">Se si rimuove questo elemento o se ne imposta il valore su False si disattiva lo stack facoltativo. Si noti che lo stack è disponibile solo in Windows 10 Creators Update e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="db09c-116">Removing this or setting the value to false will turn this optional stack off.Note that this stack is available only on Windows 10 Creators Update and above.</span></span>

| <span data-ttu-id="db09c-117">Nome</span><span class="sxs-lookup"><span data-stu-id="db09c-117">Name</span></span>    | <span data-ttu-id="db09c-118">Valore</span><span class="sxs-lookup"><span data-stu-id="db09c-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="db09c-119">Scope</span><span class="sxs-lookup"><span data-stu-id="db09c-119">Scope</span></span>   | <span data-ttu-id="db09c-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="db09c-120">Edge</span></span>        |
| <span data-ttu-id="db09c-121">Version</span><span class="sxs-lookup"><span data-stu-id="db09c-121">Version</span></span> | <span data-ttu-id="db09c-122">4.7</span><span class="sxs-lookup"><span data-stu-id="db09c-122">4.7</span></span>         |
| <span data-ttu-id="db09c-123">Type</span><span class="sxs-lookup"><span data-stu-id="db09c-123">Type</span></span>    | <span data-ttu-id="db09c-124">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="db09c-124">Retargeting</span></span> |
