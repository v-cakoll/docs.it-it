---
ms.openlocfilehash: dfdb62e8dd6db67d4fd12aba93928f4615e3f284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614952"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a><span data-ttu-id="e5346-101">Evento TabControl SelectionChanged e proprietà SelectedContent</span><span class="sxs-lookup"><span data-stu-id="e5346-101">TabControl SelectionChanged event and SelectedContent property</span></span>

#### <a name="details"></a><span data-ttu-id="e5346-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e5346-102">Details</span></span>

<span data-ttu-id="e5346-103">A partire da .NET Framework 4.7.1, un elemento <xref:System.Windows.Controls.TabControl> aggiorna il valore della proprietà <xref:System.Windows.Controls.TabControl.SelectedContent> prima di generare l'evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> quando la selezione viene modificata. In .NET Framework 4.7 e versioni precedenti l'aggiornamento a SelectedContent avviene dopo l'evento.</span><span class="sxs-lookup"><span data-stu-id="e5346-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.TabControl> updates the value of its <xref:System.Windows.Controls.TabControl.SelectedContent> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.In the .NET Framework 4.7 and earlier versions, the update to SelectedContent happened after the event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e5346-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="e5346-104">Suggestion</span></span>

<span data-ttu-id="e5346-105">Le app destinate a .NET Framework 4.7.1 o versioni successive possono rifiutare esplicitamente questa modifica e usare il comportamento legacy aggiungendo il codice seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e5346-105">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="e5346-106">Le app destinate a .NET Framework 4.7 o versioni precedenti ma in esecuzione su .NET Framework 4.7.1 o versioni successive possono abilitare il nuovo comportamento aggiungendo la riga seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e5346-106">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="e5346-107">Nome</span><span class="sxs-lookup"><span data-stu-id="e5346-107">Name</span></span>    | <span data-ttu-id="e5346-108">Valore</span><span class="sxs-lookup"><span data-stu-id="e5346-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e5346-109">Scope</span><span class="sxs-lookup"><span data-stu-id="e5346-109">Scope</span></span>   | <span data-ttu-id="e5346-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="e5346-110">Minor</span></span>       |
| <span data-ttu-id="e5346-111">Version</span><span class="sxs-lookup"><span data-stu-id="e5346-111">Version</span></span> | <span data-ttu-id="e5346-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="e5346-112">4.7.1</span></span>       |
| <span data-ttu-id="e5346-113">Type</span><span class="sxs-lookup"><span data-stu-id="e5346-113">Type</span></span>    | <span data-ttu-id="e5346-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="e5346-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e5346-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="e5346-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
