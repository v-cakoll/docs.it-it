---
ms.openlocfilehash: f907cb1939e111c586d68243e6b8a8e291974e36
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615722"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a><span data-ttu-id="1b654-101">L'arrotondamento del layout dei margini in WPF è stato modificato</span><span class="sxs-lookup"><span data-stu-id="1b654-101">WPF layout rounding of margins has changed</span></span>

#### <a name="details"></a><span data-ttu-id="1b654-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1b654-102">Details</span></span>

<span data-ttu-id="1b654-103">Il modo in cui i margini vengono arrotondati e i bordi e lo sfondo al loro interno vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="1b654-103">The way in which margins are rounded and borders and the background inside of them has changed.</span></span> <span data-ttu-id="1b654-104">Come conseguenza di questo cambiamento:</span><span class="sxs-lookup"><span data-stu-id="1b654-104">As a result of this change:</span></span>

- <span data-ttu-id="1b654-105">La larghezza o l'altezza degli elementi può aumentare o diminuire al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="1b654-105">The width or height of elements may grow or shrink by at most one pixel.</span></span>
- <span data-ttu-id="1b654-106">La posizione di un oggetto può cambiare al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="1b654-106">The placement of an object can move by at most one pixel.</span></span>
- <span data-ttu-id="1b654-107">Gli elementi centrati possono risultare decentrati in orizzontale o in verticale al massimo di un pixel.</span><span class="sxs-lookup"><span data-stu-id="1b654-107">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>
<span data-ttu-id="1b654-108">Per impostazione predefinita, questo nuovo layout è disponibile solo per app destinate a .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="1b654-108">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1b654-109">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1b654-109">Suggestion</span></span>

<span data-ttu-id="1b654-110">Poiché questa modifica tende a eliminare il ritaglio del lato destro o inferiore dei controlli WPF a DPI elevati, le app destinate a versioni precedenti di .NET Framework ma eseguite su .NET Framework 4.6 possono adottare questo nuovo comportamento aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="1b654-110">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>

<span data-ttu-id="1b654-111">Le app che usano .NET Framework 4.6, ma che richiedono che il rendering dei controlli WPF sia eseguito tramite l'algoritmo di layout precedente, possono aggiungere la riga seguente alla sezione `<runtime>` del file app.config per raggiungere tale scopo:</span><span class="sxs-lookup"><span data-stu-id="1b654-111">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>

| <span data-ttu-id="1b654-112">Nome</span><span class="sxs-lookup"><span data-stu-id="1b654-112">Name</span></span>    | <span data-ttu-id="1b654-113">Valore</span><span class="sxs-lookup"><span data-stu-id="1b654-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1b654-114">Scope</span><span class="sxs-lookup"><span data-stu-id="1b654-114">Scope</span></span>   | <span data-ttu-id="1b654-115">Minorenne</span><span class="sxs-lookup"><span data-stu-id="1b654-115">Minor</span></span>       |
| <span data-ttu-id="1b654-116">Version</span><span class="sxs-lookup"><span data-stu-id="1b654-116">Version</span></span> | <span data-ttu-id="1b654-117">4.6</span><span class="sxs-lookup"><span data-stu-id="1b654-117">4.6</span></span>         |
| <span data-ttu-id="1b654-118">Type</span><span class="sxs-lookup"><span data-stu-id="1b654-118">Type</span></span>    | <span data-ttu-id="1b654-119">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="1b654-119">Retargeting</span></span> |
